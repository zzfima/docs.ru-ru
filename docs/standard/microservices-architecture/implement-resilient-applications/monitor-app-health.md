---
title: "Наблюдение за работоспособностью"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Наблюдение за работоспособностью"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: cbbad72f06bcaa882bc50083d9103b0872f51754
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="health-monitoring"></a><span data-ttu-id="e5c77-104">Наблюдение за работоспособностью</span><span class="sxs-lookup"><span data-stu-id="e5c77-104">Health monitoring</span></span>

<span data-ttu-id="e5c77-105">Наблюдение за работоспособностью можно разрешить почти реальном времени сведения о состоянии контейнеров и микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="e5c77-105">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="e5c77-106">Наблюдение за работоспособностью крайне важно для нескольких аспектов работы микрослужбами и особенно важна при orchestrators обновления частичное применение поэтапно, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="e5c77-106">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="e5c77-107">Микрослужбами-приложениях часто используют периодических сигналов или проверки работоспособности для включения их мониторы производительности планировщиков и orchestrators для отслеживания несколько служб.</span><span class="sxs-lookup"><span data-stu-id="e5c77-107">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="e5c77-108">Если службы не удается отправить определенного рода сигнал «Я alive», по требованию или по расписанию, приложения могут появиться риски при развертывании обновлений, или он может просто определяйте слишком поздно и не удается остановить каскадных сбоев, которые могут быть сохранены в крупных сбоев.</span><span class="sxs-lookup"><span data-stu-id="e5c77-108">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might simply detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="e5c77-109">В обычной модели службы отправлять отчеты о состоянии, и эти данные агрегируются для создания общего представления о состоянии работоспособности приложения.</span><span class="sxs-lookup"><span data-stu-id="e5c77-109">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="e5c77-110">При использовании orchestrator, можете указать сведения о работоспособности кластер вашей orchestrator кластера смогут действовать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e5c77-110">If you are using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="e5c77-111">Если инвестиций в отчет о работоспособности высокого качества, который настроен для вашего приложения, можно обнаружить и облегчает Устранение проблем для выполняющегося приложения.</span><span class="sxs-lookup"><span data-stu-id="e5c77-111">If you invest in high-quality health reporting that is customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implementing-health-checks-in-aspnet-core-services"></a><span data-ttu-id="e5c77-112">Реализация работоспособности проверяет в службах ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e5c77-112">Implementing health checks in ASP.NET Core services</span></span>

<span data-ttu-id="e5c77-113">При разработке микрослужбу или веб-приложения ASP.NET Core, можно использовать библиотеку HealthChecks от службы технической поддержки ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e5c77-113">When developing an ASP.NET Core microservice or web application, you can use a library named HealthChecks from the ASP.NET team.</span></span> <span data-ttu-id="e5c77-114">(По состоянию на май 2017 г., более раннего выпуска можно найти в GitHub).</span><span class="sxs-lookup"><span data-stu-id="e5c77-114">(As of May 2017, an early release is available on GitHub).</span></span>

<span data-ttu-id="e5c77-115">Эта библиотека является простой в использовании и предоставляет возможности, позволяющие проверить работоспособность любого конкретного внешний ресурс, необходимый для приложения (например, база данных SQL Server или удаленного API).</span><span class="sxs-lookup"><span data-stu-id="e5c77-115">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="e5c77-116">При использовании этой библиотеки, можно решить, значит ресурса работоспособно, как рассказывается ниже.</span><span class="sxs-lookup"><span data-stu-id="e5c77-116">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="e5c77-117">Чтобы использовать эту библиотеку, необходимо сначала использовать библиотеку в вашей микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="e5c77-117">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="e5c77-118">Во-вторых требуется клиентское приложение, которое запрашивает для отчетов о работоспособности.</span><span class="sxs-lookup"><span data-stu-id="e5c77-118">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="e5c77-119">Интерфейс может быть пользовательского приложения для создания отчетов, или это может быть сам модуль, может реагировать соответствующим образом для состояния работоспособности.</span><span class="sxs-lookup"><span data-stu-id="e5c77-119">That front end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="e5c77-120">Использование библиотеки HealthChecks в вашей серверной части ASP.NET микрослужбами</span><span class="sxs-lookup"><span data-stu-id="e5c77-120">Using the HealthChecks library in your back end ASP.NET microservices</span></span>

