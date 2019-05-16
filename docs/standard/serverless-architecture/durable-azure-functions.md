---
title: Устойчивые функции Azure — Бессерверных приложений
description: Устойчивые функции Azure расширения среды выполнения функций Azure для включения с отслеживанием состояния потоков работ в коде.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: f7ee74926d6658042120113b49dc763383881423
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643402"
---
# <a name="durable-azure-functions"></a><span data-ttu-id="53660-103">Устойчивые функции Azure</span><span class="sxs-lookup"><span data-stu-id="53660-103">Durable Azure functions</span></span>

<span data-ttu-id="53660-104">При создании бессерверных приложений с помощью функций Azure, ваши операции, обычно быть настроены для работы в режиме без отслеживания состояния.</span><span class="sxs-lookup"><span data-stu-id="53660-104">When creating serverless applications with Azure Functions, your operations will typically be designed to run in a stateless manner.</span></span> <span data-ttu-id="53660-105">Причина этого выбора обусловлено тем, как их масштабы платформы, становится сложно предсказать, какие серверы, на которой выполняется код.</span><span class="sxs-lookup"><span data-stu-id="53660-105">The reason for this design choice is because as the platform scales, it becomes difficult to know what servers the code is running on.</span></span> <span data-ttu-id="53660-106">Он также становится сложно предсказать, сколько экземпляров активны в любой момент.</span><span class="sxs-lookup"><span data-stu-id="53660-106">It also becomes difficult to know how many instances are active at any given point.</span></span> <span data-ttu-id="53660-107">Однако существуют классы приложений, требующих текущее состояние процесса, чтобы быть известны.</span><span class="sxs-lookup"><span data-stu-id="53660-107">However, there are classes of applications that require the current state of a process to be known.</span></span> <span data-ttu-id="53660-108">Рассмотрим процесс отправки заказа для Интернет-магазина.</span><span class="sxs-lookup"><span data-stu-id="53660-108">Consider the process of submitting an order to an online store.</span></span> <span data-ttu-id="53660-109">Возможно, операция извлечения рабочий процесс, состоящий из нескольких операций, которые нужно знать состояние процесса.</span><span class="sxs-lookup"><span data-stu-id="53660-109">The checkout operation might be a workflow that is composed of multiple operations that need to know the state of the process.</span></span> <span data-ttu-id="53660-110">Такие сведения могут включать складских запасов, если пользователь имеет все кредиты на своей учетной записью, а также результаты обработки кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="53660-110">Such information may include the product inventory, if the customer has any credits on their account, and also the results of processing the credit card.</span></span> <span data-ttu-id="53660-111">Эти операции легко может быть собственных внутренних рабочих процессов или даже службы от сторонних систем.</span><span class="sxs-lookup"><span data-stu-id="53660-111">These operations could easily be their own internal workflows or even services from third-party systems.</span></span>

<span data-ttu-id="53660-112">Различные шаблоны, существует, привлечению координации состояния приложения между внутренними и внешними системами.</span><span class="sxs-lookup"><span data-stu-id="53660-112">Various patterns exist today that assist with the coordination of application state between internal and external systems.</span></span> <span data-ttu-id="53660-113">Очень часто сталкивались с решениями, которые зависят от централизованные системы организации очереди, распределенное хранилище значений ключа или общих баз данных для управления этим состоянием.</span><span class="sxs-lookup"><span data-stu-id="53660-113">It's common to come across solutions that rely on centralized queuing systems, distributed key-value stores, or shared databases to manage that state.</span></span> <span data-ttu-id="53660-114">Тем не менее это все дополнительные ресурсы, которые теперь должны быть подготовлены и управляемые.</span><span class="sxs-lookup"><span data-stu-id="53660-114">However, these are all additional resources that now need to be provisioned and managed.</span></span> <span data-ttu-id="53660-115">В бессерверной среде ваш код может стать громоздкой, одновременное координирование действий с этими ресурсами вручную.</span><span class="sxs-lookup"><span data-stu-id="53660-115">In a serverless environment, your code could become cumbersome trying to coordinate with these resources manually.</span></span> <span data-ttu-id="53660-116">Функции Azure предлагает альтернативный подход для создания функции с отслеживанием состояния, вызывается устойчивых функций.</span><span class="sxs-lookup"><span data-stu-id="53660-116">Azure Functions offers an alternative for creating stateful functions called Durable Functions.</span></span>

