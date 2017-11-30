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
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="80045-104">Реализация шаблона Размыкатель цепи</span><span class="sxs-lookup"><span data-stu-id="80045-104">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="80045-105">Как отмечалось ранее, следует обрабатывать ошибки, которые может потребоваться переменный объем времени для восстановления, как может произойти при попытке подключения к удаленной службе или ресурсу.</span><span class="sxs-lookup"><span data-stu-id="80045-105">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="80045-106">Этот тип ошибки обработки можно повысить стабильность и устойчивости приложения.</span><span class="sxs-lookup"><span data-stu-id="80045-106">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="80045-107">В распределенной среде вызовы к удаленным ресурсам и службам может завершиться ошибкой из-за временных ошибок, таких как медленные сетевые подключения и истечение времени ожидания, или ресурсам, выполняется ли медленно или временно недоступны.</span><span class="sxs-lookup"><span data-stu-id="80045-107">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="80045-108">Эти ошибки обычно разрешаться через некоторое время и надежной облачного приложения должно быть готово обработать их с помощью стратегии like шаблон "Повторить".</span><span class="sxs-lookup"><span data-stu-id="80045-108">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="80045-109">Однако также может быть ситуациях, когда имеются ошибки из-за непредвиденных событий, которые может занять больше времени для исправления.</span><span class="sxs-lookup"><span data-stu-id="80045-109">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="80045-110">Эти ошибки варьируются от частичная потеря подключения до завершения сбоя службы.</span><span class="sxs-lookup"><span data-stu-id="80045-110">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="80045-111">В таких ситуациях может быть бессмысленным постоянно повторите операцию, маловероятно, что для успешного выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="80045-111">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="80045-112">Вместо этого приложения должен быть закодирован принимать сбой операции и обработки ошибки соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="80045-112">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="80045-113">Шаблон Размыкатель цепи имеет целей, отличных от шаблон повторения попытки.</span><span class="sxs-lookup"><span data-stu-id="80045-113">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="80045-114">Шаблон повторения попытки позволяет приложению повторить попытку операции в предположении, что операция в конечном итоге будет выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="80045-114">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="80045-115">Шаблон Размыкатель цепи не позволяет приложению выполняемая операция может привести к отказу.</span><span class="sxs-lookup"><span data-stu-id="80045-115">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="80045-116">Приложение может сочетать этих двух шаблонов с помощью шаблона "Повторить" для вызова операцию с использованием Размыкатель цепи.</span><span class="sxs-lookup"><span data-stu-id="80045-116">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="80045-117">Однако логику повторных попыток должно быть чувствительно к любые исключения, возвращенных Размыкатель цепи, и его следует отказаться от повторных попыток, если Размыкатель цепи указывает, что ошибка не является временной.</span><span class="sxs-lookup"><span data-stu-id="80045-117">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="80045-118">Реализация шаблона Размыкателя цепи с Polly</span><span class="sxs-lookup"><span data-stu-id="80045-118">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="80045-119">Как при реализации повторных попыток, рекомендуемым выключатели — воспользоваться преимуществом проверенные библиотек .NET, таких как Polly.</span><span class="sxs-lookup"><span data-stu-id="80045-119">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="80045-120">Приложение eShopOnContainers использует политики Polly Размыкатель цепи при реализации HTTP повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="80045-120">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="80045-121">На самом деле приложение применяет обе политики ResilientHttpClient служебный класс.</span><span class="sxs-lookup"><span data-stu-id="80045-121">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="80045-122">Каждый раз, когда вы используете объект типа ResilientHttpClient для HTTP-запросов (с eShopOnContainers), при применении обе эти политики, но можно добавить дополнительные политики слишком.</span><span class="sxs-lookup"><span data-stu-id="80045-122">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="80045-123">Единственным дополнением здесь код, используемый для повторных попыток вызовов HTTP-код, когда добавляются политики Размыкатель цепи список политик для использования, как показано в конце следующий код:</span><span class="sxs-lookup"><span data-stu-id="80045-123">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

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

