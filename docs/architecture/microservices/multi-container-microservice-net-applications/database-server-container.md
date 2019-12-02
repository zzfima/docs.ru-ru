---
title: Использование сервера баз данных, работающего в качестве контейнера
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Использование сервера баз данных, работающего в качестве контейнера? Только для разработки! Давайте поймем, почему.
ms.date: 10/02/2018
ms.openlocfilehash: 371d622dc39681edb0b52e723faccbf611b7797c
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568435"
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="5cd81-104">Использование сервера баз данных, работающего в качестве контейнера</span><span class="sxs-lookup"><span data-stu-id="5cd81-104">Using a database server running as a container</span></span>

<span data-ttu-id="5cd81-105">Базы данных (SQL Server, PostgreSQL, MySQL и т. д.) можно размещать на обычных отдельных серверах, локальных кластерах или службах PaaS в облаке, например Azure SQL DB.</span><span class="sxs-lookup"><span data-stu-id="5cd81-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="5cd81-106">Но в средах разработки и тестирования удобнее использовать базы данных в виде контейнеров — так у вас нет внешней зависимости, и вы можете запустить все приложение по команде `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="5cd81-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency and simply running the `docker-compose up` command starts the whole application.</span></span> <span data-ttu-id="5cd81-107">При размещении баз данных в контейнерах легче проводить интеграционные тесты, ведь база данных запускается в контейнере и всегда заполняется одинаковыми демонстрационными данными, так что тестирование становится более предсказуемым.</span><span class="sxs-lookup"><span data-stu-id="5cd81-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="5cd81-108">SQL Server, запущенный в качестве контейнера с базой данных для микрослужб</span><span class="sxs-lookup"><span data-stu-id="5cd81-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="5cd81-109">В eShopOnContainers существует контейнер с именем sql.data, определенный в файле [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml), который запускает SQL Server для Linux со всеми базами данных на SQL Server, необходимыми для микрослужб.</span><span class="sxs-lookup"><span data-stu-id="5cd81-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="5cd81-110">(Вы можете использовать один контейнер SQL Server для каждой базы данных, но придется выделить для Docker больше памяти.) Важно отметить, что каждая микрослужба владеет связанными с ней данными, в данном случае — базой данных SQL.</span><span class="sxs-lookup"><span data-stu-id="5cd81-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="5cd81-111">Но базы данных могут находиться где угодно.</span><span class="sxs-lookup"><span data-stu-id="5cd81-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="5cd81-112">Контейнер SQL Server в примере приложения настроен со следующим кодом YAML в файле docker-compose.yml, который выполняется по команде `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="5cd81-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run `docker-compose up`.</span></span> <span data-ttu-id="5cd81-113">Обратите внимание, что код YAML содержит консолидированные сведения о конфигурации из общего файла docker-compose.yml и файла docker-compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="5cd81-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="5cd81-114">(В обычной ситуации вы отделяете параметры среды от базовой или статической информации, связанной с образом SQL Server.)</span><span class="sxs-lookup"><span data-stu-id="5cd81-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
  sql.data:
    image: microsoft/mssql-server-linux:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

<span data-ttu-id="5cd81-115">Аналогичным образом, вместо `docker-compose` используйте следующую команду `docker run` для запуска контейнера:</span><span class="sxs-lookup"><span data-stu-id="5cd81-115">In a similar way, instead of using `docker-compose`, the following `docker run` command can run that container:</span></span>

```console
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d microsoft/mssql-server-linux:2017-latest
```

<span data-ttu-id="5cd81-116">Но если вы развертываете приложение с несколькими контейнерами, например eShopOnContainers, удобнее использовать команду `docker-compose up`, чтобы развернуть все необходимые контейнеры для приложения.</span><span class="sxs-lookup"><span data-stu-id="5cd81-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the `docker-compose up` command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="5cd81-117">Когда вы запускаете этот контейнер SQL Server впервые, он инициализирует SQL Server с помощью указанного вами пароля.</span><span class="sxs-lookup"><span data-stu-id="5cd81-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="5cd81-118">После запуска SQL Server в качестве контейнера вы можете обновить базу данных через обычное подключение SQL, например SQL Server Management Studio, Visual Studio или код C\#.</span><span class="sxs-lookup"><span data-stu-id="5cd81-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="5cd81-119">Приложение eShopOnContainers инициализирует каждую базу данных микрослужбы, заполняя ее демонстрационными данными при запуске, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="5cd81-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="5cd81-120">Использовать SQL Server в качестве контейнера удобно не только для демоверсии, где у вас может не быть доступа к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5cd81-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="5cd81-121">Это решение также отлично подходит для среды разработки и тестирования, где вы можете легко запустить интеграционные тесты из чистого образа SQL Server с известными данными, присвоив новые демонстрационные данные.</span><span class="sxs-lookup"><span data-stu-id="5cd81-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="5cd81-122">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="5cd81-122">Additional resources</span></span>

