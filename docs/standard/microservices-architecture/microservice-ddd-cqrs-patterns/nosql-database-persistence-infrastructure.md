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
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a><span data-ttu-id="bfc75-104">Использование баз данных NoSQL как инфраструктура сохраняемости</span><span class="sxs-lookup"><span data-stu-id="bfc75-104">Using NoSQL databases as a persistence infrastructure</span></span>

<span data-ttu-id="bfc75-105">При использовании баз данных NoSQL для инфраструктуры уровня данных, обычно не используется ORM как Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="bfc75-105">When you use NoSQL databases for your infrastructure data tier, you typically do not use an ORM like Entity Framework Core.</span></span> <span data-ttu-id="bfc75-106">Вместо этого используйте API, предоставляемые подсистемой NoSQL, например Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB или таблиц хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="bfc75-106">Instead you use the API provided by the NoSQL engine, such as Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, or Azure Storage Tables.</span></span>

<span data-ttu-id="bfc75-107">Тем не менее при использовании базы данных NoSQL, особенно ориентированные на базы данных как базу данных Azure Cosmos, CouchDB или RavenDB, методов проектирования модели с помощью DDD статистических выражений аналогичен частично как это можно сделать в ядре EF, в отношении идентификации статистические корни дочерних классов сущностей и классы значений объекта.</span><span class="sxs-lookup"><span data-stu-id="bfc75-107">However, when you use a NoSQL database, especially a document-oriented database like Azure Cosmos DB, CouchDB, or RavenDB, the way you design your model with DDD aggregates is partially similar to how you can do it in EF Core, in regards to the identification of aggregate roots, child entity classes, and value object classes.</span></span> <span data-ttu-id="bfc75-108">Но в конечном счете, Выбор базы данных повлияет на этапах проектирования.</span><span class="sxs-lookup"><span data-stu-id="bfc75-108">But, ultimately, the database selection will impact in your design.</span></span>

<span data-ttu-id="bfc75-109">При использовании базы данных с учетом документа реализации агрегатную функцию как единый документ, сериализованный в формате JSON или другой формат.</span><span class="sxs-lookup"><span data-stu-id="bfc75-109">When you use a document-oriented database, you implement an aggregate as a single document, serialized in JSON or another format.</span></span> <span data-ttu-id="bfc75-110">Однако использование базы данных является прозрачным с зрения точки домена модели кода.</span><span class="sxs-lookup"><span data-stu-id="bfc75-110">However, the use of the database is transparent from a domain model code point of view.</span></span> <span data-ttu-id="bfc75-111">При использовании баз данных NoSQL, по-прежнему используется классами сущностей и статистические корневых классов, но большую гибкость, чем при использовании основной EF, так как сохраняемости не является реляционной.</span><span class="sxs-lookup"><span data-stu-id="bfc75-111">When using a NoSQL database, you still are using entity classes and aggregate root classes, but with more flexibility than when using EF Core because the persistence is not relational.</span></span>

<span data-ttu-id="bfc75-112">Разница заключается в том, как сохранить эту модель.</span><span class="sxs-lookup"><span data-stu-id="bfc75-112">The difference is in how you persist that model.</span></span> <span data-ttu-id="bfc75-113">Если реализована модель домена на основе классов сущности POCO, зависит от инфраструктуры сохраняемости, он может выглядеть, как можно переместить на другой сохраняемости инфраструктуру даже из реляционных для NoSQL.</span><span class="sxs-lookup"><span data-stu-id="bfc75-113">If you implemented your domain model based on POCO entity classes, agnostic to the infrastructure persistence, it might look like you could move to a different persistence infrastructure, even from relational to NoSQL.</span></span> <span data-ttu-id="bfc75-114">Это не должен быть поставленной задачи.</span><span class="sxs-lookup"><span data-stu-id="bfc75-114">However, that should not be your goal.</span></span> <span data-ttu-id="bfc75-115">Всегда есть ограничения в разных базах данных будет передавать вы обратно, поэтому вы не будет иметь ту же модель для реляционной или баз данных NoSQL.</span><span class="sxs-lookup"><span data-stu-id="bfc75-115">There are always constraints in the different databases will push you back, so you will not be able to have the same model for relational or NoSQL databases.</span></span> <span data-ttu-id="bfc75-116">Изменение моделей сохраняемости не будет незначительным, так как транзакции и операции сохраняемости будет сильно отличается.</span><span class="sxs-lookup"><span data-stu-id="bfc75-116">Changing persistence models would not be trivial, because transactions and persistence operations will be very different.</span></span>

<span data-ttu-id="bfc75-117">Например в базы данных с учетом документа допустимо для статистических корня иметь несколько свойств коллекции дочерних.</span><span class="sxs-lookup"><span data-stu-id="bfc75-117">For example, in a document-oriented database, it is okay for an aggregate root to have multiple child collection properties.</span></span> <span data-ttu-id="bfc75-118">В реляционной базе данных запрос несколько свойств коллекции дочерних плохо, так, как получить инструкцию UNION всех SQL обратно из EF.</span><span class="sxs-lookup"><span data-stu-id="bfc75-118">In a relational database, querying multiple child collection properties is awful, because you get a UNION ALL SQL statement back from EF.</span></span> <span data-ttu-id="bfc75-119">Того же домена модели для реляционных баз данных или баз данных NoSQL не является простым и не используйте его.</span><span class="sxs-lookup"><span data-stu-id="bfc75-119">Having the same domain model for relational databases or NoSQL databases is not simple, and you should not try it.</span></span> <span data-ttu-id="bfc75-120">Действительно необходимо разработать модели с помощью понимать как данные будут использоваться в каждой конкретной базы данных.</span><span class="sxs-lookup"><span data-stu-id="bfc75-120">You really have to design your model with an understanding of how the data is going to be used in each particular database.</span></span>

