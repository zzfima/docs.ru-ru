---
title: Реализация шаблона размыкателя цепи
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация шаблона размыкателя цепи
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.openlocfilehash: dea94d8eda3341cca5e3aaf6b3c8369c27381135
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578018"
---
# <a name="implementing-the-circuit-breaker-pattern"></a>Реализация шаблона размыкателя цепи

Как отмечалось ранее, следует реализовать обработку сбоев, на восстановление после которых может требоваться неопределенное количество времени, например, при попытке подключиться к удаленной службе или ресурсу. Обработка подобных сбоев может повысить стабильность работы и отказоустойчивость приложения.

В распределенной среде вызовы удаленных ресурсов и служб могут завершаться сбоем из-за временных состояний, таких как медленные сетевые подключения, истечение времени ожидания или временная недоступность ресурсов. Такие состояния обычно разрешаются через некоторое время. В надежном облачном приложении должна быть предусмотрена их обработка с помощью какого-либо механизма, например шаблона повторных попыток.

Однако возможны также ситуации, когда сбои происходят из-за непредвиденных событий и на их устранение может потребоваться гораздо больше времени. Такие сбои могут быть различной степени серьезности: от частичной потери соединения до полного отказа службы. В таких случаях повторные попытки выполнить операцию, успешное завершение которой маловероятно, могут быть бессмысленны. Вместо этого в коде следует реализовать возможность определения операции как неудавшейся и соответствующей обработки сбоя.

Шаблон размыкателя цепи по своему назначению отличается от шаблона повторных попыток. Шаблон повторных попыток позволяет приложению повторять операцию, исходя из предположения о том, что она в конечном итоге завершится успешно. Шаблон размыкателя цепи предотвращает выполнение операции, которая, скорее всего, завершится сбоем. Эти два шаблона могут сочетаться в приложении, при этом шаблон повторных попыток вызывает операцию через шаблон размыкателя цепи. Однако логика повторных попыток должна реагировать на исключения, возвращаемые размыкателем цепи, и прекращать попытки, если размыкатель цепи сообщает о том, что ошибка не является временной.

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>Реализация шаблона размыкателя цепи с помощью библиотеки Polly

Как и при реализации повторных попыток, рекомендуемым подходом в случае с размыкателями цепи является использование проверенных библиотек .NET, таких как Polly.

Приложение eShopOnContainers использует политику размыкателя цепи Polly при реализации повторных попыток HTTP-запросов. Фактически приложение применяет обе политики к служебному классу ResilientHttpClient. Каждый раз при использовании объекта типа ResilientHttpClient для HTTP-запросов (из eShopOnContainers) вы применяете обе эти политики, однако можно добавить и другие политики.

Единственным дополнением к коду, используемому для повторных попыток вызовов по HTTP, является фрагмент, в котором политика размыкателя цепи добавляется в список применяемых политик, как показано в конце следующего примера:

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
            // number of retries
            6,
            // exponential backofff
            retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
            // on retry
            (exception, timeSpan, retryCount, context) =>
            {
                var msg = $"Retry {retryCount} implemented with Polly RetryPolicy " +
                    $"of {context.PolicyKey} " +
                    $"at {context.ExecutionKey}, " +
                    $"due to: {exception}.";
                _logger.LogWarning(msg);
                _logger.LogDebug(msg);
            }),
            Policy.Handle<HttpRequestException>()
                .CircuitBreakerAsync(
                    // number of exceptions before breaking circuit
                    5,
                    // time circuit opened before retry
                    TimeSpan.FromMinutes(1),
                    (exception, duration) =>
                    {
                        // on circuit opened
                        _logger.LogTrace("Circuit breaker opened");
                    },
                    () =>
                    {
                        // on circuit closed
                        _logger.LogTrace("Circuit breaker reset");
                    })
    };
}
```

В этом коде политика добавляется в оболочку HTTP. Эта политика определяет размыкатель цепи, который открывается при обнаружении кодом указанного числа последовательных (идущих подряд) исключений, передаваемого в параметре exceptionsAllowedBeforeBreaking (в этом случае 5). Когда цепь разомкнута, HTTP-запросы не выполняются и вызывается исключение.

Размыкатели цепи следует также использовать для перенаправления запросов в резервную инфраструктуру, если возможны проблемы с определенным ресурсом, который развернут в среде, отличной от той, где размещается клиентское приложение или служба, выполняющие вызов по HTTP. Благодаря этому при сбоях в центре обработки данных, влияющих только на серверные микрослужбы, но не на клиентские приложения, клиентские приложения могут перенаправлять запросы в резервные службы. В библиотеке Polly планируется добавить новую политику для автоматизации применения такой [политики отработки отказа](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).

Конечно, все эти возможности предназначены для случаев, когда управление отработкой отказа осуществляется в коде .NET, а не платформой Azure независимо от расположения.

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>Использование служебного класса ResilientHttpClient из eShopOnContainers

Служебный класс ResilientHttpClient используется аналогично тому, как используется класс .NET HttpClient. В приведенном ниже примере из веб-приложения MVC eShopOnContainers (класс агента OrderingService, используемый контроллером OrderController) объект ResilientHttpClient внедряется посредством параметра httpClient конструктора. Затем этот объект применяется для выполнения HTTP-запросов.

```csharp
public class OrderingService : IOrderingService
{
    private IHttpClient _apiClient;
    private readonly string _remoteServiceBaseUrl;
    private readonly IOptionsSnapshot<AppSettings> _settings;
    private readonly IHttpContextAccessor _httpContextAccesor;

