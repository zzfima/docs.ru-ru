---
title: Использование баз данных NoSQL в качестве инфраструктуры сохраняемости
description: Использование баз данных NoSql в целом и в Azure Cosmos DB в частности для реализации сохраняемости.
ms.date: 01/30/2020
ms.openlocfilehash: 7da4141d9aadc4aaa265ac97d328bc4b7569a0cb
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502377"
---
# <a name="use-nosql-databases-as-a-persistence-infrastructure"></a>Использование баз данных NoSQL в качестве инфраструктуры сохраняемости

При использовании баз данных NoSQL для уровня данных инфраструктуры обычно не используется ORM, например Entity Framework Core. Вместо этого используйте API, предоставляемый подсистемой NoSQL, например Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB или таблицы хранилищ Azure.

Тем не менее при использовании базы данных NoSQL, особенно для документоориентированных баз данных, таких как Azure Cosmos DB, CouchDB или RavenDB, архитектура модели с агрегатами DDD частично похожа на соответствующую архитектуру в EF Core в отношении определения корней агрегации, классов дочерних объектов и классов объектов значений. Но в конечном счете выбор базы данных повлияет на вашу архитектуру.

При использовании документоориентированной базы данных агрегат реализуется в виде отдельного документа, сериализованного в JSON или в другом формате. Однако использование базы данных является прозрачным с точки зрения модели предметной области. При использовании баз данных NoSQL вы по-прежнему используете классы сущностей и классы корней агрегации, но с большей гибкостью, чем при использовании EF Core, так как сохраняемость не является реляционной.

Различие заключается в том, как реализована сохраняемость для этой модели. Если модель предметной области реализована на основе классов сущностей POCO, которые не зависят от сохраняемости инфраструктуры, вы можете перейти на другую сохраняемость инфраструктуры, даже с реляционных баз данных на NoSQL. Однако это не должно быть вашей целью. В различных технологиях баз данных всегда есть ограничения и компромиссы, поэтому вы не сможете использовать одну и ту же модель для реляционных баз данных и баз данных NoSQL. Изменение моделей сохраняемости будет непростой задачей, так как транзакции и операции сохраняемости будут сильно отличаться.

Например, в документоориентированной базе данных корень агрегирования может иметь несколько свойств дочерних коллекций. В реляционной базе данных запрос к нескольким свойствам дочерних коллекций нелегко оптимизировать, так как вы получите инструкцию UNION ALL SQL обратно из EF. Использование одной и той же модели предметной области для реляционных баз данных и баз данных NoSQL — непростое, и не стоит стараться этого достичь. На практике нужно спроектировать свою модель с пониманием того, как данные будут использоваться в каждой конкретной базе данных.

Преимущество при использовании баз данных NoSQL заключается в том, что сущности более денормализованы, поэтому вам не нужно настраивать сопоставление таблиц. Модель предметной области может быть более гибкой по сравнению с реляционной базой данных.

При проектировании модели предметной области на основе агрегатов переход на NoSQL и документоориентированные базы данных может быть еще проще по сравнению с использованием реляционных баз данных, так как создаваемые вами агрегаты похожи на сериализованные документы в документоориентированной базе данных. Затем вы сможете включить в эти "контейнеры" все необходимые сведения для этого агрегата.

Например, следующий код JSON представляет собой пример реализации агрегата порядка при использовании документоориентированной базы данных. Этот агрегат похож на агрегат порядка, реализованный в примере eShopOnContainers, но не основан на EF Core.

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

## <a name="introduction-to-azure-cosmos-db-and-the-native-cosmos-db-api"></a>Общие сведения об Azure Cosmos DB и о собственном API Cosmos DB