<span data-ttu-id="e5c77-121">Вы увидите, как библиотека HealthChecks используется в примере приложения eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="e5c77-121">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="e5c77-122">Чтобы начать, необходимо определить, что такое состояние для каждого микрослужбу.</span><span class="sxs-lookup"><span data-stu-id="e5c77-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="e5c77-123">В примере приложения микрослужбами находятся в работоспособном состоянии, если микрослужбу API доступен через HTTP, и если его связанной базы данных SQL Server будет доступен.</span><span class="sxs-lookup"><span data-stu-id="e5c77-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="e5c77-124">В будущем можно установить библиотеку HealthChecks как пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="e5c77-124">In the future, you will be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="e5c77-125">Однако на момент написания этой статьи, необходимо загрузить и компиляции кода как часть решения.</span><span class="sxs-lookup"><span data-stu-id="e5c77-125">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="e5c77-126">Клонировать код, найти по адресу https://github.com/aspnet/HealthChecks и скопируйте следующие папки решения.</span><span class="sxs-lookup"><span data-stu-id="e5c77-126">Clone the code available at https://github.com/aspnet/HealthChecks and copy the following folders to your solution.</span></span>

  - <span data-ttu-id="e5c77-127">src/Общие</span><span class="sxs-lookup"><span data-stu-id="e5c77-127">src/common</span></span>
  - <span data-ttu-id="e5c77-128">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="e5c77-128">src/Microsoft.AspNetCore.HealthChecks</span></span>
  - <span data-ttu-id="e5c77-129">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="e5c77-129">src/Microsoft.Extensions.HealthChecks</span></span>
  - <span data-ttu-id="e5c77-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="e5c77-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="e5c77-131">Можно также использовать дополнительные проверки аналогичных для Azure (Microsoft.Extensions.HealthChecks.AzureStorage), однако, поскольку эта версия eShopOnContainers не имеет какой-либо зависимостью в Azure, он не требуется.</span><span class="sxs-lookup"><span data-stu-id="e5c77-131">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="e5c77-132">Проверку работоспособности ASP.NET, не обязательно, поскольку eShopOnContainers основан на ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5c77-132">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="e5c77-133">На рис. 10-6 показаны библиотеки HealthChecks в Visual Studio, можно будет использовать как стандартный блок любой микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="e5c77-133">Figure 10-6 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![](./media/image6.png)

<span data-ttu-id="e5c77-134">**На рис. 10-6**.</span><span class="sxs-lookup"><span data-stu-id="e5c77-134">**Figure 10-6**.</span></span> <span data-ttu-id="e5c77-135">ASP.NET Core HealthChecks библиотеки исходного кода в решении Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e5c77-135">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="e5c77-136">Представленном выше, в первую очередь необходимо выполнить в каждом проекте микрослужбу является добавление ссылки на три HealthChecks библиотеки.</span><span class="sxs-lookup"><span data-stu-id="e5c77-136">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="e5c77-137">После этого добавьте действия проверки работоспособности, которые необходимо выполнить в этом микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="e5c77-137">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="e5c77-138">Эти действия, по сути являются зависимостей от других микрослужбами (HttpUrlCheck) или баз данных (в настоящее время SqlCheck\* баз данных SQL Server).</span><span class="sxs-lookup"><span data-stu-id="e5c77-138">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="e5c77-139">Можно добавить действие внутри класса при запуске каждого микрослужбу ASP.NET или веб-приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e5c77-139">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="e5c77-140">Каждая служба или веб-приложения должны быть настроены, добавив его зависимостей HTTP или базы данных в качестве одного метода AddHealthCheck.</span><span class="sxs-lookup"><span data-stu-id="e5c77-140">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="e5c77-141">Например веб-приложения MVC eShopOnContainers зависит от многих служб, поэтому имеет несколько методов AddCheck добавлен для проверки работоспособности.</span><span class="sxs-lookup"><span data-stu-id="e5c77-141">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="e5c77-142">Например в следующем коде вы увидите как микрослужбу каталога добавляет зависимость своей базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5c77-142">For instance, in the following code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

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

