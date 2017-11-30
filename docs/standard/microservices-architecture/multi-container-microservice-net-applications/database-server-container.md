---
title: "Сервер баз данных, работа в качестве контейнера"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Сервер баз данных, работа в качестве контейнера"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7e5f33c4e7edf9d0d4551c5125976fcb8fda392f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="d787e-104">Сервер баз данных, работа в качестве контейнера</span><span class="sxs-lookup"><span data-stu-id="d787e-104">Using a database server running as a container</span></span>

<span data-ttu-id="d787e-105">Регулярные автономных серверах, в локальных кластерах, или PaaS служб в облаке, такая как база данных SQL Azure может быть баз данных (SQL Server, PostgreSQL, MySQL, т. д.).</span><span class="sxs-lookup"><span data-stu-id="d787e-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="d787e-106">Тем не менее, для сред разработки и тестирования, наличие баз данных под управлением как контейнеры является удобным, так как у вас все внешние зависимости и просто работает составления docker команда запускает всего приложения.</span><span class="sxs-lookup"><span data-stu-id="d787e-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency, and simply running the docker-compose command starts the whole application.</span></span> <span data-ttu-id="d787e-107">Наличие таких баз данных как контейнеры это отлично подходит для тестирования интеграции, поскольку базы данных запускается в контейнере и всегда заполняется образцов данных, поэтому тесты могут быть более предсказуемым.</span><span class="sxs-lookup"><span data-stu-id="d787e-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="d787e-108">SQL Server, запущенный в качестве контейнера с базой данных, связанных с микрослужбу</span><span class="sxs-lookup"><span data-stu-id="d787e-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="d787e-109">В eShopOnContainers, является контейнер с именем sql.data, определенные в [docker compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) под управлением SQL Server для Linux всеми базами данных SQL Server, необходимые для микрослужбами файла.</span><span class="sxs-lookup"><span data-stu-id="d787e-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="d787e-110">(Можно также указать один контейнер SQL Server для каждой базы данных, но для этого требуется больше памяти, назначенный Docker). Важно в микрослужбами, что каждый микрослужбу принадлежат соответствующими данными, таким образом его связанной базы данных SQL в этом случае.</span><span class="sxs-lookup"><span data-stu-id="d787e-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="d787e-111">Однако базы данных может находиться в любом месте.</span><span class="sxs-lookup"><span data-stu-id="d787e-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="d787e-112">SQL Server, настроенного контейнера в демонстрационном приложении следующим кодом YAML в файле docker compose.yml, который выполняется при запуске docker образуют вверх.</span><span class="sxs-lookup"><span data-stu-id="d787e-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run docker-compose up.</span></span> <span data-ttu-id="d787e-113">Обратите внимание, что код YAML консолидированные сведения о конфигурации из файл универсального docker-compose.yml и docker compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="d787e-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="d787e-114">(Обычно бы отдельные параметры среды из базового или статические сведения, относящиеся к образа SQL Server.)</span><span class="sxs-lookup"><span data-stu-id="d787e-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

<span data-ttu-id="d787e-115">Следующие docker, выполните команду можно выполнить этот контейнер.</span><span class="sxs-lookup"><span data-stu-id="d787e-115">The following docker run command can run that container:</span></span>

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

<span data-ttu-id="d787e-116">Тем не менее, при развертывании приложения несколькими контейнера, как eShopOnContainers более удобно использовать docker составления копию команды, чтобы она развертывалась все контейнеры, необходимые для приложения.</span><span class="sxs-lookup"><span data-stu-id="d787e-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the docker-compose up command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="d787e-117">При запуске этого контейнера SQL Server в первый раз контейнера инициализирует SQL Server с помощью пароля, который предоставляется.</span><span class="sxs-lookup"><span data-stu-id="d787e-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="d787e-118">После запуска SQL Server в качестве контейнера можно обновить базу данных, подключившись с помощью любого обычное соединение SQL, таких как в SQL Server Management Studio, Visual Studio или C\# кода.</span><span class="sxs-lookup"><span data-stu-id="d787e-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="d787e-119">Приложение eShopOnContainers инициализирует каждой базы данных микрослужбу с образцами данных, ее заполнение данными во время запуска, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="d787e-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="d787e-120">SQL Server, работающий в качестве контейнера бесполезно просто для демонстрации которых у вас нет доступа к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d787e-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="d787e-121">Как отмечено выше это также отлично подходит для среды разработки и тестирования, можно легко выполнять тесты интеграции с чистой образа SQL Server и известных данных путем заполнения новый образец данных.</span><span class="sxs-lookup"><span data-stu-id="d787e-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="d787e-122">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="d787e-122">Additional resources</span></span>

-   <span data-ttu-id="d787e-123">**Запускать образ SQL Server Docker в Windows, Mac или Linux**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span><span class="sxs-lookup"><span data-stu-id="d787e-123">**Run the SQL Server Docker image on Linux, Mac, or Windows**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span></span>

-   <span data-ttu-id="d787e-124">**Подключения и запроса SQL Server в Linux с помощью sqlcmd**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="d787e-124">**Connect and query SQL Server on Linux with sqlcmd**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span></span>

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="d787e-125">Заполнение тестовыми данными при запуске веб-приложения</span><span class="sxs-lookup"><span data-stu-id="d787e-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="d787e-126">Чтобы добавить данные в базу данных при запуске приложения, Настройка метода в класс запуска проекта веб-API можно добавить код, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="d787e-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

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

<span data-ttu-id="d787e-127">Следующий код в пользовательском классе CatalogContextSeed заполняет данные.</span><span class="sxs-lookup"><span data-stu-id="d787e-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

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

