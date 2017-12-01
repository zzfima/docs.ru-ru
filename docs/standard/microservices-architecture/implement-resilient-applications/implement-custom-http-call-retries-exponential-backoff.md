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
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a>Реализация пользовательских повторные попытки вызова HTTP с экспоненциально растущим

Чтобы создать устойчивым микрослужбами, необходимо обрабатывать возможные сценарии сбоев HTTP. Для этой цели можно создать собственную реализацию повторные попытки с экспоненциально растущим.

В дополнение к обработке ресурсов Временная недоступность, экспоненциальное увеличение задержки необходимо также учитывать, что поставщика облачных служб может регулировать доступность ресурсов, чтобы предотвратить использование перегрузки. Например, очень быстро создать слишком много запросов на подключение может рассматриваться как отказ в обслуживании ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) атаки поставщиком облачных. В результате необходимо предоставить механизм масштабирования запросов на подключение, возникших порога емкости.

Как первоначального исследования, можно реализовать собственный код служебный класс для экспоненциальной отсрочки, как и в [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), а также код, аналогичный следующему (который также доступен в [в репозитории GitHub ](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).

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

С помощью следующего кода в клиенте C\# приложения (микрослужбу клиента другой веб-API, приложения ASP.NET MVC или даже C\# приложения Xamarin) нетрудно. В следующем примере показан способ, с помощью класса HttpClient.

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

Тем не менее этот код подходит только в качестве эксперимента. Следующий раздел объясняет, как использовать более сложные и проверенные библиотеки.


>[!div class="step-by-step"]
[Предыдущие] (implement-resilient-entity-framework-core-sql-connections.md) [Далее] (implement-http-call-retries-exponential-backoff-polly.md)