<span data-ttu-id="e5c77-143">Тем не менее веб-приложение MVC eShopOnContainers имеет несколько зависимостей от остальной части микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="e5c77-143">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="e5c77-144">Таким образом он вызывает один метод AddUrlCheck для каждого микрослужбу, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e5c77-144">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following example:</span></span>

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

<span data-ttu-id="e5c77-145">Таким образом микрослужбу не будет поддерживать «Исправен», пока все проверки работоспособны также.</span><span class="sxs-lookup"><span data-stu-id="e5c77-145">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="e5c77-146">Если микрослужбу имеет зависимость от службы или на сервере SQL Server, нужно просто добавить проверку Healthy("Ok").</span><span class="sxs-lookup"><span data-stu-id="e5c77-146">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="e5c77-147">Приведенный ниже код взят из микрослужбу basket.api eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="e5c77-147">The following code is from the eShopOnContainers basket.api microservice.</span></span> <span data-ttu-id="e5c77-148">(Микрослужбу корзины использует кэш Redis, но библиотеке еще не содержит поставщик проверки работоспособности Redis).</span><span class="sxs-lookup"><span data-stu-id="e5c77-148">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="e5c77-149">Для службы или веб-приложения для предоставления конечной точки проверки работоспособности, он должен включить UseHealthChecks (\[*URL-адрес\_для\_работоспособности\_проверяет*\]) расширения метод.</span><span class="sxs-lookup"><span data-stu-id="e5c77-149">For a service or web application to expose the health check endpoint, it has to enable the UseHealthChecks(\[*url\_for\_health\_checks*\]) extension method.</span></span> <span data-ttu-id="e5c77-150">Этот метод переходит на WebHostBuilder уровне основного метода в класс программы ASP.NET Core службы или веб-приложения, сразу же после UseKestrel, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="e5c77-150">This method goes at the WebHostBuilder level in the main method of the Program class of your ASP.NET Core service or web application, right after UseKestrel as shown in the code below.</span></span>

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

<span data-ttu-id="e5c77-151">Процесс выглядит следующим образом: каждый микрослужбу предоставляет / HC конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e5c77-151">The process works like this: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="e5c77-152">Этой конечной точки создается библиотекой HealthChecks по промежуточного слоя ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e5c77-152">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="e5c77-153">Все проверки работоспособности, настроенные в методе AddHealthChecks в классе запуска выполняется при вызове этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e5c77-153">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="e5c77-154">Метод UseHealthChecks ожидает, что порт или путь.</span><span class="sxs-lookup"><span data-stu-id="e5c77-154">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="e5c77-155">Этот порт или путь — это конечная точка, использовать для проверки состояния службы работоспособности.</span><span class="sxs-lookup"><span data-stu-id="e5c77-155">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="e5c77-156">Например микрослужбу каталога использует / HC путь.</span><span class="sxs-lookup"><span data-stu-id="e5c77-156">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="caching-health-check-responses"></a><span data-ttu-id="e5c77-157">Кэширование ответов проверки работоспособности</span><span class="sxs-lookup"><span data-stu-id="e5c77-157">Caching health check responses</span></span>

