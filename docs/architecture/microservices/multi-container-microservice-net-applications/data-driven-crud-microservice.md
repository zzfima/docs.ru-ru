---
title: Создание простой микрослужбы CRUD на основе данных
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Общие сведения о создании простой микрослужбы CRUD (управляемой данными) в контексте приложения для микрослужб.
ms.date: 01/30/2020
ms.openlocfilehash: b72d7defed81e57e2971c5e2b53df2d86b2dc947
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502363"
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a>Создание простой микрослужбы CRUD на основе данных

В этом разделе показывается создание простой микрослужбы, которая выполняет операции create, read, update и delete (CRUD) в источнике данных.

## <a name="designing-a-simple-crud-microservice"></a>Разработка простой микрослужбы CRUD

С точки зрения проектирования этот тип контейнерной микрослужбы очень прост. Возможно, решаемая проблема не представляет особой сложности, или реализация является лишь проверкой концепции.

![Схема, на которой показан шаблон внутренней структуры простой микрослужбы CRUD.](./media/data-driven-crud-microservice/internal-design-simple-crud-microservices.png)

**Рис. 6-4**. Внутренняя структура простой микрослужбы CRUD

Примером простой службы на основе данных такого рода является микрослужба каталога из эталонного приложения eShopOnContainers. Служба такого типа реализует все свои функции в одном проекте веб-API ASP.NET Core, который включает классы для своей модели данных, бизнес-логику и код доступа к данным. Она хранит свои связанные данные в базе данных, работающей в SQL Server (в качестве другого контейнера для целей разработки и тестирования), но это может также быть любой обычный узел SQL Server, как показано на рисунке 6-5.

![Схема, на которой показан контейнер микрослужбы CRUD на основе данных.](./media/data-driven-crud-microservice/simple-data-driven-crud-microservice.png)

**Рис. 6-5**. Структура простой микрослужбы CRUD на основе данных

