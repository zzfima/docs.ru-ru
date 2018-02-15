---
title: "Работа с данными в приложениях ASP.NET Core"
description: "Архитектора современных веб-приложений с помощью ASP.NET Core и Azure | Работа с данными в среде asp"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 648e0a4cdd388cf4a322f0fc049d5dcfca53d54b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="cb0df-103">Работа с данными в приложениях ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cb0df-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="cb0df-104">«Данные ценное вещь и будут сохраняться дольше, чем самих систем.»</span><span class="sxs-lookup"><span data-stu-id="cb0df-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>

<span data-ttu-id="cb0df-105">Тим Бернерса ли</span><span class="sxs-lookup"><span data-stu-id="cb0df-105">Tim Berners-Lee</span></span>

## <a name="summary"></a><span data-ttu-id="cb0df-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="cb0df-106">Summary</span></span>

<span data-ttu-id="cb0df-107">Доступ к данным является важной частью почти любого приложения программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="cb0df-107">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="cb0df-108">ASP.NET Core поддерживает разнообразные параметры доступа к данным, включая Entity Framework Core (а также Entity Framework 6), а также может работать с любой платформы .NET framework доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="cb0df-108">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="cb0df-109">Выбор, из которых доступ к данным инфраструктуре использовать зависит от потребностей приложения.</span><span class="sxs-lookup"><span data-stu-id="cb0df-109">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="cb0df-110">Абстрагирование варианты из проектов ApplicationCore и пользовательского интерфейса и инкапсуляции деталей реализации инфраструктуры, помогает в построении слабосвязанной, тестируемыми программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="cb0df-110">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="cb0df-111">Entity Framework Core (для реляционных баз данных)</span><span class="sxs-lookup"><span data-stu-id="cb0df-111">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="cb0df-112">При написании нового приложения ASP.NET Core, которое требуется для работы с реляционными данными основного Entity Framework (EF ядро) является рекомендуемым способом для вашего приложения, на доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="cb0df-112">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="cb0df-113">EF лежит объектно реляционного сопоставления (O/надежный обмен Сообщениями), которая позволяет разработчикам .NET для сохранения объектов из источника данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-113">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="cb0df-114">Это устраняет потребность в большую часть кода доступа к данным, которые разработчикам обычно приходится писать.</span><span class="sxs-lookup"><span data-stu-id="cb0df-114">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="cb0df-115">Как ASP.NET Core EF Core был переписан с нуля и обеспечивает поддержку модульных кросс платформенных приложений.</span><span class="sxs-lookup"><span data-stu-id="cb0df-115">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="cb0df-116">Добавление приложения как пакет NuGet, настроить их запуска и запрос через внедрения зависимостей, везде, где он нужен.</span><span class="sxs-lookup"><span data-stu-id="cb0df-116">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="cb0df-117">Чтобы использовать EF ядра базы данных SQL Server, выполните следующую команду CLI dotnet:</span><span class="sxs-lookup"><span data-stu-id="cb0df-117">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

<span data-ttu-id="cb0df-118">DotNet добавить пакет Microsoft.EntityFrameworkCore.SqlServer</span><span class="sxs-lookup"><span data-stu-id="cb0df-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span></span>

<span data-ttu-id="cb0df-119">Чтобы добавить поддержку для источника данных InMemory для тестирования:</span><span class="sxs-lookup"><span data-stu-id="cb0df-119">To add support for an InMemory data source, for testing:</span></span>

<span data-ttu-id="cb0df-120">DotNet добавить пакет Microsoft.EntityFrameworkCore.InMemory</span><span class="sxs-lookup"><span data-stu-id="cb0df-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span></span>

### <a name="the-dbcontext"></a><span data-ttu-id="cb0df-121">Класс DbContext</span><span class="sxs-lookup"><span data-stu-id="cb0df-121">The DbContext</span></span>