<span data-ttu-id="d787e-128">При выполнении тестов интеграции, полезно наличие способа для создания согласованных с тестами интеграции данных.</span><span class="sxs-lookup"><span data-stu-id="d787e-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="d787e-129">Возможность создать установку с нуля, включая экземпляр SQL Server на контейнер, отлично подходит для тестовых сред.</span><span class="sxs-lookup"><span data-stu-id="d787e-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="d787e-130">Базы данных основной InMemory EF ее SQL Server, работающий в качестве контейнера</span><span class="sxs-lookup"><span data-stu-id="d787e-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="d787e-131">Другой при выполнении тестов рекомендуется использовать поставщик Entity Framework InMemory базы данных.</span><span class="sxs-lookup"><span data-stu-id="d787e-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="d787e-132">Конфигурации можно указать в методе ConfigureServices запуска класса в проекте веб-API:</span><span class="sxs-lookup"><span data-stu-id="d787e-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

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

<span data-ttu-id="d787e-133">Хотя есть важные catch.</span><span class="sxs-lookup"><span data-stu-id="d787e-133">There is an important catch, though.</span></span> <span data-ttu-id="d787e-134">Базы данных в памяти не поддерживает многие ограничения, относящиеся к определенной базе данных.</span><span class="sxs-lookup"><span data-stu-id="d787e-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="d787e-135">Для экземпляра может добавлять уникальный индекс по столбцу в модели EF Core и написать тест, к базе данных в памяти для проверки того, что он не позволяет добавить повторяющееся значение.</span><span class="sxs-lookup"><span data-stu-id="d787e-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="d787e-136">Однако при использовании базы данных в памяти, не может обрабатывать уникальные индексы на столбце.</span><span class="sxs-lookup"><span data-stu-id="d787e-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="d787e-137">Таким образом, базы данных в памяти не ведут себя так же, как реальной базы данных SQL Server — не эмулирует ограничения, специфические для базы данных.</span><span class="sxs-lookup"><span data-stu-id="d787e-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="d787e-138">Тем не менее выполняющейся в памяти базы данных по-прежнему можно использовать для тестирования и создания прототипов.</span><span class="sxs-lookup"><span data-stu-id="d787e-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="d787e-139">Но если вы хотите создать точные интеграционных тестов, которые учитывают поведение реализации определенной базы данных, необходимо использовать реальной базы данных, как SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d787e-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="d787e-140">Для этой цели под управлением SQL Server в контейнере — лучшие choice и более точны, чем поставщик EF InMemory основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="d787e-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="d787e-141">Использование службы кэша Redis, запущенные в контейнере</span><span class="sxs-lookup"><span data-stu-id="d787e-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="d787e-142">Redis можно запускать на контейнер, особенно полезен для разработки и тестирования и подтверждение концепции сценариев.</span><span class="sxs-lookup"><span data-stu-id="d787e-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="d787e-143">Этот сценарий удобен, поскольку может быть все зависимости, работающих на контейнеры — не только компьютеры локальной разработки, но для сред тестирования в конвейеры CI или компакт-диска.</span><span class="sxs-lookup"><span data-stu-id="d787e-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="d787e-144">Тем не менее при выполнении Redis в рабочей среде, лучше искать решения высокого уровня доступности, как Redis Microsoft Azure, в который выполняется как PaaS (платформа как услуга).</span><span class="sxs-lookup"><span data-stu-id="d787e-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="d787e-145">В коде необходимо просто изменить строки подключения.</span><span class="sxs-lookup"><span data-stu-id="d787e-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="d787e-146">Redis предоставляет образа Docker с помощью Redis.</span><span class="sxs-lookup"><span data-stu-id="d787e-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="d787e-147">Этот образ доступен из Docker Hub на этот URL-адрес:</span><span class="sxs-lookup"><span data-stu-id="d787e-147">That image is available from Docker Hub at this URL:</span></span>

<span data-ttu-id="d787e-148"><https://Hub.docker.com/_/redis/></span><span class="sxs-lookup"><span data-stu-id="d787e-148"><https://hub.docker.com/_/redis/></span></span>

<span data-ttu-id="d787e-149">Можно напрямую запускать контейнер Docker Redis, выполнив в командной строке следующую команду Docker CLI:</span><span class="sxs-lookup"><span data-stu-id="d787e-149">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```
  docker run --name some-redis -d redis
```

<span data-ttu-id="d787e-150">Изображение Redis включает предоставляют: 6379 (порт, используемый Redis), поэтому стандартные связывание контейнера будет передан автоматически связанных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="d787e-150">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="d787e-151">В eShopOnContainers микрослужбу basket.api использует кэш Redis под управлением как контейнер.</span><span class="sxs-lookup"><span data-stu-id="d787e-151">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="d787e-152">Этот контейнер basket.data определяется как часть файла несколькими контейнера docker-compose.yml, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d787e-152">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="d787e-153">Этот код в docker-compose.yml определяет контейнер с именем basket.data на основе образа redis и публикации порт 6379 внутренне, это означает, что он будет доступен только из других контейнеров, работающих на узле Docker.</span><span class="sxs-lookup"><span data-stu-id="d787e-153">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="d787e-154">Наконец в файле docker compose.override.yml микрослужбу basket.api eShopOnContainers пример определяет строку подключения для этого контейнера Redis:</span><span class="sxs-lookup"><span data-stu-id="d787e-154">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
<span data-ttu-id="d787e-155">[Предыдущие] (/-container-приложения docker-compose.md) [Далее] (интеграция событие — на основе микрослужбу communications.md)</span><span class="sxs-lookup"><span data-stu-id="d787e-155">[Previous] (multi-container-applications-docker-compose.md) [Next] (integration-event-based-microservice-communications.md)</span></span>
