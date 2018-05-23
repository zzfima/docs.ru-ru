---
title: Работа с данными в приложениях ASP.NET Core
description: Разработка современных веб-приложений с помощью ASP.NET Core и Azure | Работа с данными в приложениях ASP.NET Core
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.openlocfilehash: 89df46c8e04e1826c84058e5d2a92d089eb96098
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="70a72-103">Работа с данными в приложениях ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="70a72-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="70a72-104">"Данные — это самый ценный ресурс, который намного переживет сами системы".</span><span class="sxs-lookup"><span data-stu-id="70a72-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>

<span data-ttu-id="70a72-105">Тим Бернерс-Ли (Tim Berners-Lee)</span><span class="sxs-lookup"><span data-stu-id="70a72-105">Tim Berners-Lee</span></span>

## <a name="summary"></a><span data-ttu-id="70a72-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="70a72-106">Summary</span></span>

<span data-ttu-id="70a72-107">Доступ к данным является одной из важнейших составляющих практически любой программы.</span><span class="sxs-lookup"><span data-stu-id="70a72-107">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="70a72-108">ASP.NET Core поддерживает широкий спектр способов доступа к данным, включая Entity Framework Core (и Entity Framework 6), и может работать с любыми платформами доступа к данным .NET.</span><span class="sxs-lookup"><span data-stu-id="70a72-108">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="70a72-109">Выбор используемой платформы доступа к данным зависит от потребностей приложения.</span><span class="sxs-lookup"><span data-stu-id="70a72-109">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="70a72-110">Абстрагируя выбор такой платформы от проектов ядра приложения и пользовательского интерфейса, а также инкапсулируя детали реализации в инфраструктуре, можно создавать слабо связанное приложение с расширенными возможностями для тестирования.</span><span class="sxs-lookup"><span data-stu-id="70a72-110">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="70a72-111">Entity Framework Core (для реляционных баз данных)</span><span class="sxs-lookup"><span data-stu-id="70a72-111">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="70a72-112">Если вы создаете новое приложение ASP.NET Core для работы с реляционными данными, рекомендуется выбирать Entity Framework Core (EF Core) для доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="70a72-112">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="70a72-113">EF Core является объектно-реляционным модулем сопоставления (O/RM), который позволяет разработчикам .NET обеспечивать двустороннюю сохраняемость объектов во взаимодействии с источником данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-113">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="70a72-114">Это устраняет необходимость в большей части кода для доступа к данным, который разработчикам обычно приходится писать.</span><span class="sxs-lookup"><span data-stu-id="70a72-114">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="70a72-115">Как и ASP.NET Core, платформа EF Core была переработана, чтобы обеспечить поддержку модульных кроссплатформенных приложений.</span><span class="sxs-lookup"><span data-stu-id="70a72-115">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="70a72-116">Она добавляется в приложение в виде пакета NuGet, настраивается в классе Startup и используется для обработки запросов посредством внедрения зависимостей в тот момент, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="70a72-116">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="70a72-117">Чтобы использовать EF Core с базой данных SQL Server, выполните следующую команду dotnet CLI:</span><span class="sxs-lookup"><span data-stu-id="70a72-117">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

<span data-ttu-id="70a72-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span><span class="sxs-lookup"><span data-stu-id="70a72-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span></span>

<span data-ttu-id="70a72-119">Чтобы добавить поддержку источника данных в памяти для тестирования, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="70a72-119">To add support for an InMemory data source, for testing:</span></span>

<span data-ttu-id="70a72-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span><span class="sxs-lookup"><span data-stu-id="70a72-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span></span>

### <a name="the-dbcontext"></a><span data-ttu-id="70a72-121">DbContext</span><span class="sxs-lookup"><span data-stu-id="70a72-121">The DbContext</span></span>

<span data-ttu-id="70a72-122">Для работы с EF Core вам потребуется подкласс DbContext.</span><span class="sxs-lookup"><span data-stu-id="70a72-122">To work with EF Core, you need a subclass of DbContext.</span></span> <span data-ttu-id="70a72-123">Этот класс содержит свойства, представляющие коллекцию сущностей, с которыми будет работать ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="70a72-123">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="70a72-124">Пример приложения eShopOnWeb содержит CatalogContext с коллекциями товаров, брендов и типов:</span><span class="sxs-lookup"><span data-stu-id="70a72-124">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

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

<span data-ttu-id="70a72-125">Ваш класс DbContext должен иметь конструктор, который принимает DbContextOptions и передает этот аргумент в базовый класс DbContext.</span><span class="sxs-lookup"><span data-stu-id="70a72-125">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="70a72-126">Обратите внимание, что если в вашем приложении используется только один класс DbContext, вы можете передавать экземпляр DbContextOptions, однако при наличии нескольких таких классов вам необходимо использовать универсальный тип DbContextOptions<T>, передавая ваш тип DbContext в качестве универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="70a72-126">Note that if you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="70a72-127">Настройка EF Core</span><span class="sxs-lookup"><span data-stu-id="70a72-127">Configuring EF Core</span></span>

