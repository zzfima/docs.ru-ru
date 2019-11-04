---
title: Мониторинг работоспособности
description: Изучите один из способов реализации мониторинга работоспособности.
ms.date: 01/07/2019
ms.openlocfilehash: 2d43efa7b6cfb855a033ee4d766c64c2472ceb36
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094071"
---
# <a name="health-monitoring"></a>Мониторинг работоспособности

Мониторинг работоспособности позволяет практически в реальном времени получать сведения о состоянии ваших контейнеров и микрослужб. Мониторинг работоспособности очень важен для нескольких аспектов работы микрослужб и особенно важен, когда оркестраторы выполняют частичное многоэтапное обновление приложений, как описано ниже.

Приложения на основе микрослужб часто используют пульс или проверки работоспособности, чтобы системные мониторы, планировщики и оркестраторы могли отслеживать большое количество служб. Если службам не удается отправить сигнал "Я в порядке", ваше приложение может подвергнуться риску при развертывании обновлений или может просто обнаружить ошибки слишком поздно. Это приведет к каскадным сбоям, которые будет невозможно остановить, а они, в свою очередь, приведут к масштабным сбоям.

В обычной модели службы отправляют отчеты о своем состоянии, и эти сведения агрегируются для создания общего представления о состоянии работоспособности приложения. При использовании оркестратора можно предоставить сведения работоспособности кластеру оркестратора, чтобы кластер мог предпринять необходимые действия. Если воспользоваться высококачественными средствами создания отчетов о работоспособности, специально адаптированных для вашего приложения, вы сможете гораздо быстрее и эффективнее обнаруживать и устранять проблемы с приложением.

## <a name="implement-health-checks-in-aspnet-core-services"></a>Реализация проверки работоспособности в службах ASP.NET Core

При разработке микрослужбы или веб-приложения ASP.NET Core можно использовать встроенную функцию проверки работоспособности, выпущенную в ASP .NET Core 2.2. Как и многие функции ASP.NET Core, проверки работоспособности поставляются с набором служб и ПО промежуточного слоя.

Службы и ПО промежуточного слоя проверки работоспособности просты в использовании и предоставляют функции, которые позволяют убедиться, что любой внешний ресурс, необходимый для вашего приложения (например, база данных SQL Server или удаленный API), работает правильно. При использовании этой функции также можно определить критерии работоспособности ресурса, о которых мы расскажем ниже.

Чтобы эффективно использовать эту функцию, необходимо сначала настроить службы в микрослужбах. Во-вторых, вам понадобится клиентское приложение, которое запрашивает отчеты о работоспособности. Это клиентское приложение может быть пользовательским приложением для создания отчетов или оркестратором, который будет предпринимать необходимые действия в соответствии с состоянием работоспособности.

### <a name="use-the-healthchecks-feature-in-your-back-end-aspnet-microservices"></a>Использование функции HealthChecks в серверных микрослужбах ASP.NET

В этом разделе вы узнаете, как функция HealthChecks используется в примере приложения веб-API ASP.NET Core 2.2. Реализация этой функции в крупномасштабных микрослужбах, например eShopOnContainers, рассматривается в следующем разделе. Для начала необходимо определить, что входит в состояние работоспособности для каждой микрослужбы. В примере приложения микрослужба находится в работоспособном состоянии, если API микрослужбы доступен через HTTP и соответствующая база данных SQL Server также доступна.

В .NET Core 2.2 со встроенными API-интерфейсами можно настроить службы, добавить проверку работоспособности для микрослужбы и ее зависимые базы данных SQL Server следующим образом:

```csharp
// Startup.cs from .NET Core 2.2 Web Api sample
//
public void ConfigureServices(IServiceCollection services)
{
    //...
    // Registers required services for health checks
    services.AddHealthChecks()
    // Add a health check for a SQL database
    .AddCheck("MyDatabase", new SqlConnectionHealthCheck(Configuration["ConnectionStrings:DefaultConnection"]));
}
```

В приведенном выше коде метод `services.AddHealthChecks()` настраивает базовую проверку HTTP, которая возвращает код состояния **200** "Работоспособно".  Далее метод расширения `AddCheck()` настраивает пользовательский `SqlConnectionHealthCheck`, который проверяет работоспособность связанных баз данных SQL.

