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
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="ea33d-104">Создание простой микрослужбу CRUD управляемые данными</span><span class="sxs-lookup"><span data-stu-id="ea33d-104">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="ea33d-105">Этот раздел контуров как создать простой микрослужбу, которая выполняет создание, чтение, обновление и операции удаления (CRUD) в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="ea33d-105">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="ea33d-106">Разработка простого микрослужбу CRUD</span><span class="sxs-lookup"><span data-stu-id="ea33d-106">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="ea33d-107">С точки зрения проектирования этот тип контейнерного микрослужбу очень проста.</span><span class="sxs-lookup"><span data-stu-id="ea33d-107">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="ea33d-108">Возможно, проблема является простой или может быть реализован только эксперимента.</span><span class="sxs-lookup"><span data-stu-id="ea33d-108">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![](./media/image4.png)

<span data-ttu-id="ea33d-109">**Рис. 8-4**.</span><span class="sxs-lookup"><span data-stu-id="ea33d-109">**Figure 8-4**.</span></span> <span data-ttu-id="ea33d-110">Внутренняя структура простой микрослужбами CRUD</span><span class="sxs-lookup"><span data-stu-id="ea33d-110">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="ea33d-111">Пример такого рода службы простой-диск с данными — микрослужбу каталога из eShopOnContainers образца приложения.</span><span class="sxs-lookup"><span data-stu-id="ea33d-111">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="ea33d-112">Этот тип службы реализует все функции в одном проекте веб-API ASP.NET Core, которая содержит классы для своей модели данных, его бизнес-логики и его код доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="ea33d-112">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="ea33d-113">Также связанные данные хранятся в базе данных, выполняющемся на SQL Server (как в другой контейнер для целей разработки и тестирования), но также может быть любой регулярного узла SQL Server, как показано на рисунке 8-5.</span><span class="sxs-lookup"><span data-stu-id="ea33d-113">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 8-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="ea33d-114">**Рис. 8-5**.</span><span class="sxs-lookup"><span data-stu-id="ea33d-114">**Figure 8-5**.</span></span> <span data-ttu-id="ea33d-115">Простой микрослужбу данных управляемых/CRUD разработки</span><span class="sxs-lookup"><span data-stu-id="ea33d-115">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="ea33d-116">При разработке такого рода службы требуется только [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) и API доступа к данным или ORM, например [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span><span class="sxs-lookup"><span data-stu-id="ea33d-116">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="ea33d-117">Можно также создать [Swagger](http://swagger.io/) автоматически посредством метаданных [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) для описания возможностях службы, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ea33d-117">You could also generate [Swagger](http://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="ea33d-118">Обратите внимание, что запущен сервер базы данных, как SQL Server в контейнер Docker отлично подходит для сред разработки, так как все зависимости может находиться до, а без необходимости предоставления в облаке или локальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="ea33d-118">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="ea33d-119">Это очень удобно, если выполнение интеграции тестов.</span><span class="sxs-lookup"><span data-stu-id="ea33d-119">This is very convenient when running integration tests.</span></span> <span data-ttu-id="ea33d-120">Однако для производственных сред, сервер базы данных в контейнер не рекомендуется, поскольку обычно не дает высокий уровень доступности такого подхода.</span><span class="sxs-lookup"><span data-stu-id="ea33d-120">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="ea33d-121">Для производственной среды в Azure рекомендуется использовать базу данных SQL Azure или любую другую технологию базы данных, который может предоставить высокую доступность и масштабируемость, высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="ea33d-121">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="ea33d-122">Например для подход NoSQL, может выбрать DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="ea33d-122">For example, for a NoSQL approach, you might choose DocumentDB.</span></span>

<span data-ttu-id="ea33d-123">Наконец, путем редактирования метаданных файлов Dockerfile и docker compose.yml, можно настроить как будет создан образ этого контейнера, какой базовый образ, он будет использовать, а также создать параметры, такие как внутренние и внешние имена и TCP-порты.</span><span class="sxs-lookup"><span data-stu-id="ea33d-123">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span> 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="ea33d-124">Реализация простого микрослужбу CRUD с ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ea33d-124">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="ea33d-125">Чтобы реализовать простой микрослужбу CRUD с помощью Visual Studio и .NET Core, начинается с создания простого проекта веб-API ASP.NET Core (под управлением на основе .NET Core, он может работать на узле Linux Docker), как показано на рисунке 8-6.</span><span class="sxs-lookup"><span data-stu-id="ea33d-125">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 8-6.</span></span>

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  <span data-ttu-id="ea33d-126">![](./media/image6.png)   ![](./media/image7.png)</span><span class="sxs-lookup"><span data-stu-id="ea33d-126">![](./media/image6.png)   ![](./media/image7.png)</span></span>
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

<span data-ttu-id="ea33d-127">**Рис. 8-6**.</span><span class="sxs-lookup"><span data-stu-id="ea33d-127">**Figure 8-6**.</span></span> <span data-ttu-id="ea33d-128">Создание проекта веб-API ASP.NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ea33d-128">Creating an ASP.NET Core Web API project in Visual Studio</span></span>

<span data-ttu-id="ea33d-129">После создания проекта, вы можете реализовать ваших контроллеров MVC, как и в любой другой проект веб-API, с помощью API-Интерфейс Entity Framework или другие API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-129">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="ea33d-130">В проекте eShopOnContainers.Catalog.API видно, основные зависимости для этого микрослужбу просто ASP.NET Core сам Entity Framework и Swashbuckle, как показано на рисунке 8-7.</span><span class="sxs-lookup"><span data-stu-id="ea33d-130">In the eShopOnContainers.Catalog.API project, you can see that the main dependencies for that microservice are just ASP.NET Core itself, Entity Framework, and Swashbuckle, as shown in Figure 8-7.</span></span>

![](./media/image8.PNG)

<span data-ttu-id="ea33d-131">**Рис. 8-7**.</span><span class="sxs-lookup"><span data-stu-id="ea33d-131">**Figure 8-7**.</span></span> <span data-ttu-id="ea33d-132">Зависимости в простой микрослужбу CRUD веб-API</span><span class="sxs-lookup"><span data-stu-id="ea33d-132">Dependencies in a simple CRUD Web API microservice</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="ea33d-133">Реализация служб CRUD веб-API с Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="ea33d-133">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="ea33d-134">Core Entity Framework (EF) является упрощенным, расширяемым, и технология доступа к версии кросс платформенных популярных данных Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ea33d-134">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="ea33d-135">EF лежит объектно реляционного сопоставления (ORM), которая позволяет разработчикам .NET для работы с базой данных с помощью объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="ea33d-135">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="ea33d-136">Каталог микрослужбу использует EF и поставщик SQL Server, так как его база данных работает в контейнере с SQL Server для образа Linux Docker.</span><span class="sxs-lookup"><span data-stu-id="ea33d-136">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="ea33d-137">Однако базы данных может быть развернута в любой SQL Server, например Windows в локальной или базу данных SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="ea33d-137">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="ea33d-138">Единственное, что необходимо изменить является строка подключения в микрослужбу веб-API ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ea33d-138">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>

#### <a name="add-entity-framework-core-to-your-dependencies"></a><span data-ttu-id="ea33d-139">Добавление зависимостей Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="ea33d-139">Add Entity Framework Core to your dependencies</span></span>

<span data-ttu-id="ea33d-140">Можно установить пакет NuGet для поставщика базы данных, которую вы хотите использовать, в данном случае SQL Server из в Интегрированной среде разработки Visual Studio или с помощью консоли NuGet.</span><span class="sxs-lookup"><span data-stu-id="ea33d-140">You can install the NuGet package for the database provider you want to use, in this case SQL Server, from within the Visual Studio IDE or with the NuGet console.</span></span> <span data-ttu-id="ea33d-141">Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ea33d-141">Use the following command:</span></span>

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a><span data-ttu-id="ea33d-142">Модель данных</span><span class="sxs-lookup"><span data-stu-id="ea33d-142">The data model</span></span>

<span data-ttu-id="ea33d-143">С основными EF доступ к данным выполняется с помощью модели.</span><span class="sxs-lookup"><span data-stu-id="ea33d-143">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="ea33d-144">Модель состоит из классов сущностей и производных контекст, который представляет сеанс с базой данных, что позволяет запрашивать и сохранения данных.</span><span class="sxs-lookup"><span data-stu-id="ea33d-144">A model is made up of entity classes and a derived context that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="ea33d-145">Можно создать модель на основе существующей базы данных, вручную кода модели для обеспечения соответствия базе данных или использовать миграции EF создать базу данных из модели (и его меняются при изменении модели).</span><span class="sxs-lookup"><span data-stu-id="ea33d-145">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model (and evolve it as your model changes over time).</span></span> <span data-ttu-id="ea33d-146">Для каталога микрослужбу мы используем последний подход.</span><span class="sxs-lookup"><span data-stu-id="ea33d-146">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="ea33d-147">Можно ознакомиться с примером CatalogItem класс сущностей в следующем примере кода, является простой простой старый объект среды CLR ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) класса сущностей.</span><span class="sxs-lookup"><span data-stu-id="ea33d-147">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

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

<span data-ttu-id="ea33d-148">Необходимо также DbContext, который представляет сеанс с базой данных.</span><span class="sxs-lookup"><span data-stu-id="ea33d-148">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="ea33d-149">Для каталога микрослужбу, CatalogContext класс является производным от базового класса DbContext, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ea33d-149">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

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

<span data-ttu-id="ea33d-150">Может иметь дополнительный код в реализации DbContext.</span><span class="sxs-lookup"><span data-stu-id="ea33d-150">You can have additional code in the DbContext implementation.</span></span> <span data-ttu-id="ea33d-151">Например в образце приложения, у нас есть метод OnModelCreating в классе CatalogContext, который автоматически заполняет образец данных впервые, она попытается получить доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="ea33d-151">For example, in the sample application, we have an OnModelCreating method in the CatalogContext class that automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="ea33d-152">Этот метод полезен для демонстрационных данных.</span><span class="sxs-lookup"><span data-stu-id="ea33d-152">This method is useful for demo data.</span></span> <span data-ttu-id="ea33d-153">Можно также использовать метод OnModelCreating для настройки базы данных объекта сопоставления сущности с множество других [точек расширяемости EF](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span><span class="sxs-lookup"><span data-stu-id="ea33d-153">You can also use the OnModelCreating method to customize object/database entity mappings with many other [EF extensibility points](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

<span data-ttu-id="ea33d-154">Можно просмотреть дополнительные сведения о OnModelCreating в [реализации уровня инфраструктуры сохраняемости с Entity Framework Core](#implementing_infrastructure_persistence) далее в этой книге.</span><span class="sxs-lookup"><span data-stu-id="ea33d-154">You can see further details about OnModelCreating in the [Implementing the infrastructure-persistence layer with Entity Framework Core](#implementing_infrastructure_persistence) section later in this book.</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="ea33d-155">Запросы данных из контроллеров веб-API</span><span class="sxs-lookup"><span data-stu-id="ea33d-155">Querying data from Web API controllers</span></span>

<span data-ttu-id="ea33d-156">Экземпляры классов сущностей обычно извлекаются из базы данных, используя интегрированные запросы языка (LINQ), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ea33d-156">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

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

##### <a name="saving-data"></a><span data-ttu-id="ea33d-157">Сохранение данных</span><span class="sxs-lookup"><span data-stu-id="ea33d-157">Saving data</span></span>

<span data-ttu-id="ea33d-158">Данных создается, удалить и изменить в базе данных, с помощью экземпляров классов сущностей.</span><span class="sxs-lookup"><span data-stu-id="ea33d-158">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="ea33d-159">Можно добавить код имеет следующий вид жестко (макета данных в данном случае) к контроллерам веб-API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-159">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="ea33d-160">Внедрение зависимостей в ASP.NET Core и веб-API устройства</span><span class="sxs-lookup"><span data-stu-id="ea33d-160">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="ea33d-161">В ASP.NET Core внедрения зависимости (DI) можно использовать без дополнительной настройки.</span><span class="sxs-lookup"><span data-stu-id="ea33d-161">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="ea33d-162">Необходимо настроить контейнер инверсии управления (IoC) сторонних разработчиков, несмотря на то, что основной контейнер IoC может подключаться к инфраструктуре ASP.NET Core, если требуется.</span><span class="sxs-lookup"><span data-stu-id="ea33d-162">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="ea33d-163">В этом случае это означает, что напрямую можно ввести необходимые DBContext EF или дополнительных репозиториев через конструктор контроллера.</span><span class="sxs-lookup"><span data-stu-id="ea33d-163">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span> <span data-ttu-id="ea33d-164">В приведенном выше примере класса CatalogController мы вводится CatalogContext тип объекта, а также других объектов через конструктор CatalogController.</span><span class="sxs-lookup"><span data-stu-id="ea33d-164">In the example above of the CatalogController class, we are injecting an object of CatalogContext type plus other objects through the CatalogController constructor.</span></span>

<span data-ttu-id="ea33d-165">Важные настройку в проект веб-API является регистрация класса DbContext в контейнер IoC службы.</span><span class="sxs-lookup"><span data-stu-id="ea33d-165">An important configuration to set up in the Web API project is the DbContext class registration into the service’s IoC container.</span></span> <span data-ttu-id="ea33d-166">Это обычно выполняется в класс Startup путем вызова службы. Метод AddDbContext внутри метода ConfigureServices, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ea33d-166">You typically do so in the Startup class by calling the services.AddDbContext method inside the ConfigureServices method, as shown in the following example:</span></span>

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

### <a name="additional-resources"></a><span data-ttu-id="ea33d-167">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ea33d-167">Additional resources</span></span>

-   <span data-ttu-id="ea33d-168">**Запрос данных**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span><span class="sxs-lookup"><span data-stu-id="ea33d-168">**Querying Data**
[*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span></span>

-   <span data-ttu-id="ea33d-169">**Сохранение данных**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span><span class="sxs-lookup"><span data-stu-id="ea33d-169">**Saving Data**
[*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span></span>

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="ea33d-170">DB соединения строки и среда переменных, используемых в контейнеры Docker</span><span class="sxs-lookup"><span data-stu-id="ea33d-170">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="ea33d-171">Можно использовать параметры ASP.NET Core и добавить свойство ConnectionString в файл settings.json, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ea33d-171">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

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

<span data-ttu-id="ea33d-172">Файл settings.json может иметь значения по умолчанию для свойства ConnectionString или любого другого свойства.</span><span class="sxs-lookup"><span data-stu-id="ea33d-172">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="ea33d-173">Тем не менее эти свойства будут переопределяться значения переменных среды, заданные в файле docker compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="ea33d-173">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file.</span></span>

<span data-ttu-id="ea33d-174">Из файлов docker compose.yml или docker compose.override.yml можно инициализировать этих переменных среды, что Docker будет настроить их как переменные среды операционной системы, как показано в следующем файле docker compose.override.yml (соединение строки и других строк по словам в этом примере, но будет переноситься в свой собственный файл).</span><span class="sxs-lookup"><span data-stu-id="ea33d-174">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own file).</span></span>

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

<span data-ttu-id="ea33d-175">Файлы docker compose.yml на уровне решения не только более гибким, чем файлы конфигурации на уровне проекта или микрослужбу, но также более безопасная.</span><span class="sxs-lookup"><span data-stu-id="ea33d-175">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more secure.</span></span> <span data-ttu-id="ea33d-176">Рассмотрим, не содержат образы Docker, создаваемые на микрослужбу docker-compose.yml файлы только двоичные файлы и файлы конфигурации для каждого микрослужбу, включая файл Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="ea33d-176">Consider that the Docker images that you build per microservice do not contain the docker-compose.yml files, only binary files and configuration files for each microservice, including the Dockerfile.</span></span> <span data-ttu-id="ea33d-177">Но файл docker compose.yml не устанавливается вместе с приложением; он используется только во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="ea33d-177">But the docker-compose.yml file is not deployed along with your application; it is used only at deployment time.</span></span> <span data-ttu-id="ea33d-178">Таким образом помещение значений переменных среды в этих файлах docker compose.yml (даже без шифрования значений) является более безопасны, чем размещение этих значений в обычных файлов конфигурации .NET, развернутых с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="ea33d-178">Therefore, placing environment variables values in those docker-compose.yml files (even without encrypting the values) is more secure than placing those values in regular .NET configuration files that are deployed with your code.</span></span>

<span data-ttu-id="ea33d-179">Наконец, можно получить это значение в коде с помощью конфигурации\[«ConnectionString»\], как показано в методе ConfigureServices в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ea33d-179">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="ea33d-180">Однако в рабочей среде может потребоваться обозреватель дополнительные возможности по хранению секретные данные, такие как строки подключения.</span><span class="sxs-lookup"><span data-stu-id="ea33d-180">However, for production environments, you might want to explorer additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="ea33d-181">Обычно, будут находиться под управлением вашей выбранной orchestrator, как с [помощью Docker Swarm управления секреты](https://docs.docker.com/engine/swarm/secrets/).</span><span class="sxs-lookup"><span data-stu-id="ea33d-181">Usually that will be managed by your chosen orchestrator, like you can do with [Docker Swarm secrets management](https://docs.docker.com/engine/swarm/secrets/).</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="ea33d-182">Реализация управления версиями в веб-API ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ea33d-182">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="ea33d-183">По мере изменения бизнес-требования могут быть добавлены новые коллекции ресурсов, связи между ресурсами могут меняться и структуры данных в ресурсах может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="ea33d-183">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="ea33d-184">Обновление веб-API для обработки новых требований выполняется относительно просто, однако необходимо учитывать эффекты, которые будут иметь такие изменения в клиентские приложения, использующие веб-API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-184">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="ea33d-185">Несмотря на то, что разработчик проектирование и реализация веб-API имеет полный контроль над API-Интерфейс, разработчик имеет ту же степень контроля над клиентских приложений, которые могут быть построены сторонними организациями удаленно операционной.</span><span class="sxs-lookup"><span data-stu-id="ea33d-185">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="ea33d-186">Управление версиями позволяет веб-API указать компоненты и ресурсы, которые он предоставляет.</span><span class="sxs-lookup"><span data-stu-id="ea33d-186">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="ea33d-187">Клиентское приложение затем можно отправлять запросы на определенную версию функции или ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ea33d-187">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="ea33d-188">Существует несколько подходов к реализации управления версиями.</span><span class="sxs-lookup"><span data-stu-id="ea33d-188">There are several approaches to implement versioning:</span></span>

-   <span data-ttu-id="ea33d-189">Управление версиями URI</span><span class="sxs-lookup"><span data-stu-id="ea33d-189">URI versioning</span></span>

-   <span data-ttu-id="ea33d-190">Управление версиями строки запроса</span><span class="sxs-lookup"><span data-stu-id="ea33d-190">Query string versioning</span></span>

-   <span data-ttu-id="ea33d-191">Заголовок управления версиями</span><span class="sxs-lookup"><span data-stu-id="ea33d-191">Header versioning</span></span>

<span data-ttu-id="ea33d-192">Строка запроса и управление версиями URI являются наиболее простым в реализации.</span><span class="sxs-lookup"><span data-stu-id="ea33d-192">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="ea33d-193">Заголовок управления версиями является хорошим подходом.</span><span class="sxs-lookup"><span data-stu-id="ea33d-193">Header versioning is a good approach.</span></span> <span data-ttu-id="ea33d-194">Однако заголовок управления версиями не как явные и простой задачей, как управление версиями URI.</span><span class="sxs-lookup"><span data-stu-id="ea33d-194">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="ea33d-195">Поскольку управление версиями URL-адрес является простейшим и наиболее явного, образец приложения eShopOnContainers использует управление версиями URI.</span><span class="sxs-lookup"><span data-stu-id="ea33d-195">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="ea33d-196">С управлением версиями URI, как и образец приложения eShopOnContainers каждый раз, изменить веб-API или изменить схему ресурсов, добавляемый номер версии URI для каждого ресурса.</span><span class="sxs-lookup"><span data-stu-id="ea33d-196">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="ea33d-197">Существующие идентификаторы URI должны продолжать работать как и прежде, возвращая ресурсы, которые соответствуют схеме, которая совпадает с запрошенной версией.</span><span class="sxs-lookup"><span data-stu-id="ea33d-197">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="ea33d-198">Как показано в следующем примере кода, версию можно задать с помощью атрибута маршрута в веб-API, благодаря чему версии в явном виде в URI (v1 в данном случае).</span><span class="sxs-lookup"><span data-stu-id="ea33d-198">As shown in the following code example, the version can be set by using the Route attribute in the Web API, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="ea33d-199">Этот механизм управления версиями является простым и зависит от сервера, маршрутизация запроса соответствующей конечной точке.</span><span class="sxs-lookup"><span data-stu-id="ea33d-199">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="ea33d-200">Однако для более сложных версий и наиболее подходящего метода при использовании REST, следует использовать гипермедиа и реализовать [HATEOAS (Hypertext как состояние обработчика приложения)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span><span class="sxs-lookup"><span data-stu-id="ea33d-200">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ea33d-201">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ea33d-201">Additional resources</span></span>

-   <span data-ttu-id="ea33d-202">**Скотт Хансельман. Управление версиями основных RESTful веб-API ASP.NET, стало проще**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span><span class="sxs-lookup"><span data-stu-id="ea33d-202">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
[*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span></span>

-   <span data-ttu-id="ea33d-203">**Управление версиями RESTful веб-API**</span><span class="sxs-lookup"><span data-stu-id="ea33d-203">**Versioning a RESTful web API**</span></span>

    [<span data-ttu-id="ea33d-204">*https://docs.Microsoft.com/Azure/Architecture/Best-Practices/API-Design#Versioning-a-RESTful-Web-API*</span><span class="sxs-lookup"><span data-stu-id="ea33d-204">*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*</span></span>](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   <span data-ttu-id="ea33d-205">**Roy Fielding. Управление версиями, гипермедиа и REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span><span class="sxs-lookup"><span data-stu-id="ea33d-205">**Roy Fielding. Versioning, Hypermedia, and REST**
[*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span></span>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="ea33d-206">Создание метаданных Swagger описание из веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ea33d-206">Generating Swagger description metadata from your ASP.NET Core Web API</span></span> 

<span data-ttu-id="ea33d-207">[Swagger](http://swagger.io/) — framework часто используемые открытой поддерживаемый больших экосистема средства, помогающая разработки, построения, документ и использовать ваш RESTful интерфейсы API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-207">[Swagger](http://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="ea33d-208">Он становится стандарт для домена метаданных описание API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="ea33d-208">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="ea33d-209">Следует включить описание метаданных Swagger с любой микрослужбу микрослужбами данными или для более сложных микрослужбами на основе домена (как описано в следующем разделе).</span><span class="sxs-lookup"><span data-stu-id="ea33d-209">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="ea33d-210">Основа Swagger имеет спецификацию Swagger в метаданных описание API в файле JSON или YAML.</span><span class="sxs-lookup"><span data-stu-id="ea33d-210">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="ea33d-211">Спецификации создает RESTful контракт для интерфейса API, с подробными сведениями о всех ресурсов и операций в обоих человека и machine readable формате для упрощения разработки, обнаружения и интеграции.</span><span class="sxs-lookup"><span data-stu-id="ea33d-211">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="ea33d-212">Спецификация является основой спецификации OpenAPI (OAS) и разработанных в сообществе откройте прозрачным и совместной работы стандартизировать определяются RESTful интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="ea33d-212">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="ea33d-213">Спецификация определяет структуру для как можно обнаружить службы и как его возможности поняты.</span><span class="sxs-lookup"><span data-stu-id="ea33d-213">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="ea33d-214">Дополнительные сведения, включая редактор web и примеры спецификаций Swagger из компании, например Spotify, Slack, полный и Майкрософт, см. на сайте Swagger (<http://swagger.io>).</span><span class="sxs-lookup"><span data-stu-id="ea33d-214">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<http://swagger.io>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="ea33d-215">Зачем использовать Swagger?</span><span class="sxs-lookup"><span data-stu-id="ea33d-215">Why use Swagger?</span></span>

<span data-ttu-id="ea33d-216">Ниже перечислены основных причин для создания метаданных Swagger для собственные интерфейсы API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-216">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="ea33d-217">**Возможность для других продуктов, автоматически использовать и интегрировать собственные интерфейсы API**.</span><span class="sxs-lookup"><span data-stu-id="ea33d-217">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="ea33d-218">Десятки продуктов и [Средства профессиональной](http://swagger.io/commercial-tools/) и много [библиотек и платформ](http://swagger.io/open-source-integrations/) поддерживает Swagger.</span><span class="sxs-lookup"><span data-stu-id="ea33d-218">Dozens of products and [commercial tools](http://swagger.io/commercial-tools/) and many [libraries and frameworks](http://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="ea33d-219">Корпорация Майкрософт предоставляет высокоуровневый продуктов и средства, которые автоматически могут использовать API на основе Swagger, например следующие:</span><span class="sxs-lookup"><span data-stu-id="ea33d-219">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

-   <span data-ttu-id="ea33d-220">[AutoRest](https://github.com/Azure/AutoRest).</span><span class="sxs-lookup"><span data-stu-id="ea33d-220">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="ea33d-221">Можно автоматически создать клиентские классы .NET для вызова Swagger.</span><span class="sxs-lookup"><span data-stu-id="ea33d-221">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="ea33d-222">Это</span><span class="sxs-lookup"><span data-stu-id="ea33d-222">This</span></span>

-   <span data-ttu-id="ea33d-223">средство можно использовать из CLI и она также интегрируется с Visual Studio позволяет упростить их использование через графический интерфейс пользователя.</span><span class="sxs-lookup"><span data-stu-id="ea33d-223">tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

-   <span data-ttu-id="ea33d-224">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="ea33d-224">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span></span> <span data-ttu-id="ea33d-225">Вы можете автоматически [применении и интеграции API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) в Microsoft Flow рабочий процесс высокого уровня, которых не навыки программирования требуется.</span><span class="sxs-lookup"><span data-stu-id="ea33d-225">You can automatically [use and integrate your API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

-   <span data-ttu-id="ea33d-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="ea33d-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span></span> <span data-ttu-id="ea33d-227">Можно автоматически будет использовать API из [PowerApps мобильных приложений](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) с использованием [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), с, навыки программирования не требуется.</span><span class="sxs-lookup"><span data-stu-id="ea33d-227">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), with no programming skills required.</span></span>

-   <span data-ttu-id="ea33d-228">[Служба приложений Azure Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span><span class="sxs-lookup"><span data-stu-id="ea33d-228">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="ea33d-229">Вы можете автоматически [использовать и интеграции API в Azure приложение службы логику приложений](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), с, навыки программирования не требуется.</span><span class="sxs-lookup"><span data-stu-id="ea33d-229">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="ea33d-230">**Возможность автоматического создания документации по API**.</span><span class="sxs-lookup"><span data-stu-id="ea33d-230">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="ea33d-231">При создании крупномасштабных API RESTful, например сложных приложений с микрослужбу необходимо обрабатывать много конечных точек с моделями данных, используемый в полезных данных запроса и ответа.</span><span class="sxs-lookup"><span data-stu-id="ea33d-231">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="ea33d-232">Наличие правильной документации и необходимости сплошной обозреватель API, как вы получаете с Swagger, является ключом для успеха API и внедрения разработчиками.</span><span class="sxs-lookup"><span data-stu-id="ea33d-232">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="ea33d-233">Метаданные swagger — что Microsoft Flow, PowerApps и приложения логики Azure позволяет понять, как использовать API-интерфейсы и подключаться к ним.</span><span class="sxs-lookup"><span data-stu-id="ea33d-233">Swagger’s metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="ea33d-234">Автоматизация API Swagger Создание метаданных с помощью пакета Swashbuckle NuGet</span><span class="sxs-lookup"><span data-stu-id="ea33d-234">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="ea33d-235">Создание метаданных Swagger вручную (в файле JSON или YAML) может быть утомительным работы.</span><span class="sxs-lookup"><span data-stu-id="ea33d-235">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="ea33d-236">Тем не менее, можно автоматизировать с помощью API обнаружение служб веб-API ASP.NET [пакет Swashbuckle NuGet](http://aka.ms/swashbuckledotnetcore) для динамического формирования Swagger API метаданных.</span><span class="sxs-lookup"><span data-stu-id="ea33d-236">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](http://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="ea33d-237">Swashbuckle автоматически создает метаданные Swagger для проектов веб-API ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ea33d-237">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="ea33d-238">Он поддерживает любой разновидности, таких как приложения API Azure, мобильное приложение Azure, Azure Service Fabric микрослужбами на базе ASP.NET и веб-API ASP.NET Core проектов и традиционные веб-API ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ea33d-238">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="ea33d-239">Оно также поддерживает развертывания в контейнерах, а в качестве заявлению простой веб-API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-239">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="ea33d-240">Swashbuckle объединяет обозреватель API-Интерфейсов и Swagger или [пользовательского интерфейса swagger](https://github.com/swagger-api/swagger-ui) для обеспечения взаимодействия с широкие возможности обнаружения и документацию для API потребителей.</span><span class="sxs-lookup"><span data-stu-id="ea33d-240">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="ea33d-241">В дополнение к его механизм генератора метаданных Swagger Swashbuckle также содержит встроенной версии swagger интерфейсе, он автоматически обслуживает копии после установки Swashbuckle.</span><span class="sxs-lookup"><span data-stu-id="ea33d-241">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="ea33d-242">Это означает, что могут дополнять API с низким приоритетом обнаружения пользовательского интерфейса, чтобы помочь разработчикам использовать API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-242">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="ea33d-243">Его требуется очень небольшой объем кода и обслуживание, так как оно создается автоматически, что позволяет сосредоточиться на построении API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-243">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="ea33d-244">Результат для обозреватель API выглядит как на рисунке 8-8.</span><span class="sxs-lookup"><span data-stu-id="ea33d-244">The result for the API Explorer looks like Figure 8-8.</span></span>

![](./media/image9.png)

<span data-ttu-id="ea33d-245">**Рис. 8-8**.</span><span class="sxs-lookup"><span data-stu-id="ea33d-245">**Figure 8-8**.</span></span> <span data-ttu-id="ea33d-246">Обозреватель API Swashbuckle на основе Swagger метаданных — eShopOnContainers каталога микрослужбу</span><span class="sxs-lookup"><span data-stu-id="ea33d-246">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="ea33d-247">Обозреватель API-Интерфейсов не самое главное здесь.</span><span class="sxs-lookup"><span data-stu-id="ea33d-247">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="ea33d-248">При наличии веб-API, могут описывать себя в метаданных Swagger API можно использовать без проблем с помощью средств Swagger, включая генераторы кода клиентского прокси класса, предназначенных для многих платформ.</span><span class="sxs-lookup"><span data-stu-id="ea33d-248">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="ea33d-249">Например, как упоминалось [AutoRest](https://github.com/Azure/AutoRest) автоматически создает клиентские классы .NET.</span><span class="sxs-lookup"><span data-stu-id="ea33d-249">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="ea33d-250">Однако дополнительные средства, например [swagger codegen](https://github.com/swagger-api/swagger-codegen) доступны, которая допускает создания кода клиента API библиотеки, заглушки сервера и документация автоматически.</span><span class="sxs-lookup"><span data-stu-id="ea33d-250">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="ea33d-251">В настоящее время Swashbuckle состоит из двух пакетов NuGet: Swashbuckle.SwaggerGen и Swashbuckle.SwaggerUi.</span><span class="sxs-lookup"><span data-stu-id="ea33d-251">Currently, Swashbuckle consists of two NuGet packages: Swashbuckle.SwaggerGen and Swashbuckle.SwaggerUi.</span></span> <span data-ttu-id="ea33d-252">Первый метод предоставляет функциональные возможности для создания одного или нескольких документов Swagger непосредственно из реализации API и предоставьте их как конечные точки JSON.</span><span class="sxs-lookup"><span data-stu-id="ea33d-252">The former provides functionality to generate one or more Swagger documents directly from your API implementation and expose them as JSON endpoints.</span></span> <span data-ttu-id="ea33d-253">Предоставляет встроенной версии средство пользовательского интерфейса swagger, обслуживаемых приложения и на платформе создаваемые документы Swagger для описания API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-253">The latter provides an embedded version of the swagger-ui tool that can be served by your application and powered by the generated Swagger documents to describe your API.</span></span> <span data-ttu-id="ea33d-254">Тем не менее последние версии Swashbuckle переносить их с Swashbuckle.AspNetCore metapackage.</span><span class="sxs-lookup"><span data-stu-id="ea33d-254">However, the latest versions of Swashbuckle wrap these with the Swashbuckle.AspNetCore metapackage.</span></span>

<span data-ttu-id="ea33d-255">Обратите внимание, что для проектов веб-API .NET Core, необходимо использовать [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) версии 1.0.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ea33d-255">Note that for .NET Core Web API projects, you need to use [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) version 1.0.0 or later.</span></span>

<span data-ttu-id="ea33d-256">После установки этих пакетов NuGet в проекте веб-API, необходимо настроить Swagger в классе запуска, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="ea33d-256">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following code:</span></span>

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

<span data-ttu-id="ea33d-257">После этого можно запустить приложение и перейдите следующих Swagger JSON и пользовательского интерфейса конечных точек с помощью URL-адреса, подобные этим:</span><span class="sxs-lookup"><span data-stu-id="ea33d-257">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

<span data-ttu-id="ea33d-258">Ранее вы видели, созданного пользовательского интерфейса, созданные Swashbuckle для URL-адреса, например, http://&lt;-корневого-URL-адрес &gt; /swagger/пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ea33d-258">You previously saw the generated UI created by Swashbuckle for a URL like http://&lt;your-root-url&gt;/swagger/ui.</span></span> <span data-ttu-id="ea33d-259">На рисунке 8 – 9 можно выполнить как можно проверить любой метод API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-259">In Figure 8-9 you can also see how you can test any API method.</span></span>

![](./media/image10.png)

<span data-ttu-id="ea33d-260">**На рисунке 8 – 9**.</span><span class="sxs-lookup"><span data-stu-id="ea33d-260">**Figure 8-9**.</span></span> <span data-ttu-id="ea33d-261">Метод элементы каталога или API тестирования пользовательского интерфейса Swashbuckle</span><span class="sxs-lookup"><span data-stu-id="ea33d-261">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="ea33d-262">Рис. 8-10 показывает метаданных Swagger JSON, созданных из микрослужбу eShopOnContainers (то есть использовать средства под) при запросе &lt;-корневого-URL-адрес&gt;/swagger/v1/swagger.json с помощью [почтальон](https://www.getpostman.com/).</span><span class="sxs-lookup"><span data-stu-id="ea33d-262">Figure 8-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request &lt;your-root-url&gt;/swagger/v1/swagger.json using [Postman](https://www.getpostman.com/).</span></span>

![](./media/image11.png)

<span data-ttu-id="ea33d-263">**Рис. 8-10**.</span><span class="sxs-lookup"><span data-stu-id="ea33d-263">**Figure 8-10**.</span></span> <span data-ttu-id="ea33d-264">Метаданные swagger JSON</span><span class="sxs-lookup"><span data-stu-id="ea33d-264">Swagger JSON metadata</span></span>

<span data-ttu-id="ea33d-265">Это очень просто.</span><span class="sxs-lookup"><span data-stu-id="ea33d-265">It is that simple.</span></span> <span data-ttu-id="ea33d-266">И так как оно генерируется автоматически, метаданные Swagger будет увеличиваться при добавлении дополнительные функции к вашему API.</span><span class="sxs-lookup"><span data-stu-id="ea33d-266">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ea33d-267">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ea33d-267">Additional resources</span></span>

-   <span data-ttu-id="ea33d-268">**Веб-API справки страниц ASP.NET с помощью Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span><span class="sxs-lookup"><span data-stu-id="ea33d-268">**ASP.NET Web API Help Pages using Swagger**
[*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ea33d-269">[Предыдущие] (микрослужбу приложения design.md) [Далее] (несколькими-container-приложения docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="ea33d-269">[Previous] (microservice-application-design.md) [Next] (multi-container-applications-docker-compose.md)</span></span>
