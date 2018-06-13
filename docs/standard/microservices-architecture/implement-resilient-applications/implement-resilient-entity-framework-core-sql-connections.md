---
title: Реализация устойчивых SQL-подключений Entity Framework Core
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация устойчивых SQL-подключений Entity Framework Core
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 54d0df517514c359c155de35d34e1e0f56eed4eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579227"
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>Реализация устойчивых SQL-подключений Entity Framework Core

Для баз данных Azure SQL платформа Entity Framework Core уже предоставляет логику устойчивости и повторного выполнения при подключении к внутренним базам данных. Но вам необходимо применить стратегию выполнения Entity Framework к каждому подключению DbContext, если вы хотите иметь [устойчивое подключение к EF Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).

Например, следующий код на уровне подключения к EF Core обеспечивает устойчивое SQL-подключение, которое устанавливается повторно при сбое.

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Стратегии выполнения и явные транзакции с использованием BeginTransaction и нескольких DbContext

Если в подключениях к EF Core включены повторные попытки, каждая операция, выполняемая с помощью EF Core, будет предпринимать повторные попытки. Каждый запрос и каждый вызов к SaveChanges будет повторяться снова как единица в случае сбоя.

Но если код запускает транзакцию с помощью BeginTransaction, вы сами определяете группу операций, которые должны рассматриваться как единица, — все содержимое транзакции можно будет откатить в случае сбоя. Если вы попытаетесь выполнить эту транзакцию при использовании стратегии выполнения EF (политика повтора) и включаете несколько вызовов SaveChanges из нескольких DbContext в транзакции, отобразится следующее исключение:

> System.InvalidOperationException: настроенная стратегия выполнения 'SqlServerRetryingExecutionStrategy' не поддерживает запуск транзакций пользователем. Используйте стратегию выполнения, возвращенную 'DbContext.Database.CreateExecutionStrategy()', чтобы выполнить все операции в транзакции как повторяемую единицу.

Необходимо вручную вызвать стратегию выполнения EF с делегатом, который представляет все, что должно быть выполнено. В случае временного сбоя стратегия выполнения будет снова вызывать делегат. Например, следующий код показывает, как это реализуется в eShopOnContainers с двумя DbContext (\_catalogContext и IntegrationEventLogContext) при обновлении продукта и сохранении объекта ProductPriceChangedIntegrationEvent, который должен использовать другой DbContext.

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

Первый DbContext — это \_catalogContext, а второй DbContext находится в объекте \_integrationEventLogService. Действие фиксации выполняется в нескольких DbContext с помощью стратегии выполнения EF.

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Устойчивость подключений и перехват команд в Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Сезар де ла Торре (Cesar de la Torre). Использование устойчивых SQL-подключений Entity Framework Core и транзакций**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[Назад] (implement-retries-exponential-backoff.md) [Далее] (implement-custom-http-call-retries-exponential-backoff.md)
