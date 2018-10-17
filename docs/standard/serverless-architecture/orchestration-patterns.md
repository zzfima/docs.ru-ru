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
# <a name="orchestration-patterns"></a><span data-ttu-id="f7cf6-103">Шаблоны оркестрации</span><span class="sxs-lookup"><span data-stu-id="f7cf6-103">Orchestration patterns</span></span>

<span data-ttu-id="f7cf6-104">Устойчивые функции упрощает создание с отслеживанием состояния рабочих процессов, которые состоят из отдельных, долго выполняющиеся действия в бессерверной среде.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="f7cf6-105">Так как устойчивые функции можно отслеживать ход выполнения рабочих процессов и периодически контрольные точки журнал выполнения, пригоден для реализации некоторых интересных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="f7cf6-106">Цепочки функций</span><span class="sxs-lookup"><span data-stu-id="f7cf6-106">Function chaining</span></span>

<span data-ttu-id="f7cf6-107">В типичных последовательном процессе нужно выполнить один за другим в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="f7cf6-108">При необходимости предстоящих действия может потребоваться некоторые выходные данные предыдущей функции.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="f7cf6-109">Эта зависимость на Упорядочение действий создается цепочка функция выполнения.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="f7cf6-110">Преимущество использования устойчивых функций для реализации этого шаблона рабочего процесса поступают из его возможность создания контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="f7cf6-111">В случае сбоя сервера сети времени ожидания или происходит по другим причинам, устойчивые функции можно возобновить с последнего известного состояния и продолжить выполнение рабочего процесса, даже если он находится на другом сервере.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="f7cf6-112">В предыдущем примере кода `CallActivityAsync` функция отвечает за запуск определенного действия на виртуальной машине в центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="f7cf6-113">По завершении возвращает await и базовой задачи выполнения будут записаны в таблицу журнала.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="f7cf6-114">Код в функции оркестратора можно сделать использовать любые из знакомых конструкций, библиотека параллельных задач и ключевых слов async/await.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="f7cf6-115">Ниже приведен упрощенный пример того, что `ProcessPayment` метод может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f7cf6-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="f7cf6-116">Асинхронные интерфейсы API HTTP</span><span class="sxs-lookup"><span data-stu-id="f7cf6-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="f7cf6-117">В некоторых случаях рабочие процессы может содержать действия, имеющие относительно длительного периода времени.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="f7cf6-118">Представьте себе процесс, который запускает носителя резервной копии файлов в хранилище BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="f7cf6-119">В зависимости от размера и количества файлов мультимедиа этот процесс резервного копирования может занять до часов.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="f7cf6-120">В этом случае `DurableOrchestrationClient`возможность проверить состояние работающего рабочего процесса становится полезным.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="f7cf6-121">При использовании `HttpTrigger` запустить рабочий процесс, `CreateCheckStatusResponse` метод может использоваться для возврата экземпляра `HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="f7cf6-122">Этот ответ предоставляет клиенту с URI в полезных данных, который может использоваться для проверки состояния выполняющегося процесса.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="f7cf6-123">Пример результата ниже показана структура полезных данных ответа.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="f7cf6-124">Используя предпочитаемый клиент HTTP, запросы GET можно выполнять по URI в statusQueryGetUri проверке состояния выполняющегося рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="f7cf6-125">Статусов ответ должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="f7cf6-126">Так как процесс продолжает, ответ состояние изменится на либо **Failed** или **завершено**.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="f7cf6-127">При успешном завершении **вывода** свойство в полезных данных будет содержать любые возвращаемые данные.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="f7cf6-128">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="f7cf6-128">Monitoring</span></span>

<span data-ttu-id="f7cf6-129">Для простых повторяющихся задач, функции Azure предоставляют `TimerTrigger` , можно запланировать на основании выражения CRON.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="f7cf6-130">Таймер хорошо подходит для простой и короткоживущие задачи, но возможны ситуации, когда требуется более гибкое планирование.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="f7cf6-131">Этот случай — когда шаблона мониторинга и устойчивых функций может помочь.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="f7cf6-132">Устойчивые функции обеспечивает гибкую планирования интервалы, управление временем существования и создания нескольких процессов монитор из одной оркестрации функции.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="f7cf6-133">Один из вариантов использования для использования этой функции может быть попытка создать наблюдателей для изменения цены акций, условии выполнены определенного порогового значения.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="f7cf6-134">`DurableOrchestrationContext`в `CreateTimer` метод настраивает расписание для следующего вызова цикла для проверки изменений цены акций.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="f7cf6-135">`DurableOrchestrationContext` также имеет `CurrentUtcDateTime` свойство для получения текущего значения даты и времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="f7cf6-136">Рекомендуется использовать это свойство вместо `DateTime.UtcNow` так, как его легко имитируется для тестирования.</span><span class="sxs-lookup"><span data-stu-id="f7cf6-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="f7cf6-137">Рекомендуемые ресурсы</span><span class="sxs-lookup"><span data-stu-id="f7cf6-137">Recommended resources</span></span>

* [<span data-ttu-id="f7cf6-138">Azure устойчивых функций</span><span class="sxs-lookup"><span data-stu-id="f7cf6-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [<span data-ttu-id="f7cf6-139">Модульное тестирование в .NET Core и .NET Standard</span><span class="sxs-lookup"><span data-stu-id="f7cf6-139">Unit Testing in .NET Core and .NET Standard</span></span>](https://docs.microsoft.com/dotnet/core/testing/)

>[!div class="step-by-step"]
<span data-ttu-id="f7cf6-140">[Назад](durable-azure-functions.md)
[Вперед](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="f7cf6-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