<span data-ttu-id="cb0df-122">Для работы с основными EF требуется подкласс DbContext.</span><span class="sxs-lookup"><span data-stu-id="cb0df-122">To work with EF Core, you need a subclass of DbContext.</span></span> <span data-ttu-id="cb0df-123">Этот класс содержит свойства, представляющие сущности, которые приложение будет работать с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="cb0df-123">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="cb0df-124">Пример eShopOnWeb включает CatalogContext с коллекциями элементов, торговые марки и типы:</span><span class="sxs-lookup"><span data-stu-id="cb0df-124">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {

    }

    public DbSet<CatalogItem> CatalogItems { get; set; }

    public DbSet<CatalogBrand> CatalogBrands { get; set; }

    public DbSet<CatalogType> CatalogTypes { get; set; }
}
```

<span data-ttu-id="cb0df-125">Ваш DbContext должен иметь конструктор, принимающий DbContextOptions и передать этот аргумент конструктора базового класса DbContext.</span><span class="sxs-lookup"><span data-stu-id="cb0df-125">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="cb0df-126">Обратите внимание, что если в приложении имеется только один DbContext, можно передать экземпляр DbContextOptions, но при наличии более одного необходимо использовать универсальный DbContextOptions<T> типа, передавая ему в типе DbContext как универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="cb0df-126">Note that if you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="cb0df-127">Настройка основных EF</span><span class="sxs-lookup"><span data-stu-id="cb0df-127">Configuring EF Core</span></span>

<span data-ttu-id="cb0df-128">В приложении ASP.NET Core будет обычно настраивается в методе ConfigureServices EF Core.</span><span class="sxs-lookup"><span data-stu-id="cb0df-128">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="cb0df-129">EF Core использует DbContextOptionsBuilder, которая поддерживает несколько методов расширения полезны для упрощения его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cb0df-129">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="cb0df-130">Чтобы настроить CatalogContext использовать базу данных SQL Server со строкой соединения, определенные в конфигурации, необходимо добавить следующий код в ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="cb0df-130">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="cb0df-131">Чтобы использовать базу данных в памяти:</span><span class="sxs-lookup"><span data-stu-id="cb0df-131">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="cb0df-132">После установки основных компонентов EF, дочерний тип DbContext, созданные и настройки ее в ConfigureServices вы готовы использовать EF Core.</span><span class="sxs-lookup"><span data-stu-id="cb0df-132">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="cb0df-133">Вы можете запросить экземпляр типа DbContext в любой службе, в зависимости от необходимости и приступить к работе с сохраненного сущностей с помощью LINQ, как если бы они просто в коллекции.</span><span class="sxs-lookup"><span data-stu-id="cb0df-133">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="cb0df-134">Основные EF не преобразования выражения LINQ в SQL-запросы для хранения и извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-134">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="cb0df-135">Вы увидите запросы EF Core выполняется путем настройки ведения журнала и обеспечение его уровень равен по крайней мере сведения, как показано на рисунке 8-1.</span><span class="sxs-lookup"><span data-stu-id="cb0df-135">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![](./media/image8-1.png)

<span data-ttu-id="cb0df-136">Рис. 8-1 Core EF ведение журнала запросов на консоль</span><span class="sxs-lookup"><span data-stu-id="cb0df-136">Figure 8-1 Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="cb0df-137">Извлечение и сохранение данных</span><span class="sxs-lookup"><span data-stu-id="cb0df-137">Fetching and Storing Data</span></span>

<span data-ttu-id="cb0df-138">Для получения данных из основных компонентов EF, доступ к соответствующему свойству и использовать LINQ для фильтрации результирующего.</span><span class="sxs-lookup"><span data-stu-id="cb0df-138">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="cb0df-139">Также можно использовать LINQ для выполнения проекции, преобразования результата из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="cb0df-139">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="cb0df-140">Следующий пример может извлечь CatalogBrands, упорядоченные по имени, отфильтрованные по их свойства Enabled и проецируются типа SelectListItem:</span><span class="sxs-lookup"><span data-stu-id="cb0df-140">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="cb0df-141">Очень важно в приведенном выше примере, чтобы добавить вызов ToListAsync, чтобы выполнить запрос немедленно.</span><span class="sxs-lookup"><span data-stu-id="cb0df-141">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="cb0df-142">В противном случае инструкция будет назначать тип IQueryable<SelectListItem> для brandItems, который не будет выполняться до выполнения перечисления.</span><span class="sxs-lookup"><span data-stu-id="cb0df-142">Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="cb0df-143">Есть свои преимущества и недостатки, чтобы возвращать результаты IQueryable из методов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-143">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="cb0df-144">Она позволяет ранее EF основные конструкции быть изменен, но можно также приводят к ошибкам, возникающие только во время выполнения, если операции добавляются в запрос, который EF Core не удается преобразовать запрос.</span><span class="sxs-lookup"><span data-stu-id="cb0df-144">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="cb0df-145">Обычно безопаснее для передачи все фильтры в метод, получение доступа к данным и возврата резервное коллекции в памяти (например, список<T>) в результате.</span><span class="sxs-lookup"><span data-stu-id="cb0df-145">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.</span></span>

<span data-ttu-id="cb0df-146">EF ядра отслеживает изменения на сущности, которые извлекаются из хранилища сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="cb0df-146">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="cb0df-147">Чтобы сохранить изменения Отслеживаемая сущность, просто вызовите метод SaveChanges ликвидацию, убедившись, что это тот же экземпляр DbContext, который был использован для получения сущности.</span><span class="sxs-lookup"><span data-stu-id="cb0df-147">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="cb0df-148">Добавление и удаление сущностей — непосредственно на соответствующее свойство DbSet, снова с помощью вызова SaveChanges для выполнения команд базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-148">Adding and removing entities is directly on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="cb0df-149">В следующем примере показано добавление, обновление и удаление сущностей из хранилища сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="cb0df-149">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

```csharp
// create
var newBrand = new CatalogBrand() { Brand = "Acme" };
_context.Add(newBrand);
await _context.SaveChangesAsync();

// read and update
var existingBrand = _context.CatalogBrands.Find(1);
existingBrand.Brand = "Updated Brand";
await _context.SaveChangesAsync();