- <span data-ttu-id="5cd81-123">**Запуск образа SQL Server Docker в Linux, Mac или Windows** </span><span class="sxs-lookup"><span data-stu-id="5cd81-123">**Run the SQL Server Docker image on Linux, Mac, or Windows** </span></span>\
    [https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker](/sql/linux/sql-server-linux-setup-docker)

- <span data-ttu-id="5cd81-124">**Подключения и запросы к SQL Server на Linux с помощью sqlcmd** </span><span class="sxs-lookup"><span data-stu-id="5cd81-124">**Connect and query SQL Server on Linux with sqlcmd** </span></span>\
    [https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd](/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="5cd81-125">Заполнение тестовыми данными при запуске веб-приложения</span><span class="sxs-lookup"><span data-stu-id="5cd81-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="5cd81-126">Чтобы заполнить базу данных данными при запуске приложения, вы можете добавить код, как указано ниже, в метод Configure в классе Startup проекта веб-API:</span><span class="sxs-lookup"><span data-stu-id="5cd81-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code...
    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure code...
        // Seed data through our custom class
        CatalogContextSeed.SeedAsync(app)
            .Wait();
        // Other Configure code...
    }
}
```

<span data-ttu-id="5cd81-127">Следующий код в пользовательском классе CatalogContextSeed заполняет базу данных данными.</span><span class="sxs-lookup"><span data-stu-id="5cd81-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

```csharp
public class CatalogContextSeed
{
    public static async Task SeedAsync(IApplicationBuilder applicationBuilder)
    {
        var context = (CatalogContext)applicationBuilder
            .ApplicationServices.GetService(typeof(CatalogContext));
        using (context)
        {
            context.Database.Migrate();
            if (!context.CatalogBrands.Any())
            {
                context.CatalogBrands.AddRange(
                    GetPreconfiguredCatalogBrands());
                await context.SaveChangesAsync();
            }
            if (!context.CatalogTypes.Any())
            {
                context.CatalogTypes.AddRange(
                    GetPreconfiguredCatalogTypes());
                await context.SaveChangesAsync();
            }
        }
    }

    static IEnumerable<CatalogBrand> GetPreconfiguredCatalogBrands()
    {
        return new List<CatalogBrand>()
       {
           new CatalogBrand() { Brand = "Azure"},
           new CatalogBrand() { Brand = ".NET" },
           new CatalogBrand() { Brand = "Visual Studio" },
           new CatalogBrand() { Brand = "SQL Server" }
       };
    }

    static IEnumerable<CatalogType> GetPreconfiguredCatalogTypes()
    {
        return new List<CatalogType>()
        {
            new CatalogType() { Type = "Mug"},
            new CatalogType() { Type = "T-Shirt" },
            new CatalogType() { Type = "Backpack" },
            new CatalogType() { Type = "USB Memory Stick" }
        };
    }
}
```

<span data-ttu-id="5cd81-128">При выполнении интеграционных тестов полезно иметь возможность создавать данные, соответствующие тестам.</span><span class="sxs-lookup"><span data-stu-id="5cd81-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="5cd81-129">Возможность создать все с нуля, включая экземпляр SQL Server в контейнере, имеет серьезные преимущества для тестовых сред.</span><span class="sxs-lookup"><span data-stu-id="5cd81-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="5cd81-130">База данных EF Core InMemory и SQL Server, работающий в качестве контейнера</span><span class="sxs-lookup"><span data-stu-id="5cd81-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="5cd81-131">Еще одно удачное решение для выполнения тестов — использовать базы данных Entity Framework InMemory.</span><span class="sxs-lookup"><span data-stu-id="5cd81-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="5cd81-132">Вы можете указать эту конфигурацию в методе ConfigureServices в классе Startup в проекте веб-API:</span><span class="sxs-lookup"><span data-stu-id="5cd81-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code ...
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddSingleton<IConfiguration>(Configuration);
        // DbContext using an InMemory database provider
        services.AddDbContext<CatalogContext>(opt => opt.UseInMemoryDatabase());
        //(Alternative: DbContext using a SQL Server provider
        //services.AddDbContext<CatalogContext>(c =>
        //{
            // c.UseSqlServer(Configuration["ConnectionString"]);
            //
        //});
    }
  
    // Other Startup code ...
}
```