<span data-ttu-id="80045-124">Код добавляет политику оболочки HTTP.</span><span class="sxs-lookup"><span data-stu-id="80045-124">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="80045-125">Определяет, политики Размыкатель цепи, которое открывается, если код определяет указанное число последовательных исключения (исключения в строке), как передаваемые в качестве параметра exceptionsAllowedBeforeBreaking (5 в данном случае).</span><span class="sxs-lookup"><span data-stu-id="80045-125">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="80045-126">После открытия канала HTTP-запросов не работают, но создается исключение.</span><span class="sxs-lookup"><span data-stu-id="80045-126">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="80045-127">Выключатели также следует использовать для перенаправления запросов в резервный инфраструктуры, если могут возникнуть проблемы с конкретного ресурса, который развертывается в среду, отличную от клиентского приложения или службы, который выполняет вызов HTTP.</span><span class="sxs-lookup"><span data-stu-id="80045-127">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="80045-128">Таким образом, если происходит сбой в центре обработки данных, влияющие только микрослужбами вашей серверной части, но не клиентских приложений, клиентские приложения может перенаправить резервной службы.</span><span class="sxs-lookup"><span data-stu-id="80045-128">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="80045-129">Планирует новую политику для автоматизации этой Polly [политики отработки отказа](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) сценария.</span><span class="sxs-lookup"><span data-stu-id="80045-129">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="80045-130">Конечно эти функции предназначены для случаев, где вы управляете отработки отказа с кодом .NET, сравните это с ее управляет автоматически автоматически Azure, с прозрачностью расположение.</span><span class="sxs-lookup"><span data-stu-id="80045-130">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="80045-131">С помощью служебного класса ResilientHttpClient из eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="80045-131">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="80045-132">Служебный класс ResilientHttpClient использовать так же, как использовать класс .NET HttpClient.</span><span class="sxs-lookup"><span data-stu-id="80045-132">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="80045-133">В следующем примере из веб-приложения MVC eShopOnContainers (класс OrderingService агента, используемых OrderController) объект ResilientHttpClient встраивается через параметр httpClient конструктора.</span><span class="sxs-lookup"><span data-stu-id="80045-133">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="80045-134">Затем объект используется для выполнения HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="80045-134">Then the object is used to perform HTTP requests.</span></span>

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

<span data-ttu-id="80045-135">Каждый раз, когда \_используется apiClient объект члена, внутренним образом использует класс-оболочку с Polly policiesؙ — политику повтора, Размыкатель цепи политики и другие политики, которые можно применить из коллекции политик Polly.</span><span class="sxs-lookup"><span data-stu-id="80045-135">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="80045-136">Тестирование повторных попыток в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="80045-136">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="80045-137">При каждом запуске eShopOnContainers решений в узле Docker, необходимо запустить несколько контейнеров.</span><span class="sxs-lookup"><span data-stu-id="80045-137">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="80045-138">Некоторые контейнеры происходит медленнее и инициализации, таких как SQL Server контейнер.</span><span class="sxs-lookup"><span data-stu-id="80045-138">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="80045-139">Это особенно важно при первом развертывании приложения eShopOnContainers в Docker, так как он должен настроить изображений и базы данных.</span><span class="sxs-lookup"><span data-stu-id="80045-139">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="80045-140">Тот факт, что некоторые контейнеры медленнее, чем другие может привести к остальным службам для изначально создания исключений HTTP, даже если вы настроите зависимости между контейнерами на запуск docker составления уровне, как описано в предыдущих разделах.</span><span class="sxs-lookup"><span data-stu-id="80045-140">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="80045-141">Те docker составления зависимости между контейнерами являются только на уровне процесса.</span><span class="sxs-lookup"><span data-stu-id="80045-141">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="80045-142">Возможно, запущен процесс точки входа контейнера, но SQL Server может не быть готова к запросам.</span><span class="sxs-lookup"><span data-stu-id="80045-142">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="80045-143">В результате могут появиться cascade ошибок и приложения можно получить исключение при попытке использовать этот конкретный контейнер.</span><span class="sxs-lookup"><span data-stu-id="80045-143">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="80045-144">Также возможны ошибки такого типа во время запуска, когда выполняется развертывание приложения в облако.</span><span class="sxs-lookup"><span data-stu-id="80045-144">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="80045-145">В этом случае orchestrators может перемещение контейнеры из одного узла или виртуальной Машины на другой (которое запускает новые экземпляры) при разделении количество контейнеров в узлах кластера.</span><span class="sxs-lookup"><span data-stu-id="80045-145">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="80045-146">С помощью шаблона "Повторить", который мы приведенных ранее — способ eShopOnContainers решает эту проблему.</span><span class="sxs-lookup"><span data-stu-id="80045-146">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="80045-147">Кроме того, он почему, при запуске решения, может появиться трассировки журналов и предупреждений, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="80045-147">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="80045-148">«**Попытка 1 реализуется с помощью элемента Polly RetryPolicy**из- за: System.Net.Http.HttpRequestException: произошла ошибка при отправке запроса.</span><span class="sxs-lookup"><span data-stu-id="80045-148">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="80045-149"> ---&gt;System.Net.Http.CurlException: Не удалось подключиться к серверу\\n в System.Net.Http.CurlHandler.ThrowIfCURLEError (ошибка CURLcode)\\n в \[... \].</span><span class="sxs-lookup"><span data-stu-id="80045-149"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="80045-150">Тестирование Размыкатель цепи в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="80045-150">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="80045-151">Можно открыть канал и проверить его с eShopOnContainers несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="80045-151">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="80045-152">Необходимо снизить допустимое число повторных попыток для 1 в политике Размыкатель цепи и повторного развертывания всего решения в Docker.</span><span class="sxs-lookup"><span data-stu-id="80045-152">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="80045-153">С одной повторной попытки есть риск, что HTTP-запрос завершится ошибкой во время развертывания, Размыкатель цепи будет открыт, и появляется сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="80045-153">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="80045-154">Другой вариант — использовать пользовательские по промежуточного слоя, реализованная в микрослужбу порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="80045-154">Another option is to use custom middleware that is implemented in the ordering microservice.</span></span> <span data-ttu-id="80045-155">При включении этого по промежуточного слоя, он перехватывает все HTTP-запросы и возвращает код состояния 500.</span><span class="sxs-lookup"><span data-stu-id="80045-155">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="80045-156">По промежуточного слоя можно включить, выполнив запрос GET к отказавшему URI следующего вида:</span><span class="sxs-lookup"><span data-stu-id="80045-156">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="80045-157">GET/сбой</span><span class="sxs-lookup"><span data-stu-id="80045-157">GET /failing</span></span>