На предыдущей схеме показана логическая микрослужба каталога, включающая свою базу данных каталога, которая может находиться на том же или другом узле Docker. Наличие базы данных на том же узле Docker может быть удобно для разработки, но не подходит для рабочей среды. При разработке такого рода службы требуется только [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) и ORM или API для доступа к данным, например [Entity Framework Core](https://docs.microsoft.com/ef/core/index). Можно также автоматически создать метаданные [Swagger](https://swagger.io/) посредством [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore), чтобы предоставить описание возможностей службы, как показано в следующем разделе.

Обратите внимание, что запуск сервера базы данных, такого как SQL Server, в контейнере Docker отлично подходит для сред разработки, так как вы можете получить все нужные зависимости в полной готовности без необходимости подготовки базы данных в облаке или локально. Это очень удобно при выполнении интеграционных тестов. Однако для рабочих сред запуск сервера базы данных в контейнере не рекомендуется, так как при таком подходе обычно не удается добиться высокой доступности. Для рабочей среды в Azure рекомендуется использовать базу данных SQL Azure или любую другую технологию базы данных, которая может обеспечить высокий уровень доступности и масштабируемости. Например, для варианта NoSQL можно выбрать CosmosDB.

Наконец, путем редактирования файлов метаданных Dockerfile и docker-compose.yml можно настроить порядок создания образа этого контейнера — какой базовый образ будет использоваться, а также конструктивные параметры, такие как внутренние и внешние имена и порты TCP.

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>Реализация простой микрослужбы CRUD в ASP.NET Core

Чтобы реализовать простую микрослужбу CRUD с помощью Visual Studio и .NET Core, начните с создания простого проекта веб-API ASP.NET Core (работающего в .NET Core, чтобы его можно было запустить на узле Linux Docker), как показано на рисунке 6-6.

![Снимок экрана Visual Studio, на котором показана настройка проекта.](./media/data-driven-crud-microservice/create-asp-net-core-web-api-project.png)

**Рис. 6-6**. Создание проекта веб-API ASP.NET Core в Visual Studio 2019

Для создания проекта веб-API ASP.NET Core сначала выберите веб-приложение ASP.NET Core и затем тип API. После создания проекта вы можете реализовать свои контроллеры MVC, как это делается в любом другом проекте веб-API, с помощью API Entity Framework или другого API. В новом проекте веб-API видно, что единственная имеющаяся в микрослужбе зависимость — в самом ASP.NET Core. Внутренним образом зависимость *Microsoft.AspNetCore.All* ссылается на Entity Framework и многие другие пакеты NuGet .NET Core, как показано на рисунке 6-7.

![Снимок экрана VS, на котором показаны зависимости NuGet для Catalog.Api.](./media/data-driven-crud-microservice/simple-crud-web-api-microservice-dependencies.png)

**Рис. 6-7**. Зависимости в простой микрослужбе CRUD веб-API

Проект API содержит ссылки на пакет NuGet Microsoft.AspNetCore.App, включающий в себя ссылки на все основные пакеты. Кроме того, он может включать и некоторые другие пакеты.

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Реализация служб CRUD веб-API с помощью Entity Framework Core

Entity Framework (EF) — это упрощенная, расширяемая и кроссплатформенная версия популярной технологии для доступа к данным Entity Framework. EF Core является объектно-реляционным модулем сопоставления (ORM), который позволяет разработчикам .NET работать с базой данных, используя объекты .NET.

Микрослужба каталога использует EF и поставщик SQL Server, так как его база данных работает в контейнере с образом Docker SQL Server для Linux . Тем не менее база данных может быть развернута в любом SQL Server, например локально в Windows или в базе данных SQL Azure. Единственное, что потребуется изменить, — это строку подключения в микрослужбе веб-API ASP.NET.

#### <a name="the-data-model"></a>Модель данных

В EF Core доступ к данным осуществляется с помощью модели. Модель состоит из классов сущностей (модель предметной области) и производного контекста (DbContext), который представляет сеанс взаимодействия с базой данных, позволяя запрашивать и сохранять данные. Вы можете создать модель из существующей базы данных, вручную написать код модели, соответствующей вашей базе данных, или воспользоваться миграциями EF для создания базы данных из своей модели на базе подхода Code First (что упрощает развитие базы данных по мере изменения модели). Для микрослужбы каталога мы используем последний подход. Пример класса CatalogItem можно увидеть в следующем примере кода, который представляет простой класс сущностей Plain Old CLR ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)).

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureFileName { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public int AvailableStock { get; set; }
    public int RestockThreshold { get; set; }
    public int MaxStockThreshold { get; set; }

    public bool OnReorder { get; set; }
    public CatalogItem() { }

    // Additional code ...
}
```

Также потребуется DbContext, который представляет сеанс работы с базой данных. Для микрослужбы каталога класс CatalogContext является производным от базового класса DbContext, как показано в следующем примере.

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    { }
    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...
}
```

У вас могут быть дополнительные реализации `DbContext`. Например, в примере микрослужбы Catalog.API образца имеется второй `DbContext` с именем `CatalogContextSeed`, где он автоматически заполняет демонстрационные данные при первой попытке получения доступа к базе данных. Этот метод полезен для демонстрационных данных, а также в сценариях автоматических тестов.

В `DbContext` используется метод `OnModelCreating` для настройки сопоставлений сущностей объектов или базы данных, а также других [точек расширяемости EF](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).

##### <a name="querying-data-from-web-api-controllers"></a>Запрос данных из контроллеров веб-API