<span data-ttu-id="70a72-128">В приложении ASP.NET Core настройка EF Core обычно осуществляется в методе ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="70a72-128">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="70a72-129">EF Core использует DbContextOptionsBuilder, который поддерживает несколько полезных методов расширения, позволяющих оптимизировать его конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="70a72-129">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="70a72-130">Чтобы настроить метод CatalogContext для использования базы данных SQL Server со строкой подключения, определенной в конфигурации, необходимо добавить следующий код в ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="70a72-130">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="70a72-131">Чтобы использовать выполняющуюся в памяти базу данных:</span><span class="sxs-lookup"><span data-stu-id="70a72-131">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="70a72-132">После установки EF Core, создания дочернего типа DbContext и его настройки в методе ConfigureServices вы можете использовать EF Core.</span><span class="sxs-lookup"><span data-stu-id="70a72-132">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="70a72-133">Вы можете запросить экземпляр вашего типа DbContext в любой службе, где он необходим, и начать работу с хранимыми сущностями с помощью LINQ так, как если бы они были обычными коллекциями.</span><span class="sxs-lookup"><span data-stu-id="70a72-133">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="70a72-134">EF Core автоматически преобразует выражения LINQ в запросы SQL для хранения и извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-134">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="70a72-135">Чтобы просмотреть выполнение запросов EF Core, настройте ведение журналов как минимум на уровне информационных сообщений, как показано на рис. 8-1.</span><span class="sxs-lookup"><span data-stu-id="70a72-135">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![](./media/image8-1.png)

<span data-ttu-id="70a72-136">Рис. 8-1. Вывод журнала запросов EF Core на консоль</span><span class="sxs-lookup"><span data-stu-id="70a72-136">Figure 8-1 Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="70a72-137">Получение и сохранение данных</span><span class="sxs-lookup"><span data-stu-id="70a72-137">Fetching and Storing Data</span></span>

<span data-ttu-id="70a72-138">Чтобы извлечь данные из EF Core, необходимо обратиться к соответствующему свойству и использовать LINQ для фильтрации результатов.</span><span class="sxs-lookup"><span data-stu-id="70a72-138">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="70a72-139">Также можно использовать LINQ для выполнения проекции (преобразования результата из одного типа в другой).</span><span class="sxs-lookup"><span data-stu-id="70a72-139">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="70a72-140">В следующем примере извлекается CatalogBrands с упорядочением по имени, затем осуществляется фильтровка по свойству Enabled, после чего выполняется проекция в тип SelectListItem:</span><span class="sxs-lookup"><span data-stu-id="70a72-140">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="70a72-141">В приведенном выше примере важно добавить вызов ToListAsync, чтобы выполнить запрос немедленно.</span><span class="sxs-lookup"><span data-stu-id="70a72-141">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="70a72-142">В противном случае инструкция назначит IQueryable<SelectListItem> для brandItems, и выполнение не будет начато, пока не будет выполнено перечисление.</span><span class="sxs-lookup"><span data-stu-id="70a72-142">Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="70a72-143">Возврат результатов IQueryable из методов имеет свои преимущества и недостатки.</span><span class="sxs-lookup"><span data-stu-id="70a72-143">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="70a72-144">Такой подход позволяет осуществлять дальнейшие изменения запроса, который будет создавать EF Core, но также может привести к ошибке, которая проявится только во время выполнения при добавлении операций в запрос, который EF Core не сможет преобразовать.</span><span class="sxs-lookup"><span data-stu-id="70a72-144">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="70a72-145">Как правило, более безопасный подход подразумевает передачу любых фильтров в метод, осуществляющий доступ к данным, с последующим возвратом размещаемой в памяти коллекции (например, List<T>) в виде результата.</span><span class="sxs-lookup"><span data-stu-id="70a72-145">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.</span></span>

<span data-ttu-id="70a72-146">EF Core отслеживает изменения сущностей, которые получаются из хранилища сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="70a72-146">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="70a72-147">Чтобы сохранить изменения в отслеживаемой сущности, достаточно вызвать метод SaveChanges для DbContext и убедиться, что это тот же экземпляр DbContext, который использовался при получении сущности.</span><span class="sxs-lookup"><span data-stu-id="70a72-147">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="70a72-148">Добавление и удаление сущностей осуществляется непосредственно с помощью свойства DbSet также посредством вызова метода SaveChanges для выполнения команд базы данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-148">Adding and removing entities is directly on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="70a72-149">В следующем примере показано добавление, обновление и удаление сущностей из хранилища сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="70a72-149">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

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

<span data-ttu-id="70a72-150">EF Core поддерживает как синхронные, так и асинхронные методы получения и сохранения.</span><span class="sxs-lookup"><span data-stu-id="70a72-150">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="70a72-151">В веб-приложениях рекомендуется использовать шаблон async/await для асинхронных методов. В этом случае потоки веб-сервера не блокируются на время ожидания завершения операций доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="70a72-151">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="70a72-152">Получение связанных данных</span><span class="sxs-lookup"><span data-stu-id="70a72-152">Fetching Related Data</span></span>

<span data-ttu-id="70a72-153">При получении сущностей EF Core заполняет все свойства, которые хранятся в базе данных непосредственно с этой сущностью.</span><span class="sxs-lookup"><span data-stu-id="70a72-153">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="70a72-154">Свойства навигации, например списки связанных сущностей, не заполняются и могут получать значения null.</span><span class="sxs-lookup"><span data-stu-id="70a72-154">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="70a72-155">Таким образом гарантируется, что EF Core не будет извлекать объем данных больше необходимого, что особенно важно для веб-приложений, которые должны быстро обрабатывать запросы и возвращать ответы эффективным способом.</span><span class="sxs-lookup"><span data-stu-id="70a72-155">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="70a72-156">Чтобы включить отношение с сущностью, используя *безотложную загрузку*, необходимо указать свойство, используя метод расширения Include для запроса, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="70a72-156">To include relationships with an entity using *eager loading*, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="70a72-157">Можно включить несколько отношений, а также вложенные отношения с помощью ThenInclude.</span><span class="sxs-lookup"><span data-stu-id="70a72-157">You can include multiple relationships, and you can also include sub-relationships using ThenInclude.</span></span> <span data-ttu-id="70a72-158">EF Core выполнит один запрос для извлечения результирующего набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="70a72-158">EF Core will execute a single query to retrieve the resulting set of entities.</span></span>

