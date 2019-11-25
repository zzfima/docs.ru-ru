---
title: Реализация шлюзов API с помощью Ocelot
description: Узнайте, как реализовывать шлюзы API с помощью Ocelot и как использовать Ocelot в среде на базе контейнеров.
ms.date: 10/02/2018
ms.openlocfilehash: 6c576a17d784777557bfb8bd99438eb111e8ec2e
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737656"
---
# <a name="implement-api-gateways-with-ocelot"></a><span data-ttu-id="73d75-103">Реализация шлюзов API с помощью Ocelot</span><span class="sxs-lookup"><span data-stu-id="73d75-103">Implement API Gateways with Ocelot</span></span>

<span data-ttu-id="73d75-104">В примере приложения для микрослужб [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) используется [Ocelot](https://github.com/ThreeMammals/Ocelot) — простой и легкий шлюз API, который можно развернуть где угодно вместе с вашими микрослужбами и контейнерами, например в любой из следующих сред, используемых eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="73d75-104">The reference microservice application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) is using [Ocelot](https://github.com/ThreeMammals/Ocelot), a simple and lightweight API Gateway that you can deploy anywhere along with your microservices/containers, such as in any of the following environments used by eShopOnContainers.</span></span>

- <span data-ttu-id="73d75-105">Узел Docker, на локальном компьютере разработчика, в локальной среде или в облаке.</span><span class="sxs-lookup"><span data-stu-id="73d75-105">Docker host, in your local dev PC, on-premises or in the cloud.</span></span>
- <span data-ttu-id="73d75-106">Кластер Kubernetes, локально или в управляемой облачной среде, например в службе Azure Kubernetes (AKS).</span><span class="sxs-lookup"><span data-stu-id="73d75-106">Kubernetes cluster, on-premises or in managed cloud such as Azure Kubernetes Service (AKS).</span></span>
- <span data-ttu-id="73d75-107">Кластер Service Fabric, локально или в облаке.</span><span class="sxs-lookup"><span data-stu-id="73d75-107">Service Fabric cluster, on-premises or in the cloud.</span></span>
- <span data-ttu-id="73d75-108">Сетка Service Fabric, как PaaS или бессерверное решение в Azure.</span><span class="sxs-lookup"><span data-stu-id="73d75-108">Service Fabric mesh, as PaaS/Serverless in Azure.</span></span>

## <a name="architect-and-design-your-api-gateways"></a><span data-ttu-id="73d75-109">Разработка архитектуры и проектирование шлюзов API</span><span class="sxs-lookup"><span data-stu-id="73d75-109">Architect and design your API Gateways</span></span>

<span data-ttu-id="73d75-110">На следующей архитектурной схеме показано, как реализуются шлюзы API с помощью Ocelot в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="73d75-110">The following architecture diagram shows how API Gateways are implemented with Ocelot in eShopOnContainers.</span></span>

![Схема, показывающая архитектуру eShopOnContainers.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture.png)

<span data-ttu-id="73d75-112">**Рис. 6-28**.</span><span class="sxs-lookup"><span data-stu-id="73d75-112">**Figure 6-28**.</span></span> <span data-ttu-id="73d75-113">Архитектура eShopOnContainers со шлюзами API</span><span class="sxs-lookup"><span data-stu-id="73d75-113">eShopOnContainers architecture with API Gateways</span></span>

<span data-ttu-id="73d75-114">На схеме показано, как целое приложение развертывается в одном узле Docker или на компьютере разработки с помощью Docker для Windows или Docker для Mac.</span><span class="sxs-lookup"><span data-stu-id="73d75-114">That diagram shows how the whole application is deployed into a single Docker host or development PC with “Docker for Windows” or “Docker for Mac”.</span></span> <span data-ttu-id="73d75-115">Развертывание в любом оркестраторе будет выглядеть аналогично, но любой контейнер на схеме можно было бы горизонтально масштабировать в оркестраторе.</span><span class="sxs-lookup"><span data-stu-id="73d75-115">However, deploying into any orchestrator would be pretty similar but any container in the diagram could be scaled-out in the orchestrator.</span></span>

<span data-ttu-id="73d75-116">Кроме того, ресурсы инфраструктуры, такие как базы данных, кэш и брокеры сообщений, необходимо выгрузить из оркестратора и развернуть в системах высокой доступности для инфраструктуры, таких как база данных SQL Azure, Azure Cosmos DB, Azure Redis, служебная шина Azure или любое локальное решение по кластеризации высокого уровня доступности.</span><span class="sxs-lookup"><span data-stu-id="73d75-116">In addition, the infrastructure assets such as databases, cache, and message brokers should be offloaded from the orchestrator and deployed into high available systems for infrastructure, like Azure SQL Database, Azure Cosmos DB, Azure Redis, Azure Service Bus, or any HA clustering solution on-premises.</span></span>

<span data-ttu-id="73d75-117">Как видно на схеме, наличие нескольких шлюзов API обеспечивает автономность нескольких команд разработчиков (в данном случае — маркетинговые функции и функции магазина) при разработке и развертывании микрослужб, а также собственных связанных шлюзов API.</span><span class="sxs-lookup"><span data-stu-id="73d75-117">As you can also notice in the diagram, having several API Gateways allows multiple development teams to be autonomous (in this case Marketing features vs. Shopping features) when developing and deploying their microservices plus their own related API Gateways.</span></span>

<span data-ttu-id="73d75-118">Если бы у вас был единый монолитный шлюз API, несколько команд разработчиков обновляли бы одну точку, и все микрослужбы были бы привязаны к одной части приложения.</span><span class="sxs-lookup"><span data-stu-id="73d75-118">If you had a single monolithic API Gateway that would mean a single point to be updated by several development teams, which could couple all the microservices with a single part of the application.</span></span>

<span data-ttu-id="73d75-119">Если пойти еще дальше, иногда можно выделить один детализированный шлюз API для конкретной микрослужбы в зависимости от выбранной архитектуры.</span><span class="sxs-lookup"><span data-stu-id="73d75-119">Going much further in the design, sometimes a fine-grained API Gateway can also be limited to a single business microservice depending on the chosen architecture.</span></span> <span data-ttu-id="73d75-120">Наличие границ шлюза API, определяемых бизнес-требованиями или доменом, поможет лучше спроектировать шлюз.</span><span class="sxs-lookup"><span data-stu-id="73d75-120">Having the API Gateway’s boundaries dictated by the business or domain will help you to get a better design.</span></span>

<span data-ttu-id="73d75-121">Например, высокая детализация для уровня шлюза API может быть особенно удобной для более сложных приложений с составным пользовательским интерфейсом на основе микрослужб, так как концепция детализированного шлюза API похожа на службу с составным пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="73d75-121">For instance, fine granularity in the API Gateway tier can be especially useful for more advanced composite UI applications that are based on microservices, because the concept of a fine-grained API Gateway is similar to a UI composition service.</span></span>

<span data-ttu-id="73d75-122">Подробнее этот вопрос рассмотрен в предыдущем разделе [Создание составного пользовательского интерфейса на основе микрослужб](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span><span class="sxs-lookup"><span data-stu-id="73d75-122">We delve into more details in the previous section [Creating composite UI based on microservices](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span></span>

<span data-ttu-id="73d75-123">Вкратце, пользовательский шлюз API удобно использовать для многих приложений среднего и большого размера, но не в качестве единого монолитного агрегатора или уникального централизованного пользовательского шлюза API, если только этот шлюз API не допускает несколько независимых областей конфигурации для нескольких групп разработчиков, создающих автономные микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="73d75-123">As key takeaway, for many medium- and large-size applications, using a custom-built API Gateway product is usually a good approach, but not as a single monolithic aggregator or unique central custom API Gateway unless that API Gateway allows multiple independent configuration areas for the several development teams creating autonomous microservices.</span></span>

### <a name="sample-microservicescontainers-to-re-route-through-the-api-gateways"></a><span data-ttu-id="73d75-124">Пример микрослужб и контейнеров для перенаправления через шлюзы API</span><span class="sxs-lookup"><span data-stu-id="73d75-124">Sample microservices/containers to re-route through the API Gateways</span></span>

<span data-ttu-id="73d75-125">Например, у eShopOnContainers есть около шести типов внутренних микрослужб, которые требуется публиковать через шлюзы API, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="73d75-125">As an example, eShopOnContainers has around six internal microservice-types that have to be published through the API Gateways, as shown in the following image.</span></span>

![Снимок экрана папки служб, содержащей вложенные папки.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-microservice-folders.png)

<span data-ttu-id="73d75-127">**Рис. 6-29**.</span><span class="sxs-lookup"><span data-stu-id="73d75-127">**Figure 6-29**.</span></span> <span data-ttu-id="73d75-128">Папки микрослужб в решении eShopOnContainers в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73d75-128">Microservice folders in eShopOnContainers solution in Visual Studio</span></span>

<span data-ttu-id="73d75-129">Что касается службы идентификации, в проекте она не проходит через шлюзы API, так как только она является общей для всей системы, но с помощью Ocelot ее также можно включить в списки перенаправления.</span><span class="sxs-lookup"><span data-stu-id="73d75-129">About the Identity service, in the design it's left out of the API Gateway routing because it's the only cross-cutting concern in the system, although with Ocelot it's also possible to include it as part of the rerouting lists.</span></span>

<span data-ttu-id="73d75-130">Все эти службы в настоящее время реализованы как службы веб-API ASP.NET Core, как видно из кода.</span><span class="sxs-lookup"><span data-stu-id="73d75-130">All those services are currently implemented as ASP.NET Core Web API services, as you can tell from the code.</span></span> <span data-ttu-id="73d75-131">Давайте сосредоточимся на одной из микрослужб, например коде микрослужбы каталога Catalog.</span><span class="sxs-lookup"><span data-stu-id="73d75-131">Let’s focus on one of the microservices like the Catalog microservice code.</span></span>

![Снимок экрана обозревателя решений, где показано содержимое проекта Catalog.API.](./media/implement-api-gateways-with-ocelot/catalog-api-microservice-folders.png)

<span data-ttu-id="73d75-133">**Рис. 6-30**.</span><span class="sxs-lookup"><span data-stu-id="73d75-133">**Figure 6-30**.</span></span> <span data-ttu-id="73d75-134">Пример микрослужбы веб-API (микрослужба каталога)</span><span class="sxs-lookup"><span data-stu-id="73d75-134">Sample Web API microservice (Catalog microservice)</span></span>

<span data-ttu-id="73d75-135">Вы видите, что микрослужба каталога является стандартным проектом веб-API ASP.NET Core с несколькими контроллерами и методами, как в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="73d75-135">You can see that the Catalog microservice is a typical ASP.NET Core Web API project with several controllers and methods like in the following code.</span></span>

```csharp
[HttpGet]
[Route("items/{id:int}")]
[ProducesResponseType((int)HttpStatusCode.BadRequest)]
[ProducesResponseType((int)HttpStatusCode.NotFound)]
[ProducesResponseType(typeof(CatalogItem),(int)HttpStatusCode.OK)]
public async Task<IActionResult> GetItemById(int id)
{
    if (id <= 0)
    {
        return BadRequest();
    }
    var item = await _catalogContext.CatalogItems.
                                          SingleOrDefaultAsync(ci => ci.Id == id);
    //…

    if (item != null)
    {
        return Ok(item);
    }
    return NotFound();
}
```

<span data-ttu-id="73d75-136">HTTP-запрос в итоге запустит такой код C#, который получает доступ к базе данных микрослужбы и выполняет какое-либо необходимое действие.</span><span class="sxs-lookup"><span data-stu-id="73d75-136">The HTTP request will end up running that kind of C# code accessing the microservice database and any additional required action.</span></span>

<span data-ttu-id="73d75-137">Если говорить об URL-адресе микрослужбы, при развертывании контейнеров на локальном компьютере разработки (локальном узле Docker) каждый контейнер микрослужбы всегда имеет внутренний порт (обычно это порт 80), указанный в файле dockerfile, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="73d75-137">Regarding the microservice URL, when the containers are deployed in your local development PC (local Docker host), each microservice’s container has always an internal port (usually port 80) specified in its dockerfile, as in the following dockerfile:</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0.5 AS base
WORKDIR /app
EXPOSE 80
```

<span data-ttu-id="73d75-138">Порт 80, показанный в коде, находится внутри узла Docker, поэтому клиентские приложения не имеют к нему доступа.</span><span class="sxs-lookup"><span data-stu-id="73d75-138">The port 80 shown in the code is internal within the Docker host, so it can't be reached by client apps.</span></span>

<span data-ttu-id="73d75-139">Клиентские приложения имеют доступ только к внешним портам (если таковые имеются), которые публикуются при развертывании с помощью `docker-compose`.</span><span class="sxs-lookup"><span data-stu-id="73d75-139">Client apps can access only the external ports (if any) published when deploying with `docker-compose`.</span></span>

<span data-ttu-id="73d75-140">Эти внешние порты не следует публиковать при развертывании в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="73d75-140">Those external ports shouldn't be published when deploying to a production environment.</span></span> <span data-ttu-id="73d75-141">Именно поэтому необходимо использовать шлюз API, чтобы избежать прямого обмена данными между микрослужбами и клиентскими приложениями.</span><span class="sxs-lookup"><span data-stu-id="73d75-141">This is precisely why you want to use the API Gateway, to avoid the direct communication between the client apps and the microservices.</span></span>

<span data-ttu-id="73d75-142">Тем не менее при разработке вам следует обращаться к микрослужбам или контейнерам напрямую и запускать их через Swagger.</span><span class="sxs-lookup"><span data-stu-id="73d75-142">However, when developing, you want to access the microservice/container directly and run it through Swagger.</span></span> <span data-ttu-id="73d75-143">Вот почему в eShopOnContainers внешние порты по-прежнему указываются даже в том случае, если они будут использоваться шлюзом API или клиентскими приложениями.</span><span class="sxs-lookup"><span data-stu-id="73d75-143">That’s why in eShopOnContainers, the external ports are still specified even when they won’t be used by the API Gateway or the client apps.</span></span>

<span data-ttu-id="73d75-144">Ниже приведен пример файла `docker-compose.override.yml` для микрослужбы каталога:</span><span class="sxs-lookup"><span data-stu-id="73d75-144">Here’s an example of the `docker-compose.override.yml` file for the Catalog microservice:</span></span>

```yml
catalog.api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

<span data-ttu-id="73d75-145">Вы видите, что в конфигурации docker-compose.override.yml внутренний порт контейнера каталога — это порт 80, но порт для внешнего доступа — 5101.</span><span class="sxs-lookup"><span data-stu-id="73d75-145">You can see how in the docker-compose.override.yml configuration the internal port for the Catalog container is port 80, but the port for external access is 5101.</span></span> <span data-ttu-id="73d75-146">Однако этот порт не должен использоваться приложением при использовании шлюза API. Он предназначен только для отладки, запуска и тестирования микрослужбы каталога.</span><span class="sxs-lookup"><span data-stu-id="73d75-146">But this port shouldn’t be used by the application when using an API Gateway, only to debug, run and test just the Catalog microservice.</span></span>

<span data-ttu-id="73d75-147">Как правило, вы не выполняете развертывание в рабочей среде с помощью docker-compose, так как правильной рабочей средой для развертывания микрослужб является оркестратор, например Kubernetes или Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="73d75-147">Normally, you won’t be deploying with docker-compose into a production environment because the right production deployment environment for microservices is an orchestrator like Kubernetes or Service Fabric.</span></span> <span data-ttu-id="73d75-148">При развертывании в этих средах вы используете различные файлы конфигурации, где вы не публикуете внешние порты для микрослужб напрямую, но всегда используете обратный прокси-сервер от шлюза API.</span><span class="sxs-lookup"><span data-stu-id="73d75-148">When deploying to those environments you use different configuration files where you won’t publish directly any external port for the microservices but, you'll always use the reverse proxy from the API Gateway.</span></span>

<span data-ttu-id="73d75-149">Запустите микрослужбу каталога в локальном узле Docker. Для этого запустите полное решение eShopOnContainers из Visual Studio (оно запустит все службы в файлах docker-compose) или просто запустите микрослужбу каталога с помощью следующей команды docker-compose в CMD или PowerShell в папке, где находятся `docker-compose.yml` и docker-compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="73d75-149">Run the catalog microservice in your local Docker host either by running the full eShopOnContainers solution from Visual Studio (it’ll run all the services in the docker-compose files) or just starting the Catalog microservice with the following docker-compose command in CMD or PowerShell positioned at the folder where the `docker-compose.yml` and docker-compose.override.yml are placed.</span></span>

```console
docker-compose run --service-ports catalog.api
```

<span data-ttu-id="73d75-150">Эта команда только выполняет контейнер службы catalog.api, а также зависимости, указанные в файле docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="73d75-150">This command only runs the catalog.api service container plus dependencies that are specified in the docker-compose.yml.</span></span> <span data-ttu-id="73d75-151">В данном случае это контейнер SQL Server и контейнер RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="73d75-151">In this case, the SQL Server container and RabbitMQ container.</span></span>

<span data-ttu-id="73d75-152">Затем вы можете напрямую обратиться к микрослужбе каталога и просмотреть ее методы в пользовательском интерфейсе Swagger напрямую через "внешний" порт, в данном случае `http://localhost:5101/swagger`:</span><span class="sxs-lookup"><span data-stu-id="73d75-152">Then, you can directly access the Catalog microservice and see its methods through the Swagger UI accessing directly through that “external” port, in this case `http://localhost:5101/swagger`:</span></span>

![Снимок экрана интерфейса Swagger, где показан REST API Catalog.API.](./media/implement-api-gateways-with-ocelot/test-catalog-microservice.png)

<span data-ttu-id="73d75-154">**Рис. 6-31**.</span><span class="sxs-lookup"><span data-stu-id="73d75-154">**Figure 6-31**.</span></span> <span data-ttu-id="73d75-155">Тестирование микрослужбы каталога с помощью ее пользовательского интерфейса Swagger</span><span class="sxs-lookup"><span data-stu-id="73d75-155">Testing the Catalog microservice with its Swagger UI</span></span>

<span data-ttu-id="73d75-156">На этом этапе можно установить точку останова в коде C# в Visual Studio, протестировать микрослужбу с помощью методов, предоставляемых в пользовательском интерфейсе Swagger, и, наконец, очистить все с помощью команды `docker-compose down`.</span><span class="sxs-lookup"><span data-stu-id="73d75-156">At this point, you could set a breakpoint in C# code in Visual Studio, test the microservice with the methods exposed in Swagger UI, and finally clean-up everything with the `docker-compose down` command.</span></span>

<span data-ttu-id="73d75-157">Однако прямого взаимодействия с микрослужбой, в этом случае через внешний порт 5101, как раз следует избегать в приложении.</span><span class="sxs-lookup"><span data-stu-id="73d75-157">However, direct-access communication to the microservice, in this case through the external port 5101, is precisely what you want to avoid in your application.</span></span> <span data-ttu-id="73d75-158">Для этого необходимо задать дополнительный уровень косвенного обращения через шлюз API (в данном случае Ocelot).</span><span class="sxs-lookup"><span data-stu-id="73d75-158">And you can avoid that by setting the additional level of indirection of the API Gateway (Ocelot, in this case).</span></span> <span data-ttu-id="73d75-159">Таким образом, клиентское приложение не будет обращаться к микрослужбе напрямую.</span><span class="sxs-lookup"><span data-stu-id="73d75-159">That way, the client app won’t directly access the microservice.</span></span>

## <a name="implementing-your-api-gateways-with-ocelot"></a><span data-ttu-id="73d75-160">Реализация шлюзов API с помощью Ocelot</span><span class="sxs-lookup"><span data-stu-id="73d75-160">Implementing your API Gateways with Ocelot</span></span>

<span data-ttu-id="73d75-161">По сути, Ocelot — это набор ПО промежуточного слоя, которое можно применить в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="73d75-161">Ocelot is basically a set of middlewares that you can apply in a specific order.</span></span>

<span data-ttu-id="73d75-162">Ocelot предназначен для работы только с ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="73d75-162">Ocelot is designed to work with ASP.NET Core only.</span></span> <span data-ttu-id="73d75-163">Он нацелен на netstandard2.0, поэтому его можно использовать везде, где поддерживается .NET Standard 2.0, включая среду выполнения .NET Core 2.0 и среду выполнения .NET Framework 4.6.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="73d75-163">It targets netstandard2.0 so it can be used anywhere .NET Standard 2.0 is supported, including .NET Core 2.0 runtime and .NET Framework 4.6.1 runtime and up.</span></span>

<span data-ttu-id="73d75-164">Вы устанавливаете Ocelot и его зависимости в проекте ASP.NET Core с помощью [пакета NuGet Ocelot](https://www.nuget.org/packages/Ocelot/) из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="73d75-164">You install Ocelot and its dependencies in your ASP.NET Core project with [Ocelot's NuGet package](https://www.nuget.org/packages/Ocelot/), from Visual Studio.</span></span>

```powershell
Install-Package Ocelot
```

<span data-ttu-id="73d75-165">В eShopOnContainers его реализация шлюза API представляет собой простой проект ASP.NET Core WebHost, и ПО промежуточного слоя Ocelot обрабатывают все функции шлюза API, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="73d75-165">In eShopOnContainers, its API Gateway implementation is a simple ASP.NET Core WebHost project, and Ocelot’s middlewares handle all the API Gateway features, as shown in the following image:</span></span>

![Снимок экрана обозревателя решений, где показан проект шлюза API Ocelot.](./media/implement-api-gateways-with-ocelot/ocelotapigw-base-project.png)

<span data-ttu-id="73d75-167">**Рис. 6-32**.</span><span class="sxs-lookup"><span data-stu-id="73d75-167">**Figure 6-32**.</span></span> <span data-ttu-id="73d75-168">Базовый проект OcelotApiGw в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="73d75-168">The OcelotApiGw base project in eShopOnContainers</span></span>

<span data-ttu-id="73d75-169">Этот проект ASP.NET Core WebHost, по сути, состоит из двух простых файлов: `Program.cs` и `Startup.cs`.</span><span class="sxs-lookup"><span data-stu-id="73d75-169">This ASP.NET Core WebHost project is basically built with two simple files:  `Program.cs` and `Startup.cs`.</span></span>

<span data-ttu-id="73d75-170">Файл Program.cs просто должен создать и настроить обычный BuildWebHost ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="73d75-170">The Program.cs just needs to create and configure the typical ASP.NET Core BuildWebHost.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Program
    {
        public static void Main(string[] args)
        {
            BuildWebHost(args).Run();
        }

        public static IWebHost BuildWebHost(string[] args)
        {
            var builder = WebHost.CreateDefaultBuilder(args);

            builder.ConfigureServices(s => s.AddSingleton(builder))
                    .ConfigureAppConfiguration(
                          ic => ic.AddJsonFile(Path.Combine("configuration",
                                                            "configuration.json")))
                    .UseStartup<Startup>();
            var host = builder.Build();
            return host;
        }
    }
}
```

<span data-ttu-id="73d75-171">Важно отметить, что в Ocelot вы должны предоставить построителю файл `configuration.json` через метод `AddJsonFile()`.</span><span class="sxs-lookup"><span data-stu-id="73d75-171">The important point here for Ocelot is the `configuration.json` file that you must provide to the builder through the `AddJsonFile()` method.</span></span> <span data-ttu-id="73d75-172">В файле `configuration.json` вы указываете все объекты ReRoute шлюза API, то есть внешние конечные точки с определенными портами и коррелированные внутренние конечные точки, обычно используя разные порты.</span><span class="sxs-lookup"><span data-stu-id="73d75-172">That `configuration.json` is where you specify all the API Gateway ReRoutes, meaning the external endpoints with specific ports and the correlated internal endpoints, usually using different ports.</span></span>

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

<span data-ttu-id="73d75-173">Существует два раздела конфигурации:</span><span class="sxs-lookup"><span data-stu-id="73d75-173">There are two sections to the configuration.</span></span> <span data-ttu-id="73d75-174">массив ReRoute и GlobalConfiguration.</span><span class="sxs-lookup"><span data-stu-id="73d75-174">An array of Re-Routes and a GlobalConfiguration.</span></span> <span data-ttu-id="73d75-175">ReRoute — это объекты, которые указывают Ocelot, как обрабатывать вышестоящий запрос.</span><span class="sxs-lookup"><span data-stu-id="73d75-175">The Re-Routes are the objects that tell Ocelot how to treat an upstream request.</span></span> <span data-ttu-id="73d75-176">Глобальная конфигурация может переопределять конкретные параметры объектов ReRoute.</span><span class="sxs-lookup"><span data-stu-id="73d75-176">The Global configuration allows overrides of Re-Route specific settings.</span></span> <span data-ttu-id="73d75-177">Это полезно, если вы не хотите управлять большим числом параметров ReRoute.</span><span class="sxs-lookup"><span data-stu-id="73d75-177">It’s useful if you don’t want to manage lots of Re-Route specific settings.</span></span>

<span data-ttu-id="73d75-178">Ниже приведен упрощенный пример [файла конфигурации ReRoute](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) из одного из шлюзов API в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="73d75-178">Here’s a simplified example of [ReRoute configuration file](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) from one of the API Gateways from eShopOnContainers.</span></span>

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/c/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ]
    },
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }

  ],
    "GlobalConfiguration": {
      "RequestIdKey": "OcRequestId",
      "AdministrationPath": "/administration"
    }
  }
```

<span data-ttu-id="73d75-179">Основная функция шлюзов API Ocelot — принимать входящие HTTP-запросы и перенаправлять их подчиненной службе, в настоящее время в виде другого HTTP запроса.</span><span class="sxs-lookup"><span data-stu-id="73d75-179">The main functionality of an Ocelot API Gateway is to take incoming HTTP requests and forward them on to a downstream service, currently as another HTTP request.</span></span> <span data-ttu-id="73d75-180">Ocelot описывает направление одного запроса в другой как перенаправление ReRoute.</span><span class="sxs-lookup"><span data-stu-id="73d75-180">Ocelot’s describes the routing of one request to another as a Re-Route.</span></span>

<span data-ttu-id="73d75-181">Давайте сосредоточимся на одном из перенаправлений в файле configuration.json из примера выше, где содержится конфигурация для микрослужбы корзины.</span><span class="sxs-lookup"><span data-stu-id="73d75-181">For instance, let’s focus on one of the Re-Routes in the configuration.json from above, the configuration for the Basket microservice.</span></span>

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
}
```

<span data-ttu-id="73d75-182">DownstreamPathTemplate, Scheme и DownstreamHostAndPorts формируют URL-адрес внутренней микрослужбы, которой будет переадресован запрос.</span><span class="sxs-lookup"><span data-stu-id="73d75-182">The DownstreamPathTemplate, Scheme, and DownstreamHostAndPorts make the internal microservice URL that this request will be forwarded to.</span></span>

<span data-ttu-id="73d75-183">В качестве порта указан внутренний порт, используемый службой.</span><span class="sxs-lookup"><span data-stu-id="73d75-183">The port is the internal port used by the service.</span></span> <span data-ttu-id="73d75-184">Если вы используете контейнеры, порт указан в файле dockerfile.</span><span class="sxs-lookup"><span data-stu-id="73d75-184">When using containers, the port specified at its dockerfile.</span></span>

<span data-ttu-id="73d75-185">`Host` — это имя службы, которое зависит от используемого разрешения имени службы.</span><span class="sxs-lookup"><span data-stu-id="73d75-185">The `Host` is a service name that depends on the service name resolution you are using.</span></span> <span data-ttu-id="73d75-186">При использовании docker-compose имена служб предоставляются узлом Docker, который использует имена служб, предоставленные в файлах docker-compose.</span><span class="sxs-lookup"><span data-stu-id="73d75-186">When using docker-compose, the services names are provided by the Docker Host, which is using the service names provided in the docker-compose files.</span></span> <span data-ttu-id="73d75-187">При использовании оркестратора, например Kubernetes или Service Fabric, это имя должно разрешаться DNS или службой разрешения имен, предоставляемой каждым оркестратором.</span><span class="sxs-lookup"><span data-stu-id="73d75-187">If using an orchestrator like Kubernetes or Service Fabric, that name should be resolved by the DNS or name resolution provided by each orchestrator.</span></span>

<span data-ttu-id="73d75-188">DownstreamHostAndPorts — это массив, содержащий узел и порт любых подчиненных служб, которым вы хотите переадресовывать запросы.</span><span class="sxs-lookup"><span data-stu-id="73d75-188">DownstreamHostAndPorts is an array that contains the host and port of any downstream services that you wish to forward requests to.</span></span> <span data-ttu-id="73d75-189">Обычно он содержит всего одну запись, но иногда вы можете распределять нагрузку запросов к подчиненным службам, и Ocelot позволяет добавлять несколько записей и выбирать подсистему балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="73d75-189">Usually this will just contain one entry but sometimes you might want to load balance requests to your downstream services and Ocelot lets you add more than one entry and then select a load balancer.</span></span> <span data-ttu-id="73d75-190">Но если вы используете Azure и оркестратор, возможно, лучше распределять нагрузку с помощью инфраструктуры облака и оркестратора.</span><span class="sxs-lookup"><span data-stu-id="73d75-190">But if using Azure and any orchestrator it is probably a better idea to load balance with the cloud and orchestrator infrastructure.</span></span>

<span data-ttu-id="73d75-191">UpstreamPathTemplate — это URL-адрес, который Ocelot будет использовать для выбора DownstreamPathTemplate для определенного запроса от клиента.</span><span class="sxs-lookup"><span data-stu-id="73d75-191">The UpstreamPathTemplate is the URL that Ocelot will use to identify which DownstreamPathTemplate to use for a given request from the client.</span></span> <span data-ttu-id="73d75-192">Наконец, UpstreamHttpMethod используется для того, чтобы Ocelot различал запросы (GET, POST, PUT) к одному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="73d75-192">Finally, the UpstreamHttpMethod is used so Ocelot can distinguish between different requests (GET, POST, PUT) to the same URL.</span></span>

<span data-ttu-id="73d75-193">На этом этапе у вас может быть один шлюз API Ocelot (ASP.NET Core WebHost), использующий один или [несколько объединенных файлов configuration.json](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files), или вы можете хранить [конфигурацию в хранилище Consul KV](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span><span class="sxs-lookup"><span data-stu-id="73d75-193">At this point, you could have a single Ocelot API Gateway (ASP.NET Core WebHost) using one or [multiple merged configuration.json files](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) or you can also store the [configuration in a Consul KV store](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span></span>

<span data-ttu-id="73d75-194">Но, как описывалось в разделах об архитектуре и проектировании, если вы действительно хотите иметь автономные микрослужбы, лучше разделить этот единый монолитный шлюз API на несколько шлюзов API и (или) BFF (Backend for Frontend).</span><span class="sxs-lookup"><span data-stu-id="73d75-194">But as introduced in the architecture and design sections, if you really want to have autonomous microservices, it might be better to split that single monolithic API Gateway into multiple API Gateways and/or BFF (Backend for Frontend).</span></span> <span data-ttu-id="73d75-195">Давайте посмотрим, как реализовать этот подход с контейнерами Docker.</span><span class="sxs-lookup"><span data-stu-id="73d75-195">For that purpose, let’s see how to implement that approach with Docker containers.</span></span>

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a><span data-ttu-id="73d75-196">Использование одного образа контейнера Docker для запуска нескольких типов шлюзов API/контейнеров BFF</span><span class="sxs-lookup"><span data-stu-id="73d75-196">Using a single Docker container image to run multiple different API Gateway / BFF container types</span></span>

<span data-ttu-id="73d75-197">В eShopOnContainers мы используем единый образ контейнера Docker со шлюзом API Ocelot, но затем во время выполнения мы создаем различные службы и контейнеры для каждого типа шлюза API/BFF, предоставляя отдельный файл configuration.json и используя том docker для доступа к разным папкам на компьютере для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="73d75-197">In eShopOnContainers we’re using a single Docker container image with the Ocelot API Gateway but then, at run time, we create different services/containers for each type of API-Gateway/BFF by providing a different configuration.json file, using a docker volume to access a different PC folder for each service.</span></span>

![Схема одного образа Docker шлюза Ocelot для всех шлюзов API.](./media/implement-api-gateways-with-ocelot/reusing-single-ocelot-docker-image.png)

<span data-ttu-id="73d75-199">**Рис. 6-33**.</span><span class="sxs-lookup"><span data-stu-id="73d75-199">**Figure 6-33**.</span></span> <span data-ttu-id="73d75-200">Повторное использование одного образа Ocelot Docker в нескольких типах шлюзов API</span><span class="sxs-lookup"><span data-stu-id="73d75-200">Re-using a single Ocelot Docker image across multiple API Gateway types</span></span>

<span data-ttu-id="73d75-201">В eShopOnContainers создается "Универсальный образ Docker для шлюза API Ocelot" с проектом OcelotApiGw и образом eshop/ocelotapigw, который указан в файле docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="73d75-201">In eShopOnContainers, the “Generic Ocelot API Gateway Docker Image” is created with the project named 'OcelotApiGw' and the image name “eshop/ocelotapigw” that is specified in the docker-compose.yml file.</span></span> <span data-ttu-id="73d75-202">Затем при развертывании в Docker будет четыре шлюза API с контейнерами, созданными из этого образа Docker, как показано в следующем фрагменте из файла docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="73d75-202">Then, when deploying to Docker, there will be four API-Gateway containers created from that same Docker image, as shown in the following extract from the docker-compose.yml file.</span></span>

```yml
  mobileshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  mobilemarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webmarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile
```

<span data-ttu-id="73d75-203">Кроме того, как видно из приведенного ниже файла docker-compose.override.yml, единственное различие между этими контейнерами в шлюзах API — файл конфигурации Ocelot, который отличается для каждого контейнера службы и указывается во время выполнения с помощью тома Docker.</span><span class="sxs-lookup"><span data-stu-id="73d75-203">Additionally, as you can see in the following docker-compose.override.yml file, the only difference between those API Gateway containers is the Ocelot configuration file, which is different for each service container and it's specified at runtime through a Docker volume.</span></span>

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

<span data-ttu-id="73d75-204">В результате предыдущего кода и как показано в обозревателе Visual Studio ниже, всего один файл configuration.json определяет конкретный шлюз API для BFF или подразделения, поскольку все четыре шлюза API основаны на одном образе Docker.</span><span class="sxs-lookup"><span data-stu-id="73d75-204">Because of that previous code, and as shown in the Visual Studio Explorer below, the only file needed to define each specific business/BFF API Gateway is just a configuration.json file, because the four API Gateways are based on the same Docker image.</span></span>

![Снимок экрана, где показаны все шлюзы API с файлами configuration.json.](./media/implement-api-gateways-with-ocelot/ocelot-configuration-files.png)

<span data-ttu-id="73d75-206">**Рис. 6-34**.</span><span class="sxs-lookup"><span data-stu-id="73d75-206">**Figure 6-34**.</span></span> <span data-ttu-id="73d75-207">Для определения каждого шлюза API/BFF с помощью Ocelot требуется только файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="73d75-207">The only file needed to define each API Gateway / BFF with Ocelot is a configuration file</span></span>

<span data-ttu-id="73d75-208">Если разделить один шлюз API на несколько, разные команды разработчиков, занимающиеся разными подмножествами микрослужб, смогут управлять своими шлюзами API с помощью независимых файлов конфигурации Ocelot.</span><span class="sxs-lookup"><span data-stu-id="73d75-208">By splitting the API Gateway into multiple API Gateways, different development teams focusing on different subsets of microservices can manage their own API Gateways by using independent Ocelot configuration files.</span></span> <span data-ttu-id="73d75-209">Кроме того, в то же время они могут повторно использовать один и тот же образ Docker Ocelot.</span><span class="sxs-lookup"><span data-stu-id="73d75-209">Plus, at the same time they can reuse the same Ocelot Docker image.</span></span>

<span data-ttu-id="73d75-210">Теперь при запуске eShopOnContainers со шлюзами API (включены по умолчанию в Visual Studio при открытии решения eShopOnContainers-ServicesAndWebApps.sln или выполнении команды "docker-compose up") будут выполняться направления запросов, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="73d75-210">Now, if you run eShopOnContainers with the API Gateways (included by default in VS when opening eShopOnContainers-ServicesAndWebApps.sln solution or if running “docker-compose up”), the following sample routes will be performed.</span></span>

<span data-ttu-id="73d75-211">Например, при посещении вышестоящего URL-адреса `http://localhost:5202/api/v1/c/catalog/items/2/`, обслуживаемого шлюзом API webshoppingapigw, вы получаете тот же результат от внутреннего подчиненного URL-адреса `http://catalog.api/api/v1/2` в узле Docker, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="73d75-211">For instance, when visiting the upstream URL `http://localhost:5202/api/v1/c/catalog/items/2/` served by the webshoppingapigw API Gateway, you get the same result from the internal Downstream URL `http://catalog.api/api/v1/2` within the Docker host, as in the following browser.</span></span>

![Снимок экрана браузера, где показан ответ, идущий через шлюз API.](./media/implement-api-gateways-with-ocelot/access-microservice-through-url.png)

<span data-ttu-id="73d75-213">**Рис. 6-35**.</span><span class="sxs-lookup"><span data-stu-id="73d75-213">**Figure 6-35**.</span></span> <span data-ttu-id="73d75-214">Доступ к микрослужбе с помощью URL-адреса, предоставленного шлюзом API</span><span class="sxs-lookup"><span data-stu-id="73d75-214">Accessing a microservice through a URL provided by the API Gateway</span></span>

<span data-ttu-id="73d75-215">В связи с тестированием или отладкой, если вы захотите получить прямой доступ к контейнеру Docker Catalog (только в среде разработки) без передачи через шлюз API, так как catalog.api является разрешением DNS внутри узла Docker (обнаружение служб, обрабатываемое именами служб docker-compose), это возможно только через внешний порт, опубликованный в файле docker-compose.override.yml, который предоставляется только для тестирования, например `http://localhost:5101/api/v1/Catalog/items/1` в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="73d75-215">Because of testing or debugging reasons, if you wanted to directly access to the Catalog Docker container (only at the development environment) without passing through the API Gateway, since 'catalog.api' is a DNS resolution internal to the Docker host (service discovery handled by docker-compose service names), the only way to directly access the container is through the external port published in the docker-compose.override.yml, which is provided only for development tests, such as `http://localhost:5101/api/v1/Catalog/items/1` in the following browser.</span></span>

![Снимок экрана браузера, где показан прямой ответ на Catalog.API.](./media/implement-api-gateways-with-ocelot/direct-access-microservice-testing.png)

<span data-ttu-id="73d75-217">**Рис. 6-36**.</span><span class="sxs-lookup"><span data-stu-id="73d75-217">**Figure 6-36**.</span></span> <span data-ttu-id="73d75-218">Прямой доступ к микрослужбе для тестирования</span><span class="sxs-lookup"><span data-stu-id="73d75-218">Direct access to a microservice for testing purposes</span></span>

<span data-ttu-id="73d75-219">Но приложение настроено так, что обращается ко всем микрослужбам через шлюзы API, а не через прямой порт.</span><span class="sxs-lookup"><span data-stu-id="73d75-219">But the application is configured so it accesses all the microservices through the API Gateways, not though the direct port “shortcuts”.</span></span>

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a><span data-ttu-id="73d75-220">Схема объединения шлюзов в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="73d75-220">The Gateway aggregation pattern in eShopOnContainers</span></span>

<span data-ttu-id="73d75-221">Как уже было сказано, объединять запросы удобнее всего с помощью настраиваемых служб, через код.</span><span class="sxs-lookup"><span data-stu-id="73d75-221">As introduced previously, a flexible way to implement requests aggregation is with custom services, by code.</span></span> <span data-ttu-id="73d75-222">Вы также можете объединять запросы с помощью [функции "Request Aggregation" в Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), но этот метод может оказаться недостаточно гибким.</span><span class="sxs-lookup"><span data-stu-id="73d75-222">You could also implement request aggregation with the [Request Aggregation feature in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), but it might not be as flexible as you need.</span></span> <span data-ttu-id="73d75-223">Поэтому рекомендуется реализовывать объединение в eShopOnContainers с помощью явных служб веб-API ASP.NET Core для каждого агрегатора.</span><span class="sxs-lookup"><span data-stu-id="73d75-223">Therefore, the selected way to implement aggregation in eShopOnContainers is with an explicit ASP.NET Core Web API services for each aggregator.</span></span>

<span data-ttu-id="73d75-224">С таким подходом схема шлюзов API в реальности является более расширенной, если учитывать службы агрегатора, которые не отображены в упрощенной схеме архитектуры, показанной ранее.</span><span class="sxs-lookup"><span data-stu-id="73d75-224">According to that approach, the API Gateway composition diagram is in reality a bit more extended when considering the aggregator services that are not shown in the simplified global architecture diagram shown previously.</span></span>

<span data-ttu-id="73d75-225">На следующей схеме видно, как работают службы агрегатора со связанными шлюзами API.</span><span class="sxs-lookup"><span data-stu-id="73d75-225">In the following diagram, you can also see how the aggregator services work with their related API Gateways.</span></span>

![Схема архитектуры eShopOnContainers со службами агрегатора.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture-aggregator-services.png)

<span data-ttu-id="73d75-227">**Рис. 6-37**.</span><span class="sxs-lookup"><span data-stu-id="73d75-227">**Figure 6-37**.</span></span> <span data-ttu-id="73d75-228">Архитектура eShopOnContainers со службами агрегатора</span><span class="sxs-lookup"><span data-stu-id="73d75-228">eShopOnContainers architecture with aggregator services</span></span>

<span data-ttu-id="73d75-229">Если подробнее рассмотреть область покупок на приведенном ниже изображении, можно заметить, что обмен данными между клиентскими приложениями и микрослужбами сокращается при использовании служб агрегатора в шлюзах API.</span><span class="sxs-lookup"><span data-stu-id="73d75-229">Zooming in further, on the “Shopping” business area in the following image, you can see that chattiness between the client apps and the microservices is reduced when using the aggregator services in the API Gateways.</span></span>

![Схема, показывающая увеличенную архитектуру eShopOnContainers.](./media/implement-api-gateways-with-ocelot/zoom-in-vision-aggregator-services.png)

<span data-ttu-id="73d75-231">**Рис. 6-38**.</span><span class="sxs-lookup"><span data-stu-id="73d75-231">**Figure 6-38**.</span></span> <span data-ttu-id="73d75-232">Службы агрегатора на схеме</span><span class="sxs-lookup"><span data-stu-id="73d75-232">Zoom in vision of the Aggregator services</span></span>

<span data-ttu-id="73d75-233">Можно заметить, что, когда на схеме показаны возможные запросы, поступающие из шлюзов API, она значительно усложняется.</span><span class="sxs-lookup"><span data-stu-id="73d75-233">You can notice how when the diagram shows the possible requests coming from the API Gateways it can get pretty complex.</span></span> <span data-ttu-id="73d75-234">И хотя видно, что синие стрелки можно упростить, с точки зрения клиентских приложений, использование шаблона агрегатора сокращает число вызовов и задержки при обмене данными и, в конечном счете, значительно повышает удобство работы пользователей, особенно с удаленными приложениями (мобильными и одностраничными приложениями).</span><span class="sxs-lookup"><span data-stu-id="73d75-234">Although you can see how the arrows in blue would be simplified, from a client apps perspective, when using the aggregator pattern by reducing chattiness and latency in the communication, ultimately significantly improving the user experience for the remote apps (mobile and SPA apps), especially.</span></span>

<span data-ttu-id="73d75-235">В области и микрослужбах маркетинга схема очень проста, и можно обойтись без агрегаторов, но их допустимо использовать при необходимости.</span><span class="sxs-lookup"><span data-stu-id="73d75-235">In the case of the “Marketing” business area and microservices, it is a very simple use case so there was no need to use aggregators, but it could also be possible, if needed.</span></span>

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a><span data-ttu-id="73d75-236">Проверка подлинности и авторизация в шлюзах API Ocelot</span><span class="sxs-lookup"><span data-stu-id="73d75-236">Authentication and authorization in Ocelot API Gateways</span></span>

<span data-ttu-id="73d75-237">В шлюзе API Ocelot можно разместить службу проверки подлинности, например службу веб-API ASP.NET Core, с помощью [IdentityServer](https://identityserver.io/), предоставив маркер проверки подлинности снаружи или внутри шлюза API.</span><span class="sxs-lookup"><span data-stu-id="73d75-237">In an Ocelot API Gateway you can sit the authentication service, such as an ASP.NET Core Web API service using [IdentityServer](https://identityserver.io/) providing the auth token, either out or inside the API Gateway.</span></span>

<span data-ttu-id="73d75-238">Поскольку eShopOnContainers использует разные шлюзы API с границами на основе BFF и областей бизнеса, службы идентификации или проверки подлинности находятся за пределами шлюзов API (выделено желтым на следующей схеме).</span><span class="sxs-lookup"><span data-stu-id="73d75-238">Since eShopOnContainers is using multiple API Gateways with boundaries based on BFF and business areas, the Identity/Auth service is left out of the API Gateways, as highlighted in yellow in the following diagram.</span></span>

![Схема, показывающая микрослужбу идентификации, расположенную под шлюзом API.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-identity-service-position.png)

<span data-ttu-id="73d75-240">**Рис. 6-39**.</span><span class="sxs-lookup"><span data-stu-id="73d75-240">**Figure 6-39**.</span></span> <span data-ttu-id="73d75-241">Положение службы идентификации в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="73d75-241">Position of the Identity service in eShopOnContainers</span></span>

<span data-ttu-id="73d75-242">Тем не менее Ocelot также поддерживает размещение микрослужбы идентификации или проверки подлинности в границах шлюза API, как показано на этой схеме.</span><span class="sxs-lookup"><span data-stu-id="73d75-242">However, Ocelot also supports sitting the Identity/Auth microservice within the API Gateway boundary, as in this other diagram.</span></span>

![Схема, показывающая проверку подлинности в шлюзе API Ocelot.](./media/implement-api-gateways-with-ocelot/ocelot-authentication.png)

<span data-ttu-id="73d75-244">**Рис. 6-40**.</span><span class="sxs-lookup"><span data-stu-id="73d75-244">**Figure 6-40**.</span></span> <span data-ttu-id="73d75-245">Проверка подлинности в Ocelot</span><span class="sxs-lookup"><span data-stu-id="73d75-245">Authentication in Ocelot</span></span>

<span data-ttu-id="73d75-246">Как показано на предыдущей схеме, если микрослужба идентификации находится под шлюзом API (AG), происходит следующее: 1) AG запрашивает маркер проверки подлинности у микрослужбы идентификации; 2) микрослужба идентификации возвращает маркер в AG; 3–4) AG выполняет запрос из микрослужб с использованием маркера проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73d75-246">As the previous diagram shows, when the Identity microservice is beneath the API gateway (AG): 1) AG requests an auth token from identity microservice, 2) The identity microservice returns token to AG, 3-4) AG requests from microservices using the auth token.</span></span> <span data-ttu-id="73d75-247">Поскольку приложение eShopOnContainers разделило шлюз API на несколько BFF (Backend for Frontend) и шлюзов API для областей бизнеса, для решения общих задач также можно было бы создать дополнительный шлюз API.</span><span class="sxs-lookup"><span data-stu-id="73d75-247">Because eShopOnContainers application has split the API Gateway into multiple BFF (Backend for Frontend) and business areas API Gateways, another option would had been to create an additional API Gateway for cross-cutting concerns.</span></span> <span data-ttu-id="73d75-248">Такой вариант подойдет для более сложной архитектуры на базе микрослужб с несколькими микрослужбами, выполняющими общие задачи.</span><span class="sxs-lookup"><span data-stu-id="73d75-248">That choice would be fair in a more complex microservice based architecture with multiple cross-cutting concerns microservices.</span></span> <span data-ttu-id="73d75-249">Так как в eShopOnContainers есть только одна общая задача, для простоты было решено обрабатывать службу безопасности вне области шлюза API.</span><span class="sxs-lookup"><span data-stu-id="73d75-249">Since there's only one cross-cutting concern in eShopOnContainers, it was decided to just handle the security service out of the API Gateway realm, for simplicity’s sake.</span></span>