<span data-ttu-id="e5c77-158">Поскольку вы не хотите вызвать отказ в обслуживании (DoS) в службах или просто не хотите повлиять на производительность службы, проверьте ресурсы слишком часто, можно кэшировать возвращает и настроить длительность кэширования для каждой проверки работоспособности.</span><span class="sxs-lookup"><span data-stu-id="e5c77-158">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="e5c77-159">По умолчанию длительность кэширования внутренне устанавливается в 5 минут, но вы можете изменить этот интервал кэша на каждом проверки работоспособности, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="e5c77-159">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="e5c77-160">Запросы к микрослужбами отчет о состоянии работоспособности</span><span class="sxs-lookup"><span data-stu-id="e5c77-160">Querying your microservices to report about their health status</span></span>

<span data-ttu-id="e5c77-161">После настройки проверки работоспособности, как описано здесь, поскольку микрослужбу работает в Docker, можно напрямую проверять из браузера, если он находится в работоспособном состоянии.</span><span class="sxs-lookup"><span data-stu-id="e5c77-161">When you have configured health checks as described here, once the microservice is running in Docker, you can directly check from a browser if it is healthy.</span></span> <span data-ttu-id="e5c77-162">(Это нужно, чтобы доступ к контейнеру через localhost или внешний IP-адрес узла Docker публикации порт контейнера из узла Docker.) На рис. 10-7 показан запрос в веб-браузер и соответствующие ответные меры.</span><span class="sxs-lookup"><span data-stu-id="e5c77-162">(This does require that you are publishing the container port out of the Docker host, so you can access the container through localhost or through the external Docker host IP.) Figure 10-7 shows a request in a browser and the corresponding response.</span></span>

![](./media/image7.png)

<span data-ttu-id="e5c77-163">**На рис. 10-7**.</span><span class="sxs-lookup"><span data-stu-id="e5c77-163">**Figure 10-7**.</span></span> <span data-ttu-id="e5c77-164">Проверка состояния работоспособности службы единого из браузера</span><span class="sxs-lookup"><span data-stu-id="e5c77-164">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="e5c77-165">В этом тесте видно, catalog.api микрослужбу, (работающий в порте 5101) находится в работоспособном состоянии, возвращая код состояния HTTP 200 и сведения о состоянии в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="e5c77-165">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="e5c77-166">Это также означает, что внутри службы также проверка работоспособности его зависимости базы данных SQL Server и что проверки работоспособности было получено сообщение о неполадках работоспособен.</span><span class="sxs-lookup"><span data-stu-id="e5c77-166">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="using-watchdogs"></a><span data-ttu-id="e5c77-167">С помощью watchdogs</span><span class="sxs-lookup"><span data-stu-id="e5c77-167">Using watchdogs</span></span>

<span data-ttu-id="e5c77-168">Контрольный является отдельной службе, можно посмотреть работоспособности и загрузка различных служб и отчет о работоспособности о микрослужбами путем запроса с библиотекой HealthChecks, представленный ранее.</span><span class="sxs-lookup"><span data-stu-id="e5c77-168">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the HealthChecks library introduced earlier.</span></span> <span data-ttu-id="e5c77-169">Это поможет предотвратить ошибки, которые не будут обнаружены на основе представления одной службы.</span><span class="sxs-lookup"><span data-stu-id="e5c77-169">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="e5c77-170">Watchdogs также могут лучше всего узла код, который можно выполнять действия по исправлению известных причин без вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="e5c77-170">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="e5c77-171">Образец eShopOnContainers содержит веб-страницы, отображающий образцов отчетов проверку работоспособности, как показано на рисунке 10-8.</span><span class="sxs-lookup"><span data-stu-id="e5c77-171">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 10-8.</span></span> <span data-ttu-id="e5c77-172">Это простейший наблюдения, можно создать, поскольку он осуществляет — отображает состояние микрослужбами и веб-приложений в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="e5c77-172">This is the simplest watchdog you could have, since all it does is shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="e5c77-173">Обычно контрольного также выполняет действия при обнаружении неработоспособности состояний.</span><span class="sxs-lookup"><span data-stu-id="e5c77-173">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![](./media/image8.png)