// read and delete (alternate Find syntax)
var brandToDelete = _context.Find<CatalogBrand>(2);
_context.CatalogBrands.Remove(brandToDelete);
await _context.SaveChangesAsync();
```

<span data-ttu-id="cb0df-150">EF Core поддерживает как синхронные, так и асинхронные методы для получения и сохранения.</span><span class="sxs-lookup"><span data-stu-id="cb0df-150">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="cb0df-151">В веб-приложений рекомендуется использовать шаблон async/await с асинхронными методами, чтобы потоки веб-сервера не блокируются при ожидании завершения операций доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="cb0df-151">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="cb0df-152">Извлечение связанных данных</span><span class="sxs-lookup"><span data-stu-id="cb0df-152">Fetching Related Data</span></span>

<span data-ttu-id="cb0df-153">Когда EF Core извлекает сущности, он заполняет все свойства, которые хранятся непосредственно с этой сущностью в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-153">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="cb0df-154">Свойства навигации, таких как списки связанных сущностей не заполнены и, возможно, их значение равно null.</span><span class="sxs-lookup"><span data-stu-id="cb0df-154">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="cb0df-155">Это гарантирует, что основные EF не извлекает больше данных, чем требуется, что особенно важно для веб-приложений, которые необходимо быстро обрабатывать запросы и возвращать ответы эффективное.</span><span class="sxs-lookup"><span data-stu-id="cb0df-155">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="cb0df-156">Для включения связей с сущности, используя *упреждающую*, укажите свойства с помощью метода расширения Include в запросе, как показано:</span><span class="sxs-lookup"><span data-stu-id="cb0df-156">To include relationships with an entity using *eager loading*, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="cb0df-157">Можно включить несколько связей, и может также включать вложенные связи с помощью ThenInclude.</span><span class="sxs-lookup"><span data-stu-id="cb0df-157">You can include multiple relationships, and you can also include sub-relationships using ThenInclude.</span></span> <span data-ttu-id="cb0df-158">EF Core будет выполнить один запрос для получения результирующего набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="cb0df-158">EF Core will execute a single query to retrieve the resulting set of entities.</span></span>

<span data-ttu-id="cb0df-159">Загрузка связанных данных другой вариант — использовать *явная загрузка*.</span><span class="sxs-lookup"><span data-stu-id="cb0df-159">Another option for loading related data is to use *explicit loading*.</span></span> <span data-ttu-id="cb0df-160">Явная загрузка позволяет загрузить дополнительные данные в сущность, которая уже было получено.</span><span class="sxs-lookup"><span data-stu-id="cb0df-160">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="cb0df-161">Когда речь заходит о отдельный запрос к базе данных, не рекомендуется для веб-приложений, которые следует свести к минимуму количество базы данных циклов приема-передачи внесены по запросу.</span><span class="sxs-lookup"><span data-stu-id="cb0df-161">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="cb0df-162">*Отложенная загрузка* — это компонент, который автоматически загружает связанные данные, как оно ссылается приложение.</span><span class="sxs-lookup"><span data-stu-id="cb0df-162">*Lazy loading* is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="cb0df-163">В настоящее время не поддерживается ядром EF, но как с явная загрузка его следует обычно отключить для веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="cb0df-163">It's not currently supported by EF Core, but as with explicit loading it should typically be disabled for web applications.</span></span>

### <a name="resilient-connections"></a><span data-ttu-id="cb0df-164">Отказоустойчивое подключений</span><span class="sxs-lookup"><span data-stu-id="cb0df-164">Resilient Connections</span></span>

<span data-ttu-id="cb0df-165">Внешние ресурсы, такие как базы данных SQL, иногда могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="cb0df-165">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="cb0df-166">В случаях временной недоступности приложения могут использовать логику повторных попыток, чтобы избежать возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="cb0df-166">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="cb0df-167">Этот метод часто называют *устойчивость подключений*.</span><span class="sxs-lookup"><span data-stu-id="cb0df-167">This technique is commonly referred to as *connection resiliency*.</span></span> <span data-ttu-id="cb0df-168">Можно реализовать вашей [собственные повторить с экспоненциально растущим](https://docs.microsoft.com/azure/architecture/patterns/retry) прием, пытаясь этом с экспоненциально увеличивающейся время ожидания, пока не будет достигнуто максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="cb0df-168">You can implement your [own retry with exponential backoff](https://docs.microsoft.com/azure/architecture/patterns/retry) technique by attempting to rety with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="cb0df-169">Этот метод выполняет тот факт, что облачные ресурсы периодически недоступен в течение короткого времени, что привело к сбою некоторых запросов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-169">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="cb0df-170">Для баз данных SQL Azure Entity Framework Core уже предоставляет логику устойчивости и повторите попытку подключения внутренней базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-170">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="cb0df-171">Однако необходимо включить стратегия выполнения Entity Framework для каждого соединения DbContext, если должны быть устойчивыми EF основных подключений.</span><span class="sxs-lookup"><span data-stu-id="cb0df-171">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="cb0df-172">Для экземпляра приведенный ниже код на уровне ядра EF соединения позволяет отказоустойчивой соединения SQL, выполняется повторная попытка добавления при сбое соединения.</span><span class="sxs-lookup"><span data-stu-id="cb0df-172">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        //...
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
```

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="cb0df-173">Выполнение стратегии и явные транзакции, используя BeginTransaction и несколько DbContexts</span><span class="sxs-lookup"><span data-stu-id="cb0df-173">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span> 
  
  <span data-ttu-id="cb0df-174">После включения повторных попыток подключений EF Core каждой операции, выполненные с помощью EF Core становится повторимый операции.</span><span class="sxs-lookup"><span data-stu-id="cb0df-174">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="cb0df-175">Каждый запрос и каждый вызов команды SaveChanges в случае временного сбоя будет повторена как единое целое.</span><span class="sxs-lookup"><span data-stu-id="cb0df-175">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>
  
  <span data-ttu-id="cb0df-176">Тем не менее, если код инициирует транзакцию, используя BeginTransaction, вы определяете собственную группу операций, которые должны рассматриваться как единое целое, весь код внутри транзакции выполнен откат в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="cb0df-176">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="cb0df-177">При попытке выполнения этой транзакции, при использовании стратегия выполнения EF (политику повтора) и включать несколько SaveChanges из нескольких DbContexts в нем вы увидите исключение следующим образом.</span><span class="sxs-lookup"><span data-stu-id="cb0df-177">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="cb0df-178">System.InvalidOperationException: Настроенная стратегия выполнения «SqlServerRetryingExecutionStrategy» не поддерживает транзакции, инициированной пользователем.</span><span class="sxs-lookup"><span data-stu-id="cb0df-178">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="cb0df-179">Используйте возвращенный «DbContext.Database.CreateExecutionStrategy()» стратегии выполнения для выполнения всех операций в транзакции как единое возможностью повторной попытки.</span><span class="sxs-lookup"><span data-stu-id="cb0df-179">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="cb0df-180">Решением является вызвать стратегия выполнения EF отражающее все делегатом, который должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="cb0df-180">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="cb0df-181">В случае временного сбоя стратегия выполнения будет снова вызвать делегата.</span><span class="sxs-lookup"><span data-stu-id="cb0df-181">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="cb0df-182">Следующий код показывает, как реализовать этот подход:</span><span class="sxs-lookup"><span data-stu-id="cb0df-182">The following code shows how to implement this approach:</span></span>

```csharp
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
```

