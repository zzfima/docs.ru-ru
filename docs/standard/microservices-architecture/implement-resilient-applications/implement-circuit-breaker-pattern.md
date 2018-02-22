---
title: "Реализация шаблона размыкателя цепи"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация шаблона размыкателя цепи"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5d7db6899068f84f9165022cfbf17767a75e7db9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="27a78-104">Реализация шаблона размыкателя цепи</span><span class="sxs-lookup"><span data-stu-id="27a78-104">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="27a78-105">Как отмечалось ранее, следует реализовать обработку сбоев, на восстановление после которых может требоваться неопределенное количество времени, например, при попытке подключиться к удаленной службе или ресурсу.</span><span class="sxs-lookup"><span data-stu-id="27a78-105">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="27a78-106">Обработка подобных сбоев может повысить стабильность работы и отказоустойчивость приложения.</span><span class="sxs-lookup"><span data-stu-id="27a78-106">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="27a78-107">В распределенной среде вызовы удаленных ресурсов и служб могут завершаться сбоем из-за временных состояний, таких как медленные сетевые подключения, истечение времени ожидания или временная недоступность ресурсов.</span><span class="sxs-lookup"><span data-stu-id="27a78-107">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="27a78-108">Такие состояния обычно разрешаются через некоторое время. В надежном облачном приложении должна быть предусмотрена их обработка с помощью какого-либо механизма, например шаблона повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="27a78-108">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="27a78-109">Однако возможны также ситуации, когда сбои происходят из-за непредвиденных событий и на их устранение может потребоваться гораздо больше времени.</span><span class="sxs-lookup"><span data-stu-id="27a78-109">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="27a78-110">Такие сбои могут быть различной степени серьезности: от частичной потери соединения до полного отказа службы.</span><span class="sxs-lookup"><span data-stu-id="27a78-110">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="27a78-111">В таких случаях повторные попытки выполнить операцию, успешное завершение которой маловероятно, могут быть бессмысленны.</span><span class="sxs-lookup"><span data-stu-id="27a78-111">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="27a78-112">Вместо этого в коде следует реализовать возможность определения операции как неудавшейся и соответствующей обработки сбоя.</span><span class="sxs-lookup"><span data-stu-id="27a78-112">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="27a78-113">Шаблон размыкателя цепи по своему назначению отличается от шаблона повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="27a78-113">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="27a78-114">Шаблон повторных попыток позволяет приложению повторять операцию, исходя из предположения о том, что она в конечном итоге завершится успешно.</span><span class="sxs-lookup"><span data-stu-id="27a78-114">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="27a78-115">Шаблон размыкателя цепи предотвращает выполнение операции, которая, скорее всего, завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="27a78-115">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="27a78-116">Эти два шаблона могут сочетаться в приложении, при этом шаблон повторных попыток вызывает операцию через шаблон размыкателя цепи.</span><span class="sxs-lookup"><span data-stu-id="27a78-116">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="27a78-117">Однако логика повторных попыток должна реагировать на исключения, возвращаемые размыкателем цепи, и прекращать попытки, если размыкатель цепи сообщает о том, что ошибка не является временной.</span><span class="sxs-lookup"><span data-stu-id="27a78-117">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="27a78-118">Реализация шаблона размыкателя цепи с помощью библиотеки Polly</span><span class="sxs-lookup"><span data-stu-id="27a78-118">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="27a78-119">Как и при реализации повторных попыток, рекомендуемым подходом в случае с размыкателями цепи является использование проверенных библиотек .NET, таких как Polly.</span><span class="sxs-lookup"><span data-stu-id="27a78-119">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="27a78-120">Приложение eShopOnContainers использует политику размыкателя цепи Polly при реализации повторных попыток HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="27a78-120">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="27a78-121">Фактически приложение применяет обе политики к служебному классу ResilientHttpClient.</span><span class="sxs-lookup"><span data-stu-id="27a78-121">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="27a78-122">Каждый раз при использовании объекта типа ResilientHttpClient для HTTP-запросов (из eShopOnContainers) вы применяете обе эти политики, однако можно добавить и другие политики.</span><span class="sxs-lookup"><span data-stu-id="27a78-122">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="27a78-123">Единственным дополнением к коду, используемому для повторных попыток вызовов по HTTP, является фрагмент, в котором политика размыкателя цепи добавляется в список применяемых политик, как показано в конце следующего примера:</span><span class="sxs-lookup"><span data-stu-id="27a78-123">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

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