<span data-ttu-id="e5c77-174">**На рис. 10-8**.</span><span class="sxs-lookup"><span data-stu-id="e5c77-174">**Figure 10-8**.</span></span> <span data-ttu-id="e5c77-175">Отчет о проверке работоспособности образец в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="e5c77-175">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="e5c77-176">Таким образом по промежуточного слоя ASP.NET библиотеки ASP.NET Core HealthChecks предоставляет конечную точку проверки работоспособности одной для каждого микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="e5c77-176">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="e5c77-177">Будет выполнять проверку работоспособности, определенных внутри него и вернуть состояние общей работоспособности в зависимости от этих проверок.</span><span class="sxs-lookup"><span data-stu-id="e5c77-177">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="e5c77-178">Библиотека HealthChecks расширить с помощью новых проверок работоспособности будущих внешних ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e5c77-178">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="e5c77-179">Например предполагается, что в будущем библиотека будет иметь проверки работоспособности для кэша Redis и для других баз данных.</span><span class="sxs-lookup"><span data-stu-id="e5c77-179">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="e5c77-180">Библиотека позволяет работоспособности, создание отчетов с помощью несколько зависимостей службы или приложения и предпринимать действия в зависимости от этих проверок работоспособности.</span><span class="sxs-lookup"><span data-stu-id="e5c77-180">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="e5c77-181">Проверку работоспособности при использовании orchestrators</span><span class="sxs-lookup"><span data-stu-id="e5c77-181">Health checks when using orchestrators</span></span>