    public OrderingService(IOptionsSnapshot<AppSettings> settings,
        IHttpContextAccessor httpContextAccesor,
        IHttpClient httpClient)
    {
        _remoteServiceBaseUrl = $"{settings.Value.OrderingUrl}/api/v1/orders";
        _settings = settings;
        _httpContextAccesor = httpContextAccesor;
        _apiClient = httpClient;
    }

    async public Task<List<Order>> GetMyOrders(ApplicationUser user)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        var ordersUrl = _remoteServiceBaseUrl;
        var dataString = await _apiClient.GetStringAsync(ordersUrl);
        var response = JsonConvert.DeserializeObject<List<Order>>(dataString);
        return response;
    }

    // Other methods ...
    async public Task CreateOrder(Order order)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        _apiClient.Inst.DefaultRequestHeaders.Add("x-requestid",
            order.RequestId.ToString());
        var ordersUrl = $"{_remoteServiceBaseUrl}/new";
        order.CardTypeId = 1;
        order.CardExpirationApiFormat();
        SetFakeIdToProducts(order);
        var response = await _apiClient.PostAsync(ordersUrl, order);
        response.EnsureSuccessStatusCode();
    }
}
```

Каждый раз при использовании объекта члена \_apiClient в нем используется класс-оболочка с политиками Polly: политикой повторных попыток, политикой размыкателя цепи и другими политиками из коллекции политик Polly, которые может потребоваться применить.

## <a name="testing-retries-in-eshoponcontainers"></a>Тестирование повторных попыток в eShopOnContainers

При запуске решения eShopOnContainers в узле Docker должно запускаться несколько контейнеров. Некоторые контейнеры, например контейнер SQL Server, запускаются и инициализируются медленнее, чем другие. Особенно очевидно это проявляется при первом развертывании приложения eShopOnContainers в Docker, так как при этом должны настраиваться образы и база данных. Из-за более медленного запуска некоторых контейнеров остальные службы могут изначально вызывать исключения HTTP, даже если вы настроили зависимости между контейнерами на уровне docker-compose, как было описано в предыдущих разделах. Зависимости docker-compose между контейнерами существуют на уровне процессов. Процесс точки входа в контейнер может быть запущен, но сервер SQL Server может быть не готов принимать запросы. В результате может происходить непрерывный ряд ошибок, и в приложении может возникнуть исключение при попытке использовать данный контейнер.

Подобные ошибки могут также наблюдаться при запуске приложения, развернутого в облаке. В этом случае оркестраторы могут перемещать контейнеры из одного узла (или виртуальной машины) в другой (запуская новые экземпляры) в процессе балансировки числа контейнеров между узлами кластера.

В eShopOnContainers эта проблема решается с помощью шаблона повторных попыток, который был продемонстрирован ранее. По этой же причине при запуске решения могут появляться сообщения в журнале трассировки и предупреждения, похожие на следующее:

> "**Повторная попытка 1, реализованная с помощью политики RetryPolicy библиотеки Polly** из-за System.Net.Http.HttpRequestException. Произошла ошибка при отправке запроса. ---&gt; System.Net.Http.CurlException. Не удалось подключиться к серверу\\ в System.Net.Http.CurlHandler.ThrowIfCURLEError(ошибка CURLcode)\\ в \[...\].

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>Тестирование размыкателя цепи в eShopOnContainers

Есть несколько способов разомкнуть цепь и протестировать ее в eShopOnContainers.

Один из вариантов — уменьшить разрешенное число повторных попыток до 1 в политике размыкателя цепи и повторно развернуть все решение в Docker. При одной повторной попытке высока вероятность того, что HTTP-запрос завершится сбоем во время развертывания, размыкатель цепи откроется и произойдет ошибка.

Другой вариант — использовать пользовательское ПО промежуточного слоя, реализованное в микрослужбе `Basket`. При его включении оно перехватывает все HTTP-запросы и возвращает код состояния 500. Чтобы включить ПО промежуточного слоя, можно выполнить запрос GET к сбойному универсальному коду ресурса (URI), например, следующему:

-   GET /failing

Этот запрос возвращает текущее состояние ПО промежуточного слоя. Если оно включено, запрос возвращает код состояния 500. Если оно отключено, ответа нет.

-   GET /failing?enable

Этот запрос включает ПО промежуточного слоя.

-   GET /failing?disable

Этот запрос отключает ПО промежуточного слоя.

Например, после запуска приложения вы можете включить ПО промежуточного слоя, выполнив запрос к указанному ниже коду URI в любом браузере. Обратите внимание на то, что микрослужба размещения заказов использует порт 5103.

http://localhost:5103/failing?enable

После этого состояние можно проверить, используя код URI [http://localhost:5103/failing](http://localhost:5103/failing), как показано на рисунке 10-4.

![](./media/image4.png)

**Рис. 10-4**. Проверка состояния ПО промежуточного слоя ASP.NET (в этом случае отключено) 

На этом этапе микрослужба Basket возвращает код состояния 500 при каждом вызове.

Когда ПО промежуточного слоя будет запущено, вы можете попытаться сделать заказ в веб-приложении MVC. Так как запрос завершается сбоем, цепь размыкается.

В приведенном ниже примере можно увидеть, что в веб-приложении MVC есть блок catch в логике размещения заказа. Если код перехватывает исключение размыкания цепи, он выводит сообщение с просьбой к пользователю подождать.

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            //… Other code
        }
        catch (BrokenCircuitException)
        {
            // Catches error when Basket.api is in circuit-opened mode                 
            HandleBrokenCircuitException();
        }
        return View();
    }       

    private void HandleBrokenCircuitException()
    {
        TempData["BasketInoperativeMsg"] = "Basket Service is inoperative, please try later on. (Business message due to Circuit-Breaker)";
    }
}
```