<span data-ttu-id="53660-117">Устойчивые функции — это расширение, чтобы среда выполнения функций Azure, которая позволяет определять с отслеживанием состояния потоков работ в коде.</span><span class="sxs-lookup"><span data-stu-id="53660-117">Durable Functions is an extension to the Azure Functions runtime that enables the definition of stateful workflows in code.</span></span> <span data-ttu-id="53660-118">Путем разбиения рабочих процессов в действия, расширение устойчивых функций можно управлять состоянием, создавать контрольные точки ход выполнения и обработки распространения вызовов функций между серверами.</span><span class="sxs-lookup"><span data-stu-id="53660-118">By breaking down workflows into activities, the Durable Functions extension can manage state, create progress checkpoints, and handle the distribution of function calls across servers.</span></span> <span data-ttu-id="53660-119">В фоновом режиме он позволяет использовать учетную запись хранилища Azure для сохранения журнала выполнения, планируют функции действий и получения ответов.</span><span class="sxs-lookup"><span data-stu-id="53660-119">In the background, it makes use of an Azure Storage account to persist execution history, schedule activity functions and retrieve responses.</span></span> <span data-ttu-id="53660-120">Бессерверном коде никогда не должна взаимодействовать с сохраненной информации в этой учетной записи, которое обычно не что-то с помощью которого разработчики должны взаимодействовать.</span><span class="sxs-lookup"><span data-stu-id="53660-120">Your serverless code should never interact with persisted information in that storage account, and is typically not something with which developers need to interact.</span></span>

## <a name="triggering-a-stateful-workflow"></a><span data-ttu-id="53660-121">Активация с отслеживанием состояния рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="53660-121">Triggering a stateful workflow</span></span>

<span data-ttu-id="53660-122">С отслеживанием состояния рабочих процессов в устойчивых функциях можно разделить на два встроенных компонентов; триггеры оркестрации и действия.</span><span class="sxs-lookup"><span data-stu-id="53660-122">Stateful workflows in Durable Functions can be broken down into two intrinsic components; orchestration and activity triggers.</span></span> <span data-ttu-id="53660-123">Триггеры и привязки, основные компоненты, используемые функциями Azure, позволяя вашим функциям бессерверной уведомлять для запуска, получать входные и возврата результатов.</span><span class="sxs-lookup"><span data-stu-id="53660-123">Triggers and bindings are core components used by Azure Functions to enable your serverless functions to be notified when to start, receive input, and return results.</span></span>

### <a name="working-with-the-orchestration-client"></a><span data-ttu-id="53660-124">Работа с клиента Оркестрации</span><span class="sxs-lookup"><span data-stu-id="53660-124">Working with the Orchestration client</span></span>

<span data-ttu-id="53660-125">Согласование уникальны, по сравнению с другим стилем активированные операций в функциях Azure.</span><span class="sxs-lookup"><span data-stu-id="53660-125">Orchestrations are unique when compared to other styles of triggered operations in Azure Functions.</span></span> <span data-ttu-id="53660-126">Устойчивые функции обеспечивают выполнение функций, которые может длиться несколько часов или даже дней.</span><span class="sxs-lookup"><span data-stu-id="53660-126">Durable Functions enables the execution of functions that may take hours or even days to complete.</span></span> <span data-ttu-id="53660-127">Такой тип поведения поставляется с необходимостью возможность проверить состояние выполнения оркестрации, заблаговременно завершать, или отправлять уведомления о внешних событий.</span><span class="sxs-lookup"><span data-stu-id="53660-127">That type of behavior comes with the need to able to check the status of a running orchestration, preemptively terminate, or send notifications of external events.</span></span>

<span data-ttu-id="53660-128">В таких случаях предоставляет расширение устойчивых функций `DurableOrchestrationClient` класс, который позволяет взаимодействовать с оркестрацией в функции.</span><span class="sxs-lookup"><span data-stu-id="53660-128">For such cases, the Durable Functions extension provides the `DurableOrchestrationClient` class that allows you to interact with orchestrated functions.</span></span> <span data-ttu-id="53660-129">Вы получаете доступ к клиенту оркестрации с помощью `OrchestrationClientAttribute` привязки.</span><span class="sxs-lookup"><span data-stu-id="53660-129">You get access to the orchestration client by using the `OrchestrationClientAttribute` binding.</span></span> <span data-ttu-id="53660-130">Как правило, следует включить этот атрибут с другим типом триггера, такие как `HttpTrigger` или `ServiceBusTrigger`.</span><span class="sxs-lookup"><span data-stu-id="53660-130">Generally, you would include this attribute with another trigger type, such as an `HttpTrigger` or `ServiceBusTrigger`.</span></span> <span data-ttu-id="53660-131">После активации функции источника клиента оркестрации можно использовать для запуска функции оркестратора.</span><span class="sxs-lookup"><span data-stu-id="53660-131">Once the source function has been triggered, the orchestration client can be used to start an orchestrator function.</span></span>

