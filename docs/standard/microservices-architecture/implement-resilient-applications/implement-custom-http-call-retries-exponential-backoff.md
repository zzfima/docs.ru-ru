---
title: Реализация настраиваемых повторных попыток HTTP-вызова с экспоненциальной выдержкой
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Реализация настраиваемых повторных попыток HTTP-вызова с экспоненциальной выдержкой
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 10751bb74ed648839fabec67ff7a71e458fb2a44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="4dc4a-103">Реализация настраиваемых повторных попыток HTTP-вызова с экспоненциальной выдержкой</span><span class="sxs-lookup"><span data-stu-id="4dc4a-103">Implementing custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="4dc4a-104">Для создания устойчивых микрослужб необходимо обрабатывать возможные сценарии сбоев HTTP.</span><span class="sxs-lookup"><span data-stu-id="4dc4a-104">In order to create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="4dc4a-105">Для этой цели можно создать собственную реализацию повторных попыток с экспоненциальной выдержкой.</span><span class="sxs-lookup"><span data-stu-id="4dc4a-105">For that purpose, you could create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="4dc4a-106">Наряду с временной недоступностью ресурсов экспоненциальная выдержка также должна учитывать ту ситуацию, когда облачный провайдер может регулировать доступность ресурсов, чтобы предотвратить чрезмерное использование ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4dc4a-106">In addition to handling temporal resource unavailability, the exponential backoff also needs to take into account that the cloud provider might throttle availability of resources to prevent usage overload.</span></span> <span data-ttu-id="4dc4a-107">Например, быстрое создание слишком большого числа запросов на подключение может расцениваться облачным провайдером как атака типа "отказ в обслуживании" ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)-атака).</span><span class="sxs-lookup"><span data-stu-id="4dc4a-107">For example, creating too many connection requests very quickly might be viewed as a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack by the cloud provider.</span></span> <span data-ttu-id="4dc4a-108">Поэтому необходимо предоставить механизм для сокращения числа запросов на подключение при достижении порогового значения.</span><span class="sxs-lookup"><span data-stu-id="4dc4a-108">As a result, you need to provide a mechanism to scale back connection requests when a capacity threshold has been encountered.</span></span>

<span data-ttu-id="4dc4a-109">В качестве первоначального исследования можно реализовать собственный код вспомогательного класса для экспоненциальной выдержки, взяв код из файла [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260) и добавив в него следующий код (который также доступен в [репозитории GitHub](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span><span class="sxs-lookup"><span data-stu-id="4dc4a-109">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following (which is also available on a [GitHub repo](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span></span>

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

<span data-ttu-id="4dc4a-110">Вы можете использовать следующий простой код в приложении C\# (а также в другой микрослужбе клиента веб-API, в приложении MVC ASP.NET и даже в приложении C\# Xamarin).</span><span class="sxs-lookup"><span data-stu-id="4dc4a-110">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="4dc4a-111">В следующем примере показано, как это сделать с помощью класса HttpClient.</span><span class="sxs-lookup"><span data-stu-id="4dc4a-111">The following example shows how, using the HttpClient class.</span></span>

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

<span data-ttu-id="4dc4a-112">Тем не менее этот код подходит только для иллюстрации идеи.</span><span class="sxs-lookup"><span data-stu-id="4dc4a-112">However, this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="4dc4a-113">В следующем разделе показано, как использовать более сложные и проверенные библиотеки.</span><span class="sxs-lookup"><span data-stu-id="4dc4a-113">The next topic explains how to use more sophisticated and proven libraries.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="4dc4a-114">[Назад] (implement-resilient-entity-framework-core-sql-connections.md) [Далее] (implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="4dc4a-114">[Previous] (implement-resilient-entity-framework-core-sql-connections.md) [Next] (implement-http-call-retries-exponential-backoff-polly.md)</span></span>