<span data-ttu-id="73d75-250">В любом случае, если безопасность приложения обеспечивается на уровне шлюзов API, модуль проверки подлинности шлюза API Ocelot посещается первым при попытке использовать защищенную микрослужбу.</span><span class="sxs-lookup"><span data-stu-id="73d75-250">In any case, if the app is secured at the API Gateway level, the authentication module of the Ocelot API Gateway is visited at first when trying to use any secured microservice.</span></span> <span data-ttu-id="73d75-251">Он перенаправляет HTTP-запросы в микрослужбу идентификации или проверки подлинности для получения маркера доступа, поэтому вы можете посещать защищенные службы с маркером доступа.</span><span class="sxs-lookup"><span data-stu-id="73d75-251">That re-directs the HTTP request to visit the Identity or auth microservice to get the access token so you can visit the protected services with the access_token.</span></span>

<span data-ttu-id="73d75-252">Чтобы защитить любую службу с помощью проверки подлинности на уровне шлюза API, укажите AuthenticationProviderKey в соответствующих параметрах в файле configuration.json.</span><span class="sxs-lookup"><span data-stu-id="73d75-252">The way you secure with authentication any service at the API Gateway level is by setting the AuthenticationProviderKey in its related settings at the configuration.json.</span></span>

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }
```

<span data-ttu-id="73d75-253">При запуске Ocelot он будет смотреть на AuthenticationOptions.AuthenticationProviderKey для объектов ReRoute и проверит наличие поставщика проверки подлинности, зарегистрированного с указанным ключом.</span><span class="sxs-lookup"><span data-stu-id="73d75-253">When Ocelot runs, it will look at the Re-Routes AuthenticationOptions.AuthenticationProviderKey and check that there is an Authentication Provider registered with the given key.</span></span> <span data-ttu-id="73d75-254">Если его нет, Ocelot не будет запущен.</span><span class="sxs-lookup"><span data-stu-id="73d75-254">If there isn't, then Ocelot will not start up.</span></span> <span data-ttu-id="73d75-255">Если он есть, объект ReRoute будет использовать этого поставщика при выполнении.</span><span class="sxs-lookup"><span data-stu-id="73d75-255">If there is, then the ReRoute will use that provider when it executes.</span></span>

<span data-ttu-id="73d75-256">Поскольку Ocelot WebHost настраивается с помощью `authenticationProviderKey = "IdentityApiKey"`, он требует проверки подлинности каждый раз, когда у службы есть запросы без маркера проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73d75-256">Because the Ocelot WebHost is configured with the `authenticationProviderKey = "IdentityApiKey"`, that will require authentication whenever that service has any requests without any auth token.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Startup
    {
        private readonly IConfiguration _cfg;

        public Startup(IConfiguration configuration) => _cfg = configuration;

        public void ConfigureServices(IServiceCollection services)
        {
            var identityUrl = _cfg.GetValue<string>("IdentityUrl");
            var authenticationProviderKey = "IdentityApiKey";
                         //…
            services.AddAuthentication()
                .AddJwtBearer(authenticationProviderKey, x =>
                {
                    x.Authority = identityUrl;
                    x.RequireHttpsMetadata = false;
                    x.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters()
                    {
                        ValidAudiences = new[] { "orders", "basket", "locations", "marketing", "mobileshoppingagg", "webshoppingagg" }
                    };
                });
            //...
        }
    }
}
```

