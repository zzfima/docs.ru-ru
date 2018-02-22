---
title: "Реализация повторных попыток вызова HTTP с экспоненциальной выдержкой с помощью библиотеки Polly"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация повторных попыток вызова HTTP с экспоненциальной выдержкой с помощью библиотеки Polly"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 122f617874188d3bffe689d6b3cf7d7249c59c3b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a><span data-ttu-id="c2b88-104">Реализация повторных попыток вызова HTTP с экспоненциальной выдержкой с помощью библиотеки Polly</span><span class="sxs-lookup"><span data-stu-id="c2b88-104">Implementing HTTP call retries with exponential backoff with Polly</span></span>

<span data-ttu-id="c2b88-105">Рекомендуемый подход к выполнению повторных попыток с экспоненциальной выдержкой заключается в использовании расширенных библиотек .NET, таких как библиотека [Polly](https://github.com/App-vNext/Polly) с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b88-105">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open source [Polly](https://github.com/App-vNext/Polly) library.</span></span>

<span data-ttu-id="c2b88-106">Polly — это библиотека .NET, которая предоставляет возможности обеспечения отказоустойчивости и обработки временных сбоев.</span><span class="sxs-lookup"><span data-stu-id="c2b88-106">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="c2b88-107">Эти возможности можно легко реализовать путем применения политик Polly, таких как политики повтора, размыкателя цепи, изоляции отсеков, времени ожидания и отката.</span><span class="sxs-lookup"><span data-stu-id="c2b88-107">You can implement those capabilities easily by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="c2b88-108">Библиотека Polly предназначена для .NET 4.x и .NET Standard версии 1.0 (поддерживает .NET Core).</span><span class="sxs-lookup"><span data-stu-id="c2b88-108">Polly targets .NET 4.x and the .NET Standard version 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="c2b88-109">Политика повтора из библиотеки Polly используется в приложении eShopOnContainers при реализации повторных попыток вызова HTTP.</span><span class="sxs-lookup"><span data-stu-id="c2b88-109">The Retry policy in Polly is the approach used in eShopOnContainers when implementing HTTP retries.</span></span> <span data-ttu-id="c2b88-110">С помощью Polly можно реализовать интерфейс для внедрения стандартной функциональности HttpClient или отказоустойчивой версии HttpClient в зависимости от требуемой конфигурации политики повтора.</span><span class="sxs-lookup"><span data-stu-id="c2b88-110">You can implement an interface so you can inject either standard HttpClient functionality or a resilient version of HttpClient using Polly, depending on what retry policy configuration you want to use.</span></span>

<span data-ttu-id="c2b88-111">В приведенном ниже примере показан интерфейс, реализованный в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c2b88-111">The following example shows the interface implemented in eShopOnContainers.</span></span>

```csharp
public interface IHttpClient
{
    Task<string> GetStringAsync(string uri, string authorizationToken = null,
        string authorizationMethod = "Bearer");
        Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    Task<HttpResponseMessage> DeleteAsync(string uri,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    // Other methods ...
}
```

<span data-ttu-id="c2b88-112">Вы можете использовать стандартную реализацию, если вам не нужен механизм отказоустойчивости, например при разработке или тестировании простых решений.</span><span class="sxs-lookup"><span data-stu-id="c2b88-112">You can use the standard implementation if you do not want to use a resilient mechanism, as when you are developing or testing simpler approaches.</span></span> <span data-ttu-id="c2b88-113">В приведенном ниже коде показана стандартная реализация HttpClient, допускающая при необходимости запросы с токенами проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c2b88-113">The following code shows the standard HttpClient implementation allowing requests with authentication tokens as an optional case.</span></span>

```csharp
public class StandardHttpClient : IHttpClient
{
    private HttpClient _client;
    private ILogger<StandardHttpClient> _logger;

    public StandardHttpClient(ILogger<StandardHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
    }

    public async Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
        if (authorizationToken != null)
        {
            requestMessage.Headers.Authorization =
                new AuthenticationHeaderValue(authorizationMethod, authorizationToken);
        }
        var response = await _client.SendAsync(requestMessage);
        return await response.Content.ReadAsStringAsync();
    }

    public async Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer")
    {
        // Rest of the code and other Http methods ...
```

<span data-ttu-id="c2b88-114">Интересным вариантом реализации является написание другого простого класса и использование Polly для реализации требуемых механизмов отказоустойчивости. В приведенном ниже примере это повторные попытки с экспоненциальной выдержкой.</span><span class="sxs-lookup"><span data-stu-id="c2b88-114">The interesting implementation is to code another, similar class, but using Polly to implement the resilient mechanisms you want to use—in the following example, retries with exponential backoff.</span></span>

```csharp
public class ResilientHttpClient : IHttpClient
{
    private HttpClient _client;
    private PolicyWrap _policyWrapper;
    private ILogger<ResilientHttpClient> _logger;

    public ResilientHttpClient(Policy[] policies,
        ILogger<ResilientHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
        // Add Policies to be applied
        _policyWrapper = Policy.WrapAsync(policies);
    }

    private Task<T> HttpInvoker<T>(Func<Task<T>> action)
    {
        // Executes the action applying all
        // the policies defined in the wrapper
        return _policyWrapper.ExecuteAsync(() => action());
    }

    public Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        return HttpInvoker(async () =>
        {
            var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
            // The Token's related code eliminated for clarity in code snippet
            var response = await _client.SendAsync(requestMessage);
            return await response.Content.ReadAsStringAsync();
        });
    }
    // Other Http methods executed through HttpInvoker so it applies Polly policies
    // ...
}
```

<span data-ttu-id="c2b88-115">С помощью Polly вы определяете политику повтора с числом повторных попыток, конфигурацией экспоненциальной выдержки и действиями, которые необходимо выполнить в случае исключения HTTP (например, запись ошибки в журнал).</span><span class="sxs-lookup"><span data-stu-id="c2b88-115">With Polly, you define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there is an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="c2b88-116">В этом случае политика настроена так, что она будет выполнять указанное число попыток при регистрации типов в контейнере IoC.</span><span class="sxs-lookup"><span data-stu-id="c2b88-116">In this case, the policy is configured so it will try the number of times specified when registering the types in the IoC container.</span></span> <span data-ttu-id="c2b88-117">В соответствии с конфигурацией экспоненциальной выдержки при обнаружении кодом исключения HttpRequest он будет повторно выполнять HTTP-запрос через промежуток времени, который увеличивается экспоненциально в зависимости от того, как настроена политика.</span><span class="sxs-lookup"><span data-stu-id="c2b88-117">Because of the exponential backoff configuration, whenever the code detects an HttpRequest exception, it retries the Http request after waiting an amount of time that increases exponentially depending on how the policy was configured.</span></span>

<span data-ttu-id="c2b88-118">Здесь важен метод HttpInvoker. Именно он выполняет HTTP-запросы в этом служебном классе.</span><span class="sxs-lookup"><span data-stu-id="c2b88-118">The important method is HttpInvoker, which is what makes HTTP requests throughout this utility class.</span></span> <span data-ttu-id="c2b88-119">Этот метод выполняет HTTP-запрос с помощью \_policyWrapper.ExecuteAsync с учетом политики повтора.</span><span class="sxs-lookup"><span data-stu-id="c2b88-119">That method internally executes the HTTP request with \_policyWrapper.ExecuteAsync, which takes into account the retry policy.</span></span>

<span data-ttu-id="c2b88-120">В приложении eShopOnContainers политики Polly задаются при регистрации типов в контейнере IoC, как в приведенном ниже коде из класса [веб-приложения MVC в файле startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs).</span><span class="sxs-lookup"><span data-stu-id="c2b88-120">In eShopOnContainers you specify Polly policies when registering the types at the IoC container, as in the following code from the [MVC web app at the startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) class.</span></span>

```csharp
// Startup.cs class
if (Configuration.GetValue<string>("UseResilientHttp") == bool.TrueString)
{
    services.AddTransient<IResilientHttpClientFactory,
        ResilientHttpClientFactory>();
    services.AddSingleton<IHttpClient,
        ResilientHttpClient>(sp =>
            sp.GetService<IResilientHttpClientFactory>().
            CreateResilientHttpClient());
}
else
{
    services.AddSingleton<IHttpClient, StandardHttpClient>();
}
```

<span data-ttu-id="c2b88-121">Обратите внимание на то, что объекты IHttpClient создаются как одноэлементные, а не как временные, чтобы подключения TCP эффективно использовались службой и не возникало [проблемы с сокетами](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).</span><span class="sxs-lookup"><span data-stu-id="c2b88-121">Note that the IHttpClient objects are instantiated as singleton instead of as transient so that TCP connections are used efficiently by the service and [an issue with sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) will not occur.</span></span>

<span data-ttu-id="c2b88-122">Важным моментом, касающимся отказоустойчивости, является то, что политика WaitAndRetryAsync из библиотеки Polly применяется в объекте ResilientHttpClientFactory в методе CreateResilientHttpClient, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="c2b88-122">But the important point about resiliency is that you apply the Polly WaitAndRetryAsync policy within ResilientHttpClientFactory in the CreateResilientHttpClient method, as shown in the following code:</span></span>

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

// Other code
private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
        // number of retries
        6,
        // exponential backoff
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
        // on retry
        (exception, timeSpan, retryCount, context) =>
        {
            var msg = $"Retry {retryCount} implemented with Pollys RetryPolicy " +
            $"of {context.PolicyKey} " +
            $"at {context.ExecutionKey}, " +
            $"due to: {exception}.";
            _logger.LogWarning(msg);
            _logger.LogDebug(msg);
        }),
    }
```


>[!div class="step-by-step"]
<span data-ttu-id="c2b88-123">[Назад] (implement-custom-http-call-retries-exponential-backoff.md) [Далее] (implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="c2b88-123">[Previous] (implement-custom-http-call-retries-exponential-backoff.md) [Next] (implement-circuit-breaker-pattern.md)</span></span>