Метод `AddCheck()` добавляет новые проверки работоспособности с указанным именем и реализацией типа `IHealthCheck`. Вы можете добавить несколько проверок работоспособности с помощью метода AddCheck, чтобы микрослужба не отображала состояние "Работоспособно", пока все проверки не покажут работоспособность.

`SqlConnectionHealthCheck` — это пользовательский класс, реализующий `IHealthCheck`, который принимает строку подключения в качестве параметра конструктора и выполняет простой запрос для проверки успешного подключения к базе данных SQL. Он возвращает `HealthCheckResult.Healthy()`, если запрос был выполнен успешно, и `FailureStatus` с исключением, если нет.

```csharp
// Sample SQL Connection Health Check
public class SqlConnectionHealthCheck : IHealthCheck
{
    private static readonly string DefaultTestQuery = "Select 1";

    public string ConnectionString { get; }

    public string TestQuery { get; }

    public SqlConnectionHealthCheck(string connectionString)
        : this(connectionString, testQuery: DefaultTestQuery)
    {
    }

    public SqlConnectionHealthCheck(string connectionString, string testQuery)
    {
        ConnectionString = connectionString ?? throw new ArgumentNullException(nameof(connectionString));
        TestQuery = testQuery;
    }

    public async Task<HealthCheckResult> CheckHealthAsync(HealthCheckContext context, CancellationToken cancellationToken = default(CancellationToken))
    {
        using (var connection = new SqlConnection(ConnectionString))
        {
            try
            {
                await connection.OpenAsync(cancellationToken);

                if (TestQuery != null)
                {
                    var command = connection.CreateCommand();
                    command.CommandText = TestQuery;

                    await command.ExecuteNonQueryAsync(cancellationToken);
                }
            }
            catch (DbException ex)
            {
                return new HealthCheckResult(status: context.Registration.FailureStatus, exception: ex);
            }
        }

        return HealthCheckResult.Healthy();
    }
}
```

В предыдущем коде `Select 1` — это запрос, который используется для проверки работоспособности базы данных. Для отслеживания доступности ваших микрослужб оркестраторы, такие как Kubernetes и Service Fabric, периодически выполняют проверки работоспособности, отправляя запросы для проверки микрослужб. Очень важно сохранить эффективность запросов к базе данных, чтобы эти операции выполнялись быстро и не приводили к повышенному использованию ресурсов.

Наконец, создайте ПО промежуточного слоя, которое отвечает на URL пути "/hc":

```csharp
// Startup.cs from .NET Core 2.2 Web Api sample
//
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseHealthChecks("/hc");
    //…
}
```

При вызове конечной точки `<yourmicroservice>/hc` она запускает все проверки работоспособности, которые были настроены в методе `AddHealthChecks()` в классе Startup, и показывает результат.

### <a name="healthchecks-implementation-in-eshoponcontainers"></a>Реализация HealthChecks в eShopOnContainers

Микрослужбы в eShopOnContainers зависят от нескольких служб, которые выполняют задачи. Например, микрослужба `Catalog.API` из eShopOnContainers зависит от многих служб, таких как хранилище BLOB-объектов Azure, SQL Server и RabbitMQ. Поэтому к ней добавляется несколько проверок работоспособности с помощью метода `AddCheck()`. Для каждой зависимой службы необходимо добавить пользовательскую реализацию `IHealthCheck`, которая определяет соответствующее состояние работоспособности.

Проект с открытым кодом [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) решает эту проблему путем предоставления пользовательских реализаций проверки работоспособности для каждой из этих корпоративных служб, которые построены на основе .NET Core 2.2. Каждая проверка работоспособности доступна в виде отдельного пакета NuGet, который можно легко добавить в проект. eShopOnContainers широко использует их во всех своих микрослужбах.

Например, в микрослужбе `Catalog.API` добавлены следующие пакеты NuGet:

![Представление обозревателя решений проекта Catalog.API, где указаны ссылки на пакеты NuGet AspNetCore.Diagnostics.HealthChecks](./media/image6.png)

**Рис. 8-7**. Пользовательские проверки работоспособности, реализованные в Catalog.API с помощью AspNetCore.Diagnostics.HealthChecks

В следующем коде реализации проверки работоспособности добавляются для каждой зависимой службы, а затем настраивается ПО промежуточного слоя:

```csharp
// Startup.cs from Catalog.api microservice
//
public static IServiceCollection AddCustomHealthCheck(this IServiceCollection services, IConfiguration configuration)
{
    var accountName = configuration.GetValue<string>("AzureStorageAccountName");
    var accountKey = configuration.GetValue<string>("AzureStorageAccountKey");

    var hcBuilder = services.AddHealthChecks();

    hcBuilder
        .AddSqlServer(
            configuration["ConnectionString"],
            name: "CatalogDB-check",
            tags: new string[] { "catalogdb" });

    if (!string.IsNullOrEmpty(accountName) && !string.IsNullOrEmpty(accountKey))
    {
        hcBuilder
            .AddAzureBlobStorage(
                $"DefaultEndpointsProtocol=https;AccountName={accountName};AccountKey={accountKey};EndpointSuffix=core.windows.net",
                name: "catalog-storage-check",
                tags: new string[] { "catalogstorage" });
    }
    if (configuration.GetValue<bool>("AzureServiceBusEnabled"))
    {
        hcBuilder
            .AddAzureServiceBusTopic(
                configuration["EventBusConnection"],
                topicName: "eshop_event_bus",
                name: "catalog-servicebus-check",
                tags: new string[] { "servicebus" });
    }
    else
    {
        hcBuilder
            .AddRabbitMQ(
                $"amqp://{configuration["EventBusConnection"]}",
                name: "catalog-rabbitmqbus-check",
                tags: new string[] { "rabbitmqbus" });
    }

    return services;
}
```

Наконец, мы добавляем ПО промежуточного слоя проверки работоспособности для ожидания передачи данных от конечной точки "/hc":