<span data-ttu-id="cb0df-183">— Первый DbContext \_catalogContext, а второй — DbContext находится в пределах \_integrationEventLogService объекта.</span><span class="sxs-lookup"><span data-stu-id="cb0df-183">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="cb0df-184">Наконец фиксации, будет указано действие выполнить несколько DbContexts и с помощью EF стратегия выполнения.</span><span class="sxs-lookup"><span data-stu-id="cb0df-184">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="cb0df-185">Ссылки — Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="cb0df-185">References – Entity Framework Core</span></span>
> - <span data-ttu-id="cb0df-186">**EF базовые документы**</span><span class="sxs-lookup"><span data-stu-id="cb0df-186">**EF Core Docs**</span></span>  
> <span data-ttu-id="cb0df-187"><https://docs.microsoft.com/ef/></span><span class="sxs-lookup"><span data-stu-id="cb0df-187"><https://docs.microsoft.com/ef/></span></span>
> - <span data-ttu-id="cb0df-188">**EF ядром: Связанные данные**</span><span class="sxs-lookup"><span data-stu-id="cb0df-188">**EF Core: Related Data**</span></span>  
> <span data-ttu-id="cb0df-189"><https://docs.microsoft.com/ef/core/querying/related-data></span><span class="sxs-lookup"><span data-stu-id="cb0df-189"><https://docs.microsoft.com/ef/core/querying/related-data></span></span>
> - <span data-ttu-id="cb0df-190">**Избегайте отложенную загрузку сущностей в приложениях ASPNET**</span><span class="sxs-lookup"><span data-stu-id="cb0df-190">**Avoid Lazy Loading Entities in ASPNET Applications**</span></span>  
> <span data-ttu-id="cb0df-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span><span class="sxs-lookup"><span data-stu-id="cb0df-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span></span>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="cb0df-192">EF Core или микро ORM?</span><span class="sxs-lookup"><span data-stu-id="cb0df-192">EF Core or micro-ORM?</span></span>