<span data-ttu-id="e5c77-182">Для наблюдения за доступностью вашей микрослужбами, orchestrators с помощью Docker Swarm, Kubernetes и Service Fabric периодически выполняет проверку работоспособности, отправляя запросы для проверки микрослужбами.</span><span class="sxs-lookup"><span data-stu-id="e5c77-182">To monitor the availability of your microservices, orchestrators like Docker Swarm, Kubernetes, and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="e5c77-183">Когда orchestrator определяет, что службе/контейнере неработоспособен, она перестает направлять запросы к этому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="e5c77-183">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="e5c77-184">Он также обычно создает новый экземпляр этого контейнера.</span><span class="sxs-lookup"><span data-stu-id="e5c77-184">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="e5c77-185">Например большинство orchestrators можно использовать проверки работоспособности для управления развертываниями простоев.</span><span class="sxs-lookup"><span data-stu-id="e5c77-185">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="e5c77-186">Только при изменении службы или контейнера в работоспособное состояние будет orchestrator запустите перенаправляет трафик для экземпляров службы или контейнера.</span><span class="sxs-lookup"><span data-stu-id="e5c77-186">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="e5c77-187">Наблюдение за работоспособностью особенно важно при orchestrator выполняет обновление приложения.</span><span class="sxs-lookup"><span data-stu-id="e5c77-187">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="e5c77-188">Некоторые orchestrators (например, Azure Service Fabric) обновление служб в этапах — например, может обновить пятая поверхности кластера для каждого обновления приложения.</span><span class="sxs-lookup"><span data-stu-id="e5c77-188">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="e5c77-189">Набор узлов, которая обновляется в то же время называется *домен обновления*.</span><span class="sxs-lookup"><span data-stu-id="e5c77-189">The set of nodes that is upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="e5c77-190">После каждого обновления домена будет обновлен и становится доступным для пользователей, домен обновления прошла проверку работоспособности перед развертыванием перемещается к следующему домену обновления.</span><span class="sxs-lookup"><span data-stu-id="e5c77-190">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="e5c77-191">Другим аспектом службы работоспособности сообщает метрики из службы.</span><span class="sxs-lookup"><span data-stu-id="e5c77-191">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="e5c77-192">Это расширенные возможности модели работоспособности некоторые orchestrators как Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="e5c77-192">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="e5c77-193">Метрики важны при использовании orchestrator, так как они используются для балансировки использования ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e5c77-193">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="e5c77-194">Также могут возникать метрик индикатора работоспособности системы.</span><span class="sxs-lookup"><span data-stu-id="e5c77-194">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="e5c77-195">Например возможно, которое содержит много микрослужбами и каждый экземпляр сообщает метрика запросов в секунду (RPS).</span><span class="sxs-lookup"><span data-stu-id="e5c77-195">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="e5c77-196">Если одна служба использует больше ресурсов (память, процессор, т. д.), чем другая служба, orchestrator может перемещаться экземпляров службы в кластере с целью поддержания даже использование ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e5c77-196">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="e5c77-197">Обратите внимание, что при использовании Azure Service Fabric, он предоставляет собственный [наблюдение за работоспособностью модели](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), который является более сложной, чем простой проверок.</span><span class="sxs-lookup"><span data-stu-id="e5c77-197">Note that if you are using Azure Service Fabric, it provides its own [Health Monitoring model](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="e5c77-198">Расширенный мониторинг: визуализации, анализ и предупреждения</span><span class="sxs-lookup"><span data-stu-id="e5c77-198">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="e5c77-199">Последняя часть мониторинга визуализируемый поток событий, отчеты о производительности для службы и оповещение при обнаружении проблемы.</span><span class="sxs-lookup"><span data-stu-id="e5c77-199">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="e5c77-200">Можно использовать различные решения для наблюдения за данный аспект.</span><span class="sxs-lookup"><span data-stu-id="e5c77-200">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="e5c77-201">Можно использовать простые пользовательские приложения с состоянием служб, как пользовательскую страницу мы показали, когда было показано [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="e5c77-201">You can use simple custom applications showing the state of your services, like the custom page we showed when we explained [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span></span> <span data-ttu-id="e5c77-202">Или можно использовать более сложные средства, как Azure Application Insights и Operations Management Suite, чтобы создавать оповещения на основе потока событий.</span><span class="sxs-lookup"><span data-stu-id="e5c77-202">Or you could use more advanced tools like Azure Application Insights and Operations Management Suite to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="e5c77-203">Наконец Если хранить все потоки событий, можно использовать Microsoft Power BI или решения сторонних поставщиков, например Kibana или Splunk для визуализации данных.</span><span class="sxs-lookup"><span data-stu-id="e5c77-203">Finally, if you were storing all the event streams, you can use Microsoft Power BI or a third-party solution like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e5c77-204">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e5c77-204">Additional resources</span></span>

-   <span data-ttu-id="e5c77-205">**ASP.NET Core HealthChecks** (ранний выпуск) [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span><span class="sxs-lookup"><span data-stu-id="e5c77-205">**ASP.NET Core HealthChecks** (early release) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span></span>

-   <span data-ttu-id="e5c77-206">**Введение в мониторинг работоспособности Service Fabric**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span><span class="sxs-lookup"><span data-stu-id="e5c77-206">**Introduction to Service Fabric health monitoring**
[*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span></span>

-   <span data-ttu-id="e5c77-207">**Приложения Azure Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span><span class="sxs-lookup"><span data-stu-id="e5c77-207">**Azure Application Insights**
[*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span></span>

-   <span data-ttu-id="e5c77-208">**Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span><span class="sxs-lookup"><span data-stu-id="e5c77-208">**Microsoft Operations Management Suite**
[*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e5c77-209">[Предыдущие] (реализация канала разбиения pattern.md) [Далее] (.. /Secure-NET-microservices-Web-Applications/index.MD)</span><span class="sxs-lookup"><span data-stu-id="e5c77-209">[Previous] (implement-circuit-breaker-pattern.md) [Next] (../secure-net-microservices-web-applications/index.md)</span></span>
