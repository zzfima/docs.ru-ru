---
title: Реализация повторных попыток вызова HTTP с экспоненциальной выдержкой с помощью библиотеки Polly
description: Узнайте, как обрабатывать сбои HTTP-запросов с помощью Polly и HttpClientFactory.
ms.date: 01/30/2020
ms.openlocfilehash: 60943360c9674f93b246b37b2667b48dab659e0e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502671"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a><span data-ttu-id="00ae9-103">Реализация повторных попыток вызова HTTP с экспоненциальной выдержкой с помощью HttpClientFactory и политик Polly</span><span class="sxs-lookup"><span data-stu-id="00ae9-103">Implement HTTP call retries with exponential backoff with HttpClientFactory and Polly policies</span></span>

<span data-ttu-id="00ae9-104">Рекомендуемый подход к выполнению повторных попыток с экспоненциальной выдержкой заключается в использовании расширенных библиотек .NET, таких как [библиотека Polly](https://github.com/App-vNext/Polly) с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="00ae9-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open-source [Polly library](https://github.com/App-vNext/Polly).</span></span>

<span data-ttu-id="00ae9-105">Polly — это библиотека .NET, которая предоставляет возможности обеспечения отказоустойчивости и обработки временных сбоев.</span><span class="sxs-lookup"><span data-stu-id="00ae9-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="00ae9-106">Эти возможности можно реализовать путем применения политик Polly, таких как политики повтора, размыкателя цепи, изоляции отсеков, времени ожидания и отката.</span><span class="sxs-lookup"><span data-stu-id="00ae9-106">You can implement those capabilities by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="00ae9-107">Polly используется с .NET Framework 4.x, а также .NET Standard 1.0, 1.1 и 2.0 (с поддержкой .NET Core).</span><span class="sxs-lookup"><span data-stu-id="00ae9-107">Polly targets .NET Framework 4.x and .NET Standard 1.0, 1.1, and 2.0 (which supports .NET Core).</span></span>

<span data-ttu-id="00ae9-108">Тем не менее использовать библиотеку Polly с вашим кодом с помощью HttpClient может быть довольно сложно.</span><span class="sxs-lookup"><span data-stu-id="00ae9-108">However, writing your own custom code to use Polly’s library with HttpClient can be significantly complex.</span></span> <span data-ttu-id="00ae9-109">В исходной версии eShopOnContainers существовал [стандартный блок ResilientHttpClient](https://github.com/dotnet-architecture/eShopOnContainers/commit/0c317d56f3c8937f6823cf1b45f5683397274815#diff-e6532e623eb606a0f8568663403e3a10) на базе Polly.</span><span class="sxs-lookup"><span data-stu-id="00ae9-109">In the original version of eShopOnContainers, there was a [ResilientHttpClient building-block](https://github.com/dotnet-architecture/eShopOnContainers/commit/0c317d56f3c8937f6823cf1b45f5683397274815#diff-e6532e623eb606a0f8568663403e3a10) based on Polly.</span></span> <span data-ttu-id="00ae9-110">Но с появлением [HttpClientFactory](use-httpclientfactory-to-implement-resilient-http-requests.md) стало гораздо проще реализовывать устойчивое соединение c Polly по протоколу HTTP, так что этот стандартный блок был исключен из eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="00ae9-110">But with the release of [HttpClientFactory](use-httpclientfactory-to-implement-resilient-http-requests.md), implementing resilient HTTP communication with Polly has become much simpler, so that building-block was deprecated from eShopOnContainers.</span></span>

<span data-ttu-id="00ae9-111">Ниже показано, как можно использовать повторные HTTP-запросы через Polly с интеграцией HttpClientFactory, как описано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="00ae9-111">The following steps show how you can use Http retries with Polly integrated into HttpClientFactory, which is explained in the previous section.</span></span>

<span data-ttu-id="00ae9-112">**Ссылка на пакеты ASP.NET Core 3.1**</span><span class="sxs-lookup"><span data-stu-id="00ae9-112">**Reference the ASP.NET Core 3.1 packages**</span></span>

<span data-ttu-id="00ae9-113">Решение `HttpClientFactory` доступно с версии .NET Core 2.1, но мы рекомендуем использовать в проекте последние пакеты ASP.NET Core 3.1 из NuGet.</span><span class="sxs-lookup"><span data-stu-id="00ae9-113">`HttpClientFactory` is available since .NET Core 2.1 however we recommend you to use the latest ASP.NET Core 3.1 packages from NuGet in your project.</span></span> <span data-ttu-id="00ae9-114">Обычно также требуется ссылка на пакет расширения `Microsoft.Extensions.Http.Polly`.</span><span class="sxs-lookup"><span data-stu-id="00ae9-114">You typically also need to reference the extension package `Microsoft.Extensions.Http.Polly`.</span></span>

<span data-ttu-id="00ae9-115">**Настройка клиента с помощью политики повтора Polly в параметрах запуска**</span><span class="sxs-lookup"><span data-stu-id="00ae9-115">**Configure a client with Polly’s Retry policy, in Startup**</span></span>

<span data-ttu-id="00ae9-116">Как показано в предыдущих разделах, необходимо определить конфигурацию HttpClient именованного или типизированного клиента в стандартном методе Startup.ConfigureServices(...), но теперь вам потребуется добавочный код, указывающий политику для повторных HTTP-запросов с экспоненциальной выдержкой, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="00ae9-116">As shown in previous sections, you need to define a named or typed client HttpClient configuration in your standard Startup.ConfigureServices(...) method, but now, you add incremental code specifying the policy for the Http retries with exponential backoff, as below:</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

<span data-ttu-id="00ae9-117">Метод **AddPolicyHandler()** добавляет политики для объектов `HttpClient`, которые вы будете использовать.</span><span class="sxs-lookup"><span data-stu-id="00ae9-117">The **AddPolicyHandler()** method is what adds policies to the `HttpClient` objects you'll use.</span></span> <span data-ttu-id="00ae9-118">В этом случае он добавляет политику Polly для повторных HTTP-запросов с экспоненциальной задержкой.</span><span class="sxs-lookup"><span data-stu-id="00ae9-118">In this case, it's adding a Polly’s policy for Http Retries with exponential backoff.</span></span>

<span data-ttu-id="00ae9-119">Для реализации более модульного подхода политику повтора HTTP-запросов можно определить в отдельном методе в файле `Startup.cs`, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="00ae9-119">To have a more modular approach, the Http Retry Policy can be defined in a separate method within the `Startup.cs` file, as shown in the following code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2,
                                                                    retryAttempt)));
}
```

<span data-ttu-id="00ae9-120">С помощью Polly вы определяете политику повтора с числом повторных попыток, конфигурацией экспоненциальной задержки и действиями, которые необходимо выполнить в случае исключения HTTP (например, запись ошибки в журнал).</span><span class="sxs-lookup"><span data-stu-id="00ae9-120">With Polly, you can define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there's an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="00ae9-121">В этом случае политика настроена на шесть попыток с экспоненциальной выдержкой, начиная с двух секунд.</span><span class="sxs-lookup"><span data-stu-id="00ae9-121">In this case, the policy is configured to try six times with an exponential retry, starting at two seconds.</span></span>

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="00ae9-122">Добавление стратегии обработки колебания задержки в политику повтора</span><span class="sxs-lookup"><span data-stu-id="00ae9-122">Add a jitter strategy to the retry policy</span></span>

<span data-ttu-id="00ae9-123">Обычная политика повтора может влиять на работу системы в случае высокого уровня параллелизма и масштабируемости, а также в условиях интенсивного состязания за ресурсы.</span><span class="sxs-lookup"><span data-stu-id="00ae9-123">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="00ae9-124">Чтобы решить проблему с большим числом повторных запросов, поступающих от множества клиентов в случае частичного отказа системы, можно добавить стратегию в отношении колебания задержки в алгоритм или политику повтора.</span><span class="sxs-lookup"><span data-stu-id="00ae9-124">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="00ae9-125">Это может повысить общую производительность всей системы благодаря тому, что экспоненциальная задержка становится более случайной.</span><span class="sxs-lookup"><span data-stu-id="00ae9-125">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="00ae9-126">При возникновении проблем пики размываются.</span><span class="sxs-lookup"><span data-stu-id="00ae9-126">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="00ae9-127">Этот принцип проиллюстрирован в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="00ae9-127">The principle is illustrated by the following example:</span></span>

```csharp
Random jitterer = new Random();
var retryWithJitterPolicy = HttpPolicyExtensions
    .HandleTransientHttpError()
    .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
    .WaitAndRetryAsync(6,    // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                      + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

<span data-ttu-id="00ae9-128">Polly предоставляет готовые к работе алгоритмы дрожания с помощью веб-сайта проекта.</span><span class="sxs-lookup"><span data-stu-id="00ae9-128">Polly provides production-ready jitter algorithms via the project website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="00ae9-129">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="00ae9-129">Additional resources</span></span>

- <span data-ttu-id="00ae9-130">**Шаблон повтора**</span><span class="sxs-lookup"><span data-stu-id="00ae9-130">**Retry pattern**</span></span>  
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- <span data-ttu-id="00ae9-131">**Использование Polly и HttpClientFactory**</span><span class="sxs-lookup"><span data-stu-id="00ae9-131">**Polly and HttpClientFactory**</span></span>  
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- <span data-ttu-id="00ae9-132">**Polly (библиотека для обеспечения отказоустойчивости .NET и обработки временных сбоев)**</span><span class="sxs-lookup"><span data-stu-id="00ae9-132">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <https://github.com/App-vNext/Polly>

- <span data-ttu-id="00ae9-133">**Polly: повторная попытка с дрожанием**</span><span class="sxs-lookup"><span data-stu-id="00ae9-133">**Polly: Retry with Jitter**</span></span>  
  <https://github.com/App-vNext/Polly/wiki/Retry-with-jitter>

- <span data-ttu-id="00ae9-134">**Марк Брукер (Marc Brooker). Колебания. Оптимизация с помощью случайности**</span><span class="sxs-lookup"><span data-stu-id="00ae9-134">**Marc Brooker. Jitter: Making Things Better With Randomness**</span></span>  
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
><span data-ttu-id="00ae9-135">[Назад](explore-custom-http-call-retries-exponential-backoff.md)
>[Вперед](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="00ae9-135">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>
