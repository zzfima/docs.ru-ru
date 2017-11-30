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
# <a name="using-a-database-server-running-as-a-container"></a>Сервер баз данных, работа в качестве контейнера

Регулярные автономных серверах, в локальных кластерах, или PaaS служб в облаке, такая как база данных SQL Azure может быть баз данных (SQL Server, PostgreSQL, MySQL, т. д.). Тем не менее, для сред разработки и тестирования, наличие баз данных под управлением как контейнеры является удобным, так как у вас все внешние зависимости и просто работает составления docker команда запускает всего приложения. Наличие таких баз данных как контейнеры это отлично подходит для тестирования интеграции, поскольку базы данных запускается в контейнере и всегда заполняется образцов данных, поэтому тесты могут быть более предсказуемым.

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server, запущенный в качестве контейнера с базой данных, связанных с микрослужбу

В eShopOnContainers, является контейнер с именем sql.data, определенные в [docker compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) под управлением SQL Server для Linux всеми базами данных SQL Server, необходимые для микрослужбами файла. (Можно также указать один контейнер SQL Server для каждой базы данных, но для этого требуется больше памяти, назначенный Docker). Важно в микрослужбами, что каждый микрослужбу принадлежат соответствующими данными, таким образом его связанной базы данных SQL в этом случае. Однако базы данных может находиться в любом месте.

SQL Server, настроенного контейнера в демонстрационном приложении следующим кодом YAML в файле docker compose.yml, который выполняется при запуске docker образуют вверх. Обратите внимание, что код YAML консолидированные сведения о конфигурации из файл универсального docker-compose.yml и docker compose.override.yml. (Обычно бы отдельные параметры среды из базового или статические сведения, относящиеся к образа SQL Server.)

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

Следующие docker, выполните команду можно выполнить этот контейнер.

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

Тем не менее, при развертывании приложения несколькими контейнера, как eShopOnContainers более удобно использовать docker составления копию команды, чтобы она развертывалась все контейнеры, необходимые для приложения.

При запуске этого контейнера SQL Server в первый раз контейнера инициализирует SQL Server с помощью пароля, который предоставляется. После запуска SQL Server в качестве контейнера можно обновить базу данных, подключившись с помощью любого обычное соединение SQL, таких как в SQL Server Management Studio, Visual Studio или C\# кода.

Приложение eShopOnContainers инициализирует каждой базы данных микрослужбу с образцами данных, ее заполнение данными во время запуска, как описано в следующем разделе.

SQL Server, работающий в качестве контейнера бесполезно просто для демонстрации которых у вас нет доступа к экземпляру SQL Server. Как отмечено выше это также отлично подходит для среды разработки и тестирования, можно легко выполнять тесты интеграции с чистой образа SQL Server и известных данных путем заполнения новый образец данных.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Запускать образ SQL Server Docker в Windows, Mac или Linux**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)

-   **Подключения и запроса SQL Server в Linux с помощью sqlcmd**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a>Заполнение тестовыми данными при запуске веб-приложения

Чтобы добавить данные в базу данных при запуске приложения, Настройка метода в класс запуска проекта веб-API можно добавить код, аналогичный следующему:

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

Следующий код в пользовательском классе CatalogContextSeed заполняет данные.

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

При выполнении тестов интеграции, полезно наличие способа для создания согласованных с тестами интеграции данных. Возможность создать установку с нуля, включая экземпляр SQL Server на контейнер, отлично подходит для тестовых сред.

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>Базы данных основной InMemory EF ее SQL Server, работающий в качестве контейнера

Другой при выполнении тестов рекомендуется использовать поставщик Entity Framework InMemory базы данных. Конфигурации можно указать в методе ConfigureServices запуска класса в проекте веб-API:

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

Хотя есть важные catch. Базы данных в памяти не поддерживает многие ограничения, относящиеся к определенной базе данных. Для экземпляра может добавлять уникальный индекс по столбцу в модели EF Core и написать тест, к базе данных в памяти для проверки того, что он не позволяет добавить повторяющееся значение. Однако при использовании базы данных в памяти, не может обрабатывать уникальные индексы на столбце. Таким образом, базы данных в памяти не ведут себя так же, как реальной базы данных SQL Server — не эмулирует ограничения, специфические для базы данных.

Тем не менее выполняющейся в памяти базы данных по-прежнему можно использовать для тестирования и создания прототипов. Но если вы хотите создать точные интеграционных тестов, которые учитывают поведение реализации определенной базы данных, необходимо использовать реальной базы данных, как SQL Server. Для этой цели под управлением SQL Server в контейнере — лучшие choice и более точны, чем поставщик EF InMemory основной базы данных.

### <a name="using-a-redis-cache-service-running-in-a-container"></a>Использование службы кэша Redis, запущенные в контейнере

Redis можно запускать на контейнер, особенно полезен для разработки и тестирования и подтверждение концепции сценариев. Этот сценарий удобен, поскольку может быть все зависимости, работающих на контейнеры — не только компьютеры локальной разработки, но для сред тестирования в конвейеры CI или компакт-диска.

Тем не менее при выполнении Redis в рабочей среде, лучше искать решения высокого уровня доступности, как Redis Microsoft Azure, в который выполняется как PaaS (платформа как услуга). В коде необходимо просто изменить строки подключения.

Redis предоставляет образа Docker с помощью Redis. Этот образ доступен из Docker Hub на этот URL-адрес:

<https://Hub.docker.com/_/redis/>

Можно напрямую запускать контейнер Docker Redis, выполнив в командной строке следующую команду Docker CLI:

```
  docker run --name some-redis -d redis
```

Изображение Redis включает предоставляют: 6379 (порт, используемый Redis), поэтому стандартные связывание контейнера будет передан автоматически связанных контейнеров.

В eShopOnContainers микрослужбу basket.api использует кэш Redis под управлением как контейнер. Этот контейнер basket.data определяется как часть файла несколькими контейнера docker-compose.yml, как показано в следующем примере:

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

Этот код в docker-compose.yml определяет контейнер с именем basket.data на основе образа redis и публикации порт 6379 внутренне, это означает, что он будет доступен только из других контейнеров, работающих на узле Docker.

Наконец в файле docker compose.override.yml микрослужбу basket.api eShopOnContainers пример определяет строку подключения для этого контейнера Redis:

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
[Предыдущие] (/-container-приложения docker-compose.md) [Далее] (интеграция событие — на основе микрослужбу communications.md)
