---
title: "Реализация соединений устойчивым Entity Framework Core SQL"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализация соединений устойчивым Entity Framework Core SQL"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8600625c2022d69ebaa2645c2a8159a848b12ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="d2e4a-104">Реализация соединений устойчивым Entity Framework Core SQL</span><span class="sxs-lookup"><span data-stu-id="d2e4a-104">Implementing resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="d2e4a-105">Для баз данных SQL Azure Entity Framework Core уже предоставляет логику устойчивости и повторите попытку подключения внутренней базы данных.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="d2e4a-106">Однако вам нужно включить стратегия выполнения Entity Framework для каждого соединения DbContext, если вы хотите иметь [устойчивым EF основных подключений](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="d2e4a-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="d2e4a-107">Для экземпляра приведенный ниже код на уровне ядра EF соединения позволяет отказоустойчивой соединения SQL, выполняется повторная попытка добавления при сбое соединения.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<OrderingContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 5,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="d2e4a-108">Выполнение стратегии и явные транзакции, используя BeginTransaction и несколько DbContexts</span><span class="sxs-lookup"><span data-stu-id="d2e4a-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="d2e4a-109">После включения повторных попыток подключений EF Core каждой операции, выполненные с помощью EF Core становится повторимый операции.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="d2e4a-110">Каждый запрос и каждый вызов команды SaveChanges в случае временного сбоя будет повторена как единое целое.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="d2e4a-111">Тем не менее, если код инициирует транзакцию, используя BeginTransaction, вы определяете собственную группу операций, которые должны рассматриваться как единое целое, весь код внутри транзакции выполнен откат в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="d2e4a-112">При попытке выполнения этой транзакции, при использовании стратегия выполнения EF (политику повтора) и включить несколько вызовов SaveChanges из нескольких DbContexts в транзакции, вы увидите исключение следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="d2e4a-113">System.InvalidOperationException: Настроенная стратегия выполнения «SqlServerRetryingExecutionStrategy» не поддерживает транзакции, инициированной пользователем.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="d2e4a-114">Используйте возвращенный «DbContext.Database.CreateExecutionStrategy()» стратегии выполнения для выполнения всех операций в транзакции как единое возможностью повторной попытки.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="d2e4a-115">Решением является вызвать стратегия выполнения EF отражающее все делегатом, который должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="d2e4a-116">В случае временного сбоя стратегия выполнения будет снова вызвать делегата.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="d2e4a-117">Например, следующий пример кода реализации в eShopOnContainers с двумя несколько DbContexts (\_catalogContext и IntegrationEventLogContext) при обновлении продукта и затем сохранение ProductPriceChangedIntegrationEvent объект, который должен использовать разные DbContext.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

```csharp
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem
    productToUpdate)
{
    // Other code ...
    // Update current product
    catalogItem = productToUpdate;

    // Use of an EF Core resiliency strategy when using multiple DbContexts
    // within an explicit transaction
    // See:
    // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
    var strategy = _catalogContext.Database.CreateExecutionStrategy();
    await strategy.ExecuteAsync(async () =>
    {
        // Achieving atomicity between original Catalog database operation and the
        // IntegrationEventLog thanks to a local transaction
        using (var transaction = _catalogContext.Database.BeginTransaction())
        {
            _catalogContext.CatalogItems.Update(catalogItem);
            await _catalogContext.SaveChangesAsync();
            // Save to EventLog only if product price changed
            if (raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
            transaction.Commit();
        }
    });
}
```

<span data-ttu-id="d2e4a-118">— Первый DbContext \_catalogContext, а второй — DbContext находится в пределах \_integrationEventLogService объекта.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="d2e4a-119">Через несколько DbContexts, с помощью EF стратегия выполнения выполнено действие фиксации.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d2e4a-120">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="d2e4a-120">Additional resources</span></span>

-   <span data-ttu-id="d2e4a-121">**Устойчивость подключения и команды перехвата с платформой Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="d2e4a-121">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="d2e4a-122">**Сезар де ла Торре (Cesar de la Torre). С помощью гибкой Entity Framework Core Sql соединений и транзакций**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="d2e4a-122">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="d2e4a-123">[Предыдущие] (реализация попыток экспоненциальное backoff.md) [Далее] (implement-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="d2e4a-123">[Previous] (implement-retries-exponential-backoff.md) [Next] (implement-custom-http-call-retries-exponential-backoff.md)</span></span>
