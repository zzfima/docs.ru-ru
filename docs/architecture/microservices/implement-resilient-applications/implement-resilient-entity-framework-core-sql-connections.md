---
title: Реализация устойчивых SQL-подключений Entity Framework Core
description: Сведения о реализации устойчивых SQL-подключений Entity Framework Core Этот прием особенно важен при использовании базы данных SQL Azure в облаке.
ms.date: 10/16/2018
ms.openlocfilehash: 0ded30469bb4985fed7b60938756046531c8feea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777064"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a>Реализация устойчивых SQL-подключений Entity Framework Core

Для Базы данных SQL Azure платформа Entity Framework (EF) Core уже предоставляет логику устойчивости и повторных попыток при подключении к внутренним базам данных. Но вам необходимо применить стратегию выполнения Entity Framework к каждому подключению <xref:Microsoft.EntityFrameworkCore.DbContext>, чтобы обеспечить [устойчивое подключение к EF Core](/ef/core/miscellaneous/connection-resiliency).

Например, следующий код на уровне подключения к EF Core обеспечивает устойчивое SQL-подключение, которое устанавливается повторно при сбое.

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<CatalogContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 10,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Стратегии выполнения и явные транзакции с использованием BeginTransaction и нескольких DbContext

Если в подключениях к EF Core включены повторные попытки, каждая операция, выполняемая с помощью EF Core, будет предпринимать повторные попытки. Каждый запрос и каждый вызов к `SaveChanges` будет повторяться снова как единица в случае сбоя.

Но если код инициирует транзакцию с помощью `BeginTransaction`, вы сами определяете группу операций, которые должны рассматриваться как единица. Все содержимое транзакции можно будет откатить в случае сбоя.

Если вы попытаетесь выполнить эту транзакцию при использовании стратегии выполнения EF (политика повтора) и вызываете `SaveChanges` из нескольких DbContext, отобразится исключение такого типа:

> "System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions" (System.InvalidOperationException: настроенная стратегия выполнения SqlServerRetryingExecutionStrategy не поддерживает запуск транзакций пользователем). Используйте стратегию выполнения, возвращенную 'DbContext.Database.CreateExecutionStrategy()', чтобы выполнить все операции в транзакции как повторяемую единицу.

Необходимо вручную вызвать стратегию выполнения EF с делегатом, который представляет все, что должно быть выполнено. В случае временного сбоя стратегия выполнения будет снова вызывать делегат. Например, следующий код демонстрирует, как это реализуется в eShopOnContainers с двумя DbContext (\_catalogContext и IntegrationEventLogContext) при обновлении продукта и сохранении объекта ProductPriceChangedIntegrationEvent, который должен использовать другой DbContext.

```csharp
public async Task<IActionResult> UpdateProduct(
    [FromBody]CatalogItem productToUpdate)
{
    // Other code ...

    var oldPrice = catalogItem.Price;
    var raiseProductPriceChangedEvent = oldPrice != productToUpdate.Price;

    // Update current product
    catalogItem = productToUpdate;

    // Save product's data and publish integration event through the Event Bus
    // if price has changed
    if (raiseProductPriceChangedEvent)
    {
        //Create Integration Event to be published through the Event Bus
        var priceChangedEvent = new ProductPriceChangedIntegrationEvent(
          catalogItem.Id, productToUpdate.Price, oldPrice);

       // Achieving atomicity between original Catalog database operation and the
       // IntegrationEventLog thanks to a local transaction
       await _catalogIntegrationEventService.SaveEventAndCatalogContextChangesAsync(
           priceChangedEvent);

       // Publish through the Event Bus and mark the saved event as published
       await _catalogIntegrationEventService.PublishThroughEventBusAsync(
           priceChangedEvent);
    }
    // Just save the updated product because the Product's Price hasn't changed.
    else
    {
        await _catalogContext.SaveChangesAsync();
    }
}
```

Первый <xref:Microsoft.EntityFrameworkCore.DbContext> — это `_catalogContext`, а второй `DbContext` находится в пределах объекта `_catalogIntegrationEventService`. Действие фиксации выполняется во всех объектах `DbContext` с помощью стратегии выполнения EF.

Для достижения такой фиксации нескольких `DbContext``SaveEventAndCatalogContextChangesAsync` использует класс `ResilientTransaction`, как показано в приведенном ниже примере кода.

```csharp
public class CatalogIntegrationEventService : ICatalogIntegrationEventService
{
    //…
    public async Task SaveEventAndCatalogContextChangesAsync(
        IntegrationEvent evt)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        await ResilientTransaction.New(_catalogContext).ExecuteAsync(async () =>
        {
            // Achieving atomicity between original catalog database
            // operation and the IntegrationEventLog thanks to a local transaction
            await _catalogContext.SaveChangesAsync();
            await _eventLogService.SaveEventAsync(evt,
                _catalogContext.Database.CurrentTransaction.GetDbTransaction());
        });
    }
}
```

Метод `ResilientTransaction.ExecuteAsync`, по сути, начинает транзакцию из переданного `DbContext` (`_catalogContext`) и затем указывает `EventLogService` использовать эту транзакцию для сохранения изменений из `IntegrationEventLogContext`, после чего фиксирует всю транзакцию.

```csharp
public class ResilientTransaction
{
    private DbContext _context;
    private ResilientTransaction(DbContext context) =>
        _context = context ?? throw new ArgumentNullException(nameof(context));

    public static ResilientTransaction New (DbContext context) =>
        new ResilientTransaction(context);

    public async Task ExecuteAsync(Func<Task> action)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        var strategy = _context.Database.CreateExecutionStrategy();
        await strategy.ExecuteAsync(async () =>
        {
            using (var transaction = _context.Database.BeginTransaction())
            {
                await action();
                transaction.Commit();
            }
        });
    }
}
```

## <a name="additional-resources"></a>Дополнительные ресурсы

- **Устойчивость подключений и перехват команд c помощью EF в приложении ASP.NET MVC** \
  [https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application)

- **Сезар де ла Торре (Cesar de la Torre). Using Resilient Entity Framework Core SQL Connections and Transactions (Использование устойчивых SQL-подключений Entity Framework Core и транзакций)**  \
  <https://devblogs.microsoft.com/cesardelatorre/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>

>[!div class="step-by-step"]
>[Назад](implement-retries-exponential-backoff.md)
>[Вперед](explore-custom-http-call-retries-exponential-backoff.md)