<span data-ttu-id="73d75-257">Затем необходимо также настроить авторизацию с помощью атрибута [Authorize] в любом ресурсе, к которому требуется доступ, например в микрослужбах, как в контроллере микрослужбы корзины в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="73d75-257">Then, you also need to set authorization with the [Authorize] attribute on any resource to be accessed like the microservices, such as in the following Basket microservice controller.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class BasketController : Controller
    {
      //...
    }
}
```

<span data-ttu-id="73d75-258">Объекты ValidAudiences, например "basket", коррелируют с аудиторией, определенной в каждой микрослужбе с помощью `AddJwtBearer()` в ConfigureServices() в классе Startup, как показано в приведенном ниже коде.</span><span class="sxs-lookup"><span data-stu-id="73d75-258">The ValidAudiences such as “basket” are correlated with the audience defined in each microservice with `AddJwtBearer()` at the ConfigureServices() of the Startup class, such as in the code below.</span></span>

```csharp
// prevent from mapping "sub" claim to nameidentifier.
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();

var identityUrl = Configuration.GetValue<string>("IdentityUrl");

services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

}).AddJwtBearer(options =>
{
    options.Authority = identityUrl;
    options.RequireHttpsMetadata = false;
    options.Audience = "basket";
});
```

<span data-ttu-id="73d75-259">При попытке получить доступ к любой защищенной микрослужбе, например микрослужбе корзины с URL-адресом перенаправления на основе шлюза API, например `http://localhost:5202/api/v1/b/basket/1`, возникнет ошибка 401 (неавторизованный доступ), если вы не предоставите допустимый токен.</span><span class="sxs-lookup"><span data-stu-id="73d75-259">If you try to access any secured microservice, like the Basket microservice with a Re-Route URL based on the API Gateway like `http://localhost:5202/api/v1/b/basket/1`, then you’ll get a 401 Unauthorized unless you provide a valid token.</span></span> <span data-ttu-id="73d75-260">С другой стороны, если URL-адрес перенаправления прошел проверку подлинности, Ocelot будет вызывать связанную с ним подчиненную схему (URL-адрес внутренней микрослужбы).</span><span class="sxs-lookup"><span data-stu-id="73d75-260">On the other hand, if a Re-Route URL is authenticated, Ocelot will invoke whatever downstream scheme is associated with it (the internal microservice URL).</span></span>

