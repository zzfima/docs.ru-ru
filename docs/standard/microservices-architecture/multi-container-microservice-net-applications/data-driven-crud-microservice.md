---
title: "Создание простой микрослужбу CRUD управляемые данными"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Создание простой микрослужбу CRUD управляемые данными"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b814d344f2c78e7cf57f9e2896cf1d6b52db38d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a>Создание простой микрослужбу CRUD управляемые данными

Этот раздел контуров как создать простой микрослужбу, которая выполняет создание, чтение, обновление и операции удаления (CRUD) в источнике данных.

## <a name="designing-a-simple-crud-microservice"></a>Разработка простого микрослужбу CRUD

С точки зрения проектирования этот тип контейнерного микрослужбу очень проста. Возможно, проблема является простой или может быть реализован только эксперимента.

![](./media/image4.png)

**Рис. 8-4**. Внутренняя структура простой микрослужбами CRUD

Пример такого рода службы простой-диск с данными — микрослужбу каталога из eShopOnContainers образца приложения. Этот тип службы реализует все функции в одном проекте веб-API ASP.NET Core, которая содержит классы для своей модели данных, его бизнес-логики и его код доступа к данным. Также связанные данные хранятся в базе данных, выполняющемся на SQL Server (как в другой контейнер для целей разработки и тестирования), но также может быть любой регулярного узла SQL Server, как показано на рисунке 8-5.

![](./media/image5.png)

**Рис. 8-5**. Простой микрослужбу данных управляемых/CRUD разработки

При разработке такого рода службы требуется только [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) и API доступа к данным или ORM, например [Entity Framework Core](https://docs.microsoft.com/ef/core/index). Можно также создать [Swagger](http://swagger.io/) автоматически посредством метаданных [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) для описания возможностях службы, как описано в следующем разделе.

Обратите внимание, что запущен сервер базы данных, как SQL Server в контейнер Docker отлично подходит для сред разработки, так как все зависимости может находиться до, а без необходимости предоставления в облаке или локальной базы данных. Это очень удобно, если выполнение интеграции тестов. Однако для производственных сред, сервер базы данных в контейнер не рекомендуется, поскольку обычно не дает высокий уровень доступности такого подхода. Для производственной среды в Azure рекомендуется использовать базу данных SQL Azure или любую другую технологию базы данных, который может предоставить высокую доступность и масштабируемость, высокий уровень. Например для подход NoSQL, может выбрать DocumentDB.

Наконец, путем редактирования метаданных файлов Dockerfile и docker compose.yml, можно настроить как будет создан образ этого контейнера, какой базовый образ, он будет использовать, а также создать параметры, такие как внутренние и внешние имена и TCP-порты. 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>Реализация простого микрослужбу CRUD с ASP.NET Core

Чтобы реализовать простой микрослужбу CRUD с помощью Visual Studio и .NET Core, начинается с создания простого проекта веб-API ASP.NET Core (под управлением на основе .NET Core, он может работать на узле Linux Docker), как показано на рисунке 8-6.

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  ![](./media/image6.png)   ![](./media/image7.png)
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

**Рис. 8-6**. Создание проекта веб-API ASP.NET Core в Visual Studio

После создания проекта, вы можете реализовать ваших контроллеров MVC, как и в любой другой проект веб-API, с помощью API-Интерфейс Entity Framework или другие API. В проекте eShopOnContainers.Catalog.API видно, основные зависимости для этого микрослужбу просто ASP.NET Core сам Entity Framework и Swashbuckle, как показано на рисунке 8-7.

![](./media/image8.PNG)

**Рис. 8-7**. Зависимости в простой микрослужбу CRUD веб-API

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Реализация служб CRUD веб-API с Entity Framework Core

Core Entity Framework (EF) является упрощенным, расширяемым, и технология доступа к версии кросс платформенных популярных данных Entity Framework. EF лежит объектно реляционного сопоставления (ORM), которая позволяет разработчикам .NET для работы с базой данных с помощью объектов .NET.

Каталог микрослужбу использует EF и поставщик SQL Server, так как его база данных работает в контейнере с SQL Server для образа Linux Docker. Однако базы данных может быть развернута в любой SQL Server, например Windows в локальной или базу данных SQL Azure. Единственное, что необходимо изменить является строка подключения в микрослужбу веб-API ASP.NET.

#### <a name="add-entity-framework-core-to-your-dependencies"></a>Добавление зависимостей Entity Framework Core

Можно установить пакет NuGet для поставщика базы данных, которую вы хотите использовать, в данном случае SQL Server из в Интегрированной среде разработки Visual Studio или с помощью консоли NuGet. Используйте следующую команду:

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a>Модель данных

С основными EF доступ к данным выполняется с помощью модели. Модель состоит из классов сущностей и производных контекст, который представляет сеанс с базой данных, что позволяет запрашивать и сохранения данных. Можно создать модель на основе существующей базы данных, вручную кода модели для обеспечения соответствия базе данных или использовать миграции EF создать базу данных из модели (и его меняются при изменении модели). Для каталога микрослужбу мы используем последний подход. Можно ознакомиться с примером CatalogItem класс сущностей в следующем примере кода, является простой простой старый объект среды CLR ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) класса сущностей.

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public CatalogItem() { }
}
```

Необходимо также DbContext, который представляет сеанс с базой данных. Для каталога микрослужбу, CatalogContext класс является производным от базового класса DbContext, как показано в следующем примере:

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {
    }

    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...

}
```

