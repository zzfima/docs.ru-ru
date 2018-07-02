---
title: Реализация настраиваемых повторных попыток HTTP-вызова с экспоненциальной выдержкой
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Реализация настраиваемых повторных попыток HTTP-вызова с экспоненциальной выдержкой
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 77663f193b5f788ee07eba001306caed764ed253
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104783"
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a>Реализация настраиваемых повторных попыток HTTP-вызова с экспоненциальной выдержкой

Для создания устойчивых микрослужб необходимо обрабатывать возможные сценарии сбоев HTTP. Для этой цели можно создать собственную реализацию повторных попыток с экспоненциальной выдержкой.

Наряду с временной недоступностью ресурсов экспоненциальная выдержка также должна учитывать ту ситуацию, когда облачный провайдер может регулировать доступность ресурсов, чтобы предотвратить чрезмерное использование ресурсов. Например, быстрое создание слишком большого числа запросов на подключение может расцениваться облачным провайдером как атака типа "отказ в обслуживании" ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)-атака). Поэтому необходимо предоставить механизм для сокращения числа запросов на подключение при достижении порогового значения.

В качестве первоначального исследования можно реализовать собственный код вспомогательного класса для экспоненциальной выдержки, взяв код из файла [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260) и добавив в него следующий код (который также доступен в [репозитории GitHub](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).

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

Вы можете использовать следующий простой код в приложении C\# (а также в другой микрослужбе клиента веб-API, в приложении MVC ASP.NET и даже в приложении C\# Xamarin). В следующем примере показано, как это сделать с помощью класса HttpClient.

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

Тем не менее этот код подходит только для иллюстрации идеи. В следующем разделе показано, как использовать более сложные и проверенные библиотеки.


>[!div class="step-by-step"]
[Назад](implement-resilient-entity-framework-core-sql-connections.md)
[Вперед](implement-http-call-retries-exponential-backoff-polly.md)