Вкратце рассмотрим, что происходит. Политика повторных попыток несколько раз пытается выполнить HTTP-запрос и получает ошибки HTTP. Когда число повторных попыток достигает максимального значения, заданного для политики размыкателя цепи (в этом случае 5), приложение вызывает исключение BrokenCircuitException. В результате выводится понятное сообщение для пользователя, как показано на рисунке 10-5.

![](./media/image5.png)

**Рис. 10-5**. Размыкатель цепи возвращает ошибку в пользовательский интерфейс

Вы можете реализовать другую логику размыкания цепи. Кроме того, можно пытаться выполнять HTTP-запросы к другой серверной микрослужбе, если имеется резервный центр обработки данных или избыточная серверная система.

Наконец, еще одной возможностью CircuitBreakerPolicy является использование методов Isolate (размыкает цепь и сохраняет ее в таком состоянии) и Reset (снова замыкает цепь). Таким образом, можно создать служебную конечную точку HTTP, которая напрямую вызывает методы Isolate и Reset политики. Такую конечную точку HTTP с надлежащей защитой можно также использовать в рабочей среде для временной изоляции подчиненной системы, например, если ее необходимо обновить. Кроме того, с ее помощью можно размыкать цепь вручную для защиты подчиненной системы, если есть подозрения на ее неисправность.

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>Добавление стратегии в отношении колебания задержки в политику повтора

Обычная политика повтора может влиять на работу системы в случае высокого уровня параллелизма и масштабируемости, а также в условиях интенсивного состязания за ресурсы. Чтобы решить проблему с большим числом повторных запросов, поступающих от множества клиентов в случае частичного отказа системы, можно добавить стратегию в отношении колебания задержки в алгоритм или политику повтора. Это может повысить общую производительность всей системы благодаря тому, что экспоненциальная задержка становится более случайной. При возникновении проблем пики размываются. При использовании библиотеки Polly код для реализации колебания задержки может выглядеть следующим образом:

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Шаблон повтора**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **Устойчивость подключений** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly** (библиотека для обеспечения отказоустойчивости .NET и обработки временных сбоев) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **Шаблон размыкателя цепи**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Марк Брукер (Marc Brooker). Дрожание. Оптимизация с помощью случайности** https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[Назад] (implement-http-call-retries-exponential-backoff-polly.md) [Далее] (monitor-app-health.md)