Может иметь дополнительный код в реализации DbContext. Например в образце приложения, у нас есть метод OnModelCreating в классе CatalogContext, который автоматически заполняет образец данных впервые, она попытается получить доступ к базе данных. Этот метод полезен для демонстрационных данных. Можно также использовать метод OnModelCreating для настройки базы данных объекта сопоставления сущности с множество других [точек расширяемости EF](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).

Можно просмотреть дополнительные сведения о OnModelCreating в [реализации уровня инфраструктуры сохраняемости с Entity Framework Core](#implementing_infrastructure_persistence) далее в этой книге.

##### <a name="querying-data-from-web-api-controllers"></a>Запросы данных из контроллеров веб-API

Экземпляры классов сущностей обычно извлекаются из базы данных, используя интегрированные запросы языка (LINQ), как показано в следующем примере:

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService ??
           throw new ArgumentNullException(nameof(catalogIntegrationEventService));
        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
    public async Task<IActionResult> Items([FromQuery]int pageSize = 10,
    [FromQuery]int pageIndex = 0)
    {
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

Данных создается, удалить и изменить в базе данных, с помощью экземпляров классов сущностей. Можно добавить код имеет следующий вид жестко (макета данных в данном случае) к контроллерам веб-API.

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>Внедрение зависимостей в ASP.NET Core и веб-API устройства

В ASP.NET Core внедрения зависимости (DI) можно использовать без дополнительной настройки. Необходимо настроить контейнер инверсии управления (IoC) сторонних разработчиков, несмотря на то, что основной контейнер IoC может подключаться к инфраструктуре ASP.NET Core, если требуется. В этом случае это означает, что напрямую можно ввести необходимые DBContext EF или дополнительных репозиториев через конструктор контроллера. В приведенном выше примере класса CatalogController мы вводится CatalogContext тип объекта, а также других объектов через конструктор CatalogController.

Важные настройку в проект веб-API является регистрация класса DbContext в контейнер IoC службы. Это обычно выполняется в класс Startup путем вызова службы. Метод AddDbContext внутри метода ConfigureServices, как показано в следующем примере:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
           sqlOptions.
               MigrationsAssembly(
               typeof(Startup).
               GetTypeInfo().
               Assembly.
               GetName().Name);

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

-   **Запрос данных**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)

-   **Сохранение данных**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>DB соединения строки и среда переменных, используемых в контейнеры Docker

Можно использовать параметры ASP.NET Core и добавить свойство ConnectionString в файл settings.json, как показано в следующем примере:

```csharp
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

Файл settings.json может иметь значения по умолчанию для свойства ConnectionString или любого другого свойства. Тем не менее эти свойства будут переопределяться значения переменных среды, заданные в файле docker compose.override.yml.

Из файлов docker compose.yml или docker compose.override.yml можно инициализировать этих переменных среды, что Docker будет настроить их как переменные среды операционной системы, как показано в следующем файле docker compose.override.yml (соединение строки и других строк по словам в этом примере, но будет переноситься в свой собственный файл).

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    - ExternalCatalogBaseUrl=http://10.0.75.1:5101
    #- ExternalCatalogBaseUrl=http://dockerhoststaging.westus.cloudapp.azure.com:5101
  
  ports:
    - "5101:5101"
```

Файлы docker compose.yml на уровне решения не только более гибким, чем файлы конфигурации на уровне проекта или микрослужбу, но также более безопасная. Рассмотрим, не содержат образы Docker, создаваемые на микрослужбу docker-compose.yml файлы только двоичные файлы и файлы конфигурации для каждого микрослужбу, включая файл Dockerfile. Но файл docker compose.yml не устанавливается вместе с приложением; он используется только во время развертывания. Таким образом помещение значений переменных среды в этих файлах docker compose.yml (даже без шифрования значений) является более безопасны, чем размещение этих значений в обычных файлов конфигурации .NET, развернутых с помощью кода.

Наконец, можно получить это значение в коде с помощью конфигурации\[«ConnectionString»\], как показано в методе ConfigureServices в предыдущем примере кода.

Однако в рабочей среде может потребоваться обозреватель дополнительные возможности по хранению секретные данные, такие как строки подключения. Обычно, будут находиться под управлением вашей выбранной orchestrator, как с [помощью Docker Swarm управления секреты](https://docs.docker.com/engine/swarm/secrets/).

### <a name="implementing-versioning-in-aspnet-web-apis"></a>Реализация управления версиями в веб-API ASP.NET

По мере изменения бизнес-требования могут быть добавлены новые коллекции ресурсов, связи между ресурсами могут меняться и структуры данных в ресурсах может быть изменен. Обновление веб-API для обработки новых требований выполняется относительно просто, однако необходимо учитывать эффекты, которые будут иметь такие изменения в клиентские приложения, использующие веб-API. Несмотря на то, что разработчик проектирование и реализация веб-API имеет полный контроль над API-Интерфейс, разработчик имеет ту же степень контроля над клиентских приложений, которые могут быть построены сторонними организациями удаленно операционной.

Управление версиями позволяет веб-API указать компоненты и ресурсы, которые он предоставляет. Клиентское приложение затем можно отправлять запросы на определенную версию функции или ресурсов. Существует несколько подходов к реализации управления версиями.

-   Управление версиями URI

-   Управление версиями строки запроса

-   Заголовок управления версиями

Строка запроса и управление версиями URI являются наиболее простым в реализации. Заголовок управления версиями является хорошим подходом. Однако заголовок управления версиями не как явные и простой задачей, как управление версиями URI. Поскольку управление версиями URL-адрес является простейшим и наиболее явного, образец приложения eShopOnContainers использует управление версиями URI.

С управлением версиями URI, как и образец приложения eShopOnContainers каждый раз, изменить веб-API или изменить схему ресурсов, добавляемый номер версии URI для каждого ресурса. Существующие идентификаторы URI должны продолжать работать как и прежде, возвращая ресурсы, которые соответствуют схеме, которая совпадает с запрошенной версией.

Как показано в следующем примере кода, версию можно задать с помощью атрибута маршрута в веб-API, благодаря чему версии в явном виде в URI (v1 в данном случае).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

Этот механизм управления версиями является простым и зависит от сервера, маршрутизация запроса соответствующей конечной точке. Однако для более сложных версий и наиболее подходящего метода при использовании REST, следует использовать гипермедиа и реализовать [HATEOAS (Hypertext как состояние обработчика приложения)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Скотт Хансельман. Управление версиями основных RESTful веб-API ASP.NET, стало проще**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)

-   **Управление версиями RESTful веб-API**

    [*https://docs.Microsoft.com/Azure/Architecture/Best-Practices/API-Design#Versioning-a-RESTful-Web-API*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding. Управление версиями, гипермедиа и REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>Создание метаданных Swagger описание из веб-API ASP.NET Core 

[Swagger](http://swagger.io/) — framework часто используемые открытой поддерживаемый больших экосистема средства, помогающая разработки, построения, документ и использовать ваш RESTful интерфейсы API. Он становится стандарт для домена метаданных описание API-интерфейсы. Следует включить описание метаданных Swagger с любой микрослужбу микрослужбами данными или для более сложных микрослужбами на основе домена (как описано в следующем разделе).

Основа Swagger имеет спецификацию Swagger в метаданных описание API в файле JSON или YAML. Спецификации создает RESTful контракт для интерфейса API, с подробными сведениями о всех ресурсов и операций в обоих человека и machine readable формате для упрощения разработки, обнаружения и интеграции.

Спецификация является основой спецификации OpenAPI (OAS) и разработанных в сообществе откройте прозрачным и совместной работы стандартизировать определяются RESTful интерфейсы.

Спецификация определяет структуру для как можно обнаружить службы и как его возможности поняты. Дополнительные сведения, включая редактор web и примеры спецификаций Swagger из компании, например Spotify, Slack, полный и Майкрософт, см. на сайте Swagger (<http://swagger.io>).

### <a name="why-use-swagger"></a>Зачем использовать Swagger?

Ниже перечислены основных причин для создания метаданных Swagger для собственные интерфейсы API.

**Возможность для других продуктов, автоматически использовать и интегрировать собственные интерфейсы API**. Десятки продуктов и [Средства профессиональной](http://swagger.io/commercial-tools/) и много [библиотек и платформ](http://swagger.io/open-source-integrations/) поддерживает Swagger. Корпорация Майкрософт предоставляет высокоуровневый продуктов и средства, которые автоматически могут использовать API на основе Swagger, например следующие:

-   [AutoRest](https://github.com/Azure/AutoRest). Можно автоматически создать клиентские классы .NET для вызова Swagger. Это

-   средство можно использовать из CLI и она также интегрируется с Visual Studio позволяет упростить их использование через графический интерфейс пользователя.

-   [Microsoft Flow](https://flow.microsoft.com/en-us/). Вы можете автоматически [применении и интеграции API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) в Microsoft Flow рабочий процесс высокого уровня, которых не навыки программирования требуется.

-   [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/). Можно автоматически будет использовать API из [PowerApps мобильных приложений](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) с использованием [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), с, навыки программирования не требуется.

-   [Служба приложений Azure Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps). Вы можете автоматически [использовать и интеграции API в Azure приложение службы логику приложений](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), с, навыки программирования не требуется.

**Возможность автоматического создания документации по API**. При создании крупномасштабных API RESTful, например сложных приложений с микрослужбу необходимо обрабатывать много конечных точек с моделями данных, используемый в полезных данных запроса и ответа. Наличие правильной документации и необходимости сплошной обозреватель API, как вы получаете с Swagger, является ключом для успеха API и внедрения разработчиками.

Метаданные swagger — что Microsoft Flow, PowerApps и приложения логики Azure позволяет понять, как использовать API-интерфейсы и подключаться к ним.

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Автоматизация API Swagger Создание метаданных с помощью пакета Swashbuckle NuGet

Создание метаданных Swagger вручную (в файле JSON или YAML) может быть утомительным работы. Тем не менее, можно автоматизировать с помощью API обнаружение служб веб-API ASP.NET [пакет Swashbuckle NuGet](http://aka.ms/swashbuckledotnetcore) для динамического формирования Swagger API метаданных.

Swashbuckle автоматически создает метаданные Swagger для проектов веб-API ASP.NET. Он поддерживает любой разновидности, таких как приложения API Azure, мобильное приложение Azure, Azure Service Fabric микрослужбами на базе ASP.NET и веб-API ASP.NET Core проектов и традиционные веб-API ASP.NET. Оно также поддерживает развертывания в контейнерах, а в качестве заявлению простой веб-API.

Swashbuckle объединяет обозреватель API-Интерфейсов и Swagger или [пользовательского интерфейса swagger](https://github.com/swagger-api/swagger-ui) для обеспечения взаимодействия с широкие возможности обнаружения и документацию для API потребителей. В дополнение к его механизм генератора метаданных Swagger Swashbuckle также содержит встроенной версии swagger интерфейсе, он автоматически обслуживает копии после установки Swashbuckle.

Это означает, что могут дополнять API с низким приоритетом обнаружения пользовательского интерфейса, чтобы помочь разработчикам использовать API. Его требуется очень небольшой объем кода и обслуживание, так как оно создается автоматически, что позволяет сосредоточиться на построении API. Результат для обозреватель API выглядит как на рисунке 8-8.

![](./media/image9.png)

**Рис. 8-8**. Обозреватель API Swashbuckle на основе Swagger метаданных — eShopOnContainers каталога микрослужбу

Обозреватель API-Интерфейсов не самое главное здесь. При наличии веб-API, могут описывать себя в метаданных Swagger API можно использовать без проблем с помощью средств Swagger, включая генераторы кода клиентского прокси класса, предназначенных для многих платформ. Например, как упоминалось [AutoRest](https://github.com/Azure/AutoRest) автоматически создает клиентские классы .NET. Однако дополнительные средства, например [swagger codegen](https://github.com/swagger-api/swagger-codegen) доступны, которая допускает создания кода клиента API библиотеки, заглушки сервера и документация автоматически.

В настоящее время Swashbuckle состоит из двух пакетов NuGet: Swashbuckle.SwaggerGen и Swashbuckle.SwaggerUi. Первый метод предоставляет функциональные возможности для создания одного или нескольких документов Swagger непосредственно из реализации API и предоставьте их как конечные точки JSON. Предоставляет встроенной версии средство пользовательского интерфейса swagger, обслуживаемых приложения и на платформе создаваемые документы Swagger для описания API. Тем не менее последние версии Swashbuckle переносить их с Swashbuckle.AspNetCore metapackage.

Обратите внимание, что для проектов веб-API .NET Core, необходимо использовать [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) версии 1.0.0 или более поздней версии.

После установки этих пакетов NuGet в проекте веб-API, необходимо настроить Swagger в классе запуска, как показано в следующем коде:

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...
        services.AddSwaggerGen();
        services.ConfigureSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SingleApiVersion(new Swashbuckle.Swagger.Model.Info()
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API",
                TermsOfService = "eShopOnContainers terms of service"
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
            .UseSwaggerUi();
    }
}
```

После этого можно запустить приложение и перейдите следующих Swagger JSON и пользовательского интерфейса конечных точек с помощью URL-адреса, подобные этим:

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

Ранее вы видели, созданного пользовательского интерфейса, созданные Swashbuckle для URL-адреса, например, http://&lt;-корневого-URL-адрес &gt; /swagger/пользовательского интерфейса. На рисунке 8 – 9 можно выполнить как можно проверить любой метод API.

![](./media/image10.png)

**На рисунке 8 – 9**. Метод элементы каталога или API тестирования пользовательского интерфейса Swashbuckle

Рис. 8-10 показывает метаданных Swagger JSON, созданных из микрослужбу eShopOnContainers (то есть использовать средства под) при запросе &lt;-корневого-URL-адрес&gt;/swagger/v1/swagger.json с помощью [почтальон](https://www.getpostman.com/).

![](./media/image11.png)

**Рис. 8-10**. Метаданные swagger JSON

Это очень просто. И так как оно генерируется автоматически, метаданные Swagger будет увеличиваться при добавлении дополнительные функции к вашему API.

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Веб-API справки страниц ASP.NET с помощью Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)


>[!div class="step-by-step"]
[Предыдущие] (микрослужбу приложения design.md) [Далее] (несколькими-container-приложения docker-compose.md)
