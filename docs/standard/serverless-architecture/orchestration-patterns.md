---
title: Шаблоны Orchestration — Бессерверных приложений
description: Запрос на Вытягивание устойчивых функций Azure
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 241eff4f30e63b2bb34664d6f783f854a000e7fd
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370333"
---
# <a name="orchestration-patterns"></a>Шаблоны оркестрации

Устойчивые функции упрощает создание с отслеживанием состояния рабочих процессов, которые состоят из отдельных, долго выполняющиеся действия в бессерверной среде. Так как устойчивые функции можно отслеживать ход выполнения рабочих процессов и периодически контрольные точки журнал выполнения, пригоден для реализации некоторых интересных шаблонов.

## <a name="function-chaining"></a>Цепочки функций

В типичных последовательном процессе нужно выполнить один за другим в определенном порядке. При необходимости предстоящих действия может потребоваться некоторые выходные данные предыдущей функции. Эта зависимость на Упорядочение действий создается цепочка функция выполнения.

Преимущество использования устойчивых функций для реализации этого шаблона рабочего процесса поступают из его возможность создания контрольных точек. В случае сбоя сервера сети времени ожидания или происходит по другим причинам, устойчивые функции можно возобновить с последнего известного состояния и продолжить выполнение рабочего процесса, даже если он находится на другом сервере.

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<bool>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

В предыдущем примере кода `CallActivityAsync` функция отвечает за запуск определенного действия на виртуальной машине в центре обработки данных. По завершении возвращает await и базовой задачи выполнения будут записаны в таблицу журнала. Код в функции оркестратора можно сделать использовать любые из знакомых конструкций, библиотека параллельных задач и ключевых слов async/await.

Ниже приведен упрощенный пример того, что `ProcessPayment` метод может выглядеть следующим образом:

```csharp
[FunctionName("ProcessPayment")]
public static bool ProcessPayment([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    ApplyCoupons(orderData);
    if(IssuePaymentRequest(orderData)) {
        return true;
    }

    return false;
}
```

## <a name="asynchronous-http-apis"></a>Асинхронные интерфейсы API HTTP

В некоторых случаях рабочие процессы может содержать действия, имеющие относительно длительного периода времени. Представьте себе процесс, который запускает носителя резервной копии файлов в хранилище BLOB-объектов. В зависимости от размера и количества файлов мультимедиа этот процесс резервного копирования может занять до часов.

В этом случае `DurableOrchestrationClient`возможность проверить состояние работающего рабочего процесса становится полезным. При использовании `HttpTrigger` запустить рабочий процесс, `CreateCheckStatusResponse` метод может использоваться для возврата экземпляра `HttpResponseMessage`. Этот ответ предоставляет клиенту с URI в полезных данных, который может использоваться для проверки состояния выполняющегося процесса.

```csharp
[FunctionName("OrderWorkflow")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient orchestrationClient)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

Пример результата ниже показана структура полезных данных ответа.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Используя предпочитаемый клиент HTTP, запросы GET можно выполнять по URI в statusQueryGetUri проверке состояния выполняющегося рабочего процесса. Статусов ответ должен выглядеть следующим образом.

```json
{
    "runtimeStatus": "Running",
    "input": {
        "$type": "DurableFunctionsDemos.OrderRequestData, DurableFunctionsDemos"
    },
    "output": null,
    "createdTime": "2018-01-01T00:22:05Z",
    "lastUpdatedTime": "2018-01-01T00:22:09Z"
}
```

Так как процесс продолжает, ответ состояние изменится на либо **Failed** или **завершено**. При успешном завершении **вывода** свойство в полезных данных будет содержать любые возвращаемые данные.

## <a name="monitoring"></a>Мониторинг

Для простых повторяющихся задач, функции Azure предоставляют `TimerTrigger` , можно запланировать на основании выражения CRON. Таймер хорошо подходит для простой и короткоживущие задачи, но возможны ситуации, когда требуется более гибкое планирование. Этот случай — когда шаблона мониторинга и устойчивых функций может помочь.

Устойчивые функции обеспечивает гибкую планирования интервалы, управление временем существования и создания нескольких процессов монитор из одной оркестрации функции. Один из вариантов использования для использования этой функции может быть попытка создать наблюдателей для изменения цены акций, условии выполнены определенного порогового значения.

```csharp
[FunctionName("CheckStockPrice")]
public static async Task CheckStockPrice([OrchestrationTrigger] DurableOrchestrationContext context)
{
    StockWatcherInfo stockInfo = context.GetInput<StockWatcherInfo>();
    const int checkIntervalSeconds = 120;
    StockPrice initialStockPrice = null;

    DateTime fireAt;
    DateTime exitTime = context.CurrentUtcDateTime.Add(stockInfo.TimeLimit);

    while (context.CurrentUtcDateTime < exitTime)
    {
        StockPrice currentStockPrice = await context.CallActivityAsync<StockPrice>("GetStockPrice", stockInfo);

        if (initialStockPrice == null)
        {
            initialStockPrice = currentStockPrice;
            fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
            await context.CreateTimer(fireAt, CancellationToken.None);
            continue;
        }

        decimal percentageChange = (initialStockPrice.Price - currentStockPrice.Price) /
                               ((initialStockPrice.Price + currentStockPrice.Price) / 2);

        if (Math.Abs(percentageChange) >= stockInfo.PercentageChange)
        {
            // Change threshold detected
            await context.CallActivityAsync("NotifyStockPercentageChange", currentStockPrice);
            break;
        }

        // Sleep til next polling interval
        fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
        await context.CreateTimer(fireAt, CancellationToken.None);
    }
}
```

`DurableOrchestrationContext`в `CreateTimer` метод настраивает расписание для следующего вызова цикла для проверки изменений цены акций. `DurableOrchestrationContext` также имеет `CurrentUtcDateTime` свойство для получения текущего значения даты и времени в формате UTC. Рекомендуется использовать это свойство вместо `DateTime.UtcNow` так, как его легко имитируется для тестирования.

## <a name="recommended-resources"></a>Рекомендуемые ресурсы

* [Azure устойчивых функций](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [Модульное тестирование в .NET Core и .NET Standard](https://docs.microsoft.com/dotnet/core/testing/)

>[!div class="step-by-step"]
[Назад](durable-azure-functions.md)
[Вперед](serverless-business-scenarios.md)