<span data-ttu-id="80045-158">Этот запрос возвращает текущее состояние по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="80045-158">This request returns the current state of the middleware.</span></span> <span data-ttu-id="80045-159">Если включен по промежуточного слоя, запрос возвращает код состояния 500.</span><span class="sxs-lookup"><span data-stu-id="80045-159">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="80045-160">Если по промежуточного слоя отключена, нет ответа.</span><span class="sxs-lookup"><span data-stu-id="80045-160">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="80045-161">GET/сбой? включить</span><span class="sxs-lookup"><span data-stu-id="80045-161">GET /failing?enable</span></span>

<span data-ttu-id="80045-162">Этот запрос позволяет по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="80045-162">This request enables the middleware.</span></span>

-   <span data-ttu-id="80045-163">GET/сбой? отключение</span><span class="sxs-lookup"><span data-stu-id="80045-163">GET /failing?disable</span></span>

<span data-ttu-id="80045-164">Этот запрос отключает по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="80045-164">This request disables the middleware.</span></span>

<span data-ttu-id="80045-165">Для экземпляра после запуска приложения можно включить по промежуточного слоя, выполняющего запрос, используя следующий URI в любом браузере.</span><span class="sxs-lookup"><span data-stu-id="80045-165">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="80045-166">Обратите внимание, что упорядочивания микрослужбу использует порт 5102.</span><span class="sxs-lookup"><span data-stu-id="80045-166">Note that the ordering microservice uses port 5102.</span></span>

<span data-ttu-id="80045-167">http://localhost:5102 / сбой? включить</span><span class="sxs-lookup"><span data-stu-id="80045-167">http://localhost:5102/failing?enable</span></span>

