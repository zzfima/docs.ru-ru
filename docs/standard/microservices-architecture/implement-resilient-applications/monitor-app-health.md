---
title: Мониторинг работоспособности
description: Изучите один из способов реализации мониторинга работоспособности.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: 666b55608ca4e5d18448e1a0b4a1735f3e856474
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362487"
---
# <a name="health-monitoring"></a><span data-ttu-id="5f5ca-103">Мониторинг работоспособности</span><span class="sxs-lookup"><span data-stu-id="5f5ca-103">Health monitoring</span></span>

<span data-ttu-id="5f5ca-104">Мониторинг работоспособности позволяет практически в реальном времени получать сведения о состоянии ваших контейнеров и микрослужб.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-104">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="5f5ca-105">Мониторинг работоспособности очень важен для нескольких аспектов работы микрослужб и особенно важен, когда оркестраторы выполняют частичное многоэтапное обновление приложений, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-105">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="5f5ca-106">Приложения на основе микрослужб часто используют пульс или проверки работоспособности, чтобы системные мониторы, планировщики и оркестраторы могли отслеживать большое количество служб.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-106">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="5f5ca-107">Если службам не удается отправить сигнал "Я в порядке", ваше приложение может подвергнуться риску при развертывании обновлений или может просто обнаружить ошибки слишком поздно. Это приведет к каскадным сбоям, которые будет невозможно остановить, а они, в свою очередь, приведут к масштабным сбоям.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-107">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might just detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="5f5ca-108">В обычной модели службы отправляют отчеты о своем состоянии, и эти сведения агрегируются для создания общего представления о состоянии работоспособности приложения.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-108">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="5f5ca-109">При использовании оркестратора можно предоставить сведения работоспособности кластеру оркестратора, чтобы кластер мог предпринять необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-109">If you're using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="5f5ca-110">Если воспользоваться высококачественными средствами создания отчетов о работоспособности, специально адаптированных для вашего приложения, вы сможете гораздо быстрее и эффективнее обнаруживать и устранять проблемы с приложением.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-110">If you invest in high-quality health reporting that's customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implement-health-checks-in-aspnet-core-services"></a><span data-ttu-id="5f5ca-111">Реализация проверки работоспособности в службах ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5f5ca-111">Implement health checks in ASP.NET Core services</span></span>