Экземпляры классов сущностей обычно извлекаются из базы данных с помощью LINQ, как показано в следующем примере.

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(
        CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService
            ?? throw new ArgumentNullException(nameof(catalogIntegrationEventService));

        _settings = settings.Value;
        context.ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("items")]
    [ProducesResponseType(typeof(PaginatedItemsViewModel<CatalogItem>), (int)HttpStatusCode.OK)]
    [ProducesResponseType(typeof(IEnumerable<CatalogItem>), (int)HttpStatusCode.OK)]
    [ProducesResponseType((int)HttpStatusCode.BadRequest)]
    public async Task<IActionResult> ItemsAsync(
        [FromQuery]int pageSize = 10,
        [FromQuery]int pageIndex = 0,
        string ids = null)
    {
        if (!string.IsNullOrEmpty(ids))
        {
            var items = await GetItemsByIdsAsync(ids);

            if (!items.Any())
            {
                return BadRequest("ids value invalid. Must be comma-separated list of numbers");
            }

            return Ok(items);
        }

        var totalItems = await _catalogContext.CatalogItems
            .LongCountAsync();

        var itemsOnPage = await _catalogContext.CatalogItems
            .OrderBy(c => c.Name)
            .Skip(pageSize * pageIndex)
            .Take(pageSize)
            .ToListAsync();

        itemsOnPage = ChangeUriPlaceholder(itemsOnPage);

        var model = new PaginatedItemsViewModel<CatalogItem>(
            pageIndex, pageSize, totalItems, itemsOnPage);

        return Ok(model);
    }
    //...
}
```

##### <a name="saving-data"></a>Сохранение данных

Для создания, удаления и изменения данных в базе данных используются экземпляры классов сущностей. К своим контроллерам веб-API можно добавить код, как в следующем примере с жестким заданием (макета данных в этом случае).

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>Внедрение зависимостей в ASP.NET Core и контроллеры веб-API

В ASP.NET Core можно использовать внедрение зависимостей (DI) без дополнительной настройки. Не требуется настраивать сторонний контейнер инверсии управления (IoC), хотя при желании можно включить в инфраструктуру ASP.NET Core свой предпочитаемый контейнер IoC. В данном случае это означает, что вы можете напрямую внедрить требуемый DBContext EF или дополнительные репозитории с помощью конструктора контроллера.

В приведенном выше примере класса `CatalogController` мы внедряли объект типа `CatalogContext` и другие объекты с помощью конструктора `CatalogController()`.

Важной конфигурацией для настройки в проекте веб-API является регистрация класса DbContext в контейнере IoC службы. Обычно это делается в классе `Startup` путем вызова метода `services.AddDbContext<DbContext>()` в методе `ConfigureServices()`, как показано в следующем **упрощенном** примере:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Additional code...

    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
            sqlOptions.MigrationsAssembly(
                typeof(Startup).GetTypeInfo().Assembly.GetName().Name);

           //Configuring Connection Resiliency:
           sqlOptions.
               EnableRetryOnFailure(maxRetryCount: 5,
               maxRetryDelay: TimeSpan.FromSeconds(30),
               errorNumbersToAdd: null);

       });

       // Changing default behavior when client evaluation occurs to throw.
       // Default in EFCore would be to log warning when client evaluation is done.
       options.ConfigureWarnings(warnings => warnings.Throw(
           RelationalEventId.QueryClientEvaluationWarning));
   });

  //...
}
```

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Запросы к данным** \
  [https://docs.microsoft.com/ef/core/querying/index](/ef/core/querying/index)

- **Сохранение данных** \
  [https://docs.microsoft.com/ef/core/saving/index](/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>Строка подключения к базе данных и переменные среды, используемые контейнерами Docker

Вы можете использовать параметры ASP.NET Core и добавить свойство ConnectionString в файл settings.json, как показано в следующем примере.

```json
{
    "ConnectionString": "Server=tcp:127.0.0.1,5433;Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word",
    "ExternalCatalogBaseUrl": "http://localhost:5101",
    "Logging": {
        "IncludeScopes": false,
        "LogLevel": {
            "Default": "Debug",
            "System": "Information",
            "Microsoft": "Information"
        }
    }
}
```

Файл settings.json может иметь значения по умолчанию для свойства ConnectionString или любого другого свойства. Однако при использовании Docker эти свойства будут переопределяться значениями переменных среды, заданными в файле docker-compose.override.yml.

Из файлов docker-compose.yml или docker-compose.override.yml можно инициализировать эти переменные среды, чтобы Docker устанавливал их в качестве переменных среды операционной системы, как показано в следующем файле docker-compose.override.yml (в этом примере строка подключения и другие строки переносятся, но в вашем собственном файле они не будут переноситься).

```yml
# docker-compose.override.yml

#
catalog-api:
  environment:
    - ConnectionString=Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    # Additional environment variables for this service
  ports:
    - "5101:80"
```

Файлы docker-compose.yml на уровне решения не только более гибкие, чем файлы конфигурации на уровне проекта или микрослужбы, но также и более безопасные, если вы переопределяете переменные среды, объявленные в файлах docker-compose, значениями, установленными из инструментов развертывания, например из задач развертывания Docker в Azure DevOps Services.

Наконец, можно получить это значение из кода с помощью Configuration\["ConnectionString"\], как показано в методе ConfigureServices в предыдущем примере кода.

Однако для рабочей среды вы можете исследовать дополнительные возможности по хранению секретов, таких как строки подключения. Прекрасным способом управления секретами приложений является использование [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).

Azure Key Vault обеспечивает хранение и защиту ключей шифрования и секретов, используемых облачными приложениями и службами. Секрет — это все то, что вы хотите жестко контролировать, например ключи API, строки подключения, пароли и т. п., при этом в число средств такого контроля, *среди прочего*, входит ведение журналов использования, срок действия параметров и управление доступом.

Azure Key Vault позволяет очень детально управлять уровнем использования секретов приложений, не раскрывая их никому постороннему. Секреты можно даже менять, чтобы повысить уровень безопасности, не нарушая процедуры разработки или эксплуатации.

Чтобы приложения могли использовать Key Vault, они должны быть зарегистрированы в Active Directory организации.

Дополнительные сведения см. в *документации об основных понятиях Key Vault*.

### <a name="implementing-versioning-in-aspnet-web-apis"></a>Реализация управления версиями в веб-API ASP.NET

По мере изменения бизнес-требований может происходить добавление новых коллекций ресурсов, изменение связей между ресурсами и совершенствование структуры данных в ресурсах. Обновление веб-API для обработки новых требований выполняется относительно просто, однако необходимо учитывать воздействие, которое такие изменения будут оказывать на клиентские приложения, использующие веб-API. Несмотря на то, что разработчик, разрабатывающий и реализующий веб-API, имеет полный контроль над этим API, у него нет той же степени контроля над клиентскими приложениями, которые могут быть созданы сторонними организациями, работающими удаленно.

Управление версиями позволяет веб-API указать компоненты и ресурсы, которые он предоставляет. Затем клиентское приложение может отправлять запросы к определенной версии функции или ресурса. Существует несколько методов реализации управления версиями:

- управление версиями с помощью URI;

- управление версиями с помощью строки запроса;

- управление версиями с помощью заголовка.

Проще всего реализовать управление версиями с помощью строки заголовка и URI. Управление версиями с помощью заголовка — хороший метод. Но он не настолько явный и простой, как управление версиями с помощью URI. Так как управление версиями с помощью URI является самым простым и очевидным методом, в эталонном приложении eShopOnContainers используется именно управление версиями с помощью URI.

При использовании управления версиями с помощью URI, как в эталонном приложении eShopOnContainers, при каждом изменении веб-API или схемы ресурсов в URI для каждого ресурса добавляется номер версии. Существующие URI должны продолжать работать как и прежде, возвращая ресурсы, которые подходят для схемы, соответствующей запрошенной версии.

Как показано в следующем примере кода, версию можно устанавливать с помощью атрибута Route в контроллере веб-API, что делает версию в URI явной (в данном случае это v1).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

Этот механизм управления версиями прост и зависит от сервера, направляющего запрос в соответствующую конечную точку. Однако для более сложного управления версиями и наиболее подходящего метода при использовании REST следует использовать гиперсредства и реализовать подход [HATEOAS (гипертекст как обработчик состояния приложения)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources).

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Скотт Ханселман (Scott Hanselman). Упрощение управления версиями веб-API ASP.NET Core с поддержкой REST** \
  <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

- **Управление версиями веб-API с поддержкой REST** \
  <https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api>

- **Рой Филдинг (Roy Fielding). Управление версиями, гипермедиа и REST** \
  <https://www.infoq.com/articles/roy-fielding-on-versioning>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>Создание метаданных описания Swagger из веб-API ASP.NET Core

[Swagger](https://swagger.io/) — это распространенная платформа с открытым исходным кодом, поддерживаемая большой экосистемой инструментов, помогающих разрабатывать, собирать, документировать и использовать ваши API RESTful. Она становится стандартом для домена метаданных описания API. Следует включать метаданные описания Swagger в микрослужбы любого вида — и в микрослужбы на основе данных, и в более сложные предметно-ориентированные микрослужбы (как описывается в следующем разделе).

Основу Swagger составляет спецификация Swagger, представляющая собой метаданные описания API в файле JSON или YAML. Эта спецификация создает контракт RESTful для вашего API, детализируя все его ресурсы и операции как в форме, удобной для восприятия человеком, так и в машинно-распознаваемой форме для упрощения разработки, обнаружения и интеграции.

Спецификация является основой спецификации OpenAPI (OAS) и разрабатывается в открытом, прозрачном, совместно работающем сообществе для стандартизации способа определения интерфейсов RESTful.

Спецификация определяет структуру способа обнаружения службы и понимания ее возможностей. Дополнительные сведения, включая веб-редактор и примеры спецификаций Swagger от таких компаний, как Spotify, Uber, Slack и Майкрософт, см. на сайте Swagger (<https://swagger.io>).

### <a name="why-use-swagger"></a>Почему следует использовать Swagger?

Ниже перечислены основные причины создания метаданных Swagger для ваших API.

**Возможность для других продуктов автоматически использовать и интегрировать ваши API**. Десятки продуктов и [коммерческих инструментов](https://swagger.io/commercial-tools/), а также множество [библиотек и платформ](https://swagger.io/open-source-integrations/) поддерживают Swagger. Корпорация Майкрософт предоставляет высокоуровневые продукты и инструменты, которые могут автоматически использовать API на основе Swagger, например следующие.

- [AutoRest](https://github.com/Azure/AutoRest). Вы можете автоматически создавать клиентские классы .NET для вызова Swagger. Этот инструмент можно использовать из CLI, и он также интегрируется с Visual Studio для упрощения использования через графический интерфейс пользователя.

- [Microsoft Flow](https://flow.microsoft.com/). Вы можете автоматически [использовать и интегрировать свои API](https://flow.microsoft.com/blog/integrating-custom-api/) в высокоуровневый процесс Microsoft Flow без каких-либо навыков программирования.

- [Microsoft PowerApps](https://powerapps.microsoft.com/). Вы можете автоматически использовать свои API из [мобильных приложений PowerApps](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/), созданных с помощью [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/), без каких-либо навыков программирования.

- [Приложения логики службы приложений Azure](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps). Вы можете автоматически [использовать и интегрировать свои API в приложение логики службы приложений Azure ](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api) без каких-либо навыков программирования.

**Возможность автоматического создания документации по API**. При создании крупномасштабных API RESTful, например сложных приложений на основе микрослужб, необходимо обрабатывать много конечных точек с разными моделями данных, используемых в полезной нагрузке запросов и ответов. Наличие соответствующей документации и надежного обозревателя API, что можно получить с помощью Swagger, является ключом для успеха API и внедрения разработчиками.

Метаданные Swagger используются Microsoft Flow, PowerApps и Azure Logic Apps для понимания, как следует использовать API и подключаться к ним.

Существует несколько способов автоматизировать создание метаданных Swagger для приложений REST API ASP.NET Core в виде функциональных страниц справки API на основе *swagger-ui*.

Вероятно, наиболее известен [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore), который сейчас используется в [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers), и мы рассмотрим его подробнее в этом руководстве. Однако можно также использовать [NSwag](https://github.com/RSuter/NSwag), который может создавать клиенты API Typescript и C\#, а также контроллеры C\# на базе спецификации Swagger или OpenAPI и даже посредством сканирования библиотеки DLL, содержащей контроллеры, с помощью [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio).

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Автоматизация создания метаданных Swagger API с помощью пакета NuGet Swashbuckle

Создание метаданных Swagger вручную (в файле JSON или YAML) может быть утомительным. Однако вы можете автоматизировать обнаружение API службами веб-API ASP.NET с помощью [пакета NuGet Swashbuckle](https://aka.ms/swashbuckledotnetcore) для динамического создания метаданных Swagger API.

Swashbuckle автоматически создает метаданные Swagger для проектов веб-API ASP.NET. Он поддерживает проекты веб-API ASP.NET Core, классические веб-API ASP.NET и любые разновидности, такие как приложение API Azure, мобильное приложение Azure, микрослужбы Azure Service Fabric на основе ASP.NET. Он также поддерживает простой веб-API, развертываемый в контейнерах, как в эталонном приложении.

Swashbuckle объединяет обозреватель API и Swagger или [пользовательский интерфейс Swagger](https://github.com/swagger-api/swagger-ui) для обеспечения вашим клиентам API широких возможностей использования обнаружения и документации. Помимо своей подсистемы создания метаданных Swagger, Swashbuckle также содержит встроенную версию пользовательского интерфейса swagger, которую он будет автоматически обслуживать после установки Swashbuckle.

Это означает, что вы можете дополнять свой API отличным пользовательским интерфейсом обнаружения, чтобы помочь разработчикам использовать этот API. Для него требуется совсем немного кода и поддержки, так как он создается автоматически, что позволяет сосредоточиться на построении API. Результат в обозревателе API выглядит подобно показанному на рисунке 6-8.

![Снимок экрана: обозреватель API Swagger, в котором отображается API eShopOContainers.](./media/data-driven-crud-microservice/swagger-metadata-eshoponcontainers-catalog-microservice.png)

**Рис. 6-8**. Обозреватель API Swashbuckle на основе метаданных Swagger — микрослужба каталога eShopOnContainers

Созданная Swashbuckle документация по API пользовательского интерфейса Swagger. Обозреватель API здесь не самое главное. При наличии веб-API, который может описать сам себя в метаданных Swagger, ваш API можно без проблем использовать в инструментах на основе Swagger, включая генераторы кода клиентского прокси-класса, предназначенные для многих платформ. Например, как упоминалось ранее, [AutoRest](https://github.com/Azure/AutoRest) автоматически создает клиентские классы .NET. Однако доступны также и дополнительные средства, например [swagger-codegen](https://github.com/swagger-api/swagger-codegen), что позволяет автоматически создавать код клиентских библиотек API, заглушки сервера и документацию.

Сейчас Swashbuckle состоит из пяти независимых внутренних пакетов NuGet в высокоуровневом метапакете [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) для приложений ASP.NET Core.

После установки этих пакетов NuGet в проекте веб-API нужно настроить Swagger в классе Startup, как показано в следующем **упрощенном** коде:

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...

        // Add framework services.
        services.AddSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SwaggerDoc("v1", new OpenApiInfo
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API. This is a Data-Driven/CRUD microservice sample"
            });
        });

        // Other ConfigureServices() code...
    }

    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure() code...
        // ...
        app.UseSwagger()
            .UseSwaggerUI(c =>
            {
                c.SwaggerEndpoint("/swagger/v1/swagger.json", "My API V1");
            });
    }
}
```

После этого можно запустить приложение и перейти к следующим конечным точкам пользовательского интерфейса и JSON Swagger, используя URL-адреса, подобные приведенным ниже.

```console
  http://<your-root-url>/swagger/v1/swagger.json

  http://<your-root-url>/swagger/
```

Вы ранее видели пользовательский интерфейс, созданный Swashbuckle и доступный по URL-адресу, например `http://<your-root-url>/swagger`. На рисунке 6-9 показано, как можно тестировать любой метод API.

![Снимок экрана: пользовательский интерфейс Swagger, в котором отображаются доступные средства тестирования.](./media/data-driven-crud-microservice/swashbuckle-ui-testing.png)

**Рис. 6-9**. Тестирование метода API Catalog/Items в пользовательском интерфейсе Swashbuckle

В сведениях об API пользовательского интерфейса Swagger приведен пример отклика, который можно использовать для выполнения реального API, что отлично подходит для обнаружения разработчика. На рисунке 6-10 показаны метаданные JSON Swagger, созданные из микрослужбы eShopOnContainers (именно ее инструменты используют на внутреннем уровне) при запросе `http://<your-root-url>/swagger/v1/swagger.json` с помощью [Postman](https://www.getpostman.com/).

![Снимок экрана: пример пользовательского интерфейса Postman, в котором отображаются метаданные Swagger в формате JSON.](./media/data-driven-crud-microservice/swagger-json-metadata.png)

**Рис. 6-10**. Метаданные JSON Swagger

Это так просто. И так как они создаются автоматически, метаданные Swagger будет увеличиваться при добавлении дополнительных функций к вашему API.

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Страницы справки по веб-API ASP.NET с использованием Swagger** \
  [https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger](/aspnet/core/tutorials/web-api-help-pages-using-swagger)

- **Начало работы с Swashbuckle и ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-swashbuckle](/aspnet/core/tutorials/getting-started-with-swashbuckle)

- **Начало работы с NSwag и ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-nswag](/aspnet/core/tutorials/getting-started-with-nswag)

> [!div class="step-by-step"]
> [Назад](microservice-application-design.md)
> [Вперед](multi-container-applications-docker-compose.md)
