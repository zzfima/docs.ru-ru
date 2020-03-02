---
title: Использование сервера баз данных, работающего в качестве контейнера
description: Изучите важность использования сервера базы данных, работающего в качестве контейнера, только для разработки. Не для рабочей среды.
ms.date: 01/30/2020
ms.openlocfilehash: 0cbc933003aac10970814378c27e88b5cb0ddbe5
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628531"
---
# <a name="use-a-database-server-running-as-a-container"></a>Использование сервера баз данных, работающего в качестве контейнера

Базы данных (SQL Server, PostgreSQL, MySQL и т. д.) можно размещать на обычных отдельных серверах, локальных кластерах или службах PaaS в облаке, например Azure SQL DB. Но в средах разработки и тестирования удобнее использовать базы данных в виде контейнеров — так у вас нет внешней зависимости, и вы можете запустить все приложение по команде `docker-compose up`. При размещении баз данных в контейнерах легче проводить интеграционные тесты, ведь база данных запускается в контейнере и всегда заполняется одинаковыми демонстрационными данными, так что тестирование становится более предсказуемым.

## <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server, запущенный в качестве контейнера с базой данных для микрослужб

В eShopOnContainers существует контейнер с именем `sqldata`, определенный в файле [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml), который запускает SQL Server для экземпляра Linux со всеми базами данных на SQL Server, необходимыми для микрослужб.

Ключевой точкой микрослужб является то, что каждая микрослужба владеет связанными данными, поэтому она должна иметь собственную базу данных. Однако базы данных могут находиться где угодно. В этом случае все они находятся в одном контейнере, чтобы не усложнять требования к памяти Docker. Помните, что это решение является хорошим для разработки и, возможно, тестирования, но не для рабочей среды.

Контейнер SQL Server в примере приложения настроен со следующим кодом YAML в файле docker-compose.yml, который выполняется по команде `docker-compose up`. Обратите внимание, что код YAML содержит консолидированные сведения о конфигурации из общего файла docker-compose.yml и файла docker-compose.override.yml. (В обычной ситуации вы отделяете параметры среды от базовой или статической информации, связанной с образом SQL Server.)