<span data-ttu-id="70a72-159">Также для загрузки связанных данных можно использовать *явную загрузку*.</span><span class="sxs-lookup"><span data-stu-id="70a72-159">Another option for loading related data is to use *explicit loading*.</span></span> <span data-ttu-id="70a72-160">Явная загрузка позволяет загружать дополнительные данные в уже извлеченную сущность.</span><span class="sxs-lookup"><span data-stu-id="70a72-160">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="70a72-161">Поскольку для этого требуется дополнительный запрос к базе данных, такой подход не рекомендуется для веб-приложений, в которых необходимо свести к минимуму число обращений к базе данных в рамках одного запроса.</span><span class="sxs-lookup"><span data-stu-id="70a72-161">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="70a72-162">*Отложенная загрузка* позволяет автоматически загружать данные в тот момент, когда на них ссылается приложение.</span><span class="sxs-lookup"><span data-stu-id="70a72-162">*Lazy loading* is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="70a72-163">На данный момент EF Core не поддерживает этот механизм, однако, как и в случае с явной загрузкой, в большинстве случаев для веб-приложений он должен быть отключен.</span><span class="sxs-lookup"><span data-stu-id="70a72-163">It's not currently supported by EF Core, but as with explicit loading it should typically be disabled for web applications.</span></span>

### <a name="resilient-connections"></a><span data-ttu-id="70a72-164">Устойчивые подключения</span><span class="sxs-lookup"><span data-stu-id="70a72-164">Resilient Connections</span></span>

