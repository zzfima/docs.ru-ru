---
title: Мониторинг работоспособности
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Мониторинг работоспособности
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 81c4fc7662212bb3c6586a590d87e731220b7b7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="health-monitoring"></a><span data-ttu-id="8375e-103">Мониторинг работоспособности</span><span class="sxs-lookup"><span data-stu-id="8375e-103">Health monitoring</span></span>

<span data-ttu-id="8375e-104">Мониторинг работоспособности позволяет практически в реальном времени получать сведения о состоянии ваших контейнеров и микрослужб.</span><span class="sxs-lookup"><span data-stu-id="8375e-104">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="8375e-105">Мониторинг работоспособности очень важен для нескольких аспектов работы микрослужб и особенно важен, когда оркестраторы выполняют частичное многоэтапное обновление приложений, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="8375e-105">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="8375e-106">Приложения на основе микрослужб часто используют пульс или проверки работоспособности, чтобы системные мониторы, планировщики и оркестраторы могли отслеживать большое количество служб.</span><span class="sxs-lookup"><span data-stu-id="8375e-106">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="8375e-107">Если службам не удается отправить сигнал "Я в порядке", то ваше приложение может подвергнуться риску при развертывании обновлений или просто может обнаружить ошибки слишком поздно, что приведет к каскадным сбоям, которые будет невозможно остановить, а они, в свою очередь, приведут к крупным сбоям.</span><span class="sxs-lookup"><span data-stu-id="8375e-107">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might simply detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="8375e-108">В обычной модели службы отправляют отчеты о своем состоянии, и эти сведения агрегируются для создания общего представления о состоянии работоспособности приложения.</span><span class="sxs-lookup"><span data-stu-id="8375e-108">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="8375e-109">При использовании оркестратора можно предоставить сведения работоспособности кластеру оркестратора, чтобы кластер мог предпринять необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="8375e-109">If you are using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="8375e-110">Если воспользоваться средствами создания отчетов о работоспособности высокого качества, специально адаптированных для вашего приложения, вы можете гораздо быстрее и эффективнее обнаруживать и устранять проблемы с вашим приложением.</span><span class="sxs-lookup"><span data-stu-id="8375e-110">If you invest in high-quality health reporting that is customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implementing-health-checks-in-aspnet-core-services"></a><span data-ttu-id="8375e-111">Реализация проверки работоспособности в службах ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8375e-111">Implementing health checks in ASP.NET Core services</span></span>