```csharp
// HealthCheck middleware
app.UseHealthChecks("/hc", new HealthCheckOptions()
{
    Predicate = _ => true,
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});
}
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a>Отправка запроса состояния работоспособности у микрослужб

Настроив проверки работоспособности, описанные в этой статье, вы можете непосредственно проверить работоспособность микрослужбы из браузера, если эта микрослужба запущена в Docker. Для этого необходимо опубликовать порт контейнера в узле Docker, чтобы вы могли обращаться к контейнеру по внешнему IP-адресу узла Docker или через `localhost`, как показано на рисунке 8-8.

![Представление ответа в формате JSON, полученного при проверке работоспособности, в браузере](./media/image7.png)

**Рис. 8-8**. Проверка состояния работоспособности для одной службы из браузера

В этом тесте видно, что микрослужба `Catalog.API` (которая запущена на порте 5101) находится в работоспособном состоянии. Она возвращает код HTTP 200 и сведения о состоянии в формате JSON. Служба также проверила работоспособность зависимости базы данных SQL Server и RabbitMQ, и проверка сообщила о работоспособности.

## <a name="use-watchdogs"></a>Использование наблюдателей

Наблюдатель — это отдельная служба, которая отслеживает работоспособность и загрузку различных служб и отправляет отчет о работоспособности микрослужб, опрашивая библиотеку `HealthChecks`, о которой мы рассказывали ранее. Это помогает предотвратить ошибки, которые не будут обнаружены для представления одной службы. В наблюдателях также можно размещать код, который может выполнять действия по исправлению для известных условий без вмешательства пользователя.

Пример eShopOnContainers содержит веб-страницу с примерами отчетов о проверке работоспособности, как показано на рис. 8-9. Это простейший наблюдатель, который можно создать, так как он только отображает состояние микрослужб и веб-приложений в eShopOnContainers. Обычно наблюдатель предпринимает необходимые действия при обнаружении состояний неработоспособности.

К счастью, [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) также предоставляет пакет NuGet [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/), который можно использовать для отображения результатов проверки работоспособности на основе настроенных URI.

![Представление приложения WebStatus в браузере с состоянием работоспособности всех микрослужб из eShopOnContainers](./media/image8.png)

**Рис. 8-9**. Пример отчета о проверке работоспособности в eShopOnContainers

Таким образом, эта служба наблюдения запрашивает конечную точку "/hc" каждой микрослужбы. При этом будут выполнены все проверки работоспособности, определенные в этой конечной точке, и возвращено общее состояние работоспособности в зависимости от результатов этих проверок. HealthChecksUI удобно использовать с несколькими записями конфигурации и двумя строками кода, которые нужно добавить в Startup.cs службы наблюдения.

Пример файла конфигурации для пользовательского интерфейса проверки работоспособности:

```json
// Configuration
{
  "HealthChecks-UI": {
    "HealthChecks": [
      {
        "Name": "Ordering HTTP Check",
        "Uri": "http://localhost:5102/hc"
      },
      {
        "Name": "Ordering HTTP Background Check",
        "Uri": "http://localhost:5111/hc"
      },
      //...
    ]}
}
```

Файл Startup.cs, который добавляет HealthChecksUI:

```csharp
// Startup.cs from WebStatus(Watch Dog) service
//
public void ConfigureServices(IServiceCollection services)
{
    //…
    // Registers required services for health checks
    services.AddHealthChecksUI();
}
//…
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseHealthChecksUI(config=> config.UIPath = “/hc-ui”);
    //…
}
```

## <a name="health-checks-when-using-orchestrators"></a>Проверка работоспособности при использовании оркестраторов

Для отслеживания доступности ваших микрослужб оркестраторы, такие как Kubernetes и Service Fabric, периодически выполняют проверки работоспособности, отправляя запросы для проверки микрослужб. Когда оркестратор определяет, что служба или контейнер неработоспособны, она перестает направлять запросы к этому экземпляру. Она также обычно создает новый экземпляр этого контейнера.

Например, большинство оркестраторов могут использовать проверки работоспособности для реализации развертываний без простоев. Оркестратор начинает направлять трафик к службе или контейнеру только после того, как состояние службы или контейнера изменится на работоспособное.

Мониторинг работоспособности особенно важен, когда оркестратор выполняет обновление приложения. Некоторые оркестраторы (например, Azure Service Fabric) обновляют службы поэтапно, например, они могут обновлять одну пятую поверхности кластера при каждом обновлении. Набор узлов, обновляемых одновременно, называется *доменом обновления*. После того как каждый домен обновления был обновлен и стал доступен для пользователей, этот домен обновления должен пройти проверку работоспособности перед тем, как развертывание перейдет к следующему домену обновления.

Другой аспект работоспособности службы — метрики отчетов из службы. Это сложная функция модели работоспособности для некоторых оркестраторов, например Service Fabric. Метрики важны при использовании оркестраторов, так как они применяются для балансировки использования ресурсов. Метрики также могут быть индикатором работоспособности системы. Например, у вас может быть приложение с несколькими микрослужбами, и каждый экземпляр микрослужбы передает метрику "Количество запросов в секунду" (RPS). Если одна служба использует больше ресурсов (память, процессор и т. д.), чем другая служба, оркестратор может переместить экземпляры служб в кластере для равномерного использования ресурсов.

Обратите внимание, что в Azure Service Fabric есть собственная [модель мониторинга работоспособности](/azure/service-fabric/service-fabric-health-introduction), которая является более сложной по сравнению с простыми решениями для проверки.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Расширенный мониторинг: визуализация, анализ и предупреждения

Последний компонент мониторинга — визуализация потока событий, отчеты о производительности службы и оповещения при обнаружении проблем. Для реализации этого компонента мониторинга можно использовать различные решения.

Можно использовать простые пользовательские приложения, которые отображают состояние служб, например пользовательскую страницу, о которой идет речь в описании библиотеки [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks). Или можно использовать более сложные инструменты, такие как [Azure Monitor](https://azure.microsoft.com/services/monitor/), которые будут вызывать оповещения на основе потока событий.

Наконец, если вы сохраняете все потоки событий, для визуализации данных можно использовать Microsoft Power BI или решения других поставщиков, например Kibana или Splunk.

## <a name="additional-resources"></a>Дополнительные ресурсы

- **HealthChecks и пользовательский интерфейс HealthChecks для ASP.NET Core** \
  <https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks>

- **Общие сведения о мониторинге работоспособности Service Fabric** \
  [https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction](/azure/service-fabric/service-fabric-health-introduction)

- **Azure Monitor**  
  <https://azure.microsoft.com/services/monitor/>

>[!div class="step-by-step"]
>[Назад](implement-circuit-breaker-pattern.md)
>[Вперед](../secure-net-microservices-web-applications/index.md)