<span data-ttu-id="73d75-261">**Авторизация на уровне перенаправлений Ocelot.**</span><span class="sxs-lookup"><span data-stu-id="73d75-261">**Authorization at Ocelot’s ReRoutes tier.**</span></span>  <span data-ttu-id="73d75-262">Ocelot поддерживает авторизацию на основе утверждений, которая вычисляется после проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="73d75-262">Ocelot supports claims-based authorization evaluated after the authentication.</span></span> <span data-ttu-id="73d75-263">Вы задаете авторизацию на уровне маршрута, добавляя приведенные ниже строки в конфигурацию перенаправления.</span><span class="sxs-lookup"><span data-stu-id="73d75-263">You set the authorization at a route level by adding the following lines to the ReRoute configuration.</span></span>

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

<span data-ttu-id="73d75-264">В этом примере при вызове ПО промежуточного слоя авторизации Ocelot обнаружит, имеет ли пользователь тип утверждения UserType в маркере и имеет ли это утверждение значение "employee".</span><span class="sxs-lookup"><span data-stu-id="73d75-264">In that example, when the authorization middleware is called, Ocelot will find if the user has the claim type 'UserType' in the token and if the value of that claim is 'employee'.</span></span> <span data-ttu-id="73d75-265">Если это не так, пользователь не будет авторизован, и возникнет ошибка 403 (доступ запрещен).</span><span class="sxs-lookup"><span data-stu-id="73d75-265">If it isn’t, then the user will not be authorized and the response will be 403 forbidden.</span></span>

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a><span data-ttu-id="73d75-266">Использование Kubernetes Ingress и шлюзов API Ocelot</span><span class="sxs-lookup"><span data-stu-id="73d75-266">Using Kubernetes Ingress plus Ocelot API Gateways</span></span>

