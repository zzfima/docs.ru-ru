---
title: Изучение настраиваемых повторных попыток HTTP-вызова с экспоненциальной выдержкой
description: Узнайте, как можно с нуля реализовать метод повторных попыток вызовов HTTP с экспоненциальной задержкой для обработки возможных сценариев сбоя HTTP.
ms.date: 10/16/2018
ms.openlocfilehash: 2b40b73a014faa87d4eb42192c72b5a9b6c8d4fa
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68674711"
---
# <a name="explore-custom-http-call-retries-with-exponential-backoff"></a>Изучение настраиваемых повторных попыток HTTP-вызова с экспоненциальной выдержкой

Для создания устойчивых микрослужб необходимо обрабатывать возможные сценарии сбоев HTTP. Один из способов, хотя и не лучший, обработки таких сбоев — создать собственную реализацию повторных попыток с экспоненциальной выдержкой.

**Важное примечание**. В этом разделе показано, как можно создать собственный код для реализации повторных попыток вызова HTTP. Тем не менее не рекомендуется делать это самостоятельно. Лучше использовать более эффективные и надежные и при этом простые механизмы, например `HttpClientFactory` с Polly начиная с .NET Core 2.1. Рекомендуемые подходы описываются в следующих разделах.

В качестве начального исследования можно реализовать собственный код вспомогательного класса для экспоненциальной задержки, взяв код из файла [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260) и добавив в него следующий код.

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

Помните, что этот код подходит только для иллюстрации идеи. В следующих разделах объясняется, как использовать более комплексные, но при этом простые подходы, с HttpClientFactory. HttpClientFactory доступно начиная с .NET Core 2.1 с проверенными устойчивыми библиотеками, такими как Polly.

>[!div class="step-by-step"]
>[Назад](implement-resilient-entity-framework-core-sql-connections.md)
>[Вперед](use-httpclientfactory-to-implement-resilient-http-requests.md)
