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
# <a name="using-a-database-server-running-as-a-container"></a>Использование сервера баз данных, работающего в качестве контейнера

Базы данных (SQL Server, PostgreSQL, MySQL и т. д.) можно размещать на обычных отдельных серверах, локальных кластерах или службах PaaS в облаке, например Azure SQL DB. Но в средах разработки и тестирования удобнее использовать базы данных в виде контейнеров — так у вас нет внешней зависимости, и вы можете запустить все приложение по команде `docker-compose up`. При размещении баз данных в контейнерах легче проводить интеграционные тесты, ведь база данных запускается в контейнере и всегда заполняется одинаковыми демонстрационными данными, так что тестирование становится более предсказуемым.

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server, запущенный в качестве контейнера с базой данных для микрослужб

В eShopOnContainers существует контейнер с именем sql.data, определенный в файле [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml), который запускает SQL Server для Linux со всеми базами данных на SQL Server, необходимыми для микрослужб. (Вы можете использовать один контейнер SQL Server для каждой базы данных, но придется выделить для Docker больше памяти.) Важно отметить, что каждая микрослужба владеет связанными с ней данными, в данном случае — базой данных SQL. Но базы данных могут находиться где угодно.

Контейнер SQL Server в примере приложения настроен со следующим кодом YAML в файле docker-compose.yml, который выполняется по команде `docker-compose up`. Обратите внимание, что код YAML содержит консолидированные сведения о конфигурации из общего файла docker-compose.yml и файла docker-compose.override.yml. (В обычной ситуации вы отделяете параметры среды от базовой или статической информации, связанной с образом SQL Server.)

```yml
  sql.data:
    image: microsoft/mssql-server-linux:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

Аналогичным образом, вместо `docker-compose` используйте следующую команду `docker run` для запуска контейнера:

```console
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d microsoft/mssql-server-linux:2017-latest
```

Но если вы развертываете приложение с несколькими контейнерами, например eShopOnContainers, удобнее использовать команду `docker-compose up`, чтобы развернуть все необходимые контейнеры для приложения.

Когда вы запускаете этот контейнер SQL Server впервые, он инициализирует SQL Server с помощью указанного вами пароля. После запуска SQL Server в качестве контейнера вы можете обновить базу данных через обычное подключение SQL, например SQL Server Management Studio, Visual Studio или код C\#.

Приложение eShopOnContainers инициализирует каждую базу данных микрослужбы, заполняя ее демонстрационными данными при запуске, как описано в следующем разделе.

Использовать SQL Server в качестве контейнера удобно не только для демоверсии, где у вас может не быть доступа к экземпляру SQL Server. Это решение также отлично подходит для среды разработки и тестирования, где вы можете легко запустить интеграционные тесты из чистого образа SQL Server с известными данными, присвоив новые демонстрационные данные.

#### <a name="additional-resources"></a>Дополнительные ресурсы

- **Запуск образа SQL Server Docker в Linux, Mac или Windows** \
    [https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker](/sql/linux/sql-server-linux-setup-docker)

- **Подключения и запросы к SQL Server на Linux с помощью sqlcmd** \
    [https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd](/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a>Заполнение тестовыми данными при запуске веб-приложения

Чтобы заполнить базу данных данными при запуске приложения, вы можете добавить код, как указано ниже, в метод Configure в классе Startup проекта веб-API:

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

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>База данных EF Core InMemory и SQL Server, работающий в качестве контейнера

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

### <a name="using-a-redis-cache-service-running-in-a-container"></a>Использование службы кэша Redis в контейнере

Вы можете запустить Redis в контейнере, особенно для разработки и тестирования, а также подтверждения концепции. Это удобное решение, поскольку все ваши зависимости будут выполняться в контейнерах — не только на локальных компьютерах для разработки, но и в тестовых средах в конвейерах непрерывной интеграции или поставки.

Но если вы используете Redis в рабочей среде, лучше найти решение с более высоким уровнем доступности, например Redis Microsoft Azure, которое работает как PaaS (платформа как услуга). В коде достаточно изменить строки подключения.

Redis предоставляет образ Docker с Redis. Этот образ доступен в центре Docker по URL-адресу:

<https://hub.docker.com/_/redis/>

Вы можете запустить контейнер Docker Redis напрямую, выполнив следующую команду Docker CLI в командной строке:

```console
docker run --name some-redis -d redis
```

Образ Redis включает expose:6379 (порт, используемый Redis), поэтому при стандартном связывании контейнеров он будет автоматически доступен связанным контейнерам.

В eShopOnContainers микрослужба basket.api использует кэш Redis как контейнер. Этот контейнер basket.data определяется как часть файла docker-compose.yml с несколькими контейнерами, как показано в примере:

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

Этот код в файле docker-compose.yml определяет контейнер с именем basket.data на основе образа Redis и с внутренней публикацией порта 6379. Поэтому он будет доступен только из контейнеров, выполняемых в этом узле Docker.

Наконец, в файле docker-compose.override.yml микрослужба basket.api для примера приложения eShopOnContainers определяет строку подключения, используемую для этого контейнера Redis:

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```

Как упоминалось ранее, имя микрослужбы "basket.data" разрешается с помощью DNS внутренней сети docker.

>[!div class="step-by-step"]
>[Назад](multi-container-applications-docker-compose.md)
>[Вперед](integration-event-based-microservice-communications.md)