<span data-ttu-id="70a72-165">Внешние ресурсы, например базы данных SQL, время от времени могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="70a72-165">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="70a72-166">Если ресурс временно недоступен, приложение может использовать логику повторных попыток, чтобы избежать возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="70a72-166">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="70a72-167">Такой подход часто называют *устойчивостью подключений*.</span><span class="sxs-lookup"><span data-stu-id="70a72-167">This technique is commonly referred to as *connection resiliency*.</span></span> <span data-ttu-id="70a72-168">Вы можете реализовать собственную логику [повторных попыток с экспоненциальной выдержкой](https://docs.microsoft.com/azure/architecture/patterns/retry), при котором приложение пытается повторить операцию с экспоненциально растущим временем ожидания, пока не будет достигнуто максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="70a72-168">You can implement your [own retry with exponential backoff](https://docs.microsoft.com/azure/architecture/patterns/retry) technique by attempting to rety with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="70a72-169">Этот метод учитывает тот факт, что облачные ресурсы могут быть периодически недоступны в течение нескольких секунд по различным причинам, в результате чего некоторые запросы могут завершаться сбоем.</span><span class="sxs-lookup"><span data-stu-id="70a72-169">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="70a72-170">Для баз данных Azure SQL платформа Entity Framework Core уже предоставляет логику устойчивости и повторного выполнения при подключении к внутренним базам данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-170">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="70a72-171">Но вам необходимо применить стратегию выполнения Entity Framework к каждому подключению DbContext, если вы хотите иметь устойчивое подключение к EF Core.</span><span class="sxs-lookup"><span data-stu-id="70a72-171">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="70a72-172">Например, следующий код на уровне подключения к EF Core обеспечивает устойчивое SQL-подключение, которое устанавливается повторно при сбое.</span><span class="sxs-lookup"><span data-stu-id="70a72-172">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="70a72-173">Стратегии выполнения и явные транзакции с использованием BeginTransaction и нескольких DbContext</span><span class="sxs-lookup"><span data-stu-id="70a72-173">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span> 
  
  <span data-ttu-id="70a72-174">Если в подключениях к EF Core включены повторные попытки, каждая операция, выполняемая с помощью EF Core, будет предпринимать повторные попытки.</span><span class="sxs-lookup"><span data-stu-id="70a72-174">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="70a72-175">Каждый запрос и каждый вызов к SaveChanges будет повторяться снова как единица в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="70a72-175">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>
  
  <span data-ttu-id="70a72-176">Но если код запускает транзакцию с помощью BeginTransaction, вы сами определяете группу операций, которые должны рассматриваться как единица, — все содержимое транзакции можно будет откатить в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="70a72-176">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="70a72-177">Если вы попытаетесь выполнить эту транзакцию при использовании стратегии выполнения EF (политика повтора) и включаете несколько вызовов SaveChanges из нескольких DbContext в транзакции, отобразится следующее исключение.</span><span class="sxs-lookup"><span data-stu-id="70a72-177">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="70a72-178">System.InvalidOperationException: настроенная стратегия выполнения 'SqlServerRetryingExecutionStrategy' не поддерживает запуск транзакций пользователем.</span><span class="sxs-lookup"><span data-stu-id="70a72-178">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="70a72-179">Используйте стратегию выполнения, возвращенную 'DbContext.Database.CreateExecutionStrategy()', чтобы выполнить все операции в транзакции как повторяемую единицу.</span><span class="sxs-lookup"><span data-stu-id="70a72-179">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="70a72-180">Необходимо вручную вызвать стратегию выполнения EF с делегатом, который представляет все, что должно быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="70a72-180">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="70a72-181">В случае временного сбоя стратегия выполнения будет снова вызывать делегат.</span><span class="sxs-lookup"><span data-stu-id="70a72-181">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="70a72-182">В следующем примере кода показано, как реализовать этот подход:</span><span class="sxs-lookup"><span data-stu-id="70a72-182">The following code shows how to implement this approach:</span></span>

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

<span data-ttu-id="70a72-183">Первый DbContext — это \_catalogContext, а второй DbContext находится в объекте \_integrationEventLogService.</span><span class="sxs-lookup"><span data-stu-id="70a72-183">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="70a72-184">Наконец, действие фиксации выполняется в нескольких DbContext с помощью стратегии выполнения EF.</span><span class="sxs-lookup"><span data-stu-id="70a72-184">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="70a72-185">Ссылки — получение Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="70a72-185">References – Entity Framework Core</span></span>
> - <span data-ttu-id="70a72-186">**Документация по EF Core**</span><span class="sxs-lookup"><span data-stu-id="70a72-186">**EF Core Docs**</span></span>  
> <https://docs.microsoft.com/ef/>
> - <span data-ttu-id="70a72-187">**EF Core: связанные данные**</span><span class="sxs-lookup"><span data-stu-id="70a72-187">**EF Core: Related Data**</span></span>  
> <https://docs.microsoft.com/ef/core/querying/related-data>
> - <span data-ttu-id="70a72-188">**Предотвращение отложенной загрузки сущностей в приложениях ASPNET**</span><span class="sxs-lookup"><span data-stu-id="70a72-188">**Avoid Lazy Loading Entities in ASPNET Applications**</span></span>  
> <https://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="70a72-189">EF Core или микро-ORM?</span><span class="sxs-lookup"><span data-stu-id="70a72-189">EF Core or micro-ORM?</span></span>

<span data-ttu-id="70a72-190">EF Core хорошо подходит для управления сохраняемостью и по большей части инкапсулирует детали базы данных, освобождая от труда разработчиков приложения, однако это средство не является единственным вариантом.</span><span class="sxs-lookup"><span data-stu-id="70a72-190">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it is not the only choice.</span></span> <span data-ttu-id="70a72-191">Популярным альтернативным решением с открытым исходным кодом является [Dapper](https://github.com/StackExchange/Dapper), который также называется микро-ORM.</span><span class="sxs-lookup"><span data-stu-id="70a72-191">Another popular open source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="70a72-192">Микро-ORM — это упрощенное средство сопоставления объектов со структурами данных, обладающее сокращенным набором функции.</span><span class="sxs-lookup"><span data-stu-id="70a72-192">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="70a72-193">Основной задачей Dapper является оптимизация производительности при проектировании, а не полная инкапсуляция базовых запросов, которые используются для извлечения и обновления данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-193">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="70a72-194">Поскольку это средство не абстрагирует SQL от разработчика, Dapper является более низкоуровневым инструментом, позволяя разработчикам создавать точные запросы, которые они хотят использовать для конкретных операций доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="70a72-194">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="70a72-195">EF Core может предложить две существенных функциональных возможности, которые отличают эту платформу Dapper, но при этом приводят к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="70a72-195">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="70a72-196">Первая из них — это преобразование выражений LINQ в SQL.</span><span class="sxs-lookup"><span data-stu-id="70a72-196">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="70a72-197">Эти преобразования кэшируются, однако даже в этом случае при их первом выполнении производительность снижается.</span><span class="sxs-lookup"><span data-stu-id="70a72-197">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="70a72-198">Вторая возможность — отслеживание изменений сущностей, что позволяет создавать эффективные операторы обновления.</span><span class="sxs-lookup"><span data-stu-id="70a72-198">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="70a72-199">Такое поведение можно отключить для конкретных запросов с помощью расширения AsNotTracking.</span><span class="sxs-lookup"><span data-stu-id="70a72-199">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="70a72-200">EF Core также создает эффективные SQL-запросы, которые крайне эффективны и в любом случае приемлемы с точки зрения производительности. Однако если вам требуется детальный контроль над тем, какой в точности запрос выполняется, вы также можете передать настраиваемый SQL (или выполнить хранимую процедуру) с помощью EF Core.</span><span class="sxs-lookup"><span data-stu-id="70a72-200">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="70a72-201">В такой ситуации Dapper по-прежнему, хотя и незначительно, превосходит EF Core в отношении производительности.</span><span class="sxs-lookup"><span data-stu-id="70a72-201">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="70a72-202">Джули Лерман (Julie Lerman) приводит некоторые данные по производительности в статье MSDN [Dapper, Entity Framework и гибридные приложения](https://msdn.microsoft.com/magazine/mt703432.aspx) за май 2016 г.</span><span class="sxs-lookup"><span data-stu-id="70a72-202">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span></span> <span data-ttu-id="70a72-203">Дополнительные данные по тестированию производительности для различных методов доступа к данным можно найти на [сайте Dapper](https://github.com/StackExchange/Dapper).</span><span class="sxs-lookup"><span data-stu-id="70a72-203">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="70a72-204">Чтобы ознакомиться с различиями в синтаксисе между Dapper и EF Core, рассмотрите следующие две версии одного и того же метода, извлекающего список элементов:</span><span class="sxs-lookup"><span data-stu-id="70a72-204">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

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

<span data-ttu-id="70a72-205">Для построения более сложных графов объектов с помощью Dapper вам потребуется написать связанные запросы самостоятельно (в отличие от EF Core, где для этого используется Include).</span><span class="sxs-lookup"><span data-stu-id="70a72-205">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="70a72-206">Поддержка такого поведения обеспечивается различным синтаксисом, в том числе с помощью функции множественного сопоставления, которая позволяет сопоставлять отдельные строки с несколькими сопоставленными объектами.</span><span class="sxs-lookup"><span data-stu-id="70a72-206">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="70a72-207">Например, для класса Post со свойством Owner типа User следующий SQL-код будет возвращать все необходимые данные:</span><span class="sxs-lookup"><span data-stu-id="70a72-207">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="70a72-208">Каждая возвращаемая строка будет включать данные User и Post.</span><span class="sxs-lookup"><span data-stu-id="70a72-208">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="70a72-209">Поскольку данные User должны быть присоединены к данным Post посредством свойства Owner, используется следующая функция:</span><span class="sxs-lookup"><span data-stu-id="70a72-209">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="70a72-210">Полный код, возвращающий коллекцию элементов Post, свойства Owner которых будут заполнены соответствующими данными User, будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="70a72-210">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="70a72-211">Dapper обеспечивает более низкий уровень инкапсуляции, в связи с чем разработчики должны знать больше о том, как хранятся их данные, как эффективно выполнять запросы к ним, а также о том, как писать дополнительный код для их получения.</span><span class="sxs-lookup"><span data-stu-id="70a72-211">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="70a72-212">Если модель изменяется вместо создания новой миграции (еще одна функция EF Core) и (или) обновления данных сопоставления в одном месте в DbContext, необходимо обновить каждый затрагиваемый запрос.</span><span class="sxs-lookup"><span data-stu-id="70a72-212">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="70a72-213">Для таких запросов отсутствуют гарантии времени компиляции, поэтому они могут завершиться нарушением во время выполнения в ответ на изменения в модели или базе данных, что значительно усложняет своевременное выявление ошибок.</span><span class="sxs-lookup"><span data-stu-id="70a72-213">These queries have not compile time guarantees, so they may break at runtime in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="70a72-214">Тем не менее эти недостатки Dapper компенсирует крайне высокой производительностью.</span><span class="sxs-lookup"><span data-stu-id="70a72-214">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="70a72-215">Для большинства приложений и большинства компонентов практически любых приложений EF Core предлагает приемлемый уровень производительности.</span><span class="sxs-lookup"><span data-stu-id="70a72-215">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="70a72-216">Таким образом, преимущества в удобстве для разработчика в большинстве случаев перевешивают возможное снижение производительности.</span><span class="sxs-lookup"><span data-stu-id="70a72-216">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="70a72-217">Для запросов, эффективность которых может быть повышена за счет кэширования, фактический запрос выполняется крайне редко, в связи с чем эти относительно небольшие различия в производительности обработки запросов теряют значимость.</span><span class="sxs-lookup"><span data-stu-id="70a72-217">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="70a72-218">SQL или NoSQL</span><span class="sxs-lookup"><span data-stu-id="70a72-218">SQL or NoSQL</span></span>

<span data-ttu-id="70a72-219">Реляционные базы данных, такие как SQL Server, традиционно занимают львиную долю рынка решений для хранения постоянных данных, однако они также не являются единственным решением.</span><span class="sxs-lookup"><span data-stu-id="70a72-219">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="70a72-220">Такие базы данных NoSQL, как [MongoDB](https://www.mongodb.com/what-is-mongodb), предлагают другой подход к хранению объектов.</span><span class="sxs-lookup"><span data-stu-id="70a72-220">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="70a72-221">Вместо сопоставления объектов с таблицами и строками выполняется сериализация всего графа объектов с сохранением результата.</span><span class="sxs-lookup"><span data-stu-id="70a72-221">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="70a72-222">Преимущества такого подхода, как минимум на начальной стадии, заключаются в простоте и производительности.</span><span class="sxs-lookup"><span data-stu-id="70a72-222">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="70a72-223">Безусловно, проще хранить один сериализованный объект с ключом, чем разбивать его на множество таблиц, связанных различными отношениями, и обновлять строки, которые могли быть изменены с момента последнего получения объекта из базы данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-223">It's certainly simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="70a72-224">Аналогичным образом, получение и десериализация одного объекта из основанного на ключах хранилища, как правило, выполняется значительно быстрее и проще, чем сложные объединения или множественные запросы к базе данных, необходимые для полного воссоздания объекта на основе реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-224">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="70a72-225">Отсутствие блокировок, транзакций или фиксированной схемы также обеспечивает высокую степень пригодности баз данных NoSQL для масштабирования на множестве компьютеров для поддержки очень крупных баз данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-225">The lack of locks or transactions or a fixed schema also makes NoSQL databases very amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="70a72-226">С другой стороны, базы данных NoSQL имеют свои недостатки.</span><span class="sxs-lookup"><span data-stu-id="70a72-226">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="70a72-227">Для обеспечения согласованности и предотвращения дублирования данных в реляционных базах данных применяется нормализация.</span><span class="sxs-lookup"><span data-stu-id="70a72-227">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="70a72-228">Это позволяет уменьшить общий размер базы данных и гарантировать немедленную доступность обновлений общих данных на уровне всей базы данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-228">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="70a72-229">В реляционной базе данных таблица Address может ссылаться на таблицу Country по идентификатору. Таким образом, при изменении названия страны записи адресов будут использовать обновленные данные и не потребуют отдельного обновления.</span><span class="sxs-lookup"><span data-stu-id="70a72-229">In a relational database, an Address table might reference a Country table by ID, such that if a country's name were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="70a72-230">Тем не менее в базе данных NoSQL таблица Address и связанная с ней таблица Country могут быть сериализованы в составе множества хранимых объектов.</span><span class="sxs-lookup"><span data-stu-id="70a72-230">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="70a72-231">В таких случаях при изменении названия страны потребуется обновить все такие объекты, а не одну строку.</span><span class="sxs-lookup"><span data-stu-id="70a72-231">An update to a country name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="70a72-232">Реляционные базы данных также гарантируют реляционную целостность посредством применения правил, например внешних ключей.</span><span class="sxs-lookup"><span data-stu-id="70a72-232">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="70a72-233">Базы данных NoSQL, как правило, не реализуют такие ограничения для данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-233">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="70a72-234">Также с базами данных NoSQL связаны трудности при управлении версиями.</span><span class="sxs-lookup"><span data-stu-id="70a72-234">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="70a72-235">При изменении свойств объекта может быть невозможна десериализация объекта на основе хранимых предыдущих версий.</span><span class="sxs-lookup"><span data-stu-id="70a72-235">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="70a72-236">Таким образом, все существующие объекты, у которых есть сериализованная (предыдущая) версия, должны быть обновлены в соответствии с новой схемой.</span><span class="sxs-lookup"><span data-stu-id="70a72-236">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="70a72-237">В таком поведении нет принципиальных отличий от реляционных баз данных, в которых изменение схемы иногда требует обновления скриптов или сопоставления обновлений.</span><span class="sxs-lookup"><span data-stu-id="70a72-237">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="70a72-238">Тем не менее для баз данных NoSQL число изменяемых записей зачастую намного больше из-за большего объема дублированных данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-238">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="70a72-239">В базах данных NoSQL может храниться несколько версий объектов, что в некоторых реляционных базах данных обычно не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="70a72-239">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="70a72-240">Тем не менее в этом случае в коде приложения необходимо учитывать существование предыдущих версий объектов, в результате чего сложность возрастает.</span><span class="sxs-lookup"><span data-stu-id="70a72-240">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="70a72-241">В базах данных NoSQL, как правило, не применяется концепция [ACID](https://en.wikipedia.org/wiki/ACID) (атомарность, согласованность, изолированность, устойчивость), в связи с чем они превосходят реляционные базы данных в отношении производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="70a72-241">NoSQL databases typically do not enforce [ACID](https://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="70a72-242">Они хорошо подходят для очень больших наборов данных и объектов, которые неэффективно хранить в нормализованных табличных структурах.</span><span class="sxs-lookup"><span data-stu-id="70a72-242">They're well-suited to extremely large datasets and objects that are not well-suited to storage in normalized table structures.</span></span> <span data-ttu-id="70a72-243">При этом нет никаких ограничений на использование преимуществ как реляционных баз, так и баз данных NoSQL, в рамках одного приложения в тех случаях, где это необходимо.</span><span class="sxs-lookup"><span data-stu-id="70a72-243">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-documentdb"></a><span data-ttu-id="70a72-244">Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="70a72-244">Azure DocumentDB</span></span>

<span data-ttu-id="70a72-245">Azure DocumentDB — это полностью управляемая служба баз данных NoSQL, которая предлагает облачное хранилище данных без схемы.</span><span class="sxs-lookup"><span data-stu-id="70a72-245">Azure DocumentDB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="70a72-246">DocumentDB обеспечивает высокую прогнозируемую производительность, высокую доступность, эластичную масштабируемость и возможность глобального распределения.</span><span class="sxs-lookup"><span data-stu-id="70a72-246">DocumentDB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="70a72-247">Несмотря на то, что это база данных NoSQL, разработчики могут использовать все хорошо знакомые возможности SQL-запросов к данным JSON.</span><span class="sxs-lookup"><span data-stu-id="70a72-247">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="70a72-248">Все ресурсы в DocumentDB хранятся в виде документов JSON.</span><span class="sxs-lookup"><span data-stu-id="70a72-248">All resources in DocumentDB are stored as JSON documents.</span></span> <span data-ttu-id="70a72-249">Ресурсы управляются в виде *элементов* (документы, содержащие метаданные) и *веб-каналов*, которые представляют собой коллекции элементов.</span><span class="sxs-lookup"><span data-stu-id="70a72-249">Resources are managed as *items*, which are documents containing metadata, and *feeds*, which are collections of items.</span></span> <span data-ttu-id="70a72-250">На рис. 8-2 показаны отношения между различными ресурсами DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="70a72-250">Figure 8-2 shows the relationship between different DocumentDB resources.</span></span>


![Иерархические отношения между ресурсами в DocumentDB (база данных JSON NoSQL)](./media/image8-2.png)

<span data-ttu-id="70a72-252">**Рис. 8-2.**</span><span class="sxs-lookup"><span data-stu-id="70a72-252">**Figure 8-2.**</span></span> <span data-ttu-id="70a72-253">Организация ресурсов в DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="70a72-253">DocumentDB resource organization.</span></span>

<span data-ttu-id="70a72-254">В DocumentDB используется простой и полнофункциональный язык запросов для документов JSON.</span><span class="sxs-lookup"><span data-stu-id="70a72-254">The DocumentDB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="70a72-255">Этот язык поддерживает подмножество грамматических конструкций SQL ANSI и реализует углубленную интеграцию объектов, массивов, возможностей конструирования объектов и вызова функций JavaScript.</span><span class="sxs-lookup"><span data-stu-id="70a72-255">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="70a72-256">**Ссылки — DocumentDB**</span><span class="sxs-lookup"><span data-stu-id="70a72-256">**References – DocumentDB**</span></span>

-   <span data-ttu-id="70a72-257">Общие сведения о DocumentDB\\</span><span class="sxs-lookup"><span data-stu-id="70a72-257">DocumentDB Introduction\\</span></span>
    <https://docs.microsoft.com/azure/documentdb/documentdb-introduction>

## <a name="other-persistence-options"></a><span data-ttu-id="70a72-258">Другие варианты сохраняемости</span><span class="sxs-lookup"><span data-stu-id="70a72-258">Other Persistence Options</span></span>

<span data-ttu-id="70a72-259">В дополнение к реляционным и NoSQL вариантам хранения, в приложениях ASP.NET Core можно использовать облачное масштабируемое хранилище Azure для хранения данных и файлов в различных форматах.</span><span class="sxs-lookup"><span data-stu-id="70a72-259">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="70a72-260">Хранилище Azure обеспечивает высокую степень масштабируемости, позволяя начать с хранения небольших объемов данных и при необходимости увеличить объем хранилища до сотен терабайт.</span><span class="sxs-lookup"><span data-stu-id="70a72-260">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="70a72-261">Хранилище Azure поддерживает четыре вида данных:</span><span class="sxs-lookup"><span data-stu-id="70a72-261">Azure Storage supports four kinds of data:</span></span>

-   <span data-ttu-id="70a72-262">Хранилище BLOB-объектов для хранения неструктурированных текстовых или двоичных данных, которое также называется хранилищем объектов.</span><span class="sxs-lookup"><span data-stu-id="70a72-262">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

-   <span data-ttu-id="70a72-263">Хранилище таблиц для структурированных наборов данных, доступных по ключам строк.</span><span class="sxs-lookup"><span data-stu-id="70a72-263">Table Storage for structured datasets, accessible via row keys.</span></span>

-   <span data-ttu-id="70a72-264">Хранилище очередей для надежного обмена сообщениями на основе очередей.</span><span class="sxs-lookup"><span data-stu-id="70a72-264">Queue Storage for reliable queue-based messaging.</span></span>

-   <span data-ttu-id="70a72-265">Хранилище файлов для совместного доступа к файлам между виртуальными машинами Azure и локальными приложениями.</span><span class="sxs-lookup"><span data-stu-id="70a72-265">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="70a72-266">**Ссылки — хранилище Azure**</span><span class="sxs-lookup"><span data-stu-id="70a72-266">**References – Azure Storage**</span></span>

-   <span data-ttu-id="70a72-267">Общие сведения о хранилище Azure\\</span><span class="sxs-lookup"><span data-stu-id="70a72-267">Azure Storage Introduction\\</span></span>
    <https://docs.microsoft.com/azure/storage/storage-introduction>

## <a name="caching"></a><span data-ttu-id="70a72-268">Кэширование</span><span class="sxs-lookup"><span data-stu-id="70a72-268">Caching</span></span>

<span data-ttu-id="70a72-269">В веб-приложениях каждый веб-запрос должен быть выполнен в максимально короткое время.</span><span class="sxs-lookup"><span data-stu-id="70a72-269">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="70a72-270">Одним из способов добиться этого является ограничение числа внешних вызовов, которые сервер должен выполнить для обработки запроса.</span><span class="sxs-lookup"><span data-stu-id="70a72-270">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="70a72-271">Процесс кэширования предусматривает сохранение копии данных на сервере (или в другом хранилище данных, запросы к которому выполняются более эффективно по сравнению с источником данных).</span><span class="sxs-lookup"><span data-stu-id="70a72-271">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="70a72-272">Веб-приложения, в особенности традиционные многостраничные веб-приложения, для каждого запроса должны осуществлять полное построение пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="70a72-272">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="70a72-273">При этом часто требуется многократно выполнять одни и те же запросы к базе данных от одного пользовательского запроса к другому.</span><span class="sxs-lookup"><span data-stu-id="70a72-273">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="70a72-274">В большинстве случаев эти данные редко изменяются, поэтому не имеет практического смысла постоянно запрашивать их из базы данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-274">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="70a72-275">ASP.NET Core поддерживает кэширование ответов для кэширования страниц целиком, а также кэширование данных, благодаря которому обеспечивается более детальная реализация кэширования.</span><span class="sxs-lookup"><span data-stu-id="70a72-275">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="70a72-276">При реализации кэширования важно учитывать необходимость разделения задач.</span><span class="sxs-lookup"><span data-stu-id="70a72-276">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="70a72-277">Рекомендуется избегать кэширования логики в логике доступа к данным или в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="70a72-277">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="70a72-278">Вместо этого следует инкапсулировать кэширование в собственных классах и использовать конфигурацию для управления ее поведением.</span><span class="sxs-lookup"><span data-stu-id="70a72-278">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="70a72-279">Такой подход соответствует принципам открытости/закрытости и единственной обязанности, позволяя управлять использованием кэширования в приложении по мере его расширения.</span><span class="sxs-lookup"><span data-stu-id="70a72-279">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="70a72-280">Кэширование ответов в ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="70a72-280">ASP.NET Core Response Caching</span></span>

<span data-ttu-id="70a72-281">ASP.NET Core поддерживает два уровня кэширования ответов.</span><span class="sxs-lookup"><span data-stu-id="70a72-281">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="70a72-282">На первом уровне на сервере ничего не кэшируется, однако добавляются заголовки HTTP с инструкциями по кэшированию ответов для клиентов и прокси-серверов.</span><span class="sxs-lookup"><span data-stu-id="70a72-282">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="70a72-283">Это реализуется путем добавления атрибута ResponseCache к отдельным контроллерам или действиям:</span><span class="sxs-lookup"><span data-stu-id="70a72-283">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

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

<span data-ttu-id="70a72-284">ПО промежуточного слоя для кэширования ответов будет автоматически кэшировать ответы на основе набора условий, которые при необходимости можно настроить.</span><span class="sxs-lookup"><span data-stu-id="70a72-284">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="70a72-285">По умолчанию кэшируются только ответы 200 (OK) на запросы, выполненные с помощью методов GET или HEAD.</span><span class="sxs-lookup"><span data-stu-id="70a72-285">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="70a72-286">Кроме того, запросы должны иметь ответ Cache-Control: открытый заголовок и не могут включать заголовки для Authorization или Set-Cookie.</span><span class="sxs-lookup"><span data-stu-id="70a72-286">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="70a72-287">См. [полный перечень условий кэширования, применяемых ПО промежуточного уровня для кэширования ответов](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span><span class="sxs-lookup"><span data-stu-id="70a72-287">See a [complete list of the caching conditions used by the response caching middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="70a72-288">Кэширование данных</span><span class="sxs-lookup"><span data-stu-id="70a72-288">Data Caching</span></span>

<span data-ttu-id="70a72-289">Вместо кэширования полных веб-ответов или в дополнение к нему вы можете кэшировать результаты отдельных запросов данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-289">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="70a72-290">Для этого вы можете использовать кэширование в памяти на веб-сервере или [распределенный кэш](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span><span class="sxs-lookup"><span data-stu-id="70a72-290">For this, you can use in memory caching on the web server, or use [a distributed cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="70a72-291">В этом разделе демонстрируется, как реализовать кэширование в памяти.</span><span class="sxs-lookup"><span data-stu-id="70a72-291">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="70a72-292">Поддержка кэширования в памяти (или распределенного кэша) добавляется в ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="70a72-292">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="70a72-293">Также не забудьте добавить пакет Microsoft.Extensions.Caching.Memory NuGet.</span><span class="sxs-lookup"><span data-stu-id="70a72-293">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="70a72-294">После добавления службы вы выполняете запрос IMemoryCache посредством внедрения зависимостей каждый раз, когда вам требуется доступ к кэшу.</span><span class="sxs-lookup"><span data-stu-id="70a72-294">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="70a72-295">В этом примере служба CachedCatalogService использует конструктивный шаблон прокси-сервера (или декоратора), предоставляя альтернативную реализацию ICatalogService, которая управляет доступом к базовой реализации CatalogService или дополняет ее поведение.</span><span class="sxs-lookup"><span data-stu-id="70a72-295">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

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

<span data-ttu-id="70a72-296">Чтобы настроить приложение для использования кэшированной версии службы и при этом разрешить службе получать экземпляр CatalogService, который требуется в ее конструкторе, вам необходимо добавить следующий код в ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="70a72-296">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="70a72-297">После этого вызовы базы данных для получения данных каталога будут выполняться только один раз в минуту, а не при каждом запросе.</span><span class="sxs-lookup"><span data-stu-id="70a72-297">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="70a72-298">В зависимости от объема трафика на сайте это может в значительной степени повлиять на число запросов к базе данных и среднее время загрузки домашней страницы, которое на данный момент зависит от всех трех запросов, предоставляемых этой службой.</span><span class="sxs-lookup"><span data-stu-id="70a72-298">Depending on the traffic to the site, this can have a very significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="70a72-299">При использовании кэширования возникает проблема *устаревших данных*, то есть данных, которые были изменены в источнике, но для которых в кэше хранится устаревшая версия.</span><span class="sxs-lookup"><span data-stu-id="70a72-299">An issue that arises when caching is implemented is *stale data* – that is, data that has changed at the source but an out of date version remains in the cache.</span></span> <span data-ttu-id="70a72-300">Самый простой способ устранить эту проблему заключается в сокращении продолжительности кэширования, поскольку в приложениях с высоким уровнем загрузки увеличение продолжительности кэширования данных дает минимальные преимущества.</span><span class="sxs-lookup"><span data-stu-id="70a72-300">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="70a72-301">Рассмотрим страницу, которая выполняет 1 запрос к базе данных, который повторяется 10 раз в секунду.</span><span class="sxs-lookup"><span data-stu-id="70a72-301">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="70a72-302">Если эта страница будет кэшироваться 1 раз в минуту, число запросов к базе данных за минуту уменьшится с 600 до 1, то есть на 99,8 %.</span><span class="sxs-lookup"><span data-stu-id="70a72-302">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="70a72-303">Если вместо этого задать продолжительность кэширования равной 1 часу, число запросов сократится на 99,997 %, однако при этом значительно увеличится вероятность и потенциальный "возраст" устаревших данных.</span><span class="sxs-lookup"><span data-stu-id="70a72-303">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="70a72-304">Другой подход заключается в упреждающем удалении записей кэша при обновлении данных, которые они содержат.</span><span class="sxs-lookup"><span data-stu-id="70a72-304">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="70a72-305">Любую отдельную запись можно удалить по ее ключу:</span><span class="sxs-lookup"><span data-stu-id="70a72-305">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="70a72-306">Если в вашем приложении предоставляются функции обновления кэшируемых записей, вы можете удалять соответствующие записи кэша в коде, который выполняет обновления.</span><span class="sxs-lookup"><span data-stu-id="70a72-306">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="70a72-307">В некоторых случаях от конкретного набора данных может зависеть множество различных записей.</span><span class="sxs-lookup"><span data-stu-id="70a72-307">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="70a72-308">В таких ситуациях рекомендуется создать зависимости между записями кэша с помощью CancellationChangeToken.</span><span class="sxs-lookup"><span data-stu-id="70a72-308">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="70a72-309">Используя CancellationChangeToken, вы можете одновременно завершить срок действия нескольких записей, аннулировав маркер.</span><span class="sxs-lookup"><span data-stu-id="70a72-309">With a CancellationChangeToken, you can expire multiple cache entries at once by cancelling the token.</span></span>

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
<span data-ttu-id="70a72-310">[Назад] (develop-asp-net-core-mvc-apps.md) [Далее] (test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="70a72-310">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span></span>
