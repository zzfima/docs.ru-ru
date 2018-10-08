---
title: Использование HttpClientFactory для реализации устойчивых HTTP-запросов
description: HttpClientFactory — это проверенная фабрика, доступная начиная с .NET Core 2.1. С ее помощью можно создавать экземпляры `HttpClient`, которые используются в приложениях.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 07/03/2018
ms.openlocfilehash: 6fd30a9358ca9c07b2a6e2ec591e4c5d7db54ccb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513217"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="afa67-103">Использование HttpClientFactory для реализации устойчивых HTTP-запросов</span><span class="sxs-lookup"><span data-stu-id="afa67-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="afa67-104">`HttpClientFactory` — это проверенная фабрика, доступная начиная с .NET Core 2.1. С ее помощью можно создавать экземпляры `HttpClient`, которые используются в приложениях.</span><span class="sxs-lookup"><span data-stu-id="afa67-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating `HttpClient` instances to be used in your applications.</span></span> 

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="afa67-105">Проблемы с исходным классом HttpClient, доступным в .NET Core</span><span class="sxs-lookup"><span data-stu-id="afa67-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="afa67-106">Исходный и хорошо известный класс [HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) очень прост в использовании, но иногда разработчики применяют его неправильно.</span><span class="sxs-lookup"><span data-stu-id="afa67-106">The original and well-know [HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) class can be easily used, but in some cases, it is not being properly used by many developers.</span></span> 

