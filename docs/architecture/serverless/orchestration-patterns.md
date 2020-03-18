---
title: Шаблоны оркестрации — бессерверные приложения
description: Устойчивые функции Azure
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522633"
---
# <a name="orchestration-patterns"></a>Шаблоны оркестрации

Устойчивые функции упрощают создание рабочих процессов с отслеживанием состояния, состоящих из дискретных долго выполняющихся действий, в бессерверной среде. Устойчивые функции могут отслеживать ход выполнения рабочих процессов и периодически создавать контрольные точки в журнале выполнения, поэтому они предоставляют возможности реализации некоторых интересных шаблонов.

## <a name="function-chaining"></a>Цепочка функций

В типичном последовательном процессе действия должны выполняться один за другим в определенном порядке. При необходимости для предстоящего действия могут потребоваться некоторые выходные данные предыдущей функции. Эта зависимость от порядка действий создает цепочку выполнения функций.

Преимущество использования Устойчивых функций для реализации этого шаблона рабочего процесса обусловлено возможностью создания контрольных точек. Если происходит аварийное завершение работы сервера, истекает время ожидания сети или возникает какая-либо другая проблема, Устойчивые функции могут возобновлять рабочий процесс на основе последнего известного состояния и продолжать выполнять его, даже если он запущен на другом сервере.

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

В предыдущем примере кода функция `CallActivityAsync` отвечает за выполнение определенного действия на виртуальной машине в центре обработки данных. Если значение await возвращается и базовая задача завершается, выполнение записывается в таблицу журнала. Код в функции оркестратора может использовать любую из привычных конструкций библиотеки параллельных задач и ключевых слов async/await.

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

В этом сценарии возможность `DurableOrchestrationClient` проверить состояние выполняющегося рабочего процесса будет полезной. При использовании `HttpTrigger` для запуска рабочего процесса можно применить метод `CreateCheckStatusResponse` для возврата экземпляра `HttpResponseMessage`. Этот ответ предоставляет клиенту универсальный код ресурса (URI) в полезных данных, который можно использовать для проверки состояния выполняющегося процесса.

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

Используя предпочтительный HTTP-клиент, можно выполнить запросы GET к URI в statusQueryGetUri, чтобы проверить состояние выполняющегося рабочего процесса. Возвращенный ответ о состоянии должен напоминать следующий код.

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

По мере продолжения процесса ответ о состоянии изменится на **Failed** (Сбой) или **Completed** (Завершен). При успешном завершении свойство **оutput** в полезных данных будет содержать возвращенные данные.

## <a name="monitoring"></a>Мониторинг

Для простых повторяющихся задач решение "Функции Azure" предоставляет `TimerTrigger`, который можно запланировать на основе выражения CRON. Этот таймер хорошо подходит для простых кратковременных задач, но в некоторых случаях требуется более гибкое планирование. В таких случаях могут помочь Устойчивые функции и шаблон мониторинга.

Устойчивые функции обеспечивают гибкие интервалы планирования, управление временем существования и создание нескольких процессов мониторинга из одной функции оркестрации. Одним из вариантов использования этих возможностей может быть создание наблюдателей за изменением цен на акции, которые завершаются после достижения определенного порогового значения.

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

Метод `DurableOrchestrationContext``CreateTimer` настраивает расписание следующего вызова цикла для проверки изменений цен на акции. `DurableOrchestrationContext` также имеет свойство `CurrentUtcDateTime`, позволяющее получить текущее значение даты и времени в формате UTC. Лучше использовать это свойство вместо `DateTime.UtcNow`, так как оно легко имитируется для тестирования.

## <a name="recommended-resources"></a>Рекомендуемые ресурсы

- [Что такое Устойчивые функции?](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [Модульное тестирование в .NET Core и .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Назад](durable-azure-functions.md)
>[Вперед](serverless-business-scenarios.md)