<span data-ttu-id="27a78-124">В этом коде политика добавляется в оболочку HTTP.</span><span class="sxs-lookup"><span data-stu-id="27a78-124">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="27a78-125">Эта политика определяет размыкатель цепи, который открывается при обнаружении кодом указанного числа последовательных (идущих подряд) исключений, передаваемого в параметре exceptionsAllowedBeforeBreaking (в этом случае 5).</span><span class="sxs-lookup"><span data-stu-id="27a78-125">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="27a78-126">Когда цепь разомкнута, HTTP-запросы не выполняются и вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="27a78-126">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="27a78-127">Размыкатели цепи следует также использовать для перенаправления запросов в резервную инфраструктуру, если возможны проблемы с определенным ресурсом, который развернут в среде, отличной от той, где размещается клиентское приложение или служба, выполняющие вызов по HTTP.</span><span class="sxs-lookup"><span data-stu-id="27a78-127">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="27a78-128">Благодаря этому при сбоях в центре обработки данных, влияющих только на серверные микрослужбы, но не на клиентские приложения, клиентские приложения могут перенаправлять запросы в резервные службы.</span><span class="sxs-lookup"><span data-stu-id="27a78-128">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="27a78-129">В библиотеке Polly планируется добавить новую политику для автоматизации применения такой [политики отработки отказа](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).</span><span class="sxs-lookup"><span data-stu-id="27a78-129">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="27a78-130">Конечно, все эти возможности предназначены для случаев, когда управление отработкой отказа осуществляется в коде .NET, а не платформой Azure независимо от расположения.</span><span class="sxs-lookup"><span data-stu-id="27a78-130">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="27a78-131">Использование служебного класса ResilientHttpClient из eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="27a78-131">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="27a78-132">Служебный класс ResilientHttpClient используется аналогично тому, как используется класс .NET HttpClient.</span><span class="sxs-lookup"><span data-stu-id="27a78-132">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="27a78-133">В приведенном ниже примере из веб-приложения MVC eShopOnContainers (класс агента OrderingService, используемый контроллером OrderController) объект ResilientHttpClient внедряется посредством параметра httpClient конструктора.</span><span class="sxs-lookup"><span data-stu-id="27a78-133">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="27a78-134">Затем этот объект применяется для выполнения HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="27a78-134">Then the object is used to perform HTTP requests.</span></span>

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