[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) — глобально распределенная служба баз данных корпорации Майкрософт для критически важных приложений. Azure Cosmos DB предоставляет [глобальное распределение](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), [эластичное масштабирование пропускной способности и хранилища](https://docs.microsoft.com/azure/cosmos-db/partition-data) по всему миру, задержку не более десяти миллисекунд на 99-м процентиле, [пять хорошо определенных уровней согласованности](https://docs.microsoft.com/azure/cosmos-db/consistency-levels), гарантированную высокую доступность — и все это с [ведущими в отрасли соглашениями об уровне обслуживания](https://azure.microsoft.com/support/legal/sla/cosmos-db/). Azure Cosmos DB [автоматически индексирует данные](https://www.vldb.org/pvldb/vol8/p1668-shukla.pdf) без необходимости иметь дело со схемой и управлением индексами. Она является мультимодельной и поддерживает следующие модели данных: модель данных документа, модель данных "ключ-значение", модель данных графа и столбцовая модель данных.

![Схема, на которой показано глобальное распределение Azure Cosmos DB.](./media/nosql-database-persistence-infrastructure/azure-cosmos-db-global-distribution.png)

**Рис. 7–19**. Глобальное распределение Azure Cosmos DB

При использовании модели C\# для реализации агрегирования, используемого API Azure Cosmos DB, агрегат может быть похож на классы POCO C\#, используемые в EF Core. Различие заключается в использовании классов на уровнях приложения и инфраструктуры, как показано в следующем коде:

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH AZURE COSMOS DB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).

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

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
// *** End of Domain Model Code ***

// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, orderAggregate);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

Вы увидите, что ваш способ работы с моделью предметной области может быть похож на ее использование на уровне модели предметной области в инфраструктуре EF. Вы по-прежнему можете использовать те же методы корней агрегации для обеспечения согласованности, инвариантности и для выполнения проверок в агрегатах.

Однако при сохранении модели в базе данных NoSQL код и API значительно изменяются по сравнению с кодом EF Core или с любым другим кодом для реляционных баз данных.

## <a name="implement-net-code-targeting-mongodb-and-azure-cosmos-db"></a>Реализация кода .NET для MongoDB и Azure Cosmos DB

### <a name="use-azure-cosmos-db-from-net-containers"></a>Использование Azure Cosmos DB из контейнеров .NET

Базы данных Azure Cosmos DB доступны из любого кода .NET, запущенного в контейнерах, точно так же, как из любых других приложений .NET. Например, микрослужбы Locations.API и Marketing.API в eShopOnContainers реализованы таким образом, что они могут использовать базы данных Azure Cosmos DB.

Однако с точки зрения разработки для Docker, в Azure Cosmos DB есть ограничение. Несмотря на наличие локального эмулятора [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/local-emulator), который может выполняться на локальном компьютере разработки, он поддерживает только Windows. Linux и macOS не поддерживаются.

Этот эмулятор также можно запустить в Docker, но только в контейнерах Windows, а не в контейнерах Linux. Это начальное ограничение среды разработки в том случае, если ваше приложение развертывается в виде контейнеров Linux, так как сейчас вы не можете одновременно развернуть контейнеры Linux и Windows в Docker для Windows. Все контейнеры должны быть развернуты либо в Linux, либо в Windows.

Идеальный и более простой вариант решения для разработки и тестирования — возможность развертывания систем баз данных в качестве контейнеров вместе с вашими пользовательскими контейнерами, таким образом среды разработки и тестирования всегда будут согласованы.

### <a name="use-mongodb-api-for-local-devtest-linuxwindows-containers-plus-azure-cosmos-db"></a>Использование API MongoDB для локальных контейнеров разработки и тестирования Linux/Windows и Azure Cosmos DB

Базы данных Cosmos DB поддерживают API MongoDB для .NET, а также собственный коммутации MongoDB. Это означает, что ваше приложение MongoDB сейчас сможет взаимодействовать с Cosmos DB и использовать базы данных Cosmos DB вместо баз данных MongoDB с использованием существующих драйверов, как показано на рис. 7-20.

![Схема, на которой показано, что Cosmos DB поддерживает .NET и сетевой протокол MongoDB.](./media/nosql-database-persistence-infrastructure/mongodb-api-wire-protocol.png)

**Рис. 7-20**. Использование API и протокола MongoDB для доступа к Azure Cosmos DB