<span data-ttu-id="bfc75-121">Преимущество при использовании баз данных NoSQL, что сущности являются более денормализованные, не следует присваивать свойству сопоставления таблиц.</span><span class="sxs-lookup"><span data-stu-id="bfc75-121">A benefit when using NoSQL databases is that the entities are more denormalized, so you do not set a table mapping.</span></span> <span data-ttu-id="bfc75-122">Модель домена может быть более гибким, чем при использовании реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="bfc75-122">Your domain model can be more flexible than when using a relational database.</span></span>

<span data-ttu-id="bfc75-123">При конструировании вашего домена модели, основанной на статистических выражений, перемещение NoSQL документа ориентированными базами данных возможно, проще, чем с помощью реляционной базы данных, проектировании агрегатов похожи на сериализация и документов в базе данных, ориентированные на документы.</span><span class="sxs-lookup"><span data-stu-id="bfc75-123">When you design your domain model based on aggregates, moving to NoSQL and document-oriented databases might be even easier than using a relational database, because the aggregates you design are similar to serialized documents in a document-oriented database.</span></span> <span data-ttu-id="bfc75-124">Затем можно включить в эти «пакеты» все сведения, которые могут потребоваться для сводные данные.</span><span class="sxs-lookup"><span data-stu-id="bfc75-124">Then you can include in those “bags” all the information you might need for that aggregate.</span></span>

<span data-ttu-id="bfc75-125">Для экземпляра в следующем примере кода JSON — это реализация образца статистической обработки заказа, при использовании базы данных с учетом документа.</span><span class="sxs-lookup"><span data-stu-id="bfc75-125">For instance, the following JSON code is a sample implementation of an order aggregate when using a document-oriented database.</span></span> <span data-ttu-id="bfc75-126">Это похоже на порядок агрегатных была реализована в образце eShopOnContainers, но без использования основных EF под.</span><span class="sxs-lookup"><span data-stu-id="bfc75-126">It is similar to the order aggregate we implemented in the eShopOnContainers sample, but without using EF Core underneath.</span></span>

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

<span data-ttu-id="bfc75-127">При использовании C\# модель реализация статистического выражения для использования примерно Cosmos DB пакет SDK Azure, Агрегатная функция подобна C\# POCO классы, используемые с EF Core.</span><span class="sxs-lookup"><span data-stu-id="bfc75-127">When you use a C\# model to implement the aggregate to be used by something like the Azure Cosmos DB SDK, the aggregate is similar to the C\# POCO classes used with EF Core.</span></span> <span data-ttu-id="bfc75-128">Разница заключается в том, как их использование из уровней приложений и инфраструктуры, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="bfc75-128">The difference is in the way to use them from the application and infrastructure layers, as in the following code:</span></span>

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

<span data-ttu-id="bfc75-129">Вы увидите, что способ работы с моделью домена может быть аналогично тому, как она используется на уровне модели домена при EF инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="bfc75-129">You can see that the way you work with your domain model can be similar to the way you use it in your domain model layer when the infrastructure is EF.</span></span> <span data-ttu-id="bfc75-130">По-прежнему использовать те же корневой статистические методы для обеспечения согласованности, инварианты и проверок в агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="bfc75-130">You still use the same aggregate root methods to ensure consistency, invariants, and validations within the aggregate.</span></span>

<span data-ttu-id="bfc75-131">Однако при сохранении модели в базе данных NoSQL, код и изменение API значительно по сравнению с EF основного кода или любого другого кода, относящиеся к реляционным базам данных.</span><span class="sxs-lookup"><span data-stu-id="bfc75-131">However, when you persist your model into the NoSQL database, the code and API change dramatically compared to EF Core code or any other code related to relational databases.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="bfc75-132">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="bfc75-132">Additional resources</span></span>

-   <span data-ttu-id="bfc75-133">**Моделирование данных в DocumentDB**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span><span class="sxs-lookup"><span data-stu-id="bfc75-133">**Modeling data in DocumentDB**
[*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span></span>

-   <span data-ttu-id="bfc75-134">**Вон Вернон (Vaughn Vernon). Идеальный управляемого домена разработки статистического выражения хранилище? ** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span><span class="sxs-lookup"><span data-stu-id="bfc75-134">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**
[*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span></span>

-   <span data-ttu-id="bfc75-135">**Независимые сохраняемости событий хранилища для .NET.**</span><span class="sxs-lookup"><span data-stu-id="bfc75-135">**A persistence agnostic Event Store for .NET.**</span></span> <span data-ttu-id="bfc75-136">В репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="bfc75-136">GitHub repo.</span></span>
    [<span data-ttu-id="bfc75-137">*https://github.com/NEventStore/NEventStore*</span><span class="sxs-lookup"><span data-stu-id="bfc75-137">*https://github.com/NEventStore/NEventStore*</span></span>](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
<span data-ttu-id="bfc75-138">[Предыдущие] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Далее] (microservice-application-layer-web-api-design.md)</span><span class="sxs-lookup"><span data-stu-id="bfc75-138">[Previous] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Next] (microservice-application-layer-web-api-design.md)</span></span>