```csharp
[FunctionName("KickOff")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient<orchestrationClient>)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

### <a name="the-orchestrator-function"></a><span data-ttu-id="53660-132">Функции оркестратора</span><span class="sxs-lookup"><span data-stu-id="53660-132">The orchestrator function</span></span>

<span data-ttu-id="53660-133">Создание примечаний к функции с помощью OrchestrationTriggerAttribute знаки "функции Azure" этой функции как функции оркестратора.</span><span class="sxs-lookup"><span data-stu-id="53660-133">Annotating a function with the OrchestrationTriggerAttribute in Azure Functions marks that function as an orchestrator function.</span></span> <span data-ttu-id="53660-134">Он отвечает за управление различными действиями, составляющих с отслеживанием состояния рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="53660-134">It's responsible for managing the various activities that make up your stateful workflow.</span></span>

<span data-ttu-id="53660-135">Функции оркестратора не можете использовать привязок, отличных от OrchestrationTriggerAttribute.</span><span class="sxs-lookup"><span data-stu-id="53660-135">Orchestrator functions are unable to make use of bindings other than the OrchestrationTriggerAttribute.</span></span> <span data-ttu-id="53660-136">Этот атрибут может использоваться только с типом параметра DurableOrchestrationContext.</span><span class="sxs-lookup"><span data-stu-id="53660-136">This attribute can only be used with a parameter type of DurableOrchestrationContext.</span></span> <span data-ttu-id="53660-137">Нет входных данных может использоваться, так как входные данные в сигнатуре функции десериализации не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="53660-137">No other inputs can be used since deserialization of inputs in the function signature isn't supported.</span></span> <span data-ttu-id="53660-138">Чтобы получить входные данные с помощью клиента оркестрации, GetInput\<T\> метод должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="53660-138">To get inputs provided by the orchestration client, the GetInput\<T\> method must be used.</span></span>

<span data-ttu-id="53660-139">Кроме того, типы возвращаемого значения функций оркестратора должен быть либо void, задачи или сериализуемые значения JSON.</span><span class="sxs-lookup"><span data-stu-id="53660-139">Also, the return types of orchestration functions must be either void, Task, or a JSON serializable value.</span></span>

> <span data-ttu-id="53660-140">*Код обработки ошибок были опущены для краткости*</span><span class="sxs-lookup"><span data-stu-id="53660-140">*Error handling code has been left out for brevity*</span></span>

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<string>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

<span data-ttu-id="53660-141">Несколько экземпляров оркестрации может быть запущена и работает, в то же время.</span><span class="sxs-lookup"><span data-stu-id="53660-141">Multiple instances of an orchestration can be started and running at the same time.</span></span> <span data-ttu-id="53660-142">Вызов `StartNewAsync` метод `DurableOrchestrationClient` запускает новый экземпляр оркестрации.</span><span class="sxs-lookup"><span data-stu-id="53660-142">Calling the `StartNewAsync` method on the `DurableOrchestrationClient` launches a new instance of the orchestration.</span></span> <span data-ttu-id="53660-143">Этот метод возвращает `Task<string>` которая завершается при запуске оркестрации.</span><span class="sxs-lookup"><span data-stu-id="53660-143">The method returns a `Task<string>` that completes when the orchestration has started.</span></span> <span data-ttu-id="53660-144">Исключение типа `TimeoutException` получает создается, если оркестрации не запущен в течение 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="53660-144">An exception of type `TimeoutException` gets thrown if the orchestration hasn't started within 30 seconds.</span></span>

<span data-ttu-id="53660-145">Завершенные `Task<string>` из `StartNewAsync` должен содержать уникальный идентификатор экземпляра оркестрации.</span><span class="sxs-lookup"><span data-stu-id="53660-145">The completed `Task<string>` from `StartNewAsync` should contain the unique ID of the orchestration instance.</span></span> <span data-ttu-id="53660-146">Этот идентификатор экземпляра можно использовать для вызова операций в этой определенной оркестрации.</span><span class="sxs-lookup"><span data-stu-id="53660-146">This instance ID can be used to invoke operations on that specific orchestration.</span></span> <span data-ttu-id="53660-147">Оркестрация можно запросить состояние или отправить уведомления о событиях.</span><span class="sxs-lookup"><span data-stu-id="53660-147">The orchestration can be queried for the status or sent event notifications.</span></span>

### <a name="the-activity-functions"></a><span data-ttu-id="53660-148">Функции действий</span><span class="sxs-lookup"><span data-stu-id="53660-148">The activity functions</span></span>

<span data-ttu-id="53660-149">Функции действий являются отдельные операции, которые составляются друг с другом в пределах функции оркестрации для создания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="53660-149">Activity functions are the discrete operations that get composed together within an orchestration function to create the workflow.</span></span> <span data-ttu-id="53660-150">Вот, где будет выполняться большая часть фактическую работу.</span><span class="sxs-lookup"><span data-stu-id="53660-150">Here is where most of actual work would take place.</span></span> <span data-ttu-id="53660-151">Они представляют бизнес-логику, долго выполняющихся процессов и части головоломки, чтобы более крупного решения.</span><span class="sxs-lookup"><span data-stu-id="53660-151">They represent the business logic, long running processes, and the puzzle pieces to a larger solution.</span></span>

<span data-ttu-id="53660-152">`ActivityTriggerAttribute` Создаются заметки для типа параметра функции `DurableActivityContext`.</span><span class="sxs-lookup"><span data-stu-id="53660-152">The `ActivityTriggerAttribute` is used to annotate a function parameter of type `DurableActivityContext`.</span></span> <span data-ttu-id="53660-153">С помощью заметки информирует среду CLR, что функция предназначен для использования в качестве функции действия.</span><span class="sxs-lookup"><span data-stu-id="53660-153">Using the annotation informs the runtime that the function is intended to be used as an activity function.</span></span> <span data-ttu-id="53660-154">Входные значения для функции действий можно получить с помощью `GetInput<T>` метод `DurableActivityContext` параметра.</span><span class="sxs-lookup"><span data-stu-id="53660-154">Input values to activity functions are retrieved using the `GetInput<T>` method of the `DurableActivityContext` parameter.</span></span>

<span data-ttu-id="53660-155">Подобно функции оркестрации, типы возвращаемого значения функции действий необходимо быть либо void, задачи или сериализуемые значения JSON.</span><span class="sxs-lookup"><span data-stu-id="53660-155">Similar to orchestration functions, the return types of activity functions must be either void, Task, or a JSON serializable value.</span></span>

<span data-ttu-id="53660-156">Все необработанные исключения, возникающие в функциях действий get отправляется вызывающей функции orchestrator и представлены в виде `TaskFailedException`.</span><span class="sxs-lookup"><span data-stu-id="53660-156">Any unhandled exceptions that get thrown within activity functions will get sent up to the calling orchestrator function and presented as a `TaskFailedException`.</span></span> <span data-ttu-id="53660-157">На этом этапе можно выявить ошибки и вход оркестратора и действия можно повторить.</span><span class="sxs-lookup"><span data-stu-id="53660-157">At this point, the error can be caught and logged in the orchestrator, and the activity can be retried.</span></span>

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a><span data-ttu-id="53660-158">Рекомендуемые ресурсы</span><span class="sxs-lookup"><span data-stu-id="53660-158">Recommended resources</span></span>

* [<span data-ttu-id="53660-159">Устойчивые функции</span><span class="sxs-lookup"><span data-stu-id="53660-159">Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [<span data-ttu-id="53660-160">Привязки для устойчивых функций</span><span class="sxs-lookup"><span data-stu-id="53660-160">Bindings for Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
* [<span data-ttu-id="53660-161">Управление экземплярами в устойчивых функциях</span><span class="sxs-lookup"><span data-stu-id="53660-161">Manage instances in Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
><span data-ttu-id="53660-162">[Назад](event-grid.md)
>[Вперед](orchestration-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="53660-162">[Previous](event-grid.md)
[Next](orchestration-patterns.md)</span></span>