```yml
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

Аналогичным образом, вместо `docker-compose` используйте следующую команду `docker run` для запуска контейнера:

```powershell
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```

Но если вы развертываете приложение с несколькими контейнерами, например eShopOnContainers, удобнее использовать команду `docker-compose up`, чтобы развернуть все необходимые контейнеры для приложения.

Когда вы запускаете этот контейнер SQL Server впервые, он инициализирует SQL Server с помощью указанного вами пароля. После запуска SQL Server в качестве контейнера вы можете обновить базу данных через обычное подключение SQL, например SQL Server Management Studio, Visual Studio или код C\#.

Приложение eShopOnContainers инициализирует каждую базу данных микрослужбы, заполняя ее демонстрационными данными при запуске, как описано в следующем разделе.

Использовать SQL Server в качестве контейнера удобно не только для демоверсии, где у вас может не быть доступа к экземпляру SQL Server. Это решение также отлично подходит для среды разработки и тестирования, где вы можете легко запустить интеграционные тесты из чистого образа SQL Server с известными данными, присвоив новые демонстрационные данные.

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Запуск образа SQL Server Docker в Linux, Mac или Windows** \
  <https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker>

- **Подключения и запросы к SQL Server на Linux с помощью sqlcmd** \
  <https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd>

## <a name="seeding-with-test-data-on-web-application-startup"></a>Заполнение тестовыми данными при запуске веб-приложения

Чтобы заполнить базу данных данными при запуске приложения, вы можете добавить код, как указано ниже, в метод `Main` в классе `Program` проекта веб-API:

```csharp
public static int Main(string[] args)
{
    var configuration = GetConfiguration();

    Log.Logger = CreateSerilogLogger(configuration);

    try
    {
        Log.Information("Configuring web host ({ApplicationContext})...", AppName);
        var host = CreateHostBuilder(configuration, args);

        Log.Information("Applying migrations ({ApplicationContext})...", AppName);
        host.MigrateDbContext<CatalogContext>((context, services) =>
        {
            var env = services.GetService<IWebHostEnvironment>();
            var settings = services.GetService<IOptions<CatalogSettings>>();
            var logger = services.GetService<ILogger<CatalogContextSeed>>();

            new CatalogContextSeed()
                .SeedAsync(context, env, settings, logger)
                .Wait();
        })
        .MigrateDbContext<IntegrationEventLogContext>((_, __) => { });

        Log.Information("Starting web host ({ApplicationContext})...", AppName);
        host.Run();

        return 0;
    }
    catch (Exception ex)
    {
        Log.Fatal(ex, "Program terminated unexpectedly ({ApplicationContext})!", AppName);
        return 1;
    }
    finally
    {
        Log.CloseAndFlush();
    }
}
```

При применении миграций и заполнении базы данных во время запуска контейнеров существует важная оговорка. Поскольку сервер базы данных может быть недоступен по каким-либо причинам, вы должны обрабатывать повторные попытки, пока сервер не будет доступен. Эта логика повторных попыток обрабатывается методом расширения `MigrateDbContext()`, как показано в следующем коде:

```cs
public static IWebHost MigrateDbContext<TContext>(
    this IWebHost host,
    Action<TContext,
    IServiceProvider> seeder)
      where TContext : DbContext
{
    var underK8s = host.IsInKubernetes();

    using (var scope = host.Services.CreateScope())
    {
        var services = scope.ServiceProvider;

        var logger = services.GetRequiredService<ILogger<TContext>>();

        var context = services.GetService<TContext>();

        try
        {
            logger.LogInformation("Migrating database associated with context {DbContextName}", typeof(TContext).Name);

            if (underK8s)
            {
                InvokeSeeder(seeder, context, services);
            }
            else
            {
                var retry = Policy.Handle<SqlException>()
                    .WaitAndRetry(new TimeSpan[]
                    {
                    TimeSpan.FromSeconds(3),
                    TimeSpan.FromSeconds(5),
                    TimeSpan.FromSeconds(8),
                    });

                //if the sql server container is not created on run docker compose this
                //migration can't fail for network related exception. The retry options for DbContext only
                //apply to transient exceptions
                // Note that this is NOT applied when running some orchestrators (let the orchestrator to recreate the failing service)
                retry.Execute(() => InvokeSeeder(seeder, context, services));
            }

            logger.LogInformation("Migrated database associated with context {DbContextName}", typeof(TContext).Name);
        }
        catch (Exception ex)
        {
            logger.LogError(ex, "An error occurred while migrating the database used on context {DbContextName}", typeof(TContext).Name);
            if (underK8s)
            {
                throw;          // Rethrow under k8s because we rely on k8s to re-run the pod
            }
        }
    }

    return host;
}
```

Следующий код в пользовательском классе CatalogContextSeed заполняет базу данных данными.

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

При выполнении интеграционных тестов полезно иметь возможность создавать данные, соответствующие тестам. Возможность создать все с нуля, включая экземпляр SQL Server в контейнере, имеет серьезные преимущества для тестовых сред.

## <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>База данных EF Core InMemory и SQL Server, работающий в качестве контейнера

Еще одно удачное решение для выполнения тестов — использовать базы данных Entity Framework InMemory. Вы можете указать эту конфигурацию в методе ConfigureServices в классе Startup в проекте веб-API:

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

Но есть одна сложность. База данных, выполняющаяся в памяти, не поддерживает многие ограничения, относящиеся к определенной базе данных. Например, вы можете добавить уникальный индекс в столбец в модели EF Core и написать тест для базы данных, выполняющейся в памяти, чтобы проверить, что она не позволяет вам добавлять дублирующие значения. Но при использовании базы данных, выполняющейся в памяти, вы не можете обрабатывать уникальные индексы в столбце. Таким образом, базы данных, выполняющиеся в памяти, ведут себя не так, как реальные базы данных SQL Server, — они не эмулируют ограничения, присущие базе данных.

Тем не менее выполняющаяся в памяти база данных подходит для тестирования и создания прототипов. Но если вы хотите создать точные интеграционные тесты, которые учитывают поведение определенной базы данных, используйте реальную базу данных, например SQL Server. Для этих целей лучше всего использовать SQL Server в контейнере, поскольку результат будет более точным, чем в базе данных EF Core InMemory.

## <a name="using-a-redis-cache-service-running-in-a-container"></a>Использование службы кэша Redis в контейнере

Вы можете запустить Redis в контейнере, особенно для разработки и тестирования, а также подтверждения концепции. Это удобное решение, поскольку все ваши зависимости будут выполняться в контейнерах — не только на локальных компьютерах для разработки, но и в тестовых средах в конвейерах непрерывной интеграции или поставки.

Но если вы используете Redis в рабочей среде, лучше найти решение с более высоким уровнем доступности, например Redis Microsoft Azure, которое работает как PaaS (платформа как услуга). В коде достаточно изменить строки подключения.

Redis предоставляет образ Docker с Redis. Этот образ доступен в центре Docker по URL-адресу:

<https://hub.docker.com/_/redis/>

Вы можете запустить контейнер Docker Redis напрямую, выполнив следующую команду Docker CLI в командной строке:

```console
docker run --name some-redis -d redis
```

Образ Redis включает expose:6379 (порт, используемый Redis), поэтому при стандартном связывании контейнеров он будет автоматически доступен связанным контейнерам.

В eShopOnContainers микрослужба `basket-api`использует кэш Redis как контейнер. Этот контейнер `basketdata` определяется как часть файла *docker-compose.yml* с несколькими контейнерами, как показано в примере:

```yml
#docker-compose.yml file
#...
  basketdata:
    image: redis
    expose:
      - "6379"
```

Этот код в docker-compose.yml определяет контейнер с именем `basketdata` на основе образа redis и внутренней публикации порта 6379. Это означает, что он будет доступен только из других контейнеров, работающих на узле Docker.

Наконец, в файле *docker-compose.override.yml* микрослужба `basket-api` для примера приложения eShopOnContainers определяет строку подключения, используемую для этого контейнера Redis:

```yml
  basket-api:
    environment:
      # Other data ...
      - ConnectionString=basketdata
      - EventBusConnection=rabbitmq
```

Как упоминалось ранее, имя микрослужбы `basketdata` разрешается с помощью DNS внутренней сети Docker.

>[!div class="step-by-step"]
>[Назад](multi-container-applications-docker-compose.md)
>[Вперед](integration-event-based-microservice-communications.md)
