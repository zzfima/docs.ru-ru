---
title: Шаблоны оркестрации — бессерверные приложения
description: Службы устойчивых функций Azure (по)
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522633"
---
# <a name="orchestration-patterns"></a>Шаблоны оркестрации

Устойчивые функции упрощает создание рабочих процессов с отслеживанием состояния, состоящих из дискретных долго выполняющихся действий в бессерверной среде. Поскольку Устойчивые функции может отслеживать ход выполнения рабочих процессов и периодически выполнять контрольные точки в журнале выполнения, он самостоятельно реализует некоторые интересные шаблоны.

## <a name="function-chaining"></a>Цепочки функций

В типичном последовательном процессе действия должны выполняться один за другим в определенном порядке. При необходимости предстоящее действие может потребовать некоторые выходные данные предыдущей функции. Эта зависимость от порядка действий создает цепочку функций выполнения.

Преимущество использования Устойчивые функции для реализации этого шаблона рабочего процесса обусловлено возможностью создания контрольных точек. Если сервер завершает работу, истекает время ожидания сети или возникает какая-либо другая проблема, устойчивые функции могут возобновляться из последнего известного состояния и продолжать выполнять рабочий процесс, даже если он находится на другом сервере.

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

В предыдущем примере кода функция `CallActivityAsync` отвечает за выполнение данного действия на виртуальной машине в центре обработки данных. Когда функция await возвращает результат и базовая задача завершается, выполнение будет записано в таблицу журнала. Код в функции Orchestrator может использовать любую из привычных конструкций библиотеки параллельных задач и ключевых слов async/await.

Следующий код является упрощенным примером того, как может выглядеть метод `ProcessPayment`:

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

## <a name="asynchronous-http-apis"></a>Асинхронные API HTTP

В некоторых случаях рабочие процессы могут содержать действия, выполнение которых занимает относительно длительный период времени. Представьте себе процесс, который запускает резервное копирование файлов мультимедиа в хранилище BLOB-объектов. В зависимости от размера и количества файлов мультимедиа процесс резервного копирования может занять несколько часов.

В этом сценарии `DurableOrchestrationClient` возможность проверки состояния выполняющегося рабочего процесса будет полезной. При использовании `HttpTrigger` для запуска рабочего процесса метод `CreateCheckStatusResponse` можно использовать для возврата экземпляра `HttpResponseMessage`. Этот ответ предоставляет клиенту URI в полезных данных, который можно использовать для проверки состояния выполняющегося процесса.

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

В примере ниже показана структура полезных данных ответа.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Используя предпочтительный HTTP-клиент, можно получить запросы GET к URI в statusQueryGetUri, чтобы проверить состояние выполняющегося рабочего процесса. Возвращаемый ответ о состоянии должен выглядеть следующим образом.

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

По мере продолжения процесса ответ о состоянии изменится на " **Ошибка** " или " **завершено**". При успешном завершении свойство **Output** в полезных данных будет содержать возвращенные данные.

## <a name="monitoring"></a>Мониторинг

Для простых повторяющихся задач функции Azure предоставляют `TimerTrigger`, которые могут быть запланированы на основе выражения CRON. Этот таймер хорошо подходит для простых кратковременных задач, но в некоторых случаях требуется более гибкое планирование. Этот сценарий относится к шаблону мониторинга и Устойчивые функции может помочь.

Устойчивые функции обеспечивает гибкие интервалы планирования, управление жизненным циклом и создание нескольких процессов мониторинга из одной функции оркестрации. Одним из вариантов использования этой функции может быть создание наблюдателей для изменений цен акций, которые выполняются после достижения определенного порогового значения.

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

`DurableOrchestrationContext` метода `CreateTimer` настраивает расписание следующего вызова цикла для проверки изменений цен на акции. `DurableOrchestrationContext` также имеет свойство `CurrentUtcDateTime` для получения текущего значения DateTime в формате UTC. Лучше использовать это свойство вместо `DateTime.UtcNow`, так как оно легко макетирование для тестирования.

## <a name="recommended-resources"></a>Рекомендуемые ресурсы

- [Устойчивые функции Azure](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [Модульное тестирование в .NET Core и .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Назад](durable-azure-functions.md)
>[Вперед](serverless-business-scenarios.md)