<span data-ttu-id="27a78-135">Каждый раз при использовании объекта члена \_apiClient в нем используется класс-оболочка с политиками Polly: политикой повторных попыток, политикой размыкателя цепи и другими политиками из коллекции политик Polly, которые может потребоваться применить.</span><span class="sxs-lookup"><span data-stu-id="27a78-135">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="27a78-136">Тестирование повторных попыток в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="27a78-136">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="27a78-137">При запуске решения eShopOnContainers в узле Docker должно запускаться несколько контейнеров.</span><span class="sxs-lookup"><span data-stu-id="27a78-137">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="27a78-138">Некоторые контейнеры, например контейнер SQL Server, запускаются и инициализируются медленнее, чем другие.</span><span class="sxs-lookup"><span data-stu-id="27a78-138">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="27a78-139">Особенно очевидно это проявляется при первом развертывании приложения eShopOnContainers в Docker, так как при этом должны настраиваться образы и база данных.</span><span class="sxs-lookup"><span data-stu-id="27a78-139">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="27a78-140">Из-за более медленного запуска некоторых контейнеров остальные службы могут изначально вызывать исключения HTTP, даже если вы настроили зависимости между контейнерами на уровне docker-compose, как было описано в предыдущих разделах.</span><span class="sxs-lookup"><span data-stu-id="27a78-140">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="27a78-141">Зависимости docker-compose между контейнерами существуют на уровне процессов.</span><span class="sxs-lookup"><span data-stu-id="27a78-141">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="27a78-142">Процесс точки входа в контейнер может быть запущен, но сервер SQL Server может быть не готов принимать запросы.</span><span class="sxs-lookup"><span data-stu-id="27a78-142">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="27a78-143">В результате может происходить непрерывный ряд ошибок, и в приложении может возникнуть исключение при попытке использовать данный контейнер.</span><span class="sxs-lookup"><span data-stu-id="27a78-143">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="27a78-144">Подобные ошибки могут также наблюдаться при запуске приложения, развернутого в облаке.</span><span class="sxs-lookup"><span data-stu-id="27a78-144">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="27a78-145">В этом случае оркестраторы могут перемещать контейнеры из одного узла (или виртуальной машины) в другой (запуская новые экземпляры) в процессе балансировки числа контейнеров между узлами кластера.</span><span class="sxs-lookup"><span data-stu-id="27a78-145">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="27a78-146">В eShopOnContainers эта проблема решается с помощью шаблона повторных попыток, который был продемонстрирован ранее.</span><span class="sxs-lookup"><span data-stu-id="27a78-146">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="27a78-147">По этой же причине при запуске решения могут появляться сообщения в журнале трассировки и предупреждения, похожие на следующее:</span><span class="sxs-lookup"><span data-stu-id="27a78-147">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="27a78-148">"**Повторная попытка 1, реализованная с помощью политики RetryPolicy библиотеки Polly** из-за System.Net.Http.HttpRequestException. Произошла ошибка при отправке запроса.</span><span class="sxs-lookup"><span data-stu-id="27a78-148">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="27a78-149"> ---&gt; System.Net.Http.CurlException. Не удалось подключиться к серверу\\ в System.Net.Http.CurlHandler.ThrowIfCURLEError(ошибка CURLcode)\\ в \[...\].</span><span class="sxs-lookup"><span data-stu-id="27a78-149"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="27a78-150">Тестирование размыкателя цепи в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="27a78-150">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="27a78-151">Есть несколько способов разомкнуть цепь и протестировать ее в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="27a78-151">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="27a78-152">Один из вариантов — уменьшить разрешенное число повторных попыток до 1 в политике размыкателя цепи и повторно развернуть все решение в Docker.</span><span class="sxs-lookup"><span data-stu-id="27a78-152">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="27a78-153">При одной повторной попытке высока вероятность того, что HTTP-запрос завершится сбоем во время развертывания, размыкатель цепи откроется и произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="27a78-153">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="27a78-154">Другой вариант — использовать пользовательское ПО промежуточного слоя, реализованное в микрослужбе `Basket`.</span><span class="sxs-lookup"><span data-stu-id="27a78-154">Another option is to use custom middleware that is implemented in the `Basket` microservice.</span></span> <span data-ttu-id="27a78-155">При его включении оно перехватывает все HTTP-запросы и возвращает код состояния 500.</span><span class="sxs-lookup"><span data-stu-id="27a78-155">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="27a78-156">Чтобы включить ПО промежуточного слоя, можно выполнить запрос GET к сбойному универсальному коду ресурса (URI), например, следующему:</span><span class="sxs-lookup"><span data-stu-id="27a78-156">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="27a78-157">GET /failing</span><span class="sxs-lookup"><span data-stu-id="27a78-157">GET /failing</span></span>