<span data-ttu-id="5cd81-133">Но есть одна сложность.</span><span class="sxs-lookup"><span data-stu-id="5cd81-133">There is an important catch, though.</span></span> <span data-ttu-id="5cd81-134">База данных, выполняющаяся в памяти, не поддерживает многие ограничения, относящиеся к определенной базе данных.</span><span class="sxs-lookup"><span data-stu-id="5cd81-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="5cd81-135">Например, вы можете добавить уникальный индекс в столбец в модели EF Core и написать тест для базы данных, выполняющейся в памяти, чтобы проверить, что она не позволяет вам добавлять дублирующие значения.</span><span class="sxs-lookup"><span data-stu-id="5cd81-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="5cd81-136">Но при использовании базы данных, выполняющейся в памяти, вы не можете обрабатывать уникальные индексы в столбце.</span><span class="sxs-lookup"><span data-stu-id="5cd81-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="5cd81-137">Таким образом, базы данных, выполняющиеся в памяти, ведут себя не так, как реальные базы данных SQL Server, — они не эмулируют ограничения, присущие базе данных.</span><span class="sxs-lookup"><span data-stu-id="5cd81-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="5cd81-138">Тем не менее выполняющаяся в памяти база данных подходит для тестирования и создания прототипов.</span><span class="sxs-lookup"><span data-stu-id="5cd81-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="5cd81-139">Но если вы хотите создать точные интеграционные тесты, которые учитывают поведение определенной базы данных, используйте реальную базу данных, например SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5cd81-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="5cd81-140">Для этих целей лучше всего использовать SQL Server в контейнере, поскольку результат будет более точным, чем в базе данных EF Core InMemory.</span><span class="sxs-lookup"><span data-stu-id="5cd81-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="5cd81-141">Использование службы кэша Redis в контейнере</span><span class="sxs-lookup"><span data-stu-id="5cd81-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="5cd81-142">Вы можете запустить Redis в контейнере, особенно для разработки и тестирования, а также подтверждения концепции.</span><span class="sxs-lookup"><span data-stu-id="5cd81-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="5cd81-143">Это удобное решение, поскольку все ваши зависимости будут выполняться в контейнерах — не только на локальных компьютерах для разработки, но и в тестовых средах в конвейерах непрерывной интеграции или поставки.</span><span class="sxs-lookup"><span data-stu-id="5cd81-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="5cd81-144">Но если вы используете Redis в рабочей среде, лучше найти решение с более высоким уровнем доступности, например Redis Microsoft Azure, которое работает как PaaS (платформа как услуга).</span><span class="sxs-lookup"><span data-stu-id="5cd81-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="5cd81-145">В коде достаточно изменить строки подключения.</span><span class="sxs-lookup"><span data-stu-id="5cd81-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="5cd81-146">Redis предоставляет образ Docker с Redis.</span><span class="sxs-lookup"><span data-stu-id="5cd81-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="5cd81-147">Этот образ доступен в центре Docker по URL-адресу:</span><span class="sxs-lookup"><span data-stu-id="5cd81-147">That image is available from Docker Hub at this URL:</span></span>

<https://hub.docker.com/_/redis/>

<span data-ttu-id="5cd81-148">Вы можете запустить контейнер Docker Redis напрямую, выполнив следующую команду Docker CLI в командной строке:</span><span class="sxs-lookup"><span data-stu-id="5cd81-148">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```console
docker run --name some-redis -d redis
```

<span data-ttu-id="5cd81-149">Образ Redis включает expose:6379 (порт, используемый Redis), поэтому при стандартном связывании контейнеров он будет автоматически доступен связанным контейнерам.</span><span class="sxs-lookup"><span data-stu-id="5cd81-149">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="5cd81-150">В eShopOnContainers микрослужба basket.api использует кэш Redis как контейнер.</span><span class="sxs-lookup"><span data-stu-id="5cd81-150">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="5cd81-151">Этот контейнер basket.data определяется как часть файла docker-compose.yml с несколькими контейнерами, как показано в примере:</span><span class="sxs-lookup"><span data-stu-id="5cd81-151">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="5cd81-152">Этот код в файле docker-compose.yml определяет контейнер с именем basket.data на основе образа Redis и с внутренней публикацией порта 6379. Поэтому он будет доступен только из контейнеров, выполняемых в этом узле Docker.</span><span class="sxs-lookup"><span data-stu-id="5cd81-152">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="5cd81-153">Наконец, в файле docker-compose.override.yml микрослужба basket.api для примера приложения eShopOnContainers определяет строку подключения, используемую для этого контейнера Redis:</span><span class="sxs-lookup"><span data-stu-id="5cd81-153">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```

<span data-ttu-id="5cd81-154">Как упоминалось ранее, имя микрослужбы "basket.data" разрешается с помощью DNS внутренней сети docker.</span><span class="sxs-lookup"><span data-stu-id="5cd81-154">As mentioned before, the name of the microservice "basket.data" is resolved by docker's internal network DNS.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5cd81-155">[Назад](multi-container-applications-docker-compose.md)
>[Вперед](integration-event-based-microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="5cd81-155">[Previous](multi-container-applications-docker-compose.md)
[Next](integration-event-based-microservice-communications.md)</span></span>
