---
title: Шаблоны оркестрации — бессерверные приложения
description: Устойчивые функции Azure
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522633"
---
# <a name="orchestration-patterns"></a><span data-ttu-id="a7458-103">Шаблоны оркестрации</span><span class="sxs-lookup"><span data-stu-id="a7458-103">Orchestration patterns</span></span>

<span data-ttu-id="a7458-104">Устойчивые функции упрощают создание рабочих процессов с отслеживанием состояния, состоящих из дискретных долго выполняющихся действий, в бессерверной среде.</span><span class="sxs-lookup"><span data-stu-id="a7458-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="a7458-105">Устойчивые функции могут отслеживать ход выполнения рабочих процессов и периодически создавать контрольные точки в журнале выполнения, поэтому они предоставляют возможности реализации некоторых интересных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="a7458-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="a7458-106">Цепочка функций</span><span class="sxs-lookup"><span data-stu-id="a7458-106">Function chaining</span></span>

<span data-ttu-id="a7458-107">В типичном последовательном процессе действия должны выполняться один за другим в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="a7458-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="a7458-108">При необходимости для предстоящего действия могут потребоваться некоторые выходные данные предыдущей функции.</span><span class="sxs-lookup"><span data-stu-id="a7458-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="a7458-109">Эта зависимость от порядка действий создает цепочку выполнения функций.</span><span class="sxs-lookup"><span data-stu-id="a7458-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="a7458-110">Преимущество использования Устойчивых функций для реализации этого шаблона рабочего процесса обусловлено возможностью создания контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="a7458-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="a7458-111">Если происходит аварийное завершение работы сервера, истекает время ожидания сети или возникает какая-либо другая проблема, Устойчивые функции могут возобновлять рабочий процесс на основе последнего известного состояния и продолжать выполнять его, даже если он запущен на другом сервере.</span><span class="sxs-lookup"><span data-stu-id="a7458-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="a7458-112">В предыдущем примере кода функция `CallActivityAsync` отвечает за выполнение определенного действия на виртуальной машине в центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="a7458-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="a7458-113">Если значение await возвращается и базовая задача завершается, выполнение записывается в таблицу журнала.</span><span class="sxs-lookup"><span data-stu-id="a7458-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="a7458-114">Код в функции оркестратора может использовать любую из привычных конструкций библиотеки параллельных задач и ключевых слов async/await.</span><span class="sxs-lookup"><span data-stu-id="a7458-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="a7458-115">Следующий код является упрощенным примером того, как может выглядеть метод `ProcessPayment`:</span><span class="sxs-lookup"><span data-stu-id="a7458-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="a7458-116">Асинхронные API HTTP</span><span class="sxs-lookup"><span data-stu-id="a7458-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="a7458-117">В некоторых случаях рабочие процессы могут содержать действия, выполнение которых занимает относительно длительный период времени.</span><span class="sxs-lookup"><span data-stu-id="a7458-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="a7458-118">Представьте себе процесс, который запускает резервное копирование файлов мультимедиа в хранилище BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="a7458-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="a7458-119">В зависимости от размера и количества файлов мультимедиа процесс резервного копирования может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="a7458-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="a7458-120">В этом сценарии возможность `DurableOrchestrationClient` проверить состояние выполняющегося рабочего процесса будет полезной.</span><span class="sxs-lookup"><span data-stu-id="a7458-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="a7458-121">При использовании `HttpTrigger` для запуска рабочего процесса можно применить метод `CreateCheckStatusResponse` для возврата экземпляра `HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="a7458-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="a7458-122">Этот ответ предоставляет клиенту универсальный код ресурса (URI) в полезных данных, который можно использовать для проверки состояния выполняющегося процесса.</span><span class="sxs-lookup"><span data-stu-id="a7458-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="a7458-123">В примере ниже показана структура полезных данных ответа.</span><span class="sxs-lookup"><span data-stu-id="a7458-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="a7458-124">Используя предпочтительный HTTP-клиент, можно выполнить запросы GET к URI в statusQueryGetUri, чтобы проверить состояние выполняющегося рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a7458-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="a7458-125">Возвращенный ответ о состоянии должен напоминать следующий код.</span><span class="sxs-lookup"><span data-stu-id="a7458-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="a7458-126">По мере продолжения процесса ответ о состоянии изменится на **Failed** (Сбой) или **Completed** (Завершен).</span><span class="sxs-lookup"><span data-stu-id="a7458-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="a7458-127">При успешном завершении свойство **оutput** в полезных данных будет содержать возвращенные данные.</span><span class="sxs-lookup"><span data-stu-id="a7458-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="a7458-128">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="a7458-128">Monitoring</span></span>

<span data-ttu-id="a7458-129">Для простых повторяющихся задач решение "Функции Azure" предоставляет `TimerTrigger`, который можно запланировать на основе выражения CRON.</span><span class="sxs-lookup"><span data-stu-id="a7458-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="a7458-130">Этот таймер хорошо подходит для простых кратковременных задач, но в некоторых случаях требуется более гибкое планирование.</span><span class="sxs-lookup"><span data-stu-id="a7458-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="a7458-131">В таких случаях могут помочь Устойчивые функции и шаблон мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a7458-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="a7458-132">Устойчивые функции обеспечивают гибкие интервалы планирования, управление временем существования и создание нескольких процессов мониторинга из одной функции оркестрации.</span><span class="sxs-lookup"><span data-stu-id="a7458-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="a7458-133">Одним из вариантов использования этих возможностей может быть создание наблюдателей за изменением цен на акции, которые завершаются после достижения определенного порогового значения.</span><span class="sxs-lookup"><span data-stu-id="a7458-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="a7458-134">Метод `CreateTimer` `DurableOrchestrationContext` настраивает расписание следующего вызова цикла для проверки изменений цен на акции.</span><span class="sxs-lookup"><span data-stu-id="a7458-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="a7458-135">`DurableOrchestrationContext` также имеет свойство `CurrentUtcDateTime`, позволяющее получить текущее значение даты и времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="a7458-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="a7458-136">Лучше использовать это свойство вместо `DateTime.UtcNow`, так как оно легко имитируется для тестирования.</span><span class="sxs-lookup"><span data-stu-id="a7458-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="a7458-137">Рекомендуемые ресурсы</span><span class="sxs-lookup"><span data-stu-id="a7458-137">Recommended resources</span></span>

- [<span data-ttu-id="a7458-138">Что такое Устойчивые функции?</span><span class="sxs-lookup"><span data-stu-id="a7458-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="a7458-139">Модульное тестирование в .NET Core и .NET Standard</span><span class="sxs-lookup"><span data-stu-id="a7458-139">Unit Testing in .NET Core and .NET Standard</span></span>](../../core/testing/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="a7458-140">[Назад](durable-azure-functions.md)
>[Вперед](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="a7458-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
