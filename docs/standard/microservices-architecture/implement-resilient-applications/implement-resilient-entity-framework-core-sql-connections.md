---
title: "Реализация устойчивых SQL-подключений Entity Framework Core"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация устойчивых SQL-подключений Entity Framework Core"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b37d2c5683aff44165d0330c8d42fc881effbb76
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="c656c-104">Реализация устойчивых SQL-подключений Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="c656c-104">Implementing resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="c656c-105">Для баз данных Azure SQL платформа Entity Framework Core уже предоставляет логику устойчивости и повторного выполнения при подключении к внутренним базам данных.</span><span class="sxs-lookup"><span data-stu-id="c656c-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="c656c-106">Но вам необходимо применить стратегию выполнения Entity Framework к каждому подключению DbContext, если вы хотите иметь [устойчивое подключение к EF Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="c656c-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="c656c-107">Например, следующий код на уровне подключения к EF Core обеспечивает устойчивое SQL-подключение, которое устанавливается повторно при сбое.</span><span class="sxs-lookup"><span data-stu-id="c656c-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="c656c-108">Стратегии выполнения и явные транзакции с использованием BeginTransaction и нескольких DbContext</span><span class="sxs-lookup"><span data-stu-id="c656c-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="c656c-109">Если в подключениях к EF Core включены повторные попытки, каждая операция, выполняемая с помощью EF Core, будет предпринимать повторные попытки.</span><span class="sxs-lookup"><span data-stu-id="c656c-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="c656c-110">Каждый запрос и каждый вызов к SaveChanges будет повторяться снова как единица в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="c656c-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="c656c-111">Но если код запускает транзакцию с помощью BeginTransaction, вы сами определяете группу операций, которые должны рассматриваться как единица, — все содержимое транзакции можно будет откатить в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="c656c-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="c656c-112">Если вы попытаетесь выполнить эту транзакцию при использовании стратегии выполнения EF (политика повтора) и включаете несколько вызовов SaveChanges из нескольких DbContext в транзакции, отобразится следующее исключение:</span><span class="sxs-lookup"><span data-stu-id="c656c-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="c656c-113">System.InvalidOperationException: настроенная стратегия выполнения 'SqlServerRetryingExecutionStrategy' не поддерживает запуск транзакций пользователем.</span><span class="sxs-lookup"><span data-stu-id="c656c-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="c656c-114">Используйте стратегию выполнения, возвращенную 'DbContext.Database.CreateExecutionStrategy()', чтобы выполнить все операции в транзакции как повторяемую единицу.</span><span class="sxs-lookup"><span data-stu-id="c656c-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="c656c-115">Необходимо вручную вызвать стратегию выполнения EF с делегатом, который представляет все, что должно быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="c656c-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="c656c-116">В случае временного сбоя стратегия выполнения будет снова вызывать делегат.</span><span class="sxs-lookup"><span data-stu-id="c656c-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="c656c-117">Например, следующий код показывает, как это реализуется в eShopOnContainers с двумя DbContext (\_catalogContext и IntegrationEventLogContext) при обновлении продукта и сохранении объекта ProductPriceChangedIntegrationEvent, который должен использовать другой DbContext.</span><span class="sxs-lookup"><span data-stu-id="c656c-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

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

<span data-ttu-id="c656c-118">Первый DbContext — это \_catalogContext, а второй DbContext находится в объекте \_integrationEventLogService.</span><span class="sxs-lookup"><span data-stu-id="c656c-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="c656c-119">Действие фиксации выполняется в нескольких DbContext с помощью стратегии выполнения EF.</span><span class="sxs-lookup"><span data-stu-id="c656c-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c656c-120">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="c656c-120">Additional resources</span></span>

-   <span data-ttu-id="c656c-121">**Connection Resiliency and Command Interception with the Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="c656c-121">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="c656c-122">**Сезар де ла Торре (Cesar de la Torre). Using Resilient Entity Framework Core Sql Connections and Transactions**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="c656c-122">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c656c-123">[Назад] (implement-retries-exponential-backoff.md) [Далее] (implement-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="c656c-123">[Previous] (implement-retries-exponential-backoff.md) [Next] (implement-custom-http-call-retries-exponential-backoff.md)</span></span>
