---
title: "Реализация шаблона Размыкатель цепи"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализация шаблона Размыкатель цепи"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2a629e25a7565aaba156f68cf06d9a24b6c2b8b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a>Реализация шаблона Размыкатель цепи

Как отмечалось ранее, следует обрабатывать ошибки, которые может потребоваться переменный объем времени для восстановления, как может произойти при попытке подключения к удаленной службе или ресурсу. Этот тип ошибки обработки можно повысить стабильность и устойчивости приложения.

В распределенной среде вызовы к удаленным ресурсам и службам может завершиться ошибкой из-за временных ошибок, таких как медленные сетевые подключения и истечение времени ожидания, или ресурсам, выполняется ли медленно или временно недоступны. Эти ошибки обычно разрешаться через некоторое время и надежной облачного приложения должно быть готово обработать их с помощью стратегии like шаблон "Повторить".

Однако также может быть ситуациях, когда имеются ошибки из-за непредвиденных событий, которые может занять больше времени для исправления. Эти ошибки варьируются от частичная потеря подключения до завершения сбоя службы. В таких ситуациях может быть бессмысленным постоянно повторите операцию, маловероятно, что для успешного выполнения приложения. Вместо этого приложения должен быть закодирован принимать сбой операции и обработки ошибки соответствующим образом.

Шаблон Размыкатель цепи имеет целей, отличных от шаблон повторения попытки. Шаблон повторения попытки позволяет приложению повторить попытку операции в предположении, что операция в конечном итоге будет выполнена успешно. Шаблон Размыкатель цепи не позволяет приложению выполняемая операция может привести к отказу. Приложение может сочетать этих двух шаблонов с помощью шаблона "Повторить" для вызова операцию с использованием Размыкатель цепи. Однако логику повторных попыток должно быть чувствительно к любые исключения, возвращенных Размыкатель цепи, и его следует отказаться от повторных попыток, если Размыкатель цепи указывает, что ошибка не является временной.

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>Реализация шаблона Размыкателя цепи с Polly

Как при реализации повторных попыток, рекомендуемым выключатели — воспользоваться преимуществом проверенные библиотек .NET, таких как Polly.

Приложение eShopOnContainers использует политики Polly Размыкатель цепи при реализации HTTP повторных попыток. На самом деле приложение применяет обе политики ResilientHttpClient служебный класс. Каждый раз, когда вы используете объект типа ResilientHttpClient для HTTP-запросов (с eShopOnContainers), при применении обе эти политики, но можно добавить дополнительные политики слишком.

Единственным дополнением здесь код, используемый для повторных попыток вызовов HTTP-код, когда добавляются политики Размыкатель цепи список политик для использования, как показано в конце следующий код:

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

Код добавляет политику оболочки HTTP. Определяет, политики Размыкатель цепи, которое открывается, если код определяет указанное число последовательных исключения (исключения в строке), как передаваемые в качестве параметра exceptionsAllowedBeforeBreaking (5 в данном случае). После открытия канала HTTP-запросов не работают, но создается исключение.

Выключатели также следует использовать для перенаправления запросов в резервный инфраструктуры, если могут возникнуть проблемы с конкретного ресурса, который развертывается в среду, отличную от клиентского приложения или службы, который выполняет вызов HTTP. Таким образом, если происходит сбой в центре обработки данных, влияющие только микрослужбами вашей серверной части, но не клиентских приложений, клиентские приложения может перенаправить резервной службы. Планирует новую политику для автоматизации этой Polly [политики отработки отказа](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) сценария.

Конечно эти функции предназначены для случаев, где вы управляете отработки отказа с кодом .NET, сравните это с ее управляет автоматически автоматически Azure, с прозрачностью расположение.

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>С помощью служебного класса ResilientHttpClient из eShopOnContainers

Служебный класс ResilientHttpClient использовать так же, как использовать класс .NET HttpClient. В следующем примере из веб-приложения MVC eShopOnContainers (класс OrderingService агента, используемых OrderController) объект ResilientHttpClient встраивается через параметр httpClient конструктора. Затем объект используется для выполнения HTTP-запросов.

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

Каждый раз, когда \_используется apiClient объект члена, внутренним образом использует класс-оболочку с Polly policiesؙ — политику повтора, Размыкатель цепи политики и другие политики, которые можно применить из коллекции политик Polly.

## <a name="testing-retries-in-eshoponcontainers"></a>Тестирование повторных попыток в eShopOnContainers

При каждом запуске eShopOnContainers решений в узле Docker, необходимо запустить несколько контейнеров. Некоторые контейнеры происходит медленнее и инициализации, таких как SQL Server контейнер. Это особенно важно при первом развертывании приложения eShopOnContainers в Docker, так как он должен настроить изображений и базы данных. Тот факт, что некоторые контейнеры медленнее, чем другие может привести к остальным службам для изначально создания исключений HTTP, даже если вы настроите зависимости между контейнерами на запуск docker составления уровне, как описано в предыдущих разделах. Те docker составления зависимости между контейнерами являются только на уровне процесса. Возможно, запущен процесс точки входа контейнера, но SQL Server может не быть готова к запросам. В результате могут появиться cascade ошибок и приложения можно получить исключение при попытке использовать этот конкретный контейнер.

Также возможны ошибки такого типа во время запуска, когда выполняется развертывание приложения в облако. В этом случае orchestrators может перемещение контейнеры из одного узла или виртуальной Машины на другой (которое запускает новые экземпляры) при разделении количество контейнеров в узлах кластера.

