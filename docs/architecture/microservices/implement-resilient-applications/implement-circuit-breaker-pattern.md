---
title: Реализация шаблона размыкателя цепи
description: Узнайте, как реализовать шаблон размыкателя сети в качестве дополнительной системы для повторных HTTP-запросов.
ms.date: 03/03/2020
ms.openlocfilehash: a79c6fcca1e29f3c30d697cb369060d59a72c121
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847249"
---
# <a name="implement-the-circuit-breaker-pattern"></a><span data-ttu-id="117d2-103">Реализация шаблона размыкателя цепи</span><span class="sxs-lookup"><span data-stu-id="117d2-103">Implement the Circuit Breaker pattern</span></span>

<span data-ttu-id="117d2-104">Как отмечалось ранее, следует реализовать обработку сбоев, на восстановление после которых может требоваться неопределенное количество времени, например, при попытке подключиться к удаленной службе или ресурсу.</span><span class="sxs-lookup"><span data-stu-id="117d2-104">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="117d2-105">Обработка подобных сбоев может повысить стабильность работы и отказоустойчивость приложения.</span><span class="sxs-lookup"><span data-stu-id="117d2-105">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="117d2-106">В распределенной среде вызовы удаленных ресурсов и служб могут завершаться сбоем из-за временных состояний, таких как медленные сетевые подключения, истечение времени ожидания, медленный отклик ресурсов или временная недоступность ресурсов.</span><span class="sxs-lookup"><span data-stu-id="117d2-106">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are responding slowly or are temporarily unavailable.</span></span> <span data-ttu-id="117d2-107">Такие состояния обычно разрешаются через некоторое время. В надежном облачном приложении должна быть предусмотрена их обработка с помощью какого-либо механизма, например шаблона повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="117d2-107">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the "Retry pattern".</span></span>

<span data-ttu-id="117d2-108">Однако возможны также ситуации, когда сбои происходят из-за непредвиденных событий и на их устранение может потребоваться гораздо больше времени.</span><span class="sxs-lookup"><span data-stu-id="117d2-108">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="117d2-109">Такие сбои могут быть различной степени серьезности: от частичной потери соединения до полного отказа службы.</span><span class="sxs-lookup"><span data-stu-id="117d2-109">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="117d2-110">В таких случаях повторные попытки выполнить операцию, успешное завершение которой маловероятно, могут быть бессмысленны.</span><span class="sxs-lookup"><span data-stu-id="117d2-110">In these situations, it might be pointless for an application to continually retry an operation that's unlikely to succeed.</span></span>

<span data-ttu-id="117d2-111">Вместо этого в коде следует реализовать возможность определения операции как неудавшейся и соответствующей обработки сбоя.</span><span class="sxs-lookup"><span data-stu-id="117d2-111">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="117d2-112">Бездумное использование повторных HTTP-запросов может привести к атаке типа "отказ в обслуживании" ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) в вашем программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="117d2-112">Using Http retries carelessly could result in creating a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack within your own software.</span></span> <span data-ttu-id="117d2-113">Если микрослужба завершается сбоем или работает медленно, несколько клиентов могут многократно повторять невыполненные запросы.</span><span class="sxs-lookup"><span data-stu-id="117d2-113">As a microservice fails or performs slowly, multiple clients might repeatedly retry failed requests.</span></span> <span data-ttu-id="117d2-114">Существует риск значительного увеличения трафика, адресованного неработающей службе.</span><span class="sxs-lookup"><span data-stu-id="117d2-114">That creates a dangerous risk of exponentially increasing traffic targeted at the failing service.</span></span>

<span data-ttu-id="117d2-115">Таким образом, вам требуется некий защитный барьер, который будет останавливать повторные запросы, если в них нет смысла.</span><span class="sxs-lookup"><span data-stu-id="117d2-115">Therefore, you need some kind of defense barrier so that excessive requests stop when it isn't worth to keep trying.</span></span> <span data-ttu-id="117d2-116">Этим защитным барьером и является размыкатель цепи.</span><span class="sxs-lookup"><span data-stu-id="117d2-116">That defense barrier is precisely the circuit breaker.</span></span>

