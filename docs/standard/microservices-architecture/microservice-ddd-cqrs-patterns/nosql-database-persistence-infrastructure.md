---
title: "Использование баз данных NoSQL как инфраструктура сохраняемости"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Использование баз данных NoSQL как инфраструктура сохраняемости"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e4b63511069b89cc5761ce7ed64f09e9035a56a3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a>Использование баз данных NoSQL как инфраструктура сохраняемости

При использовании баз данных NoSQL для инфраструктуры уровня данных, обычно не используется ORM как Entity Framework Core. Вместо этого используйте API, предоставляемые подсистемой NoSQL, например Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB или таблиц хранилища Azure.

Тем не менее при использовании базы данных NoSQL, особенно ориентированные на базы данных как базу данных Azure Cosmos, CouchDB или RavenDB, методов проектирования модели с помощью DDD статистических выражений аналогичен частично как это можно сделать в ядре EF, в отношении идентификации статистические корни дочерних классов сущностей и классы значений объекта. Но в конечном счете, Выбор базы данных повлияет на этапах проектирования.

При использовании базы данных с учетом документа реализации агрегатную функцию как единый документ, сериализованный в формате JSON или другой формат. Однако использование базы данных является прозрачным с зрения точки домена модели кода. При использовании баз данных NoSQL, по-прежнему используется классами сущностей и статистические корневых классов, но большую гибкость, чем при использовании основной EF, так как сохраняемости не является реляционной.

Разница заключается в том, как сохранить эту модель. Если реализована модель домена на основе классов сущности POCO, зависит от инфраструктуры сохраняемости, он может выглядеть, как можно переместить на другой сохраняемости инфраструктуру даже из реляционных для NoSQL. Это не должен быть поставленной задачи. Всегда есть ограничения в разных базах данных будет передавать вы обратно, поэтому вы не будет иметь ту же модель для реляционной или баз данных NoSQL. Изменение моделей сохраняемости не будет незначительным, так как транзакции и операции сохраняемости будет сильно отличается.

Например в базы данных с учетом документа допустимо для статистических корня иметь несколько свойств коллекции дочерних. В реляционной базе данных запрос несколько свойств коллекции дочерних плохо, так, как получить инструкцию UNION всех SQL обратно из EF. Того же домена модели для реляционных баз данных или баз данных NoSQL не является простым и не используйте его. Действительно необходимо разработать модели с помощью понимать как данные будут использоваться в каждой конкретной базы данных.

Преимущество при использовании баз данных NoSQL, что сущности являются более денормализованные, не следует присваивать свойству сопоставления таблиц. Модель домена может быть более гибким, чем при использовании реляционной базы данных.

При конструировании вашего домена модели, основанной на статистических выражений, перемещение NoSQL документа ориентированными базами данных возможно, проще, чем с помощью реляционной базы данных, проектировании агрегатов похожи на сериализация и документов в базе данных, ориентированные на документы. Затем можно включить в эти «пакеты» все сведения, которые могут потребоваться для сводные данные.

Для экземпляра в следующем примере кода JSON — это реализация образца статистической обработки заказа, при использовании базы данных с учетом документа. Это похоже на порядок агрегатных была реализована в образце eShopOnContainers, но без использования основных EF под.

```json
{
    "id": "2017001",
    "orderDate": "2/25/2017",
    "buyerId": "1234567",
    "address": [
        {
        "street": "100 One Microsoft Way",
        "city": "Redmond",
        "state": "WA",
        "zip": "98052",
        "country": "U.S."
        }
    ],
    "orderItems": [
        {"id": 20170011, "productId": "123456", "productName": ".NET T-Shirt",
        "unitPrice": 25, "units": 2, "discount": 0},
        {"id": 20170012, "productId": "123457", "productName": ".NET Mug",
        "unitPrice": 15, "units": 1, "discount": 0}
    ]
}
```

При использовании C\# модель реализация статистического выражения для использования примерно Cosmos DB пакет SDK Azure, Агрегатная функция подобна C\# POCO классы, используемые с EF Core. Разница заключается в том, как их использование из уровней приложений и инфраструктуры, как показано в следующем коде.

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH DOCUMENTDB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).
// This can be saved as JSON as is without converting into rows/columns.
Order orderAggregate = new Order
{
    Id = "2017001",
    OrderDate = new DateTime(2005, 7, 1),
    BuyerId = "1234567",
    PurchaseOrderNumber = "PO18009186470"
}

Address address = new Address
{
    Street = "100 One Microsoft Way",
    City = "Redmond",
    State = "WA",
    Zip = "98052",
    Country = "U.S."
}

orderAggregate.UpdateAddress(address);
OrderItem orderItem1 = new OrderItem
{
    Id = 20170011,
    ProductId = "123456",
    ProductName = ".NET T-Shirt",
    UnitPrice = 25,
    Units = 2,
    Discount = 0;
};

OrderItem orderItem2 = new OrderItem
{
    Id = 20170012,
    ProductId = "123457",
    ProductName = ".NET Mug",
    UnitPrice = 15,
    Units = 1,
    Discount = 0;
};

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
orderAggregate.AddOrderItem(orderItem2);

// *** End of Domain Model Code ***
//...
// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, order);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

Вы увидите, что способ работы с моделью домена может быть аналогично тому, как она используется на уровне модели домена при EF инфраструктуры. По-прежнему использовать те же корневой статистические методы для обеспечения согласованности, инварианты и проверок в агрегатной функции.

Однако при сохранении модели в базе данных NoSQL, код и изменение API значительно по сравнению с EF основного кода или любого другого кода, относящиеся к реляционным базам данных.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Моделирование данных в DocumentDB**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)

-   **Вон Вернон (Vaughn Vernon). Идеальный управляемого домена разработки статистического выражения хранилище? ** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)

-   **Независимые сохраняемости событий хранилища для .NET.** В репозитории GitHub.
    [*https://github.com/NEventStore/NEventStore*](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
[Предыдущие] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Далее] (microservice-application-layer-web-api-design.md)