<span data-ttu-id="afa67-107">Первая проблема в том, что, хотя этот класс и является одноразовым, лучше не использовать его с инструкцией `using`, поскольку даже при ликвидации объекта `HttpClient` базовый сокет не освобождается сразу, что может привести к исчерпанию сокетов.</span><span class="sxs-lookup"><span data-stu-id="afa67-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="afa67-108">Дополнительные сведения об этой проблеме см. в записи блога [Неправильное использование HttpClient и нарушение стабильной работы программного обеспечения](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="afa67-108">For more information about this issue, see [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="afa67-109">Таким образом, создается один экземпляр `HttpClient`, которые будет использоваться повторно на протяжении всего жизненного цикла приложения.</span><span class="sxs-lookup"><span data-stu-id="afa67-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="afa67-110">Создание экземпляра класса `HttpClient` для каждого запроса будет сокращать количество доступных сокетов при больших нагрузках.</span><span class="sxs-lookup"><span data-stu-id="afa67-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="afa67-111">В результате будут возникать ошибки `SocketException`.</span><span class="sxs-lookup"><span data-stu-id="afa67-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="afa67-112">Возможные способы решения этой проблемы основаны на создании объекта `HttpClient` в виде класса-одиночки или статического класса, как описано в этой [статье Майкрософт об использовании HttpClient](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="afa67-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/console-webapiclient).</span></span> 

<span data-ttu-id="afa67-113">Но есть еще одна проблема с `HttpClient`, которая может возникнуть, когда вы используете его как класс-одиночку или статический объект.</span><span class="sxs-lookup"><span data-stu-id="afa67-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="afa67-114">В этом случае класс-одиночка или статический класс `HttpClient` не учитывает изменения в DNS, как описано в этой [проблеме в репозитории GitHub по .NET Core](https://github.com/dotnet/corefx/issues/11224).</span><span class="sxs-lookup"><span data-stu-id="afa67-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue at the .NET Core GitHub repo](https://github.com/dotnet/corefx/issues/11224).</span></span> 

<span data-ttu-id="afa67-115">Чтобы решить эти проблемы и упростить управление экземплярами `HttpClient`, .NET Core 2.1 предлагает новую фабрику `HttpClientFactory`, которую также можно использовать для реализации устойчивых HTTP-вызовов путем интеграции с Polly.</span><span class="sxs-lookup"><span data-stu-id="afa67-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 offers a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>   

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="afa67-116">Что такое HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="afa67-116">What is HttpClientFactory</span></span>

<span data-ttu-id="afa67-117">Задачи `HttpClientFactory`:</span><span class="sxs-lookup"><span data-stu-id="afa67-117">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="afa67-118">Центральное расположение для именования и настройки логических объектов HttpClient.</span><span class="sxs-lookup"><span data-stu-id="afa67-118">Provide a central location for naming and configuring logical HttpClients.</span></span> <span data-ttu-id="afa67-119">Например, вы можете настроить клиент (агент службы), который предварительно настроен для доступа к определенной микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="afa67-119">For example, you may configure a client (Service Agent) that is pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="afa67-120">Кодификация концепции исходящего ПО промежуточного слоя путем делегирования обработчиков в `HttpClient` и реализация ПО промежуточного слоя на основе Polly для использования политик устойчивости Polly.</span><span class="sxs-lookup"><span data-stu-id="afa67-120">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="afa67-121">В `HttpClient` уже существует концепция делегирования обработчиков, которые можно связать друг с другом для исходящих HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="afa67-121">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="afa67-122">Вы можете регистрировать объекты HttpClient в фабрике, а также использовать обработчик Polly, чтобы использовать политики Polly для повторных попыток, размыкателя цепи и т. д.</span><span class="sxs-lookup"><span data-stu-id="afa67-122">You register http clients into the factory plus you can use a Polly handler that allows Polly policies to be used for Retry, CircuitBreakers, etc.</span></span>
- <span data-ttu-id="afa67-123">Управление временем существования HttpClientMessageHandler, чтобы избежать упомянутых проблем, которые могут возникнуть при управлении временем существования `HttpClient` самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="afa67-123">Manage the lifetime of HttpClientMessageHandlers to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span> 

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="afa67-124">Способы применения HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="afa67-124">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="afa67-125">Есть несколько способов использования `HttpClientFactory` в вашем приложении:</span><span class="sxs-lookup"><span data-stu-id="afa67-125">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="afa67-126">Использование `HttpClientFactory` напрямую</span><span class="sxs-lookup"><span data-stu-id="afa67-126">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="afa67-127">Использование именованных клиентов</span><span class="sxs-lookup"><span data-stu-id="afa67-127">Use Named Clients</span></span>
- <span data-ttu-id="afa67-128">Использование типизированных клиентов</span><span class="sxs-lookup"><span data-stu-id="afa67-128">Use Typed Clients</span></span>
- <span data-ttu-id="afa67-129">Использование созданных клиентов</span><span class="sxs-lookup"><span data-stu-id="afa67-129">Use Generated Clients</span></span>

<span data-ttu-id="afa67-130">Для краткости в этом руководстве показан наиболее структурированный способ использования `HttpClientFactory`, а именно — с помощью типизированных клиентов (шаблон агента службы), но все параметры описаны и в данный момент перечислены в этой [статье об использовании HttpClientFactory](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?#consumption-patterns).</span><span class="sxs-lookup"><span data-stu-id="afa67-130">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory` that is to use Typed Clients (Service Agent pattern), but all options are documented and are currently listed in this [article covering HttpClientFactory usage](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?#consumption-patterns).</span></span>  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="afa67-131">Как использовать типизированные клиенты с HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="afa67-131">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="afa67-132">На следующей схеме показано, как использовать типизированные клиенты с HttpClientFactory.</span><span class="sxs-lookup"><span data-stu-id="afa67-132">The following diagram shows how Typed Clients are used with HttpClientFactory.</span></span>

![Схема с контроллером MVC, использующим внедренную службу ClientService, которая использует HttpClient, настроенный с помощью HttpClientFactory и политик Polly](./media/image3.5.png)

<span data-ttu-id="afa67-134">**Рис. 10-4**.</span><span class="sxs-lookup"><span data-stu-id="afa67-134">**Figure 10-4**.</span></span> <span data-ttu-id="afa67-135">Использование `HttpClientFactory` с классами типизированных клиентов.</span><span class="sxs-lookup"><span data-stu-id="afa67-135">Using `HttpClientFactory`with Typed Client classes.</span></span>

<span data-ttu-id="afa67-136">Сначала настройте `HttpClientFactory` в приложении.</span><span class="sxs-lookup"><span data-stu-id="afa67-136">First, setup `HttpClientFactory` in your application.</span></span> <span data-ttu-id="afa67-137">Добавьте ссылку на пакет `Microsoft.Extensions.Http`, который включает метод расширения `AddHttpClient()` для `IServiceCollection`.</span><span class="sxs-lookup"><span data-stu-id="afa67-137">Add a reference to the `Microsoft.Extensions.Http` package which includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="afa67-138">Этот метод расширения регистрирует класс `DefaultHttpClientFactory`, который будет использоваться как класс-одиночка для интерфейса `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="afa67-138">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="afa67-139">Он определяет временную конфигурацию для `HttpMessageHandlerBuilder`.</span><span class="sxs-lookup"><span data-stu-id="afa67-139">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="afa67-140">Этот обработчик сообщений (объект `HttpMessageHandler`), взятый из пула, используется классом `HttpClient`, который возвращается фабрикой.</span><span class="sxs-lookup"><span data-stu-id="afa67-140">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="afa67-141">В приведенном далее коде показано, как `AddHttpClient()` может использоваться для регистрации типизированных клиентов (агентов службы), которым нужно использовать `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="afa67-141">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="afa67-142">Если вы просто добавите классы типизированного клиента с AddHttpClient() при использовании объекта `HttpClient`, который будет внедрен в ваш класс через конструктор, этот объект `HttpClient` будет использовать все указанные конфигурации и политики.</span><span class="sxs-lookup"><span data-stu-id="afa67-142">Just by adding your typed client classes with AddHttpClient(), whenever you use the `HttpClient` object that will be injected to your class through its constructor, that `HttpClient` object will be using all the configuration and policies provided.</span></span> <span data-ttu-id="afa67-143">В следующих разделах вы увидите эти политики, например политику повтора или размыкателя цепи Polly.</span><span class="sxs-lookup"><span data-stu-id="afa67-143">In the next sections, you will see those policies like Polly’s retries or circuit-breakers.</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="afa67-144">Время существования HttpClient</span><span class="sxs-lookup"><span data-stu-id="afa67-144">HttpClient lifetimes</span></span>

<span data-ttu-id="afa67-145">Каждый раз, когда вы получаете объект `HttpClient` из IHttpClientFactory, возвращается новый экземпляр `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="afa67-145">Each time you get an `HttpClient` object from IHttpClientFactory, a new instance of an `HttpClient` is returned.</span></span> <span data-ttu-id="afa67-146">У вас будет HttpMessageHandler \*\* для каждого именованного или типизированного клиента.</span><span class="sxs-lookup"><span data-stu-id="afa67-146">There will be an HttpMessageHandler\*\* per named of typed client.</span></span> <span data-ttu-id="afa67-147">`HttpClientFactory` будет объединять в пул все экземпляры HttpMessageHandler, созданные фабрикой, чтобы уменьшить потребление ресурсов.</span><span class="sxs-lookup"><span data-stu-id="afa67-147">I`HttpClientFactory` will pool the HttpMessageHandler instances created by the factory to reduce resource consumption.</span></span> <span data-ttu-id="afa67-148">Экземпляр HttpMessageHandler можно использовать повторно из пула при создании нового экземпляра `HttpClient`, если его время существования еще не истекло.</span><span class="sxs-lookup"><span data-stu-id="afa67-148">An HttpMessageHandler instance may be reused from the pool when creating a new `HttpClient` instance if its lifetime hasn't expired.</span></span>

<span data-ttu-id="afa67-149">Создание пулов обработчиков желательно, поскольку каждый обработчик обычно управляет собственными базовыми HTTP-подключениями. Создание лишних обработчиков может привести к задержке подключения.</span><span class="sxs-lookup"><span data-stu-id="afa67-149">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="afa67-150">Некоторые обработчики поддерживают подключения открытыми в течение неопределенного периода, что может помешать обработчику отреагировать на изменения DNS.</span><span class="sxs-lookup"><span data-stu-id="afa67-150">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="afa67-151">Время существования объектов HttpMessageHandler — это период, когда экземпляр HttpMessageHandler в пуле может использоваться повторно.</span><span class="sxs-lookup"><span data-stu-id="afa67-151">The HttpMessageHandler objects in the pool have a lifetime that is the length of time that an HttpMessageHandler instance in the pool can be reused.</span></span> <span data-ttu-id="afa67-152">Значение по умолчанию — две минуты, но его можно переопределить для отдельных именованных или типизированных клиентов.</span><span class="sxs-lookup"><span data-stu-id="afa67-152">The default value is two minutes, but it can be overridden per named or typed client basis.</span></span> <span data-ttu-id="afa67-153">Чтобы переопределить это значение, вызовите SetHandlerLifetime() в IHttpClientBuilder, который возвращается при создании клиента, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="afa67-153">To override it, call SetHandlerLifetime() on the IHttpClientBuilder that is returned when creating the client, as shown in the following code.</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
                 .SetHandlerLifetime(TimeSpan.FromMinutes(5));  
```

<span data-ttu-id="afa67-154">Для каждого типизированного или именованного клиента можно указать свое значение времени существования настроенного обработчика.</span><span class="sxs-lookup"><span data-stu-id="afa67-154">Each typed client or named client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="afa67-155">Установите значение InfiniteTimeSpan, чтобы отключить срок действия обработчика.</span><span class="sxs-lookup"><span data-stu-id="afa67-155">Set the lifetime to InfiniteTimeSpan to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="afa67-156">Реализация классов типизированных клиентов, использующих внедренный и настроенный HttpClient</span><span class="sxs-lookup"><span data-stu-id="afa67-156">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="afa67-157">Вы должны были уже определить классы типизированных клиентов, например классы в примере кода, такие как BasketService, CatalogService, OrderingService и т. д. Типизированный клиент — это класс, который принимает объект `HttpClient` (внедренный через конструктор) и использует его для вызова удаленной службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="afa67-157">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A typed client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="afa67-158">Пример:</span><span class="sxs-lookup"><span data-stu-id="afa67-158">For example:</span></span>

```csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;
    private readonly string _remoteServiceBaseUrl;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<Catalog> GetCatalogItems(int page, int take, 
                                               int? brand, int? type)
    {
        var uri = API.Catalog.GetAllCatalogItems(_remoteServiceBaseUrl, 
                                                 page, take, brand, type);

        var responseString = await _httpClient.GetStringAsync(uri);

        var catalog = JsonConvert.DeserializeObject<Catalog>(responseString);
        return catalog;
    }
}
```

<span data-ttu-id="afa67-159">Типизированный клиент (в примере это CatalogService) активируется посредством внедрения зависимостей, то есть он может принять любую зарегистрированную службу в свой конструктор в дополнение к HttpClient.</span><span class="sxs-lookup"><span data-stu-id="afa67-159">The typed client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="afa67-160">Типизированный клиент, по сути, — это временный объект, то есть новый экземпляр создается каждый раз, когда он нужен, и он будет получать новый экземпляр `HttpClient` при каждом создании.</span><span class="sxs-lookup"><span data-stu-id="afa67-160">A typed client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it is constructed.</span></span> <span data-ttu-id="afa67-161">Тем не менее объекты HttpMessageHandler в пуле используются повторно множеством HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="afa67-161">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="afa67-162">Использование классов типизированных клиентов</span><span class="sxs-lookup"><span data-stu-id="afa67-162">Use your Typed Client classes</span></span>

<span data-ttu-id="afa67-163">Наконец, когда вы реализуете классы типов и зарегистрируете их в AddHttpClient(), их можно будет использовать везде, где можно внедрить службы с помощью внедрения зависимостей, например в любом коде страницы Razor или любом контроллере веб-приложения MVC, как, например, в следующем коде из eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="afa67-163">Finally, once you have your type classes implemented and have them registered with AddHttpClient(), you can use it anywhere you can have services injected by DI, for example in any Razor page code or any controller of an MVC web app, like in the following code from eShopOnContainers.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC.Controllers
{
    public class CatalogController : Controller
    {
        private ICatalogService _catalogSvc;

        public CatalogController(ICatalogService catalogSvc) => 
                                                           _catalogSvc = catalogSvc;

        public async Task<IActionResult> Index(int? BrandFilterApplied, 
                                               int? TypesFilterApplied, 
                                               int? page, 
                                               [FromQuery]string errorMsg)
        {
            var itemsPage = 10;
            var catalog = await _catalogSvc.GetCatalogItems(page ?? 0, 
                                                            itemsPage, 
                                                            BrandFilterApplied, 
                                                            TypesFilterApplied);
            //… Additional code
        }

        }
}
```

<span data-ttu-id="afa67-164">Пока показанный код просто выполняет обычные HTTP-запросы. Самое интересное начнется в следующих разделах, где вы будете просто добавлять политики и делегирующие обработчики в зарегистрированные типизированные клиенты, и все HTTP-запросы, которые должны выполняться объектом `HttpClient`, будут учитывать политики отказоустойчивости, например политики повтора c экспоненциальной задержкой, размыкатели цепи или другие настраиваемые делегирующие обработчики, чтобы реализовать дополнительные функции безопасности, такие как маркеры проверки подлинности и другие настраиваемые возможности.</span><span class="sxs-lookup"><span data-stu-id="afa67-164">Until this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered typed clients, all the Http requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span> 


## <a name="additional-resources"></a><span data-ttu-id="afa67-165">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="afa67-165">Additional resources</span></span>

-   <span data-ttu-id="afa67-166">**Использование HttpClientFactory в .NET Core 2.1**
    [*https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)</span><span class="sxs-lookup"><span data-stu-id="afa67-166">**Using HttpClientFactory in .NET Core 2.1**
[*https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)</span></span>


-   <span data-ttu-id="afa67-167">**Репозиторий GitHub HttpClientFactory**</span><span class="sxs-lookup"><span data-stu-id="afa67-167">**HttpClientFactory GitHub repo**</span></span>

    [*https://github.com/aspnet/HttpClientFactory*](https://github.com/aspnet/HttpClientFactory)



>[!div class="step-by-step"]
<span data-ttu-id="afa67-168">[Назад] (explore-custom-http-call-retries-exponential-backoff.md) [Далее] (implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="afa67-168">[Previous] (explore-custom-http-call-retries-exponential-backoff.md) [Next] (implement-http-call-retries-exponential-backoff-polly.md)</span></span>
