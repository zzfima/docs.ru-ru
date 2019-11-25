---
title: Использование HttpClientFactory для реализации устойчивых HTTP-запросов
description: Узнайте, как использовать фабрику HttpClientFactory, доступную в .NET Core, начиная с версии 2.1, для создания экземпляров `HttpClient`, чтобы облегчить их применение в ваших приложениях.
ms.date: 08/08/2019
ms.openlocfilehash: 9eff4a01361b3dc6f7471bc012c945d048b9a276
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737743"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="c0cd8-103">Использование HttpClientFactory для реализации устойчивых HTTP-запросов</span><span class="sxs-lookup"><span data-stu-id="c0cd8-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="c0cd8-104">`HttpClientFactory` — это проверенная фабрика, доступная начиная с .NET Core 2.1. С ее помощью можно создавать экземпляры <xref:System.Net.Http.HttpClient>, которые используются в приложениях.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating <xref:System.Net.Http.HttpClient> instances to be used in your applications.</span></span>

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="c0cd8-105">Проблемы с исходным классом HttpClient, доступным в .NET Core</span><span class="sxs-lookup"><span data-stu-id="c0cd8-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="c0cd8-106">Исходный и хорошо известный класс <xref:System.Net.Http.HttpClient> очень просто использовать, но иногда разработчики применяют его неправильно.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-106">The original and well-known <xref:System.Net.Http.HttpClient> class can be easily used, but in some cases, it isn't being properly used by many developers.</span></span>