<span data-ttu-id="cb0df-193">Пока EF Core отлично подходит для управления сохраняемости и в большинстве случаев инкапсулирует сведения о базе данных от разработчиков приложения, не является единственным вариантом.</span><span class="sxs-lookup"><span data-stu-id="cb0df-193">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it is not the only choice.</span></span> <span data-ttu-id="cb0df-194">Другой вариант с открытым исходным кодом — [Dapper](https://github.com/StackExchange/Dapper), так называемые микро ORM.</span><span class="sxs-lookup"><span data-stu-id="cb0df-194">Another popular open source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="cb0df-195">Микро ORM является упрощенным, менее полнофункциональное средство для сопоставления объектов структуры данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-195">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="cb0df-196">В случае Dapper его макет целей акцент на производительность, вместо полностью инкапсуляции базового отправляет запрос используется для извлечения и обновления данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-196">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="cb0df-197">Так как он не абстрактного SQL от разработчика, Dapper «ближе к металл» и позволяет разработчику писать точное запросов, которые они хотят использовать для заданных данных получить доступ к операции.</span><span class="sxs-lookup"><span data-stu-id="cb0df-197">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="cb0df-198">Ядро EF имеет два важных функций, которые он предоставляет, который отделяет его от Dapper, но также добавить к снижению его производительности.</span><span class="sxs-lookup"><span data-stu-id="cb0df-198">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="cb0df-199">Во-первых, перевод из выражения LINQ в SQL.</span><span class="sxs-lookup"><span data-stu-id="cb0df-199">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="cb0df-200">Кэшируются этих переводов, но тем не менее имеется дополнительная нагрузка в их выполнения в первый раз.</span><span class="sxs-lookup"><span data-stu-id="cb0df-200">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="cb0df-201">Второе — отслеживание изменений для сущности (при этом могут создаваться инструкций update эффективный).</span><span class="sxs-lookup"><span data-stu-id="cb0df-201">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="cb0df-202">Это поведение можно отключить для конкретных запросов с использованием модуля AsNotTracking.</span><span class="sxs-lookup"><span data-stu-id="cb0df-202">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="cb0df-203">EF Core также приводит к возникновению ошибки SQL-запросов, которые обычно являются очень эффективно и в любом случае оптимальным с точки зрения производительности, но если необходимы точный контроль над точное запросов для выполнения, можно передать в пользовательских SQL (или выполнения хранимой процедуры) с помощью EF Базовая, слишком.</span><span class="sxs-lookup"><span data-stu-id="cb0df-203">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="cb0df-204">В этом случае Dapper по-прежнему превышает производительность EF Core, но лишь незначительно.</span><span class="sxs-lookup"><span data-stu-id="cb0df-204">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="cb0df-205">Некоторые данные производительности в нее могут статьи MSDN 2016 представляется Джули Лерман [Dapper, Entity Framework и гибридные приложения](https://msdn.microsoft.com/magazine/mt703432.aspx).</span><span class="sxs-lookup"><span data-stu-id="cb0df-205">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span></span> <span data-ttu-id="cb0df-206">Тестовые данные производительности для различных методов доступа к данным можно найти на [Dapper сайта](https://github.com/StackExchange/Dapper).</span><span class="sxs-lookup"><span data-stu-id="cb0df-206">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="cb0df-207">Чтобы увидеть, как синтаксис Dapper зависит от основных EF, рассмотрим эти две версии тот же метод для извлечения списка элементов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-207">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

```csharp
// EF Core
private readonly CatalogContext _context;
public async Task<IEnumerable<CatalogType>> GetCatalogTypes()
{
    return await _context.CatalogTypes.ToListAsync();
}

// Dapper
private readonly SqlConnection _conn;
public async Task<IEnumerable<CatalogType>> GetCatalogTypesWithDapper()
{
    return await _conn.QueryAsync<CatalogType>("SELECT * FROM CatalogType");
}
```

<span data-ttu-id="cb0df-208">Если необходимы для создания более сложных графов объектов с Dapper, необходимо написать связанные запросы самостоятельно (в отличие от Добавление метода Include, как и в основной EF).</span><span class="sxs-lookup"><span data-stu-id="cb0df-208">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="cb0df-209">Эта возможность поддерживается через разнообразные синтаксисов, включая называемую Multi сопоставление, позволяет сопоставить отдельных строк на несколько сопоставленных объектов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-209">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="cb0df-210">Например имеется класс Post со свойством владельца типа пользователя, следующий запрос SQL вернет все необходимые данные:</span><span class="sxs-lookup"><span data-stu-id="cb0df-210">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="cb0df-211">Каждой возвращаемой строке включает данные пользователя и Post.</span><span class="sxs-lookup"><span data-stu-id="cb0df-211">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="cb0df-212">Так как данные пользователя должны быть присоединены к данные Post через свойство владельца, используются следующие функции:</span><span class="sxs-lookup"><span data-stu-id="cb0df-212">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="cb0df-213">Полный листинг кода для возврата коллекции записей с их владельца, свойство заполняется данными пользователя будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="cb0df-213">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="cb0df-214">Так как он предоставляет меньше инкапсуляции, Dapper требует разработчикам Дополнительные сведения о их хранения, как выполнить запрос он эффективно и написать дополнительный код для извлечения их.</span><span class="sxs-lookup"><span data-stu-id="cb0df-214">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="cb0df-215">При изменении модели, а не просто создание новой миграции (другой функцией EF Core) и/или обновление сведений о сопоставлении в одном месте в DbContext, каждый запрос, это повлияет на необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="cb0df-215">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="cb0df-216">Эти запросы имеют не гарантирует времени компиляции, поэтому они могут разрываться во время выполнения в ответ на изменения, для модели или базы данных, позволяя быстро обнаружить ошибки.</span><span class="sxs-lookup"><span data-stu-id="cb0df-216">These queries have not compile time guarantees, so they may break at runtime in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="cb0df-217">Обмен эти варианты Dapper обеспечивает очень высокую производительность.</span><span class="sxs-lookup"><span data-stu-id="cb0df-217">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="cb0df-218">Для большинства приложений и большинство части практически все приложения основные EF предлагает приемлемой производительности.</span><span class="sxs-lookup"><span data-stu-id="cb0df-218">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="cb0df-219">Таким образом его преимущества производительности разработчика, скорее всего перевешивают затраты на его производительности.</span><span class="sxs-lookup"><span data-stu-id="cb0df-219">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="cb0df-220">Для запросов, которые могут использовать преимущества кэширования, фактически имеющегося запроса может быть выполнена только маленький процент времени, делая относительно небольшой запрос бессмысленными различия в производительности.</span><span class="sxs-lookup"><span data-stu-id="cb0df-220">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="cb0df-221">SQL или отличные от SQL</span><span class="sxs-lookup"><span data-stu-id="cb0df-221">SQL or NoSQL</span></span>

<span data-ttu-id="cb0df-222">В большинстве случаев реляционных баз данных, как SQL Server подчиненную marketplace для хранения постоянных данных, но они не являются единственным решением.</span><span class="sxs-lookup"><span data-stu-id="cb0df-222">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="cb0df-223">Баз данных NoSQL, таких как [MongoDB](https://www.mongodb.com/what-is-mongodb) реализует другой подход для хранения объектов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-223">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="cb0df-224">Вместо того чтобы сопоставление объектов и таблиц и строк, другой вариант — для сериализации всего графа объекта и сохранить результат.</span><span class="sxs-lookup"><span data-stu-id="cb0df-224">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="cb0df-225">Преимущества этого подхода по крайней мере первоначально, простоты и производительности.</span><span class="sxs-lookup"><span data-stu-id="cb0df-225">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="cb0df-226">Наверняка проще хранить один сериализованный объект с ключом, чем Чтобы разбить объект на множество таблиц со связями и update и строки, которые могли измениться с момента последнего объекта, полученные из базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-226">It's certainly simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="cb0df-227">Аналогично получения и десериализации объекта из хранилища на основе ключей обычно намного быстрее и проще, чем сложные соединения или несколько запросов к базе данных необходимо полностью создать один и тот же объект из реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-227">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="cb0df-228">Отсутствие блокировки или транзакции и фиксированную схему также делает очень хорошо оптимизируются для масштабирования на многих компьютерах поддержки очень больших наборов данных баз данных NoSQL.</span><span class="sxs-lookup"><span data-stu-id="cb0df-228">The lack of locks or transactions or a fixed schema also makes NoSQL databases very amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="cb0df-229">С другой стороны базах данных NoSQL (как обычно они называются) имеет свои недостатки.</span><span class="sxs-lookup"><span data-stu-id="cb0df-229">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="cb0df-230">Реляционные базы данных позволяет обеспечивать согласованность и избежать дублирования данных нормализации.</span><span class="sxs-lookup"><span data-stu-id="cb0df-230">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="cb0df-231">Это уменьшает общий размер базы данных и гарантирует, что обновления для общих данных будут доступны немедленно во всей базе данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-231">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="cb0df-232">В реляционной базе данных адрес может ссылаться таблица таблица Country по Идентификатору, таким образом, если название страны или были изменены, записи адресов получают преимущества от обновления без сами необходимости в обновлении.</span><span class="sxs-lookup"><span data-stu-id="cb0df-232">In a relational database, an Address table might reference a Country table by ID, such that if a country's name were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="cb0df-233">Тем не менее в базе данных NoSQL, адрес и его связанные страны могут быть сериализованы в процессе хранимых объектов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-233">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="cb0df-234">Обновление название страны потребуется таких объектов, необходимо обновить, а не одной строки.</span><span class="sxs-lookup"><span data-stu-id="cb0df-234">An update to a country name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="cb0df-235">Реляционные базы данных также может гарантировать реляционной целостности путем применения правил, например внешние ключи.</span><span class="sxs-lookup"><span data-stu-id="cb0df-235">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="cb0df-236">Баз данных NoSQL обычно имеют такие ограничения на использование данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-236">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="cb0df-237">Другой сложность базы данных приходится иметь дело с NoSQL — управление версиями.</span><span class="sxs-lookup"><span data-stu-id="cb0df-237">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="cb0df-238">При изменении свойств объекта, он может невозможно десериализовать из предыдущих версий, которые были сохранены.</span><span class="sxs-lookup"><span data-stu-id="cb0df-238">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="cb0df-239">Таким образом все существующие объекты, имеющие сериализованная (предыдущая) версия объекта необходимо обновить для обеспечения соответствия новой схемы.</span><span class="sxs-lookup"><span data-stu-id="cb0df-239">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="cb0df-240">Это не принципиально отличается от реляционной базы данных, где иногда изменения схемы требуется обновление скриптов, или сопоставление обновления.</span><span class="sxs-lookup"><span data-stu-id="cb0df-240">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="cb0df-241">Однако количество записей, которые необходимо изменить, чаще всего гораздо больше подход NoSQL, так как имеется несколько дублирования данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-241">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="cb0df-242">Это возможно в базах данных NoSQL для хранения нескольких версий объектов, что-нибудь Фиксированная схема реляционной базы данных обычно не поддерживают.</span><span class="sxs-lookup"><span data-stu-id="cb0df-242">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="cb0df-243">Однако в этом случае код вашего приложения будет должны учитывать наличие предыдущей версии объектов, дополнительные сложности.</span><span class="sxs-lookup"><span data-stu-id="cb0df-243">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="cb0df-244">Баз данных NoSQL обычно не выполняют [ACID](http://en.wikipedia.org/wiki/ACID), что означает, что они имеют преимущества производительности и масштабируемости реляционных баз данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-244">NoSQL databases typically do not enforce [ACID](http://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="cb0df-245">Они подходят для очень больших наборов данных и объекты, которые не подходят для хранения в структурах нормализованной таблицы.</span><span class="sxs-lookup"><span data-stu-id="cb0df-245">They're well-suited to extremely large datasets and objects that are not well-suited to storage in normalized table structures.</span></span> <span data-ttu-id="cb0df-246">Нет причин почему одно приложение не может использовать преимущества обоих реляционных и базах данных NoSQL, используя каждый там, где это наиболее подходящий.</span><span class="sxs-lookup"><span data-stu-id="cb0df-246">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-documentdb"></a><span data-ttu-id="cb0df-247">Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="cb0df-247">Azure DocumentDB</span></span>

<span data-ttu-id="cb0df-248">Azure DocumentDB является полностью управляемая служба баз данных NoSQL предоставляет хранилище данных на основе облака без схемы.</span><span class="sxs-lookup"><span data-stu-id="cb0df-248">Azure DocumentDB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="cb0df-249">DocumentDB, созданную для быстрого и прогнозируемую производительность, высокий уровень доступности, гибкого масштабирования и глобального распространения.</span><span class="sxs-lookup"><span data-stu-id="cb0df-249">DocumentDB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="cb0df-250">Несмотря на то, что базы данных NoSQL, разработчики могут использовать знакомый, широкие возможности запросов SQL по данным JSON.</span><span class="sxs-lookup"><span data-stu-id="cb0df-250">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="cb0df-251">Все ресурсы в DocumentDB хранятся в виде документов JSON.</span><span class="sxs-lookup"><span data-stu-id="cb0df-251">All resources in DocumentDB are stored as JSON documents.</span></span> <span data-ttu-id="cb0df-252">Ресурсами как *элементы*, который, документы, содержащие метаданные, и *веб-каналы*, которые представляют собой коллекции элементов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-252">Resources are managed as *items*, which are documents containing metadata, and *feeds*, which are collections of items.</span></span> <span data-ttu-id="cb0df-253">Рис. 8-2 показана связь между различных ресурсов DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="cb0df-253">Figure 8-2 shows the relationship between different DocumentDB resources.</span></span>


![Иерархические связи между ресурсами в DocumentDB, базы данных NoSQL JSON](./media/image8-2.png)

<span data-ttu-id="cb0df-255">**Рис. 8-2.**</span><span class="sxs-lookup"><span data-stu-id="cb0df-255">**Figure 8-2.**</span></span> <span data-ttu-id="cb0df-256">Организация ресурсов DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="cb0df-256">DocumentDB resource organization.</span></span>

<span data-ttu-id="cb0df-257">Язык запросов DocumentDB — это простой и эффективный интерфейс для выполнения запросов к документам JSON.</span><span class="sxs-lookup"><span data-stu-id="cb0df-257">The DocumentDB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="cb0df-258">Язык поддерживает подмножество ANSI SQL-грамматику и добавляет тесная интеграция объект JavaScript, массивов, конструирование объекта и вызова функции.</span><span class="sxs-lookup"><span data-stu-id="cb0df-258">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="cb0df-259">**Ссылки — DocumentDB**</span><span class="sxs-lookup"><span data-stu-id="cb0df-259">**References – DocumentDB**</span></span>

-   <span data-ttu-id="cb0df-260">DocumentDB Introduction\\</span><span class="sxs-lookup"><span data-stu-id="cb0df-260">DocumentDB Introduction\\</span></span>
    <span data-ttu-id="cb0df-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span><span class="sxs-lookup"><span data-stu-id="cb0df-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span></span>

## <a name="other-persistence-options"></a><span data-ttu-id="cb0df-262">Другие параметры сохраняемости</span><span class="sxs-lookup"><span data-stu-id="cb0df-262">Other Persistence Options</span></span>

<span data-ttu-id="cb0df-263">В дополнение к реляционным и варианты хранилищ NoSQL приложения ASP.NET Core можно использовать для хранения различных форматов данных и файлов в виде облачных, масштабируемые хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="cb0df-263">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="cb0df-264">Хранилище Azure — высокой степенью масштабируемости, чтобы вы могли начать out хранения небольших объемов данных и масштаб до сохранения сотнями или терабайт, если это необходимо приложению.</span><span class="sxs-lookup"><span data-stu-id="cb0df-264">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="cb0df-265">Хранилище Azure поддерживает четыре типа данных:</span><span class="sxs-lookup"><span data-stu-id="cb0df-265">Azure Storage supports four kinds of data:</span></span>

-   <span data-ttu-id="cb0df-266">Хранилище больших двоичных объектов для неструктурированных текстовых или двоичных хранилища, также называют хранения объектов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-266">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

-   <span data-ttu-id="cb0df-267">Хранилище таблиц для структурированные наборы данных, доступны через ключей строк.</span><span class="sxs-lookup"><span data-stu-id="cb0df-267">Table Storage for structured datasets, accessible via row keys.</span></span>

-   <span data-ttu-id="cb0df-268">Очереди хранилища для надежного обмена сообщениями на основе очереди.</span><span class="sxs-lookup"><span data-stu-id="cb0df-268">Queue Storage for reliable queue-based messaging.</span></span>

-   <span data-ttu-id="cb0df-269">Хранилище файлов для доступа к общему файлу между виртуальными машинами Azure и локальными приложениями.</span><span class="sxs-lookup"><span data-stu-id="cb0df-269">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="cb0df-270">**Ссылки — хранилища Azure**</span><span class="sxs-lookup"><span data-stu-id="cb0df-270">**References – Azure Storage**</span></span>

-   <span data-ttu-id="cb0df-271">Introduction\ хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="cb0df-271">Azure Storage Introduction\\</span></span>
    <span data-ttu-id="cb0df-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span><span class="sxs-lookup"><span data-stu-id="cb0df-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span></span>

## <a name="caching"></a><span data-ttu-id="cb0df-273">Кэширование</span><span class="sxs-lookup"><span data-stu-id="cb0df-273">Caching</span></span>

<span data-ttu-id="cb0df-274">В веб-приложениях следует выполнить каждого веб-запроса в максимально короткий срок.</span><span class="sxs-lookup"><span data-stu-id="cb0df-274">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="cb0df-275">Для этого можно ограничить число внешних вызовов, который сервер должен принимать для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="cb0df-275">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="cb0df-276">Кэширование предполагает сохранение копии данных на сервере (или другого хранилища данных, то есть более легко можно запросить от источника данных).</span><span class="sxs-lookup"><span data-stu-id="cb0df-276">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="cb0df-277">Веб-приложений и особенно не SPA традиционной веб-приложений, потребуется выполнить сборку и весь пользовательский интерфейс, с каждым запросом.</span><span class="sxs-lookup"><span data-stu-id="cb0df-277">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="cb0df-278">Часто это подразумевает, что многие из тех же запросах базы данных, несколько раз из одного пользователя запроса к следующему.</span><span class="sxs-lookup"><span data-stu-id="cb0df-278">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="cb0df-279">В большинстве случаев эти данные изменений редко, практически не существует причин для постоянно запроса из базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-279">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="cb0df-280">ASP.NET Core поддерживает кэширование ответов для кэширования всей страницы и кэширование данных, которая поддерживает более детального поведение кэширования.</span><span class="sxs-lookup"><span data-stu-id="cb0df-280">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="cb0df-281">При реализации кэширования, нужно иметь в виду Разделение областей ответственности.</span><span class="sxs-lookup"><span data-stu-id="cb0df-281">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="cb0df-282">Избегайте реализации логики кэширования в вашей логики доступа к данным или в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="cb0df-282">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="cb0df-283">Вместо этого инкапсуляции кэширования в собственные классы и использовать конфигурацию управлять ее работой.</span><span class="sxs-lookup"><span data-stu-id="cb0df-283">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="cb0df-284">Следует открыть или закрытое и принципы персональной ответственности и упростит управление использование кэша в приложении по мере его роста.</span><span class="sxs-lookup"><span data-stu-id="cb0df-284">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="cb0df-285">Кэширование ответов ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cb0df-285">ASP.NET Core Response Caching</span></span>

<span data-ttu-id="cb0df-286">ASP.NET Core поддерживает два уровня кэширование ответов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-286">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="cb0df-287">Первый уровень не кэширует ничего на сервере, но добавляет заголовки HTTP, которые указывают для клиентов и прокси-серверами для кэширования ответов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-287">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="cb0df-288">Это реализуется путем добавления атрибута ResponseCache отдельных контроллеров или действий:</span><span class="sxs-lookup"><span data-stu-id="cb0df-288">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }
    
    ViewData["Message"] = "Your contact page.";
    return View();
}