<span data-ttu-id="27a78-158">Этот запрос возвращает текущее состояние ПО промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="27a78-158">This request returns the current state of the middleware.</span></span> <span data-ttu-id="27a78-159">Если оно включено, запрос возвращает код состояния 500.</span><span class="sxs-lookup"><span data-stu-id="27a78-159">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="27a78-160">Если оно отключено, ответа нет.</span><span class="sxs-lookup"><span data-stu-id="27a78-160">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="27a78-161">GET /failing?enable</span><span class="sxs-lookup"><span data-stu-id="27a78-161">GET /failing?enable</span></span>

<span data-ttu-id="27a78-162">Этот запрос включает ПО промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="27a78-162">This request enables the middleware.</span></span>

-   <span data-ttu-id="27a78-163">GET /failing?disable</span><span class="sxs-lookup"><span data-stu-id="27a78-163">GET /failing?disable</span></span>

<span data-ttu-id="27a78-164">Этот запрос отключает ПО промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="27a78-164">This request disables the middleware.</span></span>

<span data-ttu-id="27a78-165">Например, после запуска приложения вы можете включить ПО промежуточного слоя, выполнив запрос к указанному ниже коду URI в любом браузере.</span><span class="sxs-lookup"><span data-stu-id="27a78-165">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="27a78-166">Обратите внимание на то, что микрослужба размещения заказов использует порт 5103.</span><span class="sxs-lookup"><span data-stu-id="27a78-166">Note that the ordering microservice uses port 5103.</span></span>

<span data-ttu-id="27a78-167">http://localhost:5103/failing?enable</span><span class="sxs-lookup"><span data-stu-id="27a78-167">http://localhost:5103/failing?enable</span></span>

