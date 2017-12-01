---
title: "Реализация повторные попытки вызова HTTP с экспоненциально растущим с Polly"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализация повторные попытки вызова HTTP с экспоненциально растущим с Polly"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1ed48142546403ea710f4c132e038521232c20ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>Реализация повторные попытки вызова HTTP с экспоненциально растущим с Polly

Для повторных попыток с экспоненциально растущим рекомендуется пользоваться преимуществами более сложных библиотек .NET, как открыть источник [Polly](https://github.com/App-vNext/Polly) библиотеки.

Polly — это библиотека .NET, которая предоставляет возможности обработки временных сбоев и устойчивости. Можно реализовать эти возможности легко путем применения Polly политики, такие как "Повторить", Размыкатель цепи, блочный изоляции, время ожидания и Fallback. Polly обращается .NET 4.x и .NET Standard версии 1.0 (который поддерживает .NET Core).

Политика повтора в Polly именно этот подход используется в eShopOnContainers при реализации HTTP повторных попыток. Можно реализовать интерфейс, поэтому можно ввести стандартных функциональных возможностей HttpClient или более устойчивым версии HttpClient, с помощью Polly, в зависимости от конфигурации политик повторных попыток, которые вы хотите использовать.

В следующем примере показано интерфейс, реализованный в eShopOnContainers.

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

Если не хотите использовать устойчивым механизм, как при разработке или тестирования проще подходов можно использовать стандартную реализацию. В следующем коде показано Стандартная HttpClient реализацию разрешает запросы с маркерами безопасности как дополнительный вариант.

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

Интересные реализуется кода класса другой, похожий, но с использованием Polly для реализации гибкой механизмов, которые вы хотите использовать — в следующем примере повторных попыток с экспоненциально растущим.

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

Polly определять политику повторов с числом повторов, экспоненциально растущим конфигурации и действия, выполняемые при возникновении исключения HTTP, например, ведение журнала ошибок. В этом случае политика настроена, будет предпринята попытка количество времени, указанного при регистрации типов в контейнер IoC. Из-за конфигурации экспоненциально растущим всякий раз, когда код обнаруживает исключение HttpRequest повторяет HTTP-запроса после ожидания за период времени, растет в геометрической прогрессии в зависимости от настроек политики.

Важный метод — HttpInvoker, который указывает, что HTTP-запросы по всему служебный класс. Внутренне выполняется HTTP-запрос с метод \_policyWrapper.ExecuteAsync, который учитывает политику повтора.

В eShopOnContainers при регистрации типов на контейнер IoC, как показано в следующем коде из указываются политики Polly [веб-приложение MVC в файле startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) класса.

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

Обратите внимание, что, чтобы подключения TCP эффективно используются службы как singleton, а не как временной создаются экземпляры объектов IHttpClient и [проблему с помощью сокетов](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) не произойдет.

Однако важно об устойчивости, применить политику Polly WaitAndRetryAsync в ResilientHttpClientFactory в методе CreateResilientHttpClient, как показано в следующем коде:

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
[Предыдущие] (implement-custom-http-call-retries-exponential-backoff.md) [Далее] (реализуйте канал выключатель pattern.md)