<span data-ttu-id="73d75-267">При использовании Kubernetes (как в кластере Службы Azure Kubernetes) вы обычно унифицируете все HTTP-запросы через [уровень Kubernetes Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) на основе *Nginx*.</span><span class="sxs-lookup"><span data-stu-id="73d75-267">When using Kubernetes (like in an Azure Kubernetes Service cluster), you usually unify all the HTTP requests through the [Kubernetes Ingress tier](https://kubernetes.io/docs/concepts/services-networking/ingress/) based on *Nginx*.</span></span>

<span data-ttu-id="73d75-268">Если в Kubernetes вы не используете точку входа, IP ваших служб и модулей pod может перенаправляться только сетью кластера.</span><span class="sxs-lookup"><span data-stu-id="73d75-268">In Kubernetes, if you don’t use any ingress approach, then your services and pods have IPs only routable by the cluster network.</span></span>

<span data-ttu-id="73d75-269">Но если вы используете точку входа, у вас есть промежуточный уровень между Интернетом и службами (включая шлюзы API), который выступает в качестве обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="73d75-269">But if you use an ingress approach, you'll have a middle tier between the Internet and your services (including your API Gateways), acting as a reverse proxy.</span></span>

<span data-ttu-id="73d75-270">Точка входа — это набор правил, которые разрешают входящие подключения к службам кластера.</span><span class="sxs-lookup"><span data-stu-id="73d75-270">As a definition, an Ingress is a collection of rules that allow inbound connections to reach the cluster services.</span></span> <span data-ttu-id="73d75-271">Обычно точка входа настраивается для предоставления службам доступных извне URL-адресов, распределения нагрузки трафика, завершения SSL-запросов и многого другого.</span><span class="sxs-lookup"><span data-stu-id="73d75-271">An ingress is usually configured to provide services externally reachable URLs, load balance traffic, SSL termination and more.</span></span> <span data-ttu-id="73d75-272">Пользователи запрашивают точку входа с помощью запроса POST для ресурса Ingress к серверу API.</span><span class="sxs-lookup"><span data-stu-id="73d75-272">Users request ingress by POSTing the Ingress resource to the API server.</span></span>

<span data-ttu-id="73d75-273">В eShopOnContainers при локальной разработке и использовании только компьютера разработки в качестве узла Docker вы используете не точку входа, а только несколько шлюзов API.</span><span class="sxs-lookup"><span data-stu-id="73d75-273">In eShopOnContainers, when developing locally and using just your development machine as the Docker host, you are not using any ingress but only the multiple API Gateways.</span></span>

<span data-ttu-id="73d75-274">Но при ориентации на "рабочую" среду на основе Kubernetes eShopOnContainers использует точку входа перед шлюзами API.</span><span class="sxs-lookup"><span data-stu-id="73d75-274">However, when targeting a “production” environment based on Kubernetes, eShopOnContainers is using an ingress in front of the API gateways.</span></span> <span data-ttu-id="73d75-275">Таким образом, клиенты по-прежнему вызывают тот же базовый URL-адрес, но запросы направляются к нескольким шлюзам API или BFF.</span><span class="sxs-lookup"><span data-stu-id="73d75-275">That way, the clients still call the same base URL but the requests are routed to multiple API Gateways or BFF.</span></span>

<span data-ttu-id="73d75-276">Обратите внимание, что шлюзы API — это внешний интерфейс, взаимодействующий только со службами, но не с веб-приложениями, которые обычно находятся вне области их действия.</span><span class="sxs-lookup"><span data-stu-id="73d75-276">Note that API Gateways are front-ends or façades surfacing only the services but not the web applications that are usually out of their scope.</span></span> <span data-ttu-id="73d75-277">Кроме того, шлюзы API могут скрывать некоторые внутренние микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="73d75-277">In addition, the API Gateways might hide certain internal microservices.</span></span>

<span data-ttu-id="73d75-278">Но точка входа просто перенаправляет запросы HTTP и не пытается скрыть микрослужбы или веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="73d75-278">The ingress, however, is just redirecting HTTP requests but not trying to hide any microservice or web app.</span></span>

<span data-ttu-id="73d75-279">В идеальной архитектуре есть входящий уровень Nginx в Kubernetes перед веб-приложениями, а также несколько шлюзов API Ocelot/BFF, как показано на приведенной ниже схеме.</span><span class="sxs-lookup"><span data-stu-id="73d75-279">Having an ingress Nginx tier in Kubernetes in front of the web applications plus the several Ocelot API Gateways / BFF is the ideal architecture, as shown in the following diagram.</span></span>

![Схема, показывающая входящий уровень в среде AKS.](./media/implement-api-gateways-with-ocelot/eshoponcontainer-ingress-tier.png)

<span data-ttu-id="73d75-281">**Рис. 6-41**.</span><span class="sxs-lookup"><span data-stu-id="73d75-281">**Figure 6-41**.</span></span> <span data-ttu-id="73d75-282">Входящий уровень в eShopOnContainers при развертывании в Kubernetes</span><span class="sxs-lookup"><span data-stu-id="73d75-282">The ingress tier in eShopOnContainers when deployed into Kubernetes</span></span>

<span data-ttu-id="73d75-283">Kubernetes Ingress выступает в качестве обратного прокси-сервера для всего трафика, направляемого в приложение, включая веб-приложения, которые обычно выходят из области действия шлюза API.</span><span class="sxs-lookup"><span data-stu-id="73d75-283">A Kubernetes Ingress acts as a reverse proxy for all traffic to the app, including the web applications, that are usually out of the Api gateway scope.</span></span> <span data-ttu-id="73d75-284">При развертывании eShopOnContainers в Kubernetes предоставляется всего несколько служб или конечных точек через _точку входа_, в основном только следующий список постфиксов в URL-адресах:</span><span class="sxs-lookup"><span data-stu-id="73d75-284">When you deploy eShopOnContainers into Kubernetes, it exposes just a few services or endpoints via _ingress_, basically the following list of postfixes on the URLs:</span></span>

- <span data-ttu-id="73d75-285">`/` для клиента веб-приложения SPA</span><span class="sxs-lookup"><span data-stu-id="73d75-285">`/` for the client SPA web application</span></span>
- <span data-ttu-id="73d75-286">`/webmvc` для клиента веб-приложения MVC</span><span class="sxs-lookup"><span data-stu-id="73d75-286">`/webmvc` for the client MVC web application</span></span>
- <span data-ttu-id="73d75-287">`/webstatus` для клиента веб-приложения с отображением состояния или проверки работоспособности</span><span class="sxs-lookup"><span data-stu-id="73d75-287">`/webstatus` for the client web app showing the status/healthchecks</span></span>
- <span data-ttu-id="73d75-288">`/webshoppingapigw` для веб-BFF и бизнес-процессов покупок</span><span class="sxs-lookup"><span data-stu-id="73d75-288">`/webshoppingapigw` for the web BFF and shopping business processes</span></span>
- <span data-ttu-id="73d75-289">`/webmarketingapigw` для веб-BFF и бизнес-процессов маркетинга</span><span class="sxs-lookup"><span data-stu-id="73d75-289">`/webmarketingapigw` for the web BFF and marketing business processes</span></span>
- <span data-ttu-id="73d75-290">`/mobileshoppingapigw` для мобильного BFF и бизнес-процессов покупок</span><span class="sxs-lookup"><span data-stu-id="73d75-290">`/mobileshoppingapigw` for the mobile BFF and shopping business processes</span></span>
- <span data-ttu-id="73d75-291">`/mobilemarketingapigw` для мобильного -BFF и бизнес-процессов маркетинга</span><span class="sxs-lookup"><span data-stu-id="73d75-291">`/mobilemarketingapigw` for the mobile BFF and marketing business processes</span></span>

<span data-ttu-id="73d75-292">При развертывании в Kubernetes каждый шлюз API Ocelot использует отдельный файл configuration.json для каждого модуля _pod_, управляющего шлюзами API.</span><span class="sxs-lookup"><span data-stu-id="73d75-292">When deploying to Kubernetes, each Ocelot API Gateway is using a different “configuration.json” file for each _pod_ running the API Gateways.</span></span> <span data-ttu-id="73d75-293">Эти файлы configuration.json предоставляются путем подключения (изначально с помощью сценария deploy.ps1) тома, созданного на основе _схемы конфигурации_ Kubernetes с именем "ocelot".</span><span class="sxs-lookup"><span data-stu-id="73d75-293">Those “configuration.json” files are provided by mounting (originally with the deploy.ps1 script) a volume created based on a Kubernetes _config map_ named ‘ocelot’.</span></span> <span data-ttu-id="73d75-294">Каждый контейнер подключает связанный файл конфигурации в папку контейнера с именем `/app/configuration`.</span><span class="sxs-lookup"><span data-stu-id="73d75-294">Each container mounts its related configuration file in the container’s folder named `/app/configuration`.</span></span>

<span data-ttu-id="73d75-295">В файлах исходного кода eShopOnContainers исходные файлы configuration.json можно найти в папке `k8s/ocelot/`.</span><span class="sxs-lookup"><span data-stu-id="73d75-295">In the source code files of eShopOnContainers, the original “configuration.json” files can be found within the `k8s/ocelot/` folder.</span></span> <span data-ttu-id="73d75-296">Существует один файл для каждого BFF/шлюза API.</span><span class="sxs-lookup"><span data-stu-id="73d75-296">There’s one file for each BFF/APIGateway.</span></span>

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a><span data-ttu-id="73d75-297">Дополнительные перекрестные функции в шлюзе API Ocelot</span><span class="sxs-lookup"><span data-stu-id="73d75-297">Additional cross-cutting features in an Ocelot API Gateway</span></span>

<span data-ttu-id="73d75-298">Изучите другие важные функции, связанные с использованием шлюза API Ocelot, по следующим ссылкам.</span><span class="sxs-lookup"><span data-stu-id="73d75-298">There are other important features to research and use, when using an Ocelot API Gateway, described in the following links.</span></span>

- <span data-ttu-id="73d75-299">**Обнаружение службы на стороне клиента через интеграцию Ocelot с Consul или Eureka** </span><span class="sxs-lookup"><span data-stu-id="73d75-299">**Service discovery in the client side integrating Ocelot with Consul or Eureka** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- <span data-ttu-id="73d75-300">**Кэширование на уровне шлюза API** </span><span class="sxs-lookup"><span data-stu-id="73d75-300">**Caching at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- <span data-ttu-id="73d75-301">**Ведение журнала на уровне шлюза API** </span><span class="sxs-lookup"><span data-stu-id="73d75-301">**Logging at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- <span data-ttu-id="73d75-302">**Качество обслуживания (повторы и размыкатели цепи) на уровне шлюза API** </span><span class="sxs-lookup"><span data-stu-id="73d75-302">**Quality of Service (Retries and Circuit breakers) at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- <span data-ttu-id="73d75-303">**Ограничения скорости** </span><span class="sxs-lookup"><span data-stu-id="73d75-303">**Rate limiting** </span></span>\
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> <span data-ttu-id="73d75-304">[Назад](background-tasks-with-ihostedservice.md)
> [Вперед](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="73d75-304">[Previous](background-tasks-with-ihostedservice.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