С помощью шаблона "Повторить", который мы приведенных ранее — способ eShopOnContainers решает эту проблему. Кроме того, он почему, при запуске решения, может появиться трассировки журналов и предупреждений, следующим образом:

> «**Попытка 1 реализуется с помощью элемента Polly RetryPolicy**из- за: System.Net.Http.HttpRequestException: произошла ошибка при отправке запроса. ---&gt;System.Net.Http.CurlException: Не удалось подключиться к серверу\\n в System.Net.Http.CurlHandler.ThrowIfCURLEError (ошибка CURLcode)\\n в \[... \].

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>Тестирование Размыкатель цепи в eShopOnContainers

Можно открыть канал и проверить его с eShopOnContainers несколькими способами.

Необходимо снизить допустимое число повторных попыток для 1 в политике Размыкатель цепи и повторного развертывания всего решения в Docker. С одной повторной попытки есть риск, что HTTP-запрос завершится ошибкой во время развертывания, Размыкатель цепи будет открыт, и появляется сообщение об ошибке.

Другой вариант — использовать пользовательские по промежуточного слоя, реализованная в микрослужбу порядка сортировки. При включении этого по промежуточного слоя, он перехватывает все HTTP-запросы и возвращает код состояния 500. По промежуточного слоя можно включить, выполнив запрос GET к отказавшему URI следующего вида:

-   GET/сбой

Этот запрос возвращает текущее состояние по промежуточного слоя. Если включен по промежуточного слоя, запрос возвращает код состояния 500. Если по промежуточного слоя отключена, нет ответа.

-   GET/сбой? включить

Этот запрос позволяет по промежуточного слоя.

-   GET/сбой? отключение

Этот запрос отключает по промежуточного слоя.

Для экземпляра после запуска приложения можно включить по промежуточного слоя, выполняющего запрос, используя следующий URI в любом браузере. Обратите внимание, что упорядочивания микрослужбу использует порт 5102.

http://localhost:5102 / сбой? включить

Затем можно проверить состояние с помощью URI [http://localhost:5102 / сбой](http://localhost:5100/failing), как показано на рисунке 10-4.

![](./media/image4.png)

**На рис. 10-4**. Имитация неисправности с помощью по промежуточного слоя ASP.NET

На этом этапе упорядочения микрослужбу ответ с кодом состояния 500, при каждом вызове выполнять соответствующие действия.

После запуска по промежуточного слоя, попробуйте сделать заказ из веб-приложения MVC. Так как произошел сбой запроса, канал будет открыт.

В следующем примере можно увидеть, что веб-приложение MVC имеет catch блока в логику для размещения заказа. Если код перехватывает исключение открытия канала, показывает пользователь понятное сообщение, уведомляющее о ожидания.

```csharp
[HttpPost]
public async Task<IActionResult> Create(Order model, string action)
{
    try
    {
        if (ModelState.IsValid)
        {
            var user = _appUserParser.Parse(HttpContext.User);
            await _orderSvc.CreateOrder(model);
            //Redirect to historic list.
            return RedirectToAction("Index");
        }
    }
    catch(BrokenCircuitException ex)
    {
        ModelState.AddModelError("Error",
            "It was not possible to create a new order, please try later on");
    }
    return View(model);
}
```

Ниже приведена сводка. Политика повтора пытается несколько раз, чтобы сделать HTTP-запрос и возвращает ошибки HTTP. Когда число попыток достигает максимальное число, заданное для политики Размыкатель цепи (в данном случае 5), приложение выдает BrokenCircuitException. Результатом является понятное сообщение, как показано на рисунке 10-5.

![](./media/image5.png)

**На рис. 10-5**. Размыкатель цепи, возвращается ошибка пользовательского интерфейса

Можно реализовать другой логикой, когда для открытия канала. Или при наличии резервной центра обработки данных или избыточные серверную систему, можно попробовать HTTP-запрос к другой микрослужбу серверной части.

Наконец другая возможность CircuitBreakerPolicy является использование изолировать (который заставляет открытым и оставляет открытым канала) и сброса (которая закрывает снова). Они используются для построения программы конечной точки HTTP, вызывающий изолировать и сброс непосредственно в политике. Такой конечной точки HTTP также может использоваться, подходящим образом защищены в рабочей среде для временно изоляции подчиненных системы, например, если вы хотите обновить его. Или он может быть вручную, чтобы защитить подчиненных систему, которую предполагается быть сброса канала.

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>Добавление стратегии флуктуации политику повтора

Регулярные политику повторов может повлиять на системы в случаях, масштабируемость и высокий уровень параллелизма, а также в разделе большого количества состязаний данных. Чтобы преодолеть пиков аналогичные повторных попыток, поступающих от большого числа клиентов в случае частичного простои, хорошим решением проблемы является добавление стратегии флуктуации алгоритм или политику повтора. Это может повысить общую производительность системы начала до конца, добавив случайности экспоненциальное увеличение задержки. В этом случае пиковых при возникновении неисправности. При использовании Polly код для реализации флуктуации может выглядеть как в следующем примере:

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Повторите шаблон**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **Устойчивость подключения** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly** (устойчивость .NET и обработки ошибок динамической библиотеки) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **Размыкатель цепи шаблон**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Марк Brooker. Флуктуации: Что лучше неупорядоченных** https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[Предыдущие] (implement-http-call-retries-exponential-backoff-polly.md) [Далее] (health.md монитор приложения)