<span data-ttu-id="27a78-168">После этого состояние можно проверить, используя код URI [http://localhost:5103/failing](http://localhost:5103/failing), как показано на рисунке 10-4.</span><span class="sxs-lookup"><span data-stu-id="27a78-168">You can then check the status using the URI [http://localhost:5103/failing](http://localhost:5103/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="27a78-169">**Рис. 10-4**.</span><span class="sxs-lookup"><span data-stu-id="27a78-169">**Figure 10-4**.</span></span> <span data-ttu-id="27a78-170">Проверка состояния ПО промежуточного слоя ASP.NET (в этом случае отключено)</span><span class="sxs-lookup"><span data-stu-id="27a78-170">Checking the state of the “Failing” ASP.NET middleware – In this case, disabled.</span></span> 

<span data-ttu-id="27a78-171">На этом этапе микрослужба Basket возвращает код состояния 500 при каждом вызове.</span><span class="sxs-lookup"><span data-stu-id="27a78-171">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="27a78-172">Когда ПО промежуточного слоя будет запущено, вы можете попытаться сделать заказ в веб-приложении MVC.</span><span class="sxs-lookup"><span data-stu-id="27a78-172">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="27a78-173">Так как запрос завершается сбоем, цепь размыкается.</span><span class="sxs-lookup"><span data-stu-id="27a78-173">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="27a78-174">В приведенном ниже примере можно увидеть, что в веб-приложении MVC есть блок catch в логике размещения заказа.</span><span class="sxs-lookup"><span data-stu-id="27a78-174">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="27a78-175">Если код перехватывает исключение размыкания цепи, он выводит сообщение с просьбой к пользователю подождать.</span><span class="sxs-lookup"><span data-stu-id="27a78-175">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

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

<span data-ttu-id="27a78-176">Вкратце рассмотрим, что происходит.</span><span class="sxs-lookup"><span data-stu-id="27a78-176">Here’s a summary.</span></span> <span data-ttu-id="27a78-177">Политика повторных попыток несколько раз пытается выполнить HTTP-запрос и получает ошибки HTTP.</span><span class="sxs-lookup"><span data-stu-id="27a78-177">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="27a78-178">Когда число повторных попыток достигает максимального значения, заданного для политики размыкателя цепи (в этом случае 5), приложение вызывает исключение BrokenCircuitException.</span><span class="sxs-lookup"><span data-stu-id="27a78-178">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="27a78-179">В результате выводится понятное сообщение для пользователя, как показано на рисунке 10-5.</span><span class="sxs-lookup"><span data-stu-id="27a78-179">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="27a78-180">**Рис. 10-5**.</span><span class="sxs-lookup"><span data-stu-id="27a78-180">**Figure 10-5**.</span></span> <span data-ttu-id="27a78-181">Размыкатель цепи возвращает ошибку в пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="27a78-181">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="27a78-182">Вы можете реализовать другую логику размыкания цепи.</span><span class="sxs-lookup"><span data-stu-id="27a78-182">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="27a78-183">Кроме того, можно пытаться выполнять HTTP-запросы к другой серверной микрослужбе, если имеется резервный центр обработки данных или избыточная серверная система.</span><span class="sxs-lookup"><span data-stu-id="27a78-183">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="27a78-184">Наконец, еще одной возможностью CircuitBreakerPolicy является использование методов Isolate (размыкает цепь и сохраняет ее в таком состоянии) и Reset (снова замыкает цепь).</span><span class="sxs-lookup"><span data-stu-id="27a78-184">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="27a78-185">Таким образом, можно создать служебную конечную точку HTTP, которая напрямую вызывает методы Isolate и Reset политики.</span><span class="sxs-lookup"><span data-stu-id="27a78-185">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="27a78-186">Такую конечную точку HTTP с надлежащей защитой можно также использовать в рабочей среде для временной изоляции подчиненной системы, например, если ее необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="27a78-186">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="27a78-187">Кроме того, с ее помощью можно размыкать цепь вручную для защиты подчиненной системы, если есть подозрения на ее неисправность.</span><span class="sxs-lookup"><span data-stu-id="27a78-187">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="27a78-188">Добавление стратегии в отношении колебания задержки в политику повтора</span><span class="sxs-lookup"><span data-stu-id="27a78-188">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="27a78-189">Обычная политика повтора может влиять на работу системы в случае высокого уровня параллелизма и масштабируемости, а также в условиях интенсивного состязания за ресурсы.</span><span class="sxs-lookup"><span data-stu-id="27a78-189">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="27a78-190">Чтобы решить проблему с большим числом повторных запросов, поступающих от множества клиентов в случае частичного отказа системы, можно добавить стратегию в отношении колебания задержки в алгоритм или политику повтора.</span><span class="sxs-lookup"><span data-stu-id="27a78-190">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="27a78-191">Это может повысить общую производительность всей системы благодаря тому, что экспоненциальная задержка становится более случайной.</span><span class="sxs-lookup"><span data-stu-id="27a78-191">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="27a78-192">При возникновении проблем пики размываются.</span><span class="sxs-lookup"><span data-stu-id="27a78-192">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="27a78-193">При использовании библиотеки Polly код для реализации колебания задержки может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="27a78-193">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="27a78-194">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="27a78-194">Additional resources</span></span>

-   <span data-ttu-id="27a78-195">**Шаблон повторов**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="27a78-195">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="27a78-196">**Устойчивость подключений** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="27a78-196">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="27a78-197">**Polly** (библиотека для обеспечения отказоустойчивости .NET и обработки временных сбоев) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="27a78-197">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="27a78-198">**Шаблон автоматического выключения**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="27a78-198">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="27a78-199">**Марк Брукер (Marc Brooker). Jitter: Making Things Better With Randomness (Колебание задержки: более стабильная работа благодаря элементу случайности)** https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="27a78-199">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="27a78-200">[Назад] (implement-http-call-retries-exponential-backoff-polly.md) [Далее] (monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="27a78-200">[Previous] (implement-http-call-retries-exponential-backoff-polly.md) [Next] (monitor-app-health.md)</span></span>