The above example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.

Cache-Control: public,max-age=60

In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware. This middleware is configured in both ConfigureServices and Configure in Startup:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddResponseCaching();
}

public void Configure(IApplicationBuilder app)
{
    app.UseResponseCaching();
}
```

<span data-ttu-id="cb0df-289">По промежуточного слоя кэширования ответа автоматически кэширует ответы на основе набора условий, которые можно настроить.</span><span class="sxs-lookup"><span data-stu-id="cb0df-289">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="cb0df-290">По умолчанию только 200 (ОК) ответы, запрашиваемой через методы GET или HEAD, кэшируются.</span><span class="sxs-lookup"><span data-stu-id="cb0df-290">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="cb0df-291">Кроме того, запросы должен иметь ответ с Cache-Control: открытого заголовка и не может включать заголовки для авторизации или Set-Cookie.</span><span class="sxs-lookup"><span data-stu-id="cb0df-291">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="cb0df-292">В разделе [полный перечень кэширования условия, используемые по промежуточного слоя кэширование ответов](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span><span class="sxs-lookup"><span data-stu-id="cb0df-292">See a [complete list of the caching conditions used by the response caching middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="cb0df-293">Кэширование данных</span><span class="sxs-lookup"><span data-stu-id="cb0df-293">Data Caching</span></span>

<span data-ttu-id="cb0df-294">Вместо (или в дополнение к) кэширование полного веб-откликов, можно кэшировать результаты отдельных запросов.</span><span class="sxs-lookup"><span data-stu-id="cb0df-294">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="cb0df-295">Для этого можно использовать в кэширование памяти на веб-сервере или использовать [распределенного кэша](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span><span class="sxs-lookup"><span data-stu-id="cb0df-295">For this, you can use in memory caching on the web server, or use [a distributed cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="cb0df-296">В этом разделе будет показано, как реализовать в кэширование памяти.</span><span class="sxs-lookup"><span data-stu-id="cb0df-296">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="cb0df-297">Добавить поддержку для памяти (или распределенные) кэширования в ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="cb0df-297">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="cb0df-298">Не забудьте добавить пакет Microsoft.Extensions.Caching.Memory NuGet.</span><span class="sxs-lookup"><span data-stu-id="cb0df-298">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="cb0df-299">После добавления службы, где требуется доступ к кэшу вы запрашиваете IMemoryCache через внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="cb0df-299">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="cb0df-300">В этом примере CachedCatalogService используется шаблон разработки прокси-сервера (или Decorator), предоставляя альтернативной реализации ICatalogService, который управляет доступом к (или добавляет поведение) CatalogService базовой реализации.</span><span class="sxs-lookup"><span data-stu-id="cb0df-300">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
    private static readonly string _itemsKeyTemplate = "items-{0}-{1}-{2}-{3}";
    private static readonly TimeSpan _defaultCacheDuration = TimeSpan.FromSeconds(30);
    public CachedCatalogService(IMemoryCache cache,
    CatalogService catalogService)
    {
        _cache = cache;
        _catalogService = catalogService;
    }
    
    public async Task<IEnumerable<SelectListItem>> GetBrands()
    {
        return await _cache.GetOrCreateAsync(_brandsKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetBrands();
        });
    }
    
    public async Task<Catalog> GetCatalogItems(int pageIndex, int itemsPage, int? brandID, int? typeId)
    {
        string cacheKey = String.Format(_itemsKeyTemplate, pageIndex, itemsPage, brandID, typeId);
        return await _cache.GetOrCreateAsync(cacheKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetCatalogItems(pageIndex, itemsPage, brandID, typeId);
        });
    }
    
    public async Task<IEnumerable<SelectListItem>> GetTypes()
    {
        return await _cache.GetOrCreateAsync(_typesKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetTypes();
        });
    }
}
```

