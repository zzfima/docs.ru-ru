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
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>Реализация повторных попыток вызова HTTP с экспоненциальной выдержкой с помощью библиотеки Polly

Рекомендуемый подход к выполнению повторных попыток с экспоненциальной выдержкой заключается в использовании расширенных библиотек .NET, таких как библиотека [Polly](https://github.com/App-vNext/Polly) с открытым кодом.

Polly — это библиотека .NET, которая предоставляет возможности обеспечения отказоустойчивости и обработки временных сбоев. Эти возможности можно легко реализовать путем применения политик Polly, таких как политики повтора, размыкателя цепи, изоляции отсеков, времени ожидания и отката. Библиотека Polly предназначена для .NET 4.x и .NET Standard версии 1.0 (поддерживает .NET Core).

Политика повтора из библиотеки Polly используется в приложении eShopOnContainers при реализации повторных попыток вызова HTTP. С помощью Polly можно реализовать интерфейс для внедрения стандартной функциональности HttpClient или отказоустойчивой версии HttpClient в зависимости от требуемой конфигурации политики повтора.

В приведенном ниже примере показан интерфейс, реализованный в eShopOnContainers.

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

Вы можете использовать стандартную реализацию, если вам не нужен механизм отказоустойчивости, например при разработке или тестировании простых решений. В приведенном ниже коде показана стандартная реализация HttpClient, допускающая при необходимости запросы с токенами проверки подлинности.

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

Интересным вариантом реализации является написание другого простого класса и использование Polly для реализации требуемых механизмов отказоустойчивости. В приведенном ниже примере это повторные попытки с экспоненциальной выдержкой.

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

С помощью Polly вы определяете политику повтора с числом повторных попыток, конфигурацией экспоненциальной выдержки и действиями, которые необходимо выполнить в случае исключения HTTP (например, запись ошибки в журнал). В этом случае политика настроена так, что она будет выполнять указанное число попыток при регистрации типов в контейнере IoC. В соответствии с конфигурацией экспоненциальной выдержки при обнаружении кодом исключения HttpRequest он будет повторно выполнять HTTP-запрос через промежуток времени, который увеличивается экспоненциально в зависимости от того, как настроена политика.

Здесь важен метод HttpInvoker. Именно он выполняет HTTP-запросы в этом служебном классе. Этот метод выполняет HTTP-запрос с помощью \_policyWrapper.ExecuteAsync с учетом политики повтора.

В приложении eShopOnContainers политики Polly задаются при регистрации типов в контейнере IoC, как в приведенном ниже коде из класса [веб-приложения MVC в файле startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs).

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

Обратите внимание на то, что объекты IHttpClient создаются как одноэлементные, а не как временные, чтобы подключения TCP эффективно использовались службой и не возникало [проблемы с сокетами](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).

Важным моментом, касающимся отказоустойчивости, является то, что политика WaitAndRetryAsync из библиотеки Polly применяется в объекте ResilientHttpClientFactory в методе CreateResilientHttpClient, как показано в следующем коде:

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
[Назад] (implement-custom-http-call-retries-exponential-backoff.md) [Далее] (implement-circuit-breaker-pattern.md)