<span data-ttu-id="c0cd8-107">Первая проблема в том, что, хотя этот класс и является одноразовым, лучше не использовать его с инструкцией `using`, поскольку даже при ликвидации объекта `HttpClient` базовый сокет не освобождается сразу, что может привести к исчерпанию сокетов.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="c0cd8-108">Дополнительные сведения об этой проблеме см. в записи блога [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) (Неправильное использование HttpClient и нарушение стабильной работы программного обеспечения).</span><span class="sxs-lookup"><span data-stu-id="c0cd8-108">For more information about this issue, see [You're using HttpClient wrong and it's destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="c0cd8-109">Таким образом, создается один экземпляр `HttpClient`, которые будет использоваться повторно на протяжении всего жизненного цикла приложения.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="c0cd8-110">Создание экземпляра класса `HttpClient` для каждого запроса будет сокращать количество доступных сокетов при больших нагрузках.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="c0cd8-111">В результате будут возникать ошибки `SocketException`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="c0cd8-112">Возможные способы решения этой проблемы основаны на создании объекта `HttpClient` в виде класса-одиночки или статического класса, как описано в этой [статье Майкрософт об использовании HttpClient](../../../csharp/tutorials/console-webapiclient.md).</span><span class="sxs-lookup"><span data-stu-id="c0cd8-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](../../../csharp/tutorials/console-webapiclient.md).</span></span>

<span data-ttu-id="c0cd8-113">Но есть еще одна проблема с `HttpClient`, которая может возникнуть, когда вы используете его как класс-одиночку или статический объект.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="c0cd8-114">В этом случае класс-одиночка или статический класс `HttpClient` не учитывает изменения в DNS. Эта проблема описывается [в репозитории GitHub dotnet/corefx](https://github.com/dotnet/corefx/issues/11224).</span><span class="sxs-lookup"><span data-stu-id="c0cd8-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue](https://github.com/dotnet/corefx/issues/11224) at the dotnet/corefx GitHub repository.</span></span>

<span data-ttu-id="c0cd8-115">Чтобы решить эти проблемы и упростить управление экземплярами `HttpClient`, в .NET Core 2.1 появилась новая фабрика `HttpClientFactory`, которую также можно использовать для реализации устойчивых HTTP-вызовов путем интеграции с Polly.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 introduced a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>

<span data-ttu-id="c0cd8-116">[Polly](http://www.thepollyproject.org/) — это библиотека для обеспечения обработки временных сбоев, которая позволяет разработчикам повысить устойчивость своих приложений, используя некоторые стандартные политики более эффективным и потокобезопасным способом.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-116">[Polly](http://www.thepollyproject.org/) is transient-fault-handling library that helps developers add resiliency to their applications, by using some pre-defined policies in a fluent and thread-safe manner.</span></span>

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="c0cd8-117">Что такое HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="c0cd8-117">What is HttpClientFactory</span></span>

<span data-ttu-id="c0cd8-118">Задачи `HttpClientFactory`:</span><span class="sxs-lookup"><span data-stu-id="c0cd8-118">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="c0cd8-119">Центральное расположение для именования и настройки логических объектов `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-119">Provide a central location for naming and configuring logical `HttpClient` objects.</span></span> <span data-ttu-id="c0cd8-120">Например, вы можете настроить клиент (агент службы), который предварительно настроен для доступа к определенной микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-120">For example, you may configure a client (Service Agent) that's pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="c0cd8-121">Кодификация концепции исходящего ПО промежуточного слоя путем делегирования обработчиков в `HttpClient` и реализация ПО промежуточного слоя на основе Polly для использования политик устойчивости Polly.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-121">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="c0cd8-122">В `HttpClient` уже существует концепция делегирования обработчиков, которые можно связать друг с другом для исходящих HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-122">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="c0cd8-123">Вы можете регистрировать клиенты HTTP в фабрике, а также использовать обработчик Polly, чтобы использовать политики Polly для повторных попыток, размыкателя цепи и т. д.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-123">You register HTTP clients into the factory and you can use a Polly handler to use Polly policies for Retry, CircuitBreakers, and so on.</span></span>
- <span data-ttu-id="c0cd8-124">Управление временем существования `HttpClientMessageHandlers`, чтобы избежать упомянутых проблем, которые могут возникнуть при управлении временем существования `HttpClient` самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-124">Manage the lifetime of `HttpClientMessageHandlers` to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span>

> [!NOTE]
> <span data-ttu-id="c0cd8-125">`HttpClientFactory` тесно привязывается к реализации внедрения зависимостей (DI) в пакете NuGet `Microsoft.Extensions.DependencyInjection`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-125">`HttpClientFactory` is tightly tied to the dependency injection (DI) implementation in the `Microsoft.Extensions.DependencyInjection` NuGet package.</span></span> <span data-ttu-id="c0cd8-126">См. сведения об использовании других контейнеров внедрения зависимостей в этом [обсуждении GitHub](https://github.com/aspnet/Extensions/issues/1345).</span><span class="sxs-lookup"><span data-stu-id="c0cd8-126">For more information about using other dependency injection containers, see this [GitHub discussion](https://github.com/aspnet/Extensions/issues/1345).</span></span>

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="c0cd8-127">Способы применения HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="c0cd8-127">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="c0cd8-128">Есть несколько способов использования `HttpClientFactory` в вашем приложении:</span><span class="sxs-lookup"><span data-stu-id="c0cd8-128">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="c0cd8-129">Использование `HttpClientFactory` напрямую</span><span class="sxs-lookup"><span data-stu-id="c0cd8-129">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="c0cd8-130">Использование именованных клиентов</span><span class="sxs-lookup"><span data-stu-id="c0cd8-130">Use Named Clients</span></span>
- <span data-ttu-id="c0cd8-131">Использование типизированных клиентов</span><span class="sxs-lookup"><span data-stu-id="c0cd8-131">Use Typed Clients</span></span>
- <span data-ttu-id="c0cd8-132">Использование созданных клиентов</span><span class="sxs-lookup"><span data-stu-id="c0cd8-132">Use Generated Clients</span></span>

<span data-ttu-id="c0cd8-133">Для краткости в этом руководстве показан наиболее структурированный способ использования `HttpClientFactory`, а именно — с помощью типизированных клиентов (шаблон агента службы).</span><span class="sxs-lookup"><span data-stu-id="c0cd8-133">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory`, which is to use Typed Clients (Service Agent pattern).</span></span> <span data-ttu-id="c0cd8-134">Все параметры описаны и перечислены в [этой статье об использовании HttpClientFactory](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span><span class="sxs-lookup"><span data-stu-id="c0cd8-134">However, all options are documented and are currently listed in this [article covering HttpClientFactory usage](/aspnet/core/fundamentals/http-requests#consumption-patterns).</span></span>

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="c0cd8-135">Как использовать типизированные клиенты с HttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="c0cd8-135">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="c0cd8-136">Так что же такое типизированный клиент?</span><span class="sxs-lookup"><span data-stu-id="c0cd8-136">So, what's a "Typed Client"?</span></span> <span data-ttu-id="c0cd8-137">Это просто класс `HttpClient`, настроенный после внедрения с помощью `DefaultHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-137">It's just an `HttpClient` that's configured upon injection by the `DefaultHttpClientFactory`.</span></span>

<span data-ttu-id="c0cd8-138">На следующей схеме показано, как использовать типизированные клиенты с `HttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-138">The following diagram shows how Typed Clients are used with `HttpClientFactory`:</span></span>

![На схеме показано, как использовать типизированные клиенты с HttpClientFactory.](./media/use-httpclientfactory-to-implement-resilient-http-requests/client-application-code.png)

<span data-ttu-id="c0cd8-140">**Рис. 8-4**.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-140">**Figure 8-4**.</span></span> <span data-ttu-id="c0cd8-141">Использование HttpClientFactory с классами типизированных клиентов.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-141">Using HttpClientFactory with Typed Client classes.</span></span>

<span data-ttu-id="c0cd8-142">На изображении выше ClientService (применяется контроллером или в коде клиента) использует объект `HttpClient`, созданный зарегистрированной фабрикой `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-142">In the above image, a ClientService (used by a controller or client code) uses an `HttpClient` created by the registered `IHttpClientFactory`.</span></span> <span data-ttu-id="c0cd8-143">Эта фабрика назначает `HttpClient` `HttpMessageHandler` из пула, которым она управляет.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-143">This factory assigns the `HttpClient` an `HttpMessageHandler` from a pool it manages.</span></span> <span data-ttu-id="c0cd8-144">`HttpClient` можно настроить с помощью политик Polly при регистрации фабрики `IHttpClientFactory` в контейнере внедрения зависимостей, используя метод расширения `AddHttpClient`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-144">The `HttpClient` can be configured with Polly's policies when registering the `IHttpClientFactory` in the DI container with the extension method `AddHttpClient`.</span></span>

<span data-ttu-id="c0cd8-145">Чтобы настроить такую структуру, добавьте `HttpClientFactory` в приложение, установив пакет NuGet `Microsoft.Extensions.Http`, который содержит метод расширения `AddHttpClient()` для `IServiceCollection`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-145">To configure the above structure, add `HttpClientFactory` in your application by installing the `Microsoft.Extensions.Http` NuGet package that includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="c0cd8-146">Этот метод расширения регистрирует класс `DefaultHttpClientFactory`, который будет использоваться как класс-одиночка для интерфейса `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-146">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="c0cd8-147">Он определяет временную конфигурацию для `HttpMessageHandlerBuilder`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-147">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="c0cd8-148">Этот обработчик сообщений (объект `HttpMessageHandler`), взятый из пула, используется классом `HttpClient`, который возвращается фабрикой.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-148">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="c0cd8-149">В приведенном далее коде показано, как `AddHttpClient()` может использоваться для регистрации типизированных клиентов (агентов службы), которым нужно использовать `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-149">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services)
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="c0cd8-150">Как показано в предыдущем примере кода, регистрация клиентских служб позволяет `DefaultClientFactory` создать объект `HttpClient` для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-150">Registering the client services as shown in the previous code, makes the `DefaultClientFactory` create a standard `HttpClient` for each service.</span></span>

<span data-ttu-id="c0cd8-151">В регистрацию можно также добавить настройки конкретного экземпляра, например, настроить базовый адрес и добавить некоторые политики устойчивости, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="c0cd8-151">You could also add instance-specific configuration in the registration to, for example, configure the base address, and add some resiliency policies, as shown in the following code:</span></span>

```csharp
services.AddHttpClient<ICatalogService, CatalogService>(client =>
{
    client.BaseAddress = new Uri(Configuration["BaseUrl"]);
})
    .AddPolicyHandler(GetRetryPolicy())
    .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="c0cd8-152">В следующем коде для примера показана одна из приведенных выше политик.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-152">Just for the example sake, you can see one of the above policies in the next code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)));
}
```

<span data-ttu-id="c0cd8-153">Дополнительные сведения об использовании Polly можно найти в [следующей статье](implement-http-call-retries-exponential-backoff-polly.md).</span><span class="sxs-lookup"><span data-stu-id="c0cd8-153">You can find more details about using Polly in the [Next article](implement-http-call-retries-exponential-backoff-polly.md).</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="c0cd8-154">Время существования HttpClient</span><span class="sxs-lookup"><span data-stu-id="c0cd8-154">HttpClient lifetimes</span></span>

<span data-ttu-id="c0cd8-155">Каждый раз, когда вы получаете объект `HttpClient` из `IHttpClientFactory`, возвращается новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-155">Each time you get an `HttpClient` object from the `IHttpClientFactory`, a new instance is returned.</span></span> <span data-ttu-id="c0cd8-156">Но чтобы уменьшить потребление ресурсов, каждый объект `HttpClient` использует из пула экземпляр `HttpMessageHandler`, который также применяется фабрикой `IHttpClientFactory`, если время существования `HttpMessageHandler` еще не истекло.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-156">But each `HttpClient` uses an `HttpMessageHandler` that's pooled and reused by the `IHttpClientFactory` to reduce resource consumption, as long as the `HttpMessageHandler`'s lifetime hasn't expired.</span></span>

<span data-ttu-id="c0cd8-157">Создание пулов обработчиков желательно, поскольку каждый обработчик обычно управляет собственными базовыми HTTP-подключениями. Создание лишних обработчиков может привести к задержке подключения.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-157">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="c0cd8-158">Некоторые обработчики поддерживают подключения открытыми в течение неопределенного периода, что может помешать обработчику отреагировать на изменения DNS.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-158">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="c0cd8-159">Время существования объектов `HttpMessageHandler`это период, в течение которого экземпляр `HttpMessageHandler` в пуле может использоваться повторно.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-159">The `HttpMessageHandler` objects in the pool have a lifetime that's the length of time that an `HttpMessageHandler` instance in the pool can be reused.</span></span> <span data-ttu-id="c0cd8-160">Значение по умолчанию — две минуты, но его можно переопределить для отдельных типизированных клиентов.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-160">The default value is two minutes, but it can be overridden per Typed Client.</span></span> <span data-ttu-id="c0cd8-161">Чтобы переопределить это значение, вызовите `SetHandlerLifetime()` в экземпляре `IHttpClientBuilder`, который возвращается при создании клиента, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="c0cd8-161">To override it, call `SetHandlerLifetime()` on the `IHttpClientBuilder` that's returned when creating the client, as shown in the following code:</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client
services.AddHttpClient<ICatalogService, CatalogService>()
    .SetHandlerLifetime(TimeSpan.FromMinutes(5));
```

<span data-ttu-id="c0cd8-162">Для каждого типизированного клиента можно указать свое значение времени существования настроенного обработчика.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-162">Each Typed Client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="c0cd8-163">Установите значение `InfiniteTimeSpan`, чтобы отключить срок действия обработчика.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-163">Set the lifetime to `InfiniteTimeSpan` to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="c0cd8-164">Реализация классов типизированных клиентов, использующих внедренный и настроенный HttpClient</span><span class="sxs-lookup"><span data-stu-id="c0cd8-164">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="c0cd8-165">Вы уже должны были уже определить классы типизированных клиентов, например классы в примере кода, такие как BasketService, CatalogService, OrderingService и т. д. Типизированный клиент — это класс, который принимает объект `HttpClient` (внедренный через конструктор) и использует его для вызова удаленной службы HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-165">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A Typed Client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="c0cd8-166">Например:</span><span class="sxs-lookup"><span data-stu-id="c0cd8-166">For example:</span></span>

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

<span data-ttu-id="c0cd8-167">Типизированный клиент (в нашем примере это CatalogService) активируется путем внедрения зависимостей, то есть он может принять любую зарегистрированную службу в свой конструктор в дополнение к HttpClient.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-167">The Typed Client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="c0cd8-168">По сути, типизированный клиент — это временный объект, то есть экземпляр создается каждый раз по необходимости и при этом он будет получать новый экземпляр `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-168">A Typed Client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it's constructed.</span></span> <span data-ttu-id="c0cd8-169">Тем не менее объекты HttpMessageHandler в пуле используются повторно множеством HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-169">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="c0cd8-170">Использование классов типизированных клиентов</span><span class="sxs-lookup"><span data-stu-id="c0cd8-170">Use your Typed Client classes</span></span>

<span data-ttu-id="c0cd8-171">Наконец, когда вы реализуете классы типов и зарегистрируете их в `AddHttpClient()`, их можно будет использовать везде, где можно внедрить службы с помощью внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-171">Finally, once you have your typed classes implemented and have them registered with `AddHttpClient()`, you can use them wherever you can have services injected by DI.</span></span> <span data-ttu-id="c0cd8-172">Например, в любом коде страницы Razor или любом контроллере веб-приложения MVC, как в следующем коде из eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-172">For example, in a Razor page code or controller of an MVC web app, like in the following code from eShopOnContainers:</span></span>

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

<span data-ttu-id="c0cd8-173">Пока пример кода просто выполняет обычные HTTP-запросы. Самое интересное начнется в следующих разделах, где вы будете просто добавлять политики и делегирующие обработчики в зарегистрированные типизированные клиенты. Все HTTP-запросы, которые должны выполняться объектом `HttpClient`, будут учитывать политики отказоустойчивости, например политики повтора c экспоненциальной задержкой, размыкатели цепи или другие настраиваемые делегирующие обработчики, чтобы реализовать дополнительные функции безопасности, такие как маркеры проверки подлинности и другие настраиваемые возможности.</span><span class="sxs-lookup"><span data-stu-id="c0cd8-173">Up to this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered Typed Clients, all the HTTP requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c0cd8-174">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="c0cd8-174">Additional resources</span></span>

- <span data-ttu-id="c0cd8-175">**Использование HttpClientFactory в .NET Core**</span><span class="sxs-lookup"><span data-stu-id="c0cd8-175">**Using HttpClientFactory in .NET Core**</span></span>  
  [https://docs.microsoft.com/aspnet/core/fundamentals/http-requests](/aspnet/core/fundamentals/http-requests)

- <span data-ttu-id="c0cd8-176">**Исходный код HttpClientFactory в репозитории GitHub `aspnet/Extensions`**</span><span class="sxs-lookup"><span data-stu-id="c0cd8-176">**HttpClientFactory source code in the `aspnet/Extensions` GitHub repository**</span></span>  
  <https://github.com/aspnet/Extensions/tree/master/src/HttpClientFactory>

- <span data-ttu-id="c0cd8-177">**Polly (библиотека для обеспечения отказоустойчивости .NET и обработки временных сбоев)**</span><span class="sxs-lookup"><span data-stu-id="c0cd8-177">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <http://www.thepollyproject.org/>
  
- <span data-ttu-id="c0cd8-178">**Использование HttpClientFactory без внедрения зависимостей (проблема GitHub)**</span><span class="sxs-lookup"><span data-stu-id="c0cd8-178">**Using HttpClientFactory without dependency injection (GitHub issue)**</span></span>  
  <https://github.com/aspnet/Extensions/issues/1345>

>[!div class="step-by-step"]
><span data-ttu-id="c0cd8-179">[Назад](explore-custom-http-call-retries-exponential-backoff.md)
>[Вперед](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="c0cd8-179">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