<span data-ttu-id="8375e-112">При разработке микрослужбы или веб-приложения ASP.NET Core можно использовать библиотеку `HealthChecks` от команды ASP.NET (официально не входит в ASP.NETCore).</span><span class="sxs-lookup"><span data-stu-id="8375e-112">When developing an ASP.NET Core microservice or web application, you can use an out-of-band library (not official as part of ASP.NETCore) named `HealthChecks` from the ASP.NET team.</span></span> <span data-ttu-id="8375e-113">Ее можно найти в этом [репозитории GitHub](https://github.com/dotnet-architecture/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="8375e-113">It is available at this [GitHub repo](https://github.com/dotnet-architecture/HealthChecks).</span></span>

<span data-ttu-id="8375e-114">Эта библиотека проста в использовании и предоставляет функции, которые позволяют убедиться, что любой внешний ресурс, необходимый для вашего приложения (например, база данных SQL Server или удаленный API), работает правильно.</span><span class="sxs-lookup"><span data-stu-id="8375e-114">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="8375e-115">При использовании этой библиотеки также можно определить критерии работоспособности ресурса, о которых мы расскажем ниже.</span><span class="sxs-lookup"><span data-stu-id="8375e-115">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="8375e-116">Чтобы использовать эту библиотеку, необходимо сначала использовать библиотеку в ваших микрослужбах.</span><span class="sxs-lookup"><span data-stu-id="8375e-116">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="8375e-117">Во-вторых, вам понадобится клиентское приложение, которое запрашивает отчеты о работоспособности.</span><span class="sxs-lookup"><span data-stu-id="8375e-117">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="8375e-118">Это клиентское приложение может представлять собой пользовательское приложение для создания отчетов или сам оркестратор, который может предпринимать необходимые действия в соответствии с состоянием работоспособности.</span><span class="sxs-lookup"><span data-stu-id="8375e-118">That front end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="8375e-119">Использование библиотеки HealthChecks в серверных микрослужбах ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8375e-119">Using the HealthChecks library in your back end ASP.NET microservices</span></span>

<span data-ttu-id="8375e-120">Вы видите, как библиотека HealthChecks используется в примере приложения eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8375e-120">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="8375e-121">Для начала необходимо определить, что входит в состояние работоспособности для каждой микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="8375e-121">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="8375e-122">В примере приложения микрослужба находится в работоспособном состоянии, если API микрослужбы доступен через HTTP и соответствующая база данных SQL Server также доступна.</span><span class="sxs-lookup"><span data-stu-id="8375e-122">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="8375e-123">В будущем вы можете установить библиотеку HealthChecks в виде пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="8375e-123">In the future, you will be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="8375e-124">Но на момент написания этой статьи необходимо скачать и скомпилировать код как часть решения.</span><span class="sxs-lookup"><span data-stu-id="8375e-124">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="8375e-125">Клонируйте код, доступный по адресу https://github.com/dotnet-architecture/HealthChecks, и скопируйте следующие папки в ваше решение:</span><span class="sxs-lookup"><span data-stu-id="8375e-125">Clone the code available at https://github.com/dotnet-architecture/HealthChecks and copy the following folders to your solution:</span></span>

  - <span data-ttu-id="8375e-126">src/common</span><span class="sxs-lookup"><span data-stu-id="8375e-126">src/common</span></span>
  - <span data-ttu-id="8375e-127">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="8375e-127">src/Microsoft.AspNetCore.HealthChecks</span></span>
  - <span data-ttu-id="8375e-128">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="8375e-128">src/Microsoft.Extensions.HealthChecks</span></span>
  - <span data-ttu-id="8375e-129">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="8375e-129">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="8375e-130">Также можно было бы использовать дополнительные проверки, например Microsoft.Extensions.HealthChecks.AzureStorage для Azure, но так как эта версия eShopOnContainers никак не зависит от Azure, это не требуется.</span><span class="sxs-lookup"><span data-stu-id="8375e-130">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="8375e-131">Вам не требуется выполнять проверки работоспособности ASP.NET, так как решение eShopOnContainers основано на ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="8375e-131">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="8375e-132">На рис. 10-6 показана библиотека HealthChecks в Visual Studio, которую можно использовать при разработке любых микрослужб.</span><span class="sxs-lookup"><span data-stu-id="8375e-132">Figure 10-6 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![](./media/image6.png)

<span data-ttu-id="8375e-133">**Рис. 10-6**.</span><span class="sxs-lookup"><span data-stu-id="8375e-133">**Figure 10-6**.</span></span> <span data-ttu-id="8375e-134">Исходный код библиотеки HealthChecks ASP.NET Core в решении Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8375e-134">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="8375e-135">Как описано выше, первое, что нужно сделать в проекте любой микрослужбы, — добавить ссылку на три библиотеки HealthChecks.</span><span class="sxs-lookup"><span data-stu-id="8375e-135">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="8375e-136">После этого необходимо добавить действия проверки работоспособности, которые нужно выполнить в этой микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="8375e-136">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="8375e-137">Эти действия по сути являются зависимостями от других микрослужб (HttpUrlCheck) или баз данных (сейчас SqlCheck\* для баз данных SQL Server).</span><span class="sxs-lookup"><span data-stu-id="8375e-137">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="8375e-138">Вы добавляете действие в класс Startup для каждой микрослужбы ASP.NET или веб-приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8375e-138">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="8375e-139">Каждую службу и каждое веб-приложение следует настроить, добавив все зависимости HTTP и баз данных для этой службы или этого приложения в качестве одного метода AddHealthCheck.</span><span class="sxs-lookup"><span data-stu-id="8375e-139">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="8375e-140">Например, веб-приложение MVC eShopOnContainers зависит от многих служб и поэтому имеет несколько методов AddCheck для проверки работоспособности.</span><span class="sxs-lookup"><span data-stu-id="8375e-140">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="8375e-141">Например, в следующем коде вы увидите, как микрослужба каталога добавляет зависимость от своей базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8375e-141">For instance, in the following code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

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

<span data-ttu-id="8375e-142">Однако у веб-приложения MVC eShopOnContainers есть несколько зависимостей от остальных микрослужб.</span><span class="sxs-lookup"><span data-stu-id="8375e-142">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="8375e-143">Поэтому оно вызывает метод AddUrlCheck для каждой микрослужбы, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8375e-143">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following example:</span></span>

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

<span data-ttu-id="8375e-144">Таким образом, микрослужба не будет возвращать состояние "Работоспособно", пока все ее проверки работоспособности не завершатся успешно.</span><span class="sxs-lookup"><span data-stu-id="8375e-144">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="8375e-145">Если у микрослужбы нет зависимости от службы или от SQL Server, просто добавьте проверку Healthy("Ok").</span><span class="sxs-lookup"><span data-stu-id="8375e-145">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="8375e-146">Приведенный ниже код взят из микрослужбы basket.api в решении eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8375e-146">The following code is from the eShopOnContainers basket.api microservice.</span></span> <span data-ttu-id="8375e-147">(Микрослужба корзины использует кэш Redis, но библиотека еще не содержит поставщика проверки работоспособности Redis.)</span><span class="sxs-lookup"><span data-stu-id="8375e-147">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="8375e-148">Чтобы служба или веб-приложение предоставили конечную точку проверки работоспособности, в них необходимо включить метод расширения UseHealthChecks(\[*URL-адрес\_для\_проверки\_работоспособности*\]).</span><span class="sxs-lookup"><span data-stu-id="8375e-148">For a service or web application to expose the health check endpoint, it has to enable the UseHealthChecks(\[*url\_for\_health\_checks*\]) extension method.</span></span> <span data-ttu-id="8375e-149">Этот метод переходит на уровень WebHostBuilder основного метода класса Program службы ASP.NET Core или веб-приложения, сразу после UseKestrel, как показано в коде ниже.</span><span class="sxs-lookup"><span data-stu-id="8375e-149">This method goes at the WebHostBuilder level in the main method of the Program class of your ASP.NET Core service or web application, right after UseKestrel as shown in the code below.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();
            host.Run();
        }
    }
}
```

<span data-ttu-id="8375e-150">Процесс выглядит следующим образом: каждая микрослужба предоставляет конечную точку /hc.</span><span class="sxs-lookup"><span data-stu-id="8375e-150">The process works like this: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="8375e-151">Эта конечная точка создается ПО промежуточного слоя ASP.NET Core для библиотеки HealthChecks.</span><span class="sxs-lookup"><span data-stu-id="8375e-151">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="8375e-152">При вызове этой конечной точки она запускает все проверки работоспособности, которые были настроены в методе AddHealthChecks в классе Startup.</span><span class="sxs-lookup"><span data-stu-id="8375e-152">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="8375e-153">Метод UseHealthChecks получает в качестве параметра порт или путь.</span><span class="sxs-lookup"><span data-stu-id="8375e-153">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="8375e-154">Это порт или путь к конечной точке, которая используется для проверки состояния работоспособности службы.</span><span class="sxs-lookup"><span data-stu-id="8375e-154">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="8375e-155">Например, микрослужба каталога использует путь /hc.</span><span class="sxs-lookup"><span data-stu-id="8375e-155">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="caching-health-check-responses"></a><span data-ttu-id="8375e-156">Кэширование ответов проверки работоспособности</span><span class="sxs-lookup"><span data-stu-id="8375e-156">Caching health check responses</span></span>

<span data-ttu-id="8375e-157">Поскольку вы не хотите создать атаку типа "отказ в обслуживании" (DoS) для своих служб или просто не хотите влиять на работоспособность службы, проверяя ресурсы слишком часто, вы можете кэшировать результаты проверки работоспособности и настроить длительность кэширования для каждой проверки.</span><span class="sxs-lookup"><span data-stu-id="8375e-157">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="8375e-158">По умолчанию длительность кэширования устанавливается в 5 минут, но вы можете изменить ее для каждой проверки работоспособности, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="8375e-158">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="8375e-159">Запрос состояния работоспособности у микрослужб</span><span class="sxs-lookup"><span data-stu-id="8375e-159">Querying your microservices to report about their health status</span></span>

<span data-ttu-id="8375e-160">После настройки проверок работоспособности, как описано здесь, вы можете напрямую проверить работоспособность микрослужбы из браузера, если эта микрослужба запущена в Docker.</span><span class="sxs-lookup"><span data-stu-id="8375e-160">When you have configured health checks as described here, once the microservice is running in Docker, you can directly check from a browser if it is healthy.</span></span> <span data-ttu-id="8375e-161">(Для этого необходимо пробросить порт контейнера из узла Docker, чтобы вы могли обращаться к контейнеру через localhost или через внешний IP-адрес узла Docker.) На рис. 10-7 показаны запрос в веб-браузере и соответствующий ответ.</span><span class="sxs-lookup"><span data-stu-id="8375e-161">(This does require that you are publishing the container port out of the Docker host, so you can access the container through localhost or through the external Docker host IP.) Figure 10-7 shows a request in a browser and the corresponding response.</span></span>

![](./media/image7.png)

<span data-ttu-id="8375e-162">**Рис. 10-7**.</span><span class="sxs-lookup"><span data-stu-id="8375e-162">**Figure 10-7**.</span></span> <span data-ttu-id="8375e-163">Проверка состояния работоспособности для одной службы из браузера</span><span class="sxs-lookup"><span data-stu-id="8375e-163">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="8375e-164">В этом тесте видно, что микрослужба catalog.api (которая запущена на порте 5101) находится в работоспособном состоянии. Она возвращает код HTTP 200 и сведения о состоянии в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="8375e-164">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="8375e-165">Это также означает, что внутри службы также осуществляется проверка работоспособности зависимой базы данных SQL Server для этой микрослужбы и что проверка работоспособности возвратила результат, свидетельствующий о нарушении работоспособности.</span><span class="sxs-lookup"><span data-stu-id="8375e-165">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="using-watchdogs"></a><span data-ttu-id="8375e-166">Использование наблюдателей</span><span class="sxs-lookup"><span data-stu-id="8375e-166">Using watchdogs</span></span>

<span data-ttu-id="8375e-167">Наблюдатель — это отдельная служба, которая отслеживает работоспособность и загрузку различных служб и отправляет отчет о работоспособности микрослужб, опрашивая библиотеку HealthChecks, о которой мы рассказывали ранее.</span><span class="sxs-lookup"><span data-stu-id="8375e-167">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the HealthChecks library introduced earlier.</span></span> <span data-ttu-id="8375e-168">Это помогает предотвратить ошибки, которые не будут обнаружены для представления одной службы.</span><span class="sxs-lookup"><span data-stu-id="8375e-168">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="8375e-169">В наблюдателях также можно размещать код, который может выполнять действия по исправлению для известных условий без вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="8375e-169">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="8375e-170">Пример eShopOnContainers включает веб-страницу с примерами отчетов о проверке работоспособности, как показано на рис. 10-8.</span><span class="sxs-lookup"><span data-stu-id="8375e-170">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 10-8.</span></span> <span data-ttu-id="8375e-171">Это простейший наблюдатель, который можно создать, так как он отображает состояние микрослужб и веб-приложений в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8375e-171">This is the simplest watchdog you could have, since all it does is shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="8375e-172">Обычно наблюдатель предпринимает необходимые действия при обнаружении состояний неработоспособности.</span><span class="sxs-lookup"><span data-stu-id="8375e-172">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![](./media/image8.png)

<span data-ttu-id="8375e-173">**Рис. 10-8**.</span><span class="sxs-lookup"><span data-stu-id="8375e-173">**Figure 10-8**.</span></span> <span data-ttu-id="8375e-174">Пример отчета о проверке работоспособности в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="8375e-174">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="8375e-175">ПО промежуточного слоя ASP.NET Core для библиотеки HealthChecks предоставляет по одной конечной точке проверки работоспособности для каждой микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="8375e-175">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="8375e-176">При этом будут выполнены все проверки работоспособности, определенные в этой конечной точке, и возвращено общее состояние работоспособности в зависимости от результатов этих проверок.</span><span class="sxs-lookup"><span data-stu-id="8375e-176">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="8375e-177">Библиотека HealthChecks является расширяемой. В нее могут быть добавлены новые проверки работоспособности или новые внешние ресурсы.</span><span class="sxs-lookup"><span data-stu-id="8375e-177">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="8375e-178">Например, мы ожидаем, что в будущем в библиотеке появятся проверки работоспособности для кэша Redis и для других баз данных.</span><span class="sxs-lookup"><span data-stu-id="8375e-178">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="8375e-179">Библиотека позволяет создавать отчеты о работоспособности для нескольких зависимых служб и приложений, и вы можете выполнять определенные действия в зависимости от этих проверок работоспособности.</span><span class="sxs-lookup"><span data-stu-id="8375e-179">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="8375e-180">Проверка работоспособности при использовании оркестраторов</span><span class="sxs-lookup"><span data-stu-id="8375e-180">Health checks when using orchestrators</span></span>

<span data-ttu-id="8375e-181">Для отслеживания доступности ваших микрослужб оркестраторы, такие как Docker Swarm, Kubernetes и Service Fabric, периодически выполняют проверки работоспособности, отправляя запросы для проверки микрослужб.</span><span class="sxs-lookup"><span data-stu-id="8375e-181">To monitor the availability of your microservices, orchestrators like Docker Swarm, Kubernetes, and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="8375e-182">Когда оркестратор определяет, что служба или контейнер неработоспособны, она перестает направлять запросы к этому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="8375e-182">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="8375e-183">Она также обычно создает новый экземпляр этого контейнера.</span><span class="sxs-lookup"><span data-stu-id="8375e-183">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="8375e-184">Например, большинство оркестраторов могут использовать проверки работоспособности для реализации развертываний без простоев.</span><span class="sxs-lookup"><span data-stu-id="8375e-184">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="8375e-185">Оркестратор начинает направлять трафик к службе или контейнеру только после того, как состояние службы или контейнера изменится на работоспособное.</span><span class="sxs-lookup"><span data-stu-id="8375e-185">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="8375e-186">Мониторинг работоспособности особенно важен, когда оркестратор выполняет обновление приложения.</span><span class="sxs-lookup"><span data-stu-id="8375e-186">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="8375e-187">Некоторые оркестраторы (например, Azure Service Fabric) обновляют службы поэтапно, например, они могут обновлять одну пятую поверхности кластера при каждом обновлении.</span><span class="sxs-lookup"><span data-stu-id="8375e-187">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="8375e-188">Набор узлов, на которых выполняется обновление в один момент времени, называется *доменом обновления*.</span><span class="sxs-lookup"><span data-stu-id="8375e-188">The set of nodes that is upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="8375e-189">После того как каждый домен обновления был обновлен и стал доступен для пользователей, этот домен обновления должен пройти проверку работоспособности перед тем, как развертывание перейдет к следующему домену обновления.</span><span class="sxs-lookup"><span data-stu-id="8375e-189">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="8375e-190">Другой аспект работоспособности службы — метрики отчетов из службы.</span><span class="sxs-lookup"><span data-stu-id="8375e-190">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="8375e-191">Это сложная функция модели работоспособности для некоторых оркестраторов, например Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="8375e-191">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="8375e-192">Метрики важны при использовании оркестраторов, так как они применяются для балансировки использования ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8375e-192">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="8375e-193">Метрики также могут быть индикатором работоспособности системы.</span><span class="sxs-lookup"><span data-stu-id="8375e-193">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="8375e-194">Например, у вас может быть приложение с несколькими микрослужбами, и каждый экземпляр микрослужбы передает метрику "Количество запросов в секунду" (RPS).</span><span class="sxs-lookup"><span data-stu-id="8375e-194">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="8375e-195">Если одна служба использует больше ресурсов (память, процессор и т. д.), чем другая служба, оркестратор может переместить экземпляры служб в кластере для равномерного использования ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8375e-195">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="8375e-196">Обратите внимание, что в Azure Service Fabric есть собственная [модель мониторинга работоспособности](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), которая является более сложной по сравнению с простыми проверками.</span><span class="sxs-lookup"><span data-stu-id="8375e-196">Note that if you are using Azure Service Fabric, it provides its own [Health Monitoring model](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="8375e-197">Расширенный мониторинг: визуализация, анализ и предупреждения</span><span class="sxs-lookup"><span data-stu-id="8375e-197">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="8375e-198">Последний компонент мониторинга — визуализация потока событий, отчеты о производительности службы и оповещения при обнаружении проблем.</span><span class="sxs-lookup"><span data-stu-id="8375e-198">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="8375e-199">Для реализации этого компонента мониторинга можно использовать различные решения.</span><span class="sxs-lookup"><span data-stu-id="8375e-199">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="8375e-200">Можно использовать простые пользовательские приложения, которые отображают состояние служб, например пользовательскую страницу, о которой мы рассказывали при объяснении библиотеки [HealthChecks ASP.NET Core](https://github.com/aspnet/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="8375e-200">You can use simple custom applications showing the state of your services, like the custom page we showed when we explained [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span></span> <span data-ttu-id="8375e-201">Или можно использовать более сложные инструменты, такие как Azure Application Insights и Operations Management Suite, которые будут создавать оповещения на основе потока событий.</span><span class="sxs-lookup"><span data-stu-id="8375e-201">Or you could use more advanced tools like Azure Application Insights and Operations Management Suite to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="8375e-202">Наконец, если вы сохраняете все потоки событий, то для визуализации данных можно использовать Microsoft Power BI или решения сторонних поставщиков, например Kibana или Splunk.</span><span class="sxs-lookup"><span data-stu-id="8375e-202">Finally, if you were storing all the event streams, you can use Microsoft Power BI or a third-party solution like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8375e-203">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="8375e-203">Additional resources</span></span>

-   <span data-ttu-id="8375e-204">**ASP.NET Core HealthChecks** (ранний выпуск) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span><span class="sxs-lookup"><span data-stu-id="8375e-204">**ASP.NET Core HealthChecks** (early release) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span></span>

-   <span data-ttu-id="8375e-205">**Общие сведения о мониторинге работоспособности Service Fabric**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span><span class="sxs-lookup"><span data-stu-id="8375e-205">**Introduction to Service Fabric health monitoring**
[*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span></span>

-   <span data-ttu-id="8375e-206">**Azure Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span><span class="sxs-lookup"><span data-stu-id="8375e-206">**Azure Application Insights**
[*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span></span>

-   <span data-ttu-id="8375e-207">**Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span><span class="sxs-lookup"><span data-stu-id="8375e-207">**Microsoft Operations Management Suite**
[*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="8375e-208">[Назад] (implement-circuit-breaker-pattern.md) [Далее] (../secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="8375e-208">[Previous] (implement-circuit-breaker-pattern.md) [Next] (../secure-net-microservices-web-applications/index.md)</span></span>