<span data-ttu-id="80045-168">Затем можно проверить состояние с помощью URI [http://localhost:5102 / сбой](http://localhost:5100/failing), как показано на рисунке 10-4.</span><span class="sxs-lookup"><span data-stu-id="80045-168">You can then check the status using the URI [http://localhost:5102/failing](http://localhost:5100/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="80045-169">**На рис. 10-4**.</span><span class="sxs-lookup"><span data-stu-id="80045-169">**Figure 10-4**.</span></span> <span data-ttu-id="80045-170">Имитация неисправности с помощью по промежуточного слоя ASP.NET</span><span class="sxs-lookup"><span data-stu-id="80045-170">Simulating a failure with ASP.NET middleware</span></span>

<span data-ttu-id="80045-171">На этом этапе упорядочения микрослужбу ответ с кодом состояния 500, при каждом вызове выполнять соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="80045-171">At this point, the ordering microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="80045-172">После запуска по промежуточного слоя, попробуйте сделать заказ из веб-приложения MVC.</span><span class="sxs-lookup"><span data-stu-id="80045-172">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="80045-173">Так как произошел сбой запроса, канал будет открыт.</span><span class="sxs-lookup"><span data-stu-id="80045-173">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="80045-174">В следующем примере можно увидеть, что веб-приложение MVC имеет catch блока в логику для размещения заказа.</span><span class="sxs-lookup"><span data-stu-id="80045-174">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="80045-175">Если код перехватывает исключение открытия канала, показывает пользователь понятное сообщение, уведомляющее о ожидания.</span><span class="sxs-lookup"><span data-stu-id="80045-175">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

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

<span data-ttu-id="80045-176">Ниже приведена сводка.</span><span class="sxs-lookup"><span data-stu-id="80045-176">Here’s a summary.</span></span> <span data-ttu-id="80045-177">Политика повтора пытается несколько раз, чтобы сделать HTTP-запрос и возвращает ошибки HTTP.</span><span class="sxs-lookup"><span data-stu-id="80045-177">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="80045-178">Когда число попыток достигает максимальное число, заданное для политики Размыкатель цепи (в данном случае 5), приложение выдает BrokenCircuitException.</span><span class="sxs-lookup"><span data-stu-id="80045-178">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="80045-179">Результатом является понятное сообщение, как показано на рисунке 10-5.</span><span class="sxs-lookup"><span data-stu-id="80045-179">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="80045-180">**На рис. 10-5**.</span><span class="sxs-lookup"><span data-stu-id="80045-180">**Figure 10-5**.</span></span> <span data-ttu-id="80045-181">Размыкатель цепи, возвращается ошибка пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="80045-181">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="80045-182">Можно реализовать другой логикой, когда для открытия канала.</span><span class="sxs-lookup"><span data-stu-id="80045-182">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="80045-183">Или при наличии резервной центра обработки данных или избыточные серверную систему, можно попробовать HTTP-запрос к другой микрослужбу серверной части.</span><span class="sxs-lookup"><span data-stu-id="80045-183">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="80045-184">Наконец другая возможность CircuitBreakerPolicy является использование изолировать (который заставляет открытым и оставляет открытым канала) и сброса (которая закрывает снова).</span><span class="sxs-lookup"><span data-stu-id="80045-184">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="80045-185">Они используются для построения программы конечной точки HTTP, вызывающий изолировать и сброс непосредственно в политике.</span><span class="sxs-lookup"><span data-stu-id="80045-185">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="80045-186">Такой конечной точки HTTP также может использоваться, подходящим образом защищены в рабочей среде для временно изоляции подчиненных системы, например, если вы хотите обновить его.</span><span class="sxs-lookup"><span data-stu-id="80045-186">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="80045-187">Или он может быть вручную, чтобы защитить подчиненных систему, которую предполагается быть сброса канала.</span><span class="sxs-lookup"><span data-stu-id="80045-187">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="80045-188">Добавление стратегии флуктуации политику повтора</span><span class="sxs-lookup"><span data-stu-id="80045-188">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="80045-189">Регулярные политику повторов может повлиять на системы в случаях, масштабируемость и высокий уровень параллелизма, а также в разделе большого количества состязаний данных.</span><span class="sxs-lookup"><span data-stu-id="80045-189">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="80045-190">Чтобы преодолеть пиков аналогичные повторных попыток, поступающих от большого числа клиентов в случае частичного простои, хорошим решением проблемы является добавление стратегии флуктуации алгоритм или политику повтора.</span><span class="sxs-lookup"><span data-stu-id="80045-190">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="80045-191">Это может повысить общую производительность системы начала до конца, добавив случайности экспоненциальное увеличение задержки.</span><span class="sxs-lookup"><span data-stu-id="80045-191">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="80045-192">В этом случае пиковых при возникновении неисправности.</span><span class="sxs-lookup"><span data-stu-id="80045-192">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="80045-193">При использовании Polly код для реализации флуктуации может выглядеть как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="80045-193">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="80045-194">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="80045-194">Additional resources</span></span>

-   <span data-ttu-id="80045-195">**Повторите шаблон**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="80045-195">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="80045-196">**Устойчивость подключения** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="80045-196">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="80045-197">**Polly** (устойчивость .NET и обработки ошибок динамической библиотеки) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="80045-197">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="80045-198">**Размыкатель цепи шаблон**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="80045-198">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="80045-199">**Марк Brooker. Флуктуации: Что лучше неупорядоченных** https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="80045-199">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="80045-200">[Предыдущие] (implement-http-call-retries-exponential-backoff-polly.md) [Далее] (health.md монитор приложения)</span><span class="sxs-lookup"><span data-stu-id="80045-200">[Previous] (implement-http-call-retries-exponential-backoff-polly.md) [Next] (monitor-app-health.md)</span></span>