<span data-ttu-id="5f5ca-112">При разработке микрослужбы или веб-приложения ASP.NET Core можно использовать экспериментальную библиотеку *HealthChecks* от команды ASP.NET (официально не входит в ASP.NET Core и является устаревшей).</span><span class="sxs-lookup"><span data-stu-id="5f5ca-112">When developing an ASP.NET Core microservice or web application, you can use an experimental out-of-band library (not official as part of ASP.NETCore and now deprecated) named *Health Checks* from the ASP.NET team.</span></span> <span data-ttu-id="5f5ca-113">Эту библиотеку можно скачать в [репозитории GitHub dotnet-architecture](https://github.com/dotnet-architecture/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="5f5ca-113">It's available at this [dotnet-architecture GitHub repository](https://github.com/dotnet-architecture/HealthChecks).</span></span> <span data-ttu-id="5f5ca-114">При этом релиз официальной версии библиотеки *HealthChecks* [будет входить в состав ASP.NET Core 2.2](https://github.com/aspnet/Announcements/issues/307) (официальный выпуск запланирован на конец 2018 года).</span><span class="sxs-lookup"><span data-stu-id="5f5ca-114">However, the official version of *Health Checks* [will be released in ASP.NET Core 2.2](https://github.com/aspnet/Announcements/issues/307) (Should be officially released by the end of 2018).</span></span>

<span data-ttu-id="5f5ca-115">Эта библиотека проста в использовании и предоставляет функции, которые позволяют убедиться, что любой внешний ресурс, необходимый для вашего приложения (например, база данных SQL Server или удаленный API), работает правильно.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-115">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="5f5ca-116">При использовании этой библиотеки также можно определить критерии работоспособности ресурса, о которых мы расскажем ниже.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-116">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="5f5ca-117">Чтобы использовать эту библиотеку, необходимо сначала использовать библиотеку в ваших микрослужбах.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-117">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="5f5ca-118">Во-вторых, вам понадобится клиентское приложение, которое запрашивает отчеты о работоспособности.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-118">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="5f5ca-119">Это клиентское приложение может быть пользовательским приложением для создания отчетов или оркестратором, который будет предпринимать необходимые действия в соответствии с состоянием работоспособности.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-119">That front-end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="use-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="5f5ca-120">Использование библиотеки HealthChecks в серверных микрослужбах ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5f5ca-120">Use the HealthChecks library in your back-end ASP.NET microservices</span></span>

<span data-ttu-id="5f5ca-121">Вы видите, как библиотека HealthChecks используется в примере приложения eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-121">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="5f5ca-122">Для начала необходимо определить, что входит в состояние работоспособности для каждой микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="5f5ca-123">В примере приложения микрослужба находится в работоспособном состоянии, если API микрослужбы доступен через HTTP и соответствующая база данных SQL Server также доступна.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="5f5ca-124">В будущем вы сможете установить библиотеку HealthChecks в виде пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-124">In the future, you'll be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="5f5ca-125">Но на момент написания этой статьи необходимо скачать и скомпилировать код как часть решения.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-125">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="5f5ca-126">Клонируйте код, доступный по адресу <https://github.com/dotnet-architecture/HealthChecks>, и скопируйте следующие папки в ваше решение:</span><span class="sxs-lookup"><span data-stu-id="5f5ca-126">Clone the code available at <https://github.com/dotnet-architecture/HealthChecks> and copy the following folders to your solution:</span></span>

- <span data-ttu-id="5f5ca-127">src/common</span><span class="sxs-lookup"><span data-stu-id="5f5ca-127">src/common</span></span>
- <span data-ttu-id="5f5ca-128">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="5f5ca-128">src/Microsoft.AspNetCore.HealthChecks</span></span>
- <span data-ttu-id="5f5ca-129">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="5f5ca-129">src/Microsoft.Extensions.HealthChecks</span></span>
- <span data-ttu-id="5f5ca-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="5f5ca-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="5f5ca-131">Также можно было бы использовать дополнительные проверки, например Microsoft.Extensions.HealthChecks.AzureStorage для Azure, но так как эта версия eShopOnContainers никак не зависит от Azure, это не требуется.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-131">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="5f5ca-132">Вам не требуется выполнять проверки работоспособности ASP.NET, так как решение eShopOnContainers основано на ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-132">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="5f5ca-133">На рис. 8-7 показана библиотека HealthChecks в Visual Studio, которую можно использовать при разработке любых микрослужб.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-133">Figure 8-7 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![Представление обозревателя решений с папкой HealthChecks, содержащей три проекта.](./media/image6.png)

<span data-ttu-id="5f5ca-135">**Рис. 8-7**.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-135">**Figure 8-7**.</span></span> <span data-ttu-id="5f5ca-136">Исходный код библиотеки HealthChecks ASP.NET Core в решении Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5f5ca-136">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="5f5ca-137">Как описано выше, первое, что нужно сделать в проекте любой микрослужбы, — добавить ссылку на три библиотеки HealthChecks.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-137">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="5f5ca-138">После этого необходимо добавить действия проверки работоспособности, которые нужно выполнить в этой микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-138">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="5f5ca-139">Эти действия по сути являются зависимостями от других микрослужб (HttpUrlCheck) или баз данных (сейчас SqlCheck\* для баз данных SQL Server).</span><span class="sxs-lookup"><span data-stu-id="5f5ca-139">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="5f5ca-140">Вы добавляете действие в класс Startup для каждой микрослужбы ASP.NET или веб-приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-140">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="5f5ca-141">Каждую службу и каждое веб-приложение следует настроить, добавив все зависимости HTTP и баз данных для этой службы или этого приложения в качестве одного метода AddHealthCheck.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-141">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="5f5ca-142">Например, веб-приложение MVC eShopOnContainers зависит от многих служб и поэтому имеет несколько методов AddCheck для проверки работоспособности.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-142">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="5f5ca-143">Например, в следующем упрощенном коде вы увидите, как микрослужба каталога добавляет зависимость своей базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-143">For instance, in the following (simplified) code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

```csharp
// Startup.cs from Catalog.api microservice
//
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services
        services.AddHealthChecks(checks =>
        {
            checks.AddSqlCheck("CatalogDb", Configuration["ConnectionString"]);
        });
        // Other services
    }
}
```

<span data-ttu-id="5f5ca-144">Однако у веб-приложения MVC eShopOnContainers есть несколько зависимостей от остальных микрослужб.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-144">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="5f5ca-145">Поэтому оно вызывает метод AddUrlCheck для каждой микрослужбы, как показано в следующем упрощенном примере:</span><span class="sxs-lookup"><span data-stu-id="5f5ca-145">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following (simplified) example:</span></span>

```csharp
// Startup.cs from the MVC web app
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.Configure<AppSettings>(Configuration);
        services.AddHealthChecks(checks =>
        {
            checks.AddUrlCheck(Configuration["CatalogUrl"]);
            checks.AddUrlCheck(Configuration["OrderingUrl"]);
            checks.AddUrlCheck(Configuration["BasketUrl"]);
            checks.AddUrlCheck(Configuration["IdentityUrl"]);
        });
    }
}
```

<span data-ttu-id="5f5ca-146">Таким образом, микрослужба не будет возвращать состояние "Работоспособно", пока все ее проверки работоспособности не завершатся успешно.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-146">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="5f5ca-147">Если у микрослужбы нет зависимости от службы или от SQL Server, просто добавьте проверку Healthy("Ok").</span><span class="sxs-lookup"><span data-stu-id="5f5ca-147">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="5f5ca-148">Приведенный ниже код взят из микрослужбы `basket.api` в решении eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-148">The following code is from the eShopOnContainers `basket.api` microservice.</span></span> <span data-ttu-id="5f5ca-149">(Микрослужба корзины использует кэш Redis, но библиотека еще не содержит поставщика проверки работоспособности Redis.)</span><span class="sxs-lookup"><span data-stu-id="5f5ca-149">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="5f5ca-150">Чтобы служба или веб-приложение предоставили конечную точку проверки работоспособности, в них необходимо включить метод расширения `UseHealthChecks([*url_for_health_checks*])`.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-150">For a service or web application to expose the health check endpoint, it has to enable the `UseHealthChecks([*url_for_health_checks*])` extension method.</span></span> <span data-ttu-id="5f5ca-151">Этот метод переходит на уровень `WebHostBuilder` метода main класса `Program` службы ASP.NET Core или веб-приложения, сразу после <xref:Microsoft.AspNetCore.WebHost.CreateDefaultBuilder>, как показано в следующем упрощенном коде:</span><span class="sxs-lookup"><span data-stu-id="5f5ca-151">This method goes at the `WebHostBuilder` level in the main method of the `Program` class of your ASP.NET Core service or web application, right after <xref:Microsoft.AspNetCore.WebHost.CreateDefaultBuilder> as shown in the following simplified code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = WebHost.CreateDefaultBuilder(args)
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseStartup<Startup>()
                .Build();

            host.Run();
        }
    }
}
```

<span data-ttu-id="5f5ca-152">Процесс выглядит следующим образом: каждая микрослужба предоставляет конечную точку /hc.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-152">The process works this way: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="5f5ca-153">Эта конечная точка создается ПО промежуточного слоя ASP.NET Core для библиотеки HealthChecks.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-153">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="5f5ca-154">При вызове этой конечной точки она запускает все проверки работоспособности, которые были настроены в методе AddHealthChecks в классе Startup.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-154">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="5f5ca-155">Метод UseHealthChecks получает в качестве параметра порт или путь.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-155">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="5f5ca-156">Это порт или путь к конечной точке, которая используется для проверки состояния работоспособности службы.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-156">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="5f5ca-157">Например, микрослужба каталога использует путь /hc.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-157">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="cache-health-check-responses"></a><span data-ttu-id="5f5ca-158">Кэширование ответов проверки работоспособности</span><span class="sxs-lookup"><span data-stu-id="5f5ca-158">Cache health check responses</span></span>

<span data-ttu-id="5f5ca-159">Поскольку вы не хотите создать атаку типа "отказ в обслуживании" (DoS) для своих служб или просто не хотите влиять на работоспособность службы, проверяя ресурсы слишком часто, вы можете кэшировать результаты проверки работоспособности и настроить длительность кэширования для каждой проверки.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-159">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="5f5ca-160">По умолчанию длительность кэширования устанавливается в 5 минут, но вы можете изменить ее для каждой проверки работоспособности, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="5f5ca-160">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="5f5ca-161">Отправка запроса состояния работоспособности у микрослужб</span><span class="sxs-lookup"><span data-stu-id="5f5ca-161">Query your microservices to report about their health status</span></span>

<span data-ttu-id="5f5ca-162">Настроив проверки работоспособности, описанные в этой статье, вы можете непосредственно проверить работоспособность микрослужбы из браузера, если эта микрослужба запущена в Docker.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-162">When you've configured health checks as described in this article and you have the microservice running in Docker, you can directly check from a browser if it's healthy.</span></span>

<span data-ttu-id="5f5ca-163">Для этого необходимо опубликовать порт контейнера в узле Docker, чтобы вы могли обращаться к контейнеру по внешнему IP-адресу узла Docker или через `localhost`, как показано на рисунке 8-8.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-163">You have to publish the container port in the Docker host, so you can access the container through the external Docker host IP or through `localhost`, as shown in figure 8-8.</span></span>

![Представление ответа в формате JSON, полученного при проверке работоспособности, в браузере](./media/image7.png)

<span data-ttu-id="5f5ca-165">**Рис. 8-8**.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-165">**Figure 8-8**.</span></span> <span data-ttu-id="5f5ca-166">Проверка состояния работоспособности для одной службы из браузера</span><span class="sxs-lookup"><span data-stu-id="5f5ca-166">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="5f5ca-167">В этом тесте видно, что микрослужба catalog.api (которая запущена на порте 5101) находится в работоспособном состоянии. Она возвращает код HTTP 200 и сведения о состоянии в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-167">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="5f5ca-168">Это также означает, что внутри службы также осуществляется проверка работоспособности зависимой базы данных SQL Server для этой микрослужбы и что проверка работоспособности возвратила результат, свидетельствующий о нарушении работоспособности.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-168">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="use-watchdogs"></a><span data-ttu-id="5f5ca-169">Использование наблюдателей</span><span class="sxs-lookup"><span data-stu-id="5f5ca-169">Use watchdogs</span></span>

<span data-ttu-id="5f5ca-170">Наблюдатель — это отдельная служба, которая отслеживает работоспособность и загрузку различных служб и отправляет отчет о работоспособности микрослужб, опрашивая библиотеку `HealthChecks`, о которой мы рассказывали ранее.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-170">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the `HealthChecks` library introduced earlier.</span></span> <span data-ttu-id="5f5ca-171">Это помогает предотвратить ошибки, которые не будут обнаружены для представления одной службы.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-171">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="5f5ca-172">В наблюдателях также можно размещать код, который может выполнять действия по исправлению для известных условий без вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-172">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="5f5ca-173">Пример eShopOnContainers содержит веб-страницу с примерами отчетов о проверке работоспособности, как показано на рис. 8-9.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-173">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 8-9.</span></span> <span data-ttu-id="5f5ca-174">Это простейший наблюдатель, который можно создать, так как он только отображает состояние микрослужб и веб-приложений в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-174">This is the simplest watchdog you could have since it only shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="5f5ca-175">Обычно наблюдатель предпринимает необходимые действия при обнаружении состояний неработоспособности.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-175">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![Представление приложения WebStatus с состоянием работоспособности пяти микрослужб из eShopOnContainers](./media/image8.png)

<span data-ttu-id="5f5ca-177">**Рис. 8-9**.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-177">**Figure 8-9**.</span></span> <span data-ttu-id="5f5ca-178">Пример отчета о проверке работоспособности в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="5f5ca-178">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="5f5ca-179">ПО промежуточного слоя ASP.NET Core для библиотеки HealthChecks предоставляет по одной конечной точке проверки работоспособности для каждой микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-179">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="5f5ca-180">При этом будут выполнены все проверки работоспособности, определенные в этой конечной точке, и возвращено общее состояние работоспособности в зависимости от результатов этих проверок.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-180">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="5f5ca-181">Библиотека HealthChecks является расширяемой. В нее могут быть добавлены новые проверки работоспособности или новые внешние ресурсы.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-181">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="5f5ca-182">Например, мы ожидаем, что в будущем в библиотеке появятся проверки работоспособности для кэша Redis и для других баз данных.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-182">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="5f5ca-183">Библиотека позволяет создавать отчеты о работоспособности для нескольких зависимых служб и приложений, и вы можете выполнять определенные действия в зависимости от этих проверок работоспособности.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-183">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="5f5ca-184">Проверка работоспособности при использовании оркестраторов</span><span class="sxs-lookup"><span data-stu-id="5f5ca-184">Health checks when using orchestrators</span></span>

<span data-ttu-id="5f5ca-185">Для отслеживания доступности ваших микрослужб оркестраторы, такие как Kubernetes и Service Fabric, периодически выполняют проверки работоспособности, отправляя запросы для проверки микрослужб.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-185">To monitor the availability of your microservices, orchestrators like Kubernetes and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="5f5ca-186">Когда оркестратор определяет, что служба или контейнер неработоспособны, она перестает направлять запросы к этому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-186">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="5f5ca-187">Она также обычно создает новый экземпляр этого контейнера.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-187">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="5f5ca-188">Например, большинство оркестраторов могут использовать проверки работоспособности для реализации развертываний без простоев.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-188">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="5f5ca-189">Оркестратор начинает направлять трафик к службе или контейнеру только после того, как состояние службы или контейнера изменится на работоспособное.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-189">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="5f5ca-190">Мониторинг работоспособности особенно важен, когда оркестратор выполняет обновление приложения.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-190">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="5f5ca-191">Некоторые оркестраторы (например, Azure Service Fabric) обновляют службы поэтапно, например, они могут обновлять одну пятую поверхности кластера при каждом обновлении.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-191">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="5f5ca-192">Набор узлов, обновляемых одновременно, называется *доменом обновления*.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-192">The set of nodes that's upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="5f5ca-193">После того как каждый домен обновления был обновлен и стал доступен для пользователей, этот домен обновления должен пройти проверку работоспособности перед тем, как развертывание перейдет к следующему домену обновления.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-193">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="5f5ca-194">Другой аспект работоспособности службы — метрики отчетов из службы.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-194">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="5f5ca-195">Это сложная функция модели работоспособности для некоторых оркестраторов, например Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-195">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="5f5ca-196">Метрики важны при использовании оркестраторов, так как они применяются для балансировки использования ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-196">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="5f5ca-197">Метрики также могут быть индикатором работоспособности системы.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-197">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="5f5ca-198">Например, у вас может быть приложение с несколькими микрослужбами, и каждый экземпляр микрослужбы передает метрику "Количество запросов в секунду" (RPS).</span><span class="sxs-lookup"><span data-stu-id="5f5ca-198">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="5f5ca-199">Если одна служба использует больше ресурсов (память, процессор и т. д.), чем другая служба, оркестратор может переместить экземпляры служб в кластере для равномерного использования ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-199">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="5f5ca-200">Обратите внимание, что в Azure Service Fabric есть собственная [модель мониторинга работоспособности](/azure/service-fabric/service-fabric-health-introduction), которая является более сложной по сравнению с простыми решениями для проверки.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-200">Note that Azure Service Fabric provides its own [Health Monitoring model](/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="5f5ca-201">Расширенный мониторинг: визуализация, анализ и предупреждения</span><span class="sxs-lookup"><span data-stu-id="5f5ca-201">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="5f5ca-202">Последний компонент мониторинга — визуализация потока событий, отчеты о производительности службы и оповещения при обнаружении проблем.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-202">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="5f5ca-203">Для реализации этого компонента мониторинга можно использовать различные решения.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-203">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="5f5ca-204">Можно использовать простые пользовательские приложения, которые отображают состояние служб, например пользовательскую страницу, о которой идет речь в описании библиотеки [HealthChecks ASP.NET Core](https://github.com/dotnet-architecture/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="5f5ca-204">You can use simple custom applications showing the state of your services, like the custom page shown when explaining the [ASP.NET Core HealthChecks](https://github.com/dotnet-architecture/HealthChecks).</span></span> <span data-ttu-id="5f5ca-205">Или можно использовать более сложные инструменты, такие как Azure Application Insights, которые будут создавать оповещения на основе потока событий.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-205">Or you could use more advanced tools like Azure Application Insights to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="5f5ca-206">Наконец, если вы сохраняете все потоки событий, для визуализации данных можно использовать Microsoft Power BI или решения других поставщиков, например Kibana или Splunk.</span><span class="sxs-lookup"><span data-stu-id="5f5ca-206">Finally, if you're storing all the event streams, you can use Microsoft Power BI or other solutions like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5f5ca-207">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="5f5ca-207">Additional resources</span></span>

- <span data-ttu-id="5f5ca-208">**ASP.NET Core HealthChecks** (экспериментальный выпуск)</span><span class="sxs-lookup"><span data-stu-id="5f5ca-208">**ASP.NET Core HealthChecks** (experimental release)\\</span></span>
  [*https://github.com/dotnet-architecture/HealthChecks/*](https://github.com/dotnet-architecture/HealthChecks/)

- <span data-ttu-id="5f5ca-209">**Общие сведения о мониторинге работоспособности Service Fabric**\\</span><span class="sxs-lookup"><span data-stu-id="5f5ca-209">**Introduction to Service Fabric health monitoring**\\</span></span>
  [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](/azure/service-fabric/service-fabric-health-introduction)

- <span data-ttu-id="5f5ca-210">**Azure Application Insights**\\</span><span class="sxs-lookup"><span data-stu-id="5f5ca-210">**Azure Application Insights**\\</span></span>
  [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

- <span data-ttu-id="5f5ca-211">**Microsoft Operations Management Suite**\\</span><span class="sxs-lookup"><span data-stu-id="5f5ca-211">**Microsoft Operations Management Suite**\\</span></span>
  [*https://www.microsoft.com/cloud-platform/operations-management-suite*](https://www.microsoft.com/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
><span data-ttu-id="5f5ca-212">[Назад](implement-circuit-breaker-pattern.md)
>[Вперед](../secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="5f5ca-212">[Previous](implement-circuit-breaker-pattern.md)
[Next](../secure-net-microservices-web-applications/index.md)</span></span>