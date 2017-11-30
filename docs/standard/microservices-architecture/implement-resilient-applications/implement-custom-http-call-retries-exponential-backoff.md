---
title: "Реализация пользовательских повторные попытки вызова HTTP с экспоненциально растущим"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализация пользовательских повторные попытки вызова HTTP с экспоненциально растущим"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4449e5d7e0ca3c81aead26fac653de3ba2187a92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="8b428-104">Реализация пользовательских повторные попытки вызова HTTP с экспоненциально растущим</span><span class="sxs-lookup"><span data-stu-id="8b428-104">Implementing custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="8b428-105">Чтобы создать устойчивым микрослужбами, необходимо обрабатывать возможные сценарии сбоев HTTP.</span><span class="sxs-lookup"><span data-stu-id="8b428-105">In order to create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="8b428-106">Для этой цели можно создать собственную реализацию повторные попытки с экспоненциально растущим.</span><span class="sxs-lookup"><span data-stu-id="8b428-106">For that purpose, you could create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="8b428-107">В дополнение к обработке ресурсов Временная недоступность, экспоненциальное увеличение задержки необходимо также учитывать, что поставщика облачных служб может регулировать доступность ресурсов, чтобы предотвратить использование перегрузки.</span><span class="sxs-lookup"><span data-stu-id="8b428-107">In addition to handling temporal resource unavailability, the exponential backoff also needs to take into account that the cloud provider might throttle availability of resources to prevent usage overload.</span></span> <span data-ttu-id="8b428-108">Например, очень быстро создать слишком много запросов на подключение может рассматриваться как отказ в обслуживании ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) атаки поставщиком облачных.</span><span class="sxs-lookup"><span data-stu-id="8b428-108">For example, creating too many connection requests very quickly might be viewed as a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack by the cloud provider.</span></span> <span data-ttu-id="8b428-109">В результате необходимо предоставить механизм масштабирования запросов на подключение, возникших порога емкости.</span><span class="sxs-lookup"><span data-stu-id="8b428-109">As a result, you need to provide a mechanism to scale back connection requests when a capacity threshold has been encountered.</span></span>

<span data-ttu-id="8b428-110">Как первоначального исследования, можно реализовать собственный код служебный класс для экспоненциальной отсрочки, как и в [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), а также код, аналогичный следующему (который также доступен в [в репозитории GitHub ](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span><span class="sxs-lookup"><span data-stu-id="8b428-110">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following (which is also available on a [GitHub repo](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span></span>

```csharp
public sealed class RetryWithExponentialBackoff
{
    private readonly int maxRetries, delayMilliseconds, maxDelayMilliseconds;

    public RetryWithExponentialBackoff(int maxRetries = 50,
        int delayMilliseconds = 200,
        int maxDelayMilliseconds = 2000)
    {
        this.maxRetries = maxRetries;
        this.delayMilliseconds = delayMilliseconds;
        this.maxDelayMilliseconds = maxDelayMilliseconds;
    }

    public async Task RunAsync(Func<Task> func)
    {
        ExponentialBackoff backoff = new ExponentialBackoff(this.maxRetries,
            this.delayMilliseconds,
            this.maxDelayMilliseconds);
        retry:
        try
        {
            await func();
        }
        catch (Exception ex) when (ex is TimeoutException ||
            ex is System.Net.Http.HttpRequestException)
        {
            Debug.WriteLine("Exception raised is: " +
                ex.GetType().ToString() +
                " –Message: " + ex.Message +
                " -- Inner Message: " +
                ex.InnerException.Message);
            await backoff.Delay();
            goto retry;
        }
    }
}

public struct ExponentialBackoff
{
    private readonly int m_maxRetries, m_delayMilliseconds, m_maxDelayMilliseconds;
    private int m_retries, m_pow;

    public ExponentialBackoff(int maxRetries, int delayMilliseconds,
        int maxDelayMilliseconds)
    {
        m_maxRetries = maxRetries;
        m_delayMilliseconds = delayMilliseconds;
        m_maxDelayMilliseconds = maxDelayMilliseconds;
        m_retries = 0;
        m_pow = 1;
    }

    public Task Delay()
    {
        if (m_retries == m_maxRetries)
        {
            throw new TimeoutException("Max retry attempts exceeded.");
        }
        ++m_retries;
        if (m_retries < 31)
        {
            m_pow = m_pow << 1; // m_pow = Pow(2, m_retries - 1)
        }
        int delay = Math.Min(m_delayMilliseconds * (m_pow - 1) / 2,
            m_maxDelayMilliseconds);
        return Task.Delay(delay);
    }
}
```

<span data-ttu-id="8b428-111">С помощью следующего кода в клиенте C\# приложения (микрослужбу клиента другой веб-API, приложения ASP.NET MVC или даже C\# приложения Xamarin) нетрудно.</span><span class="sxs-lookup"><span data-stu-id="8b428-111">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="8b428-112">В следующем примере показан способ, с помощью класса HttpClient.</span><span class="sxs-lookup"><span data-stu-id="8b428-112">The following example shows how, using the HttpClient class.</span></span>

```csharp
public async Task<Catalog> GetCatalogItems(int page,int take, int? brand, int? type)
{
    _apiClient = new HttpClient();
    var itemsQs = $"items?pageIndex={page}&pageSize={take}";
    var filterQs = "";
    var catalogUrl = $"{_remoteServiceBaseUrl}items{filterQs}?pageIndex={page}&pageSize={take}";
    var dataString = "";
    //
    // Using HttpClient with Retry and Exponential Backoff
    //
    var retry = new RetryWithExponentialBackoff();
    await retry.RunAsync(async () =>
    {
        // work with HttpClient call
        dataString = await _apiClient.GetStringAsync(catalogUrl);
    });
    return JsonConvert.DeserializeObject<Catalog>(dataString);
}
```

<span data-ttu-id="8b428-113">Тем не менее этот код подходит только в качестве эксперимента.</span><span class="sxs-lookup"><span data-stu-id="8b428-113">However, this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="8b428-114">Следующий раздел объясняет, как использовать более сложные и проверенные библиотеки.</span><span class="sxs-lookup"><span data-stu-id="8b428-114">The next topic explains how to use more sophisticated and proven libraries.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="8b428-115">[Предыдущие] (implement-resilient-entity-framework-core-sql-connections.md) [Далее] (implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="8b428-115">[Previous] (implement-resilient-entity-framework-core-sql-connections.md) [Next] (implement-http-call-retries-exponential-backoff-polly.md)</span></span>