<span data-ttu-id="cb0df-301">Чтобы настроить приложение, чтобы использовать кэшированная версия службы, но по-прежнему позволяет службе для получения экземпляра CatalogService ему в конструкторе, необходимо добавить следующие в ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="cb0df-301">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="cb0df-302">Это место вызовы базы данных для выборки данных каталога будут выполняться только один раз в минуту, а не при каждом запросе.</span><span class="sxs-lookup"><span data-stu-id="cb0df-302">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="cb0df-303">В зависимости от трафика на узел это может иметь очень значительное влияние на количество запросов, выполняемых в базу данных и среднее время загрузки страницы на домашнюю страницу, которая в настоящее время зависит от всех трех запросов, предоставляемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="cb0df-303">Depending on the traffic to the site, this can have a very significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="cb0df-304">Проблема, которая возникает, когда кэширование реализуется — *устаревшие данные* — то есть данные, изменившиеся в источнике, но устаревшая версия остается в кэше.</span><span class="sxs-lookup"><span data-stu-id="cb0df-304">An issue that arises when caching is implemented is *stale data* – that is, data that has changed at the source but an out of date version remains in the cache.</span></span> <span data-ttu-id="cb0df-305">Простой способ устранения этой проблемы — использовать небольшой продолжительность хранения в кэше, так как работающее приложение нет ограниченная дополнительное преимущество расширение длину хранения данных в кэше.</span><span class="sxs-lookup"><span data-stu-id="cb0df-305">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="cb0df-306">Например, рассмотрим страницы, которая делает запрос одной базы данных и запрашивается 10 раз в секунду.</span><span class="sxs-lookup"><span data-stu-id="cb0df-306">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="cb0df-307">Если эта страница кэшируется в течение одной минуты, приведет к число запросов к базе данных в минуту, выполненных для удаления из 600 сокращения 99.8% 1.</span><span class="sxs-lookup"><span data-stu-id="cb0df-307">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="cb0df-308">Если вместо этого длительность кэширования были внесены в один час, Общее уменьшение будет 99.997%, но теперь вероятность и потенциально возраст устаревшие данные и значительно увеличился.</span><span class="sxs-lookup"><span data-stu-id="cb0df-308">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="cb0df-309">Другой подход заключается упреждающего удаление записей кэша, при обновлении данных, содержащихся в них.</span><span class="sxs-lookup"><span data-stu-id="cb0df-309">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="cb0df-310">Можно удалить любой отдельной операции, если известен его ключ:</span><span class="sxs-lookup"><span data-stu-id="cb0df-310">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="cb0df-311">Если ваше приложение предоставляет функциональность для обновления записей, которые он кэширует, можно удалить соответствующие записи кэша в коде, который выполняет обновления.</span><span class="sxs-lookup"><span data-stu-id="cb0df-311">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="cb0df-312">Иногда может быть много разных записей, которые зависят от определенного набора данных.</span><span class="sxs-lookup"><span data-stu-id="cb0df-312">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="cb0df-313">В этом случае может оказаться полезным создать зависимости между записей кэша, с помощью CancellationChangeToken.</span><span class="sxs-lookup"><span data-stu-id="cb0df-313">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="cb0df-314">С CancellationChangeToken может истечь нескольких записей кэша за один раз при отмене токена.</span><span class="sxs-lookup"><span data-stu-id="cb0df-314">With a CancellationChangeToken, you can expire multiple cache entries at once by cancelling the token.</span></span>

```csharp
// configure CancellationToken and add entry to cache
var cts = new CancellationTokenSource();
_cache.Set("cts", cts);
_cache.Set(cacheKey,
itemToCache,
new CancellationChangeToken(cts.Token));

// elsewhere, expire the cache by cancelling the token\
_cache.Get<CancellationTokenSource>("cts").Cancel();
```

>[!div class="step-by-step"]
<span data-ttu-id="cb0df-315">[Предыдущие] (develop-asp-net-core-mvc-apps.md) [Далее] (test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="cb0df-315">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span></span>