<span data-ttu-id="117d2-117">Шаблон размыкателя цепи по своему назначению отличается от шаблона повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="117d2-117">The Circuit Breaker pattern has a different purpose than the "Retry pattern".</span></span> <span data-ttu-id="117d2-118">Шаблон повторных попыток позволяет приложению повторять операцию, исходя из предположения о том, что она в конечном итоге завершится успешно.</span><span class="sxs-lookup"><span data-stu-id="117d2-118">The "Retry pattern" enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="117d2-119">Шаблон размыкателя цепи предотвращает выполнение операции, которая, скорее всего, завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="117d2-119">The Circuit Breaker pattern prevents an application from performing an operation that's likely to fail.</span></span> <span data-ttu-id="117d2-120">Эти два шаблона могут сочетаться в приложении.</span><span class="sxs-lookup"><span data-stu-id="117d2-120">An application can combine these two patterns.</span></span> <span data-ttu-id="117d2-121">Однако логика повторных попыток должна реагировать на исключения, возвращаемые размыкателем цепи, и прекращать попытки, если размыкатель цепи сообщает о том, что ошибка не является временной.</span><span class="sxs-lookup"><span data-stu-id="117d2-121">However, the retry logic should be sensitive to any exception returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implement-circuit-breaker-pattern-with-ihttpclientfactory-and-polly"></a><span data-ttu-id="117d2-122">Реализация шаблона размыкателя цепи с помощью `IHttpClientFactory` и Polly</span><span class="sxs-lookup"><span data-stu-id="117d2-122">Implement Circuit Breaker pattern with `IHttpClientFactory` and Polly</span></span>

<span data-ttu-id="117d2-123">Как и при реализации повторных попыток, рекомендуемым подходом в случае с размыкателями цепи является использование проверенных библиотек .NET, таких как Polly, и преимуществ интеграции ее платформенной функциональности с `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="117d2-123">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly and its native integration with `IHttpClientFactory`.</span></span>

<span data-ttu-id="117d2-124">Добавление политики размыкателя цепи в исходящий конвейер ПО промежуточного слоя `IHttpClientFactory` сводится к добавлению одного фрагмента кода к тому, что у вас уже есть при использовании `IHttpClientFactory`.</span><span class="sxs-lookup"><span data-stu-id="117d2-124">Adding a circuit breaker policy into your `IHttpClientFactory` outgoing middleware pipeline is as simple as adding a single incremental piece of code to what you already have when using `IHttpClientFactory`.</span></span>

<span data-ttu-id="117d2-125">Единственным дополнением к коду, используемому для повторных попыток вызовов по HTTP, является фрагмент, в котором политика размыкателя цепи добавляется в список применяемых политик, как показано в конце следующего примера добавочного кода в методе ConfigureServices().</span><span class="sxs-lookup"><span data-stu-id="117d2-125">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown in the following incremental code, part of the ConfigureServices() method.</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Sample. Default lifetime is 2 minutes
        .AddHttpMessageHandler<HttpClientAuthorizationDelegatingHandler>()
        .AddPolicyHandler(GetRetryPolicy())
        .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="117d2-126">Метод `AddPolicyHandler()` добавляет политики для объектов `HttpClient`, которые вы будете использовать.</span><span class="sxs-lookup"><span data-stu-id="117d2-126">The `AddPolicyHandler()` method is what adds policies to the `HttpClient` objects you'll use.</span></span> <span data-ttu-id="117d2-127">В этом случае он добавляет политику Polly для размыкателя цепи.</span><span class="sxs-lookup"><span data-stu-id="117d2-127">In this case, it's adding a Polly policy for a circuit breaker.</span></span>

<span data-ttu-id="117d2-128">Для реализации более модульного подхода политику размыкателя цепи можно определить в отдельном методе `GetCircuitBreakerPolicy()`, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="117d2-128">To have a more modular approach, the Circuit Breaker Policy is defined in a separate method called `GetCircuitBreakerPolicy()`, as shown in the following code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetCircuitBreakerPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .CircuitBreakerAsync(5, TimeSpan.FromSeconds(30));
}
```

<span data-ttu-id="117d2-129">В приведенном выше примере кода политика размыкателя цепи настроена таким образом, что прерывает или размыкает цепь после пяти последовательных попыток при повторной отправке HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="117d2-129">In the code example above, the circuit breaker policy is configured so it breaks or opens the circuit when there have been five consecutive faults when retrying the Http requests.</span></span> <span data-ttu-id="117d2-130">Если это произойдет, цепь разомкнется на 30 секунд: в этот период вызовы не будут размещаться, а будут немедленно завершаться размыкателем цепи.</span><span class="sxs-lookup"><span data-stu-id="117d2-130">When that happens, the circuit will break for 30 seconds: in that period, calls will be failed immediately by the circuit-breaker rather than actually be placed.</span></span>  <span data-ttu-id="117d2-131">Политика автоматически интерпретирует [соответствующие исключения и коды состояния HTTP](/aspnet/core/fundamentals/http-requests#handle-transient-faults) как ошибки.</span><span class="sxs-lookup"><span data-stu-id="117d2-131">The policy automatically interprets [relevant exceptions and HTTP status codes](/aspnet/core/fundamentals/http-requests#handle-transient-faults) as faults.</span></span>  

<span data-ttu-id="117d2-132">Размыкатели цепи следует также использовать для перенаправления запросов в резервную инфраструктуру, если возникали проблемы с определенным ресурсом, который развернут в среде, отличной от той, где размещается клиентское приложение или служба, выполняющие вызовы HTTP.</span><span class="sxs-lookup"><span data-stu-id="117d2-132">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you had issues in a particular resource that's deployed in a different environment than the client application or service that's performing the HTTP call.</span></span> <span data-ttu-id="117d2-133">Таким образом, при сбоях в центре обработки данных, влияющих только на серверные микрослужбы, а не на клиентские приложения, клиентские приложения могут перенаправлять запросы в резервные службы.</span><span class="sxs-lookup"><span data-stu-id="117d2-133">That way, if there's an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="117d2-134">В библиотеке Polly планируется добавить новую политику для автоматизации применения такой [политики отработки отказа](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).</span><span class="sxs-lookup"><span data-stu-id="117d2-134">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="117d2-135">Все эти возможности предназначены для случаев, когда управление отработкой отказа осуществляется в коде .NET, а не автоматически платформой Azure независимо от расположения.</span><span class="sxs-lookup"><span data-stu-id="117d2-135">All those features are for cases where you're managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

<span data-ttu-id="117d2-136">С точки зрения применения, при использовании HttpClient не нужно добавлять ничего нового, так как код будет таким же, как и при использовании `HttpClient` с `IHttpClientFactory`, как показано в предыдущих разделах.</span><span class="sxs-lookup"><span data-stu-id="117d2-136">From a usage point of view, when using HttpClient, there’s no need to add anything new here because the code is the same than when using `HttpClient` with `IHttpClientFactory`, as shown in previous sections.</span></span>

## <a name="test-http-retries-and-circuit-breakers-in-eshoponcontainers"></a><span data-ttu-id="117d2-137">Тестирование повторных HTTP-запросов и размыкателей цепи в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="117d2-137">Test Http retries and circuit breakers in eShopOnContainers</span></span>

<span data-ttu-id="117d2-138">При запуске решения eShopOnContainers в узле Docker должно запускаться несколько контейнеров.</span><span class="sxs-lookup"><span data-stu-id="117d2-138">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="117d2-139">Некоторые контейнеры, например контейнер SQL Server, запускаются и инициализируются медленнее, чем другие.</span><span class="sxs-lookup"><span data-stu-id="117d2-139">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="117d2-140">Это особенно проявляется при первом развертывании приложения eShopOnContainers в Docker, так как при этом должны настраиваться образы и база данных.</span><span class="sxs-lookup"><span data-stu-id="117d2-140">This is especially true the first time you deploy the eShopOnContainers application into Docker because it needs to set up the images and the database.</span></span> <span data-ttu-id="117d2-141">Из-за более медленного запуска некоторых контейнеров остальные службы могут изначально вызывать исключения HTTP, даже если вы настроили зависимости между контейнерами на уровне docker-compose, как было описано в предыдущих разделах.</span><span class="sxs-lookup"><span data-stu-id="117d2-141">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="117d2-142">Зависимости docker-compose между контейнерами существуют на уровне процессов.</span><span class="sxs-lookup"><span data-stu-id="117d2-142">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="117d2-143">Процесс точки входа в контейнер может быть запущен, но сервер SQL Server может быть не готов принимать запросы.</span><span class="sxs-lookup"><span data-stu-id="117d2-143">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="117d2-144">В результате может происходить непрерывный ряд ошибок, и в приложении может возникнуть исключение при попытке использовать данный контейнер.</span><span class="sxs-lookup"><span data-stu-id="117d2-144">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="117d2-145">Подобные ошибки могут также наблюдаться при запуске приложения, развернутого в облаке.</span><span class="sxs-lookup"><span data-stu-id="117d2-145">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="117d2-146">В этом случае оркестраторы могут перемещать контейнеры из одного узла (или виртуальной машины) в другой (запуская новые экземпляры) в процессе балансировки числа контейнеров между узлами кластера.</span><span class="sxs-lookup"><span data-stu-id="117d2-146">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="117d2-147">eShopOnContainers решает эти проблемы при запуске всех контейнеров с помощью шаблона повторных попыток, описанного ранее.</span><span class="sxs-lookup"><span data-stu-id="117d2-147">The way 'eShopOnContainers' solves those issues when starting all the containers is by using the Retry pattern illustrated earlier.</span></span>

### <a name="test-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="117d2-148">Тестирование размыкателя цепи в eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="117d2-148">Test the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="117d2-149">Есть несколько способов разомкнуть цепь и протестировать ее в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="117d2-149">There are a few ways you can break/open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="117d2-150">Один из вариантов — уменьшить разрешенное число повторных попыток до 1 в политике размыкателя цепи и повторно развернуть все решение в Docker.</span><span class="sxs-lookup"><span data-stu-id="117d2-150">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="117d2-151">При одной повторной попытке высока вероятность того, что HTTP-запрос завершится сбоем во время развертывания, размыкатель цепи откроется и произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="117d2-151">With a single retry, there's a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="117d2-152">Другой вариант — использовать пользовательское ПО промежуточного слоя, реализованное в микрослужбе **Basket**.</span><span class="sxs-lookup"><span data-stu-id="117d2-152">Another option is to use custom middleware that's implemented in the **Basket** microservice.</span></span> <span data-ttu-id="117d2-153">При его включении оно перехватывает все HTTP-запросы и возвращает код состояния 500.</span><span class="sxs-lookup"><span data-stu-id="117d2-153">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="117d2-154">Чтобы включить ПО промежуточного слоя, можно выполнить запрос GET к сбойному универсальному коду ресурса (URI), например, следующему:</span><span class="sxs-lookup"><span data-stu-id="117d2-154">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

- `GET http://localhost:5103/failing`\
  <span data-ttu-id="117d2-155">Этот запрос возвращает текущее состояние ПО промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="117d2-155">This request returns the current state of the middleware.</span></span> <span data-ttu-id="117d2-156">Если оно включено, запрос возвращает код состояния 500.</span><span class="sxs-lookup"><span data-stu-id="117d2-156">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="117d2-157">Если оно отключено, ответа нет.</span><span class="sxs-lookup"><span data-stu-id="117d2-157">If the middleware is disabled, there's no response.</span></span>

- `GET http://localhost:5103/failing?enable`\
  <span data-ttu-id="117d2-158">Этот запрос включает ПО промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="117d2-158">This request enables the middleware.</span></span>

- `GET http://localhost:5103/failing?disable`\
  <span data-ttu-id="117d2-159">Этот запрос отключает ПО промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="117d2-159">This request disables the middleware.</span></span>

<span data-ttu-id="117d2-160">Например, после запуска приложения вы можете включить ПО промежуточного слоя, выполнив запрос к указанному ниже коду URI в любом браузере.</span><span class="sxs-lookup"><span data-stu-id="117d2-160">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="117d2-161">Обратите внимание на то, что микрослужба размещения заказов использует порт 5103.</span><span class="sxs-lookup"><span data-stu-id="117d2-161">Note that the ordering microservice uses port 5103.</span></span>

`http://localhost:5103/failing?enable`

<span data-ttu-id="117d2-162">После этого можно проверить состояние, используя код URI `http://localhost:5103/failing`, как показано на рис. 8-5.</span><span class="sxs-lookup"><span data-stu-id="117d2-162">You can then check the status using the URI `http://localhost:5103/failing`, as shown in Figure 8-5.</span></span>

![Снимок экрана: проверка состояния при имитации сбоя ПО промежуточного слоя.](./media/implement-circuit-breaker-pattern/failing-middleware-simulation.png)

<span data-ttu-id="117d2-164">**Рис. 8-5**.</span><span class="sxs-lookup"><span data-stu-id="117d2-164">**Figure 8-5**.</span></span> <span data-ttu-id="117d2-165">Проверка состояния ПО промежуточного слоя ASP.NET (в этом случае отключено)</span><span class="sxs-lookup"><span data-stu-id="117d2-165">Checking the state of the “Failing” ASP.NET middleware – In this case, disabled.</span></span>

<span data-ttu-id="117d2-166">На этом этапе микрослужба Basket возвращает код состояния 500 при каждом вызове.</span><span class="sxs-lookup"><span data-stu-id="117d2-166">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="117d2-167">Когда ПО промежуточного слоя будет запущено, вы можете попытаться сделать заказ в веб-приложении MVC.</span><span class="sxs-lookup"><span data-stu-id="117d2-167">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="117d2-168">Так как запрос завершается сбоем, цепь размыкается.</span><span class="sxs-lookup"><span data-stu-id="117d2-168">Because the requests fail, the circuit will open.</span></span>

<span data-ttu-id="117d2-169">В приведенном ниже примере можно увидеть, что в веб-приложении MVC есть блок catch в логике размещения заказа.</span><span class="sxs-lookup"><span data-stu-id="117d2-169">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span>  <span data-ttu-id="117d2-170">Если код перехватывает исключение размыкания цепи, он выводит сообщение с просьбой к пользователю подождать.</span><span class="sxs-lookup"><span data-stu-id="117d2-170">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            var user = _appUserParser.Parse(HttpContext.User);
            //Http requests using the Typed Client (Service Agent)
            var vm = await _basketSvc.GetBasket(user);
            return View(vm);
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

<span data-ttu-id="117d2-171">Вкратце рассмотрим, что происходит.</span><span class="sxs-lookup"><span data-stu-id="117d2-171">Here’s a summary.</span></span> <span data-ttu-id="117d2-172">Политика повторных попыток несколько раз пытается выполнить HTTP-запрос и получает ошибки HTTP.</span><span class="sxs-lookup"><span data-stu-id="117d2-172">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="117d2-173">Когда число повторных попыток достигает максимального значения, заданного для политики размыкателя цепи (в этом случае 5), приложение вызывает исключение BrokenCircuitException.</span><span class="sxs-lookup"><span data-stu-id="117d2-173">When the number of retries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="117d2-174">В результате выводится понятное сообщение для пользователя, как показано на рис. 8-6.</span><span class="sxs-lookup"><span data-stu-id="117d2-174">The result is a friendly message, as shown in Figure 8-6.</span></span>

![Снимок экрана: веб-приложение MVC с ошибкой Basket Service is inoperative (Служба Basket не работает).](./media/implement-circuit-breaker-pattern/basket-service-inoperative.png)

<span data-ttu-id="117d2-176">**Рис. 8-6**.</span><span class="sxs-lookup"><span data-stu-id="117d2-176">**Figure 8-6**.</span></span> <span data-ttu-id="117d2-177">Размыкатель цепи возвращает ошибку в пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="117d2-177">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="117d2-178">Вы можете реализовать другую логику размыкания цепи.</span><span class="sxs-lookup"><span data-stu-id="117d2-178">You can implement different logic for when to open/break the circuit.</span></span> <span data-ttu-id="117d2-179">Кроме того, можно пытаться выполнять HTTP-запросы к другой серверной микрослужбе, если есть резервный центр обработки данных или избыточная серверная система.</span><span class="sxs-lookup"><span data-stu-id="117d2-179">Or you can try an HTTP request against a different back-end microservice if there's a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="117d2-180">Наконец, еще одной возможностью для `CircuitBreakerPolicy` является использование методов `Isolate` (размыкает цепь и сохраняет ее в таком состоянии) и `Reset` (снова замыкает цепь).</span><span class="sxs-lookup"><span data-stu-id="117d2-180">Finally, another possibility for the `CircuitBreakerPolicy` is to use `Isolate` (which forces open and holds open the circuit) and `Reset` (which closes it again).</span></span> <span data-ttu-id="117d2-181">Таким образом, можно создать служебную конечную точку HTTP, которая напрямую вызывает методы Isolate и Reset политики.</span><span class="sxs-lookup"><span data-stu-id="117d2-181">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span>  <span data-ttu-id="117d2-182">Такую конечную точку HTTP с надлежащей защитой можно также использовать в рабочей среде для временной изоляции подчиненной системы, например, если ее необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="117d2-182">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="117d2-183">Кроме того, с ее помощью можно размыкать цепь вручную для защиты подчиненной системы, если есть подозрения на ее неисправность.</span><span class="sxs-lookup"><span data-stu-id="117d2-183">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="117d2-184">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="117d2-184">Additional resources</span></span>

- <span data-ttu-id="117d2-185">**Шаблон размыкателя цепи**</span><span class="sxs-lookup"><span data-stu-id="117d2-185">**Circuit Breaker pattern**</span></span>\
  [https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker](/azure/architecture/patterns/circuit-breaker)

>[!div class="step-by-step"]
><span data-ttu-id="117d2-186">[Назад](implement-http-call-retries-exponential-backoff-polly.md)
>[Вперед](monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="117d2-186">[Previous](implement-http-call-retries-exponential-backoff-polly.md)
[Next](monitor-app-health.md)</span></span>
