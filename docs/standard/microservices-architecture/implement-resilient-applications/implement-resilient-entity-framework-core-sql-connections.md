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
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>Реализация соединений устойчивым Entity Framework Core SQL

Для баз данных SQL Azure Entity Framework Core уже предоставляет логику устойчивости и повторите попытку подключения внутренней базы данных. Однако вам нужно включить стратегия выполнения Entity Framework для каждого соединения DbContext, если вы хотите иметь [устойчивым EF основных подключений](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).

Для экземпляра приведенный ниже код на уровне ядра EF соединения позволяет отказоустойчивой соединения SQL, выполняется повторная попытка добавления при сбое соединения.

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Выполнение стратегии и явные транзакции, используя BeginTransaction и несколько DbContexts

После включения повторных попыток подключений EF Core каждой операции, выполненные с помощью EF Core становится повторимый операции. Каждый запрос и каждый вызов команды SaveChanges в случае временного сбоя будет повторена как единое целое.

Тем не менее, если код инициирует транзакцию, используя BeginTransaction, вы определяете собственную группу операций, которые должны рассматриваться как единое целое, весь код внутри транзакции выполнен откат в случае сбоя. При попытке выполнения этой транзакции, при использовании стратегия выполнения EF (политику повтора) и включить несколько вызовов SaveChanges из нескольких DbContexts в транзакции, вы увидите исключение следующим образом.

> System.InvalidOperationException: Настроенная стратегия выполнения «SqlServerRetryingExecutionStrategy» не поддерживает транзакции, инициированной пользователем. Используйте возвращенный «DbContext.Database.CreateExecutionStrategy()» стратегии выполнения для выполнения всех операций в транзакции как единое возможностью повторной попытки.

Решением является вызвать стратегия выполнения EF отражающее все делегатом, который должен выполняться вручную. В случае временного сбоя стратегия выполнения будет снова вызвать делегата. Например, следующий пример кода реализации в eShopOnContainers с двумя несколько DbContexts (\_catalogContext и IntegrationEventLogContext) при обновлении продукта и затем сохранение ProductPriceChangedIntegrationEvent объект, который должен использовать разные DbContext.

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

— Первый DbContext \_catalogContext, а второй — DbContext находится в пределах \_integrationEventLogService объекта. Через несколько DbContexts, с помощью EF стратегия выполнения выполнено действие фиксации.

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Устойчивость подключения и команды перехвата с платформой Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Сезар де ла Торре (Cesar de la Torre). С помощью гибкой Entity Framework Core Sql соединений и транзакций**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[Предыдущие] (реализация попыток экспоненциальное backoff.md) [Далее] (implement-custom-http-call-retries-exponential-backoff.md)