Это очень удобный подход для подтверждения концепций в средах Docker с контейнерами Linux, так как [образ Docker MongoDB](https://hub.docker.com/r/_/mongo/) — это образ с поддержкой нескольких архитектур. Он поддерживает как контейнеры Linux, так и контейнеры Windows в Docker.

Как показано на следующем рисунке, eShopOnContainers поддерживает контейнеры Windows и Linux MongoDB для локальной среды разработки с API MongoDB. Но вы можете перейти на масштабируемое облачное решение PaaS, такое как Azure Cosmos DB, просто [изменив строку подключения MongoDB, так чтобы она указывала на Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).

![Схема, на которой показано, что микрослужба Location в eShopOnContainers может использовать либо Cosmos DB, либо MongoDB.](./media/nosql-database-persistence-infrastructure/eshoponcontainers-mongodb-containers.png)

**Рис. 7-21**. Решение eShopOnContainers, использующее контейнеры MongoDB для среды разработки и Azure Cosmos DB для рабочей среды

Рабочая база данных Azure Cosmos DB была бы запущена в облаке Azure как PaaS и масштабируемая служба.

Пользовательские контейнеры .NET Core можно запустить на локальном узле Docker (на котором используется Docker для Windows на компьютере Windows 10) или развернуть в рабочей среде, например, в Kubernetes в Azure AKS или в Azure Service Fabric. Во второй среде вы разворачиваете только пользовательские контейнеры .NET Core, но не контейнер MongoDB, так как вы будете использовать Azure Cosmos DB в облаке для обработки данных в рабочей среде.

Очевидное преимущество API MongoDB — в том, что ваше решение можно запустить как в MongoDB, так и в Azure Cosmos DB, поэтому перенос в другую среду не должен представлять сложностей. Однако иногда стоит использовать собственный API (то есть собственный API Cosmos DB), чтобы получить полный набор возможностей конкретной СУБД.

Дальнейшее сравнение простого использования MongoDB и Cosmos DB в облаке см. в разделе [Преимущества использования Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction) на этой странице.

### <a name="analyze-your-approach-for-production-applications-mongodb-api-vs-cosmos-db-api"></a>Анализ подходов для приложений в рабочей среде: сравнение API MongoDB и API Cosmos DB

В eShopOnContainers мы используем API MongoDB, так как нашим главным приоритетом была согласованная среда разработки и тестирования с использованием базы данных NoSQL, которая могла бы также работать с Azure Cosmos DB.

Тем не менее если вы планируете использовать API MongoDB для доступа к Azure Cosmos DB в Azure из приложений в рабочей среде, следует проанализировать различия в возможностях и производительности при использовании API MongoDB для доступа к базам данных Azure Cosmos DB по сравнению с использованием собственного API Azure Cosmos DB. Если возможности и производительность сопоставимы, вы можете использовать API MongoDB и получите поддержку двух СУБД NoSQL одновременно.

Также можно использовать кластеры MongoDB в рабочей базе данных в облаке Azure с помощью [службы MongoDB Azure](https://www.mongodb.com/scale/mongodb-azure-service). Однако эта служба — не служба PaaS, предоставляемая Майкрософт. В этом случае в Azure просто размещается решение MongoDB.

По сути, это просто предупреждение о том, что не следует всегда выбирать API MongoDB в сравнении с Azure Cosmos DB, как мы сделали в eShopOnContainers, так как API MongoDB хорошо подходит для контейнеров Linux. При принятии решения следует учитывать конкретные потребности и провести конкретные проверки для приложения в рабочей среде.

### <a name="the-code-use-mongodb-api-in-net-core-applications"></a>Код. Использование API MongoDB в приложениях .NET Core

API MongoDB для .NET основан на пакетах NuGet, которые необходимо добавить в свои проекты, например проект Locations.API, показанный на следующем рисунке.

![Снимок экрана: зависимости в пакетах NuGet MongoDB.](./media/nosql-database-persistence-infrastructure/mongodb-api-nuget-packages.png)

**Рис. 7-22**. Ссылки на пакеты NuGet для API MongoDB в проекте .NET Core

Давайте рассмотрим код, приведенный в следующих разделах.

#### <a name="a-model-used-by-mongodb-api"></a>Модель, используемая API MongoDB

Во-первых, необходимо определить модель, которая будет содержать данные, поступающие из базы данных в пространство памяти приложения. Ниже приведен пример модели, используемой для расположений в eShopOnContainers.

```csharp
using MongoDB.Bson;
using MongoDB.Bson.Serialization.Attributes;
using MongoDB.Driver.GeoJsonObjectModel;
using System.Collections.Generic;

public class Locations
{
    [BsonId]
    [BsonRepresentation(BsonType.ObjectId)]
    public string Id { get; set; }
    public int LocationId { get; set; }
    public string Code { get; set; }
    [BsonRepresentation(BsonType.ObjectId)]
    public string Parent_Id { get; set; }
    public string Description { get; set; }
    public double Latitude { get; set; }
    public double Longitude { get; set; }
    public GeoJsonPoint<GeoJson2DGeographicCoordinates> Location
                                                             { get; private set; }
    public GeoJsonPolygon<GeoJson2DGeographicCoordinates> Polygon
                                                             { get; private set; }
    public void SetLocation(double lon, double lat) => SetPosition(lon, lat);
    public void SetArea(List<GeoJson2DGeographicCoordinates> coordinatesList)
                                                    => SetPolygon(coordinatesList);

    private void SetPosition(double lon, double lat)
    {
        Latitude = lat;
        Longitude = lon;
        Location = new GeoJsonPoint<GeoJson2DGeographicCoordinates>(
            new GeoJson2DGeographicCoordinates(lon, lat));
    }

    private void SetPolygon(List<GeoJson2DGeographicCoordinates> coordinatesList)
    {
        Polygon = new GeoJsonPolygon<GeoJson2DGeographicCoordinates>(
                  new GeoJsonPolygonCoordinates<GeoJson2DGeographicCoordinates>(
                  new GeoJsonLinearRingCoordinates<GeoJson2DGeographicCoordinates>(
                                                                 coordinatesList)));
    }
}
```

Как вы видите, в ней есть несколько атрибутов и типов из пакетов NuGet MongoDB.

Базы данных NoSQL обычно очень хорошо подходят для работы с нереляционными иерархическими данными. В этом примере мы используем типы MongoDB, специально предназначенные для географических расположений, например `GeoJson2DGeographicCoordinates`.

#### <a name="retrieve-the-database-and-the-collection"></a>Получение базы данных и коллекции

В eShopOnContainers мы создали пользовательский контекст базы данных, в котором реализовали код для получения базы данных и коллекций MongoCollections, как показано в следующем коде.

```csharp
public class LocationsContext
{
    private readonly IMongoDatabase _database = null;

    public LocationsContext(IOptions<LocationSettings> settings)
    {
        var client = new MongoClient(settings.Value.ConnectionString);
        if (client != null)
            _database = client.GetDatabase(settings.Value.Database);
    }

    public IMongoCollection<Locations> Locations
    {
        get
        {
            return _database.GetCollection<Locations>("Locations");
        }
    }
}
```

#### <a name="retrieve-the-data"></a>Получение данных

В коде C#, например, в контроллерах веб-API или в реализации пользовательских репозиториев вы можете использовать похожий код для выполнения запросов с помощью API MongoDB. Обратите внимание, что объект `_context` является экземпляром предыдущего класса `LocationsContext`.

```csharp
public async Task<Locations> GetAsync(int locationId)
{
    var filter = Builders<Locations>.Filter.Eq("LocationId", locationId);
    return await _context.Locations
                            .Find(filter)
                            .FirstOrDefaultAsync();
}
```

#### <a name="use-an-env-var-in-the-docker-composeoverrideyml-file-for-the-mongodb-connection-string"></a>Использование переменной среды в файле docker-compose.override.yml для строки подключения MongoDB

При создании объекта MongoClient необходимо указать фундаментальный параметр, который представляет собой параметр `ConnectionString`, указывающий на нужную базу данных. Для eShopOnContainers строка подключения может указывать на локальный контейнер MongoDB Docker или на "рабочую" базу данных Azure Cosmos DB.  Эта строка подключения берется из переменных среды, заданных в файлах `docker-compose.override.yml`, используемых при развертывании с помощью docker-compose или Visual Studio, как показано в следующем коде YML.

```yml
# docker-compose.override.yml
version: '3.4'
services:
  # Other services
  locations-api:
    environment:
      # Other settings
      - ConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}

```

Переменная среды `ConnectionString` разрешается следующим образом: если в файле `.env` определена глобальная переменная `ESHOP_AZURE_COSMOSDB` со строкой подключения Azure Cosmos DB, эта строка подключения будет использована для обращения к базе данных Azure Cosmos DB в облаке. Если она не определена, будет использоваться значение `mongodb://nosqldata` и контейнер разработки MongoDB.

В следующем коде показан файл `.env` с глобальной переменной среды для строки подключения Azure Cosmos DB, так, как это было реализовано в решении eShopOnContainers:

```yml
# .env file, in eShopOnContainers root folder
# Other Docker environment variables

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost
ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=<YourDockerHostIP>

#ESHOP_AZURE_COSMOSDB=<YourAzureCosmosDBConnData>

#Other environment variables for additional Azure infrastructure assets
#ESHOP_AZURE_REDIS_BASKET_DB=<YourAzureRedisBasketInfo>
#ESHOP_AZURE_STORAGE_CATALOG_URL=<YourAzureStorage_Catalog_BLOB_URL>
#ESHOP_AZURE_SERVICE_BUS=<YourAzureServiceBusInfo>
```

Раскомментируйте строку ESHOP_AZURE_COSMOSDB и замените ее на строку подключения к Azure Cosmos DB, полученную на портале Azure в соответствии с инструкциями в статье [Connect a MongoDB application to Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account) (Подключение приложения MongoDB к Azure Cosmos DB).

Если глобальная переменная `ESHOP_AZURE_COSMOSDB` пуста, то есть она записывается в файл `.env`, контейнер использует строку подключения MongoDB по умолчанию. Эта строка подключения указывает на локальный контейнер MongoDB, развернутый в eShopOnContainers с именем `nosqldata`, определенный в файле docker-compose, как показано в следующем коде .yml:

``` yml
# docker-compose.yml
version: '3.4'
services:
  # ...Other services...
  nosqldata:
    image: mongo
```

#### <a name="additional-resources"></a>Дополнительные ресурсы

- **Моделирование документальных данных в базах данных NoSQL** \
  <https://docs.microsoft.com/azure/cosmos-db/modeling-data>

- **Вон Вернон (Vaughn Vernon). Идеальное хранилище агрегатов, созданное с помощью предметно-ориентированного проектирования?** \
  <https://kalele.io/blog-posts/the-ideal-domain-driven-design-aggregate-store/>

- **Введение в Azure Cosmos DB: API для MongoDB**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction>

- **Azure Cosmos DB. Разработка веб-приложения API MongoDB с помощью .NET и портала Azure**  \
  <https://docs.microsoft.com/azure/cosmos-db/create-mongodb-dotnet>

- **Использование эмулятора Azure Cosmos DB для разработки и тестирования в локальной среде**  \
  <https://docs.microsoft.com/azure/cosmos-db/local-emulator>

- **Подключение приложения MongoDB к Azure Cosmos DB**  \
  <https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account>

- **Образ Docker эмулятора Cosmos DB (контейнер для Windows)**   \
  <https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/>

- **Образ Docker MongoDB (контейнер для Linux и Windows)**   \
  <https://hub.docker.com/_/mongo/>

- **Использование MongoChef (Studio 3T) с Azure Cosmos DB: API для учетной записи MongoDB**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-mongochef>

>[!div class="step-by-step"]
>[Назад](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
>[Вперед](microservice-application-layer-web-api-design.md)
