---
title: Устойчивые функции Azure — бессерверные приложения
description: Устойчивые функции Azure расширяют среду выполнения Функций Azure, чтобы реализовать рабочие процессы с отслеживанием состояния в коде.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2c0ad086640409ac187c3aa882add4d6b39b6ff9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522865"
---
# <a name="durable-azure-functions"></a><span data-ttu-id="75843-103">Устойчивые функции Azure</span><span class="sxs-lookup"><span data-stu-id="75843-103">Durable Azure functions</span></span>

<span data-ttu-id="75843-104">При создании бессерверных приложений с помощью Функций Azure операции обычно проектируются таким образом, чтобы выполняться без отслеживания состояния.</span><span class="sxs-lookup"><span data-stu-id="75843-104">When creating serverless applications with Azure Functions, your operations will typically be designed to run in a stateless manner.</span></span> <span data-ttu-id="75843-105">Причина выбора этого варианта проектирования заключается в том, что при масштабировании платформы становится трудно определить, на каких серверах выполняется код.</span><span class="sxs-lookup"><span data-stu-id="75843-105">The reason for this design choice is because as the platform scales, it becomes difficult to know what servers the code is running on.</span></span> <span data-ttu-id="75843-106">Кроме того, сложно понять, сколько экземпляров активно в любой момент.</span><span class="sxs-lookup"><span data-stu-id="75843-106">It also becomes difficult to know how many instances are active at any given point.</span></span> <span data-ttu-id="75843-107">Однако существуют классы приложений, которым требуется знать текущее состояние процесса.</span><span class="sxs-lookup"><span data-stu-id="75843-107">However, there are classes of applications that require the current state of a process to be known.</span></span> <span data-ttu-id="75843-108">Рассмотрим процесс отправки заказа в интернет-магазин.</span><span class="sxs-lookup"><span data-stu-id="75843-108">Consider the process of submitting an order to an online store.</span></span> <span data-ttu-id="75843-109">Операция проверки может быть рабочим процессом, состоящим из нескольких операций, которым необходимо знать состояние процесса.</span><span class="sxs-lookup"><span data-stu-id="75843-109">The checkout operation might be a workflow that is composed of multiple operations that need to know the state of the process.</span></span> <span data-ttu-id="75843-110">Такие сведения могут включать в себя запасы продукта, если ли у клиента кредиты по своей учетной записи, а также результаты обработки кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="75843-110">Such information may include the product inventory, if the customer has any credits on their account, and also the results of processing the credit card.</span></span> <span data-ttu-id="75843-111">Эти операции могут быть внутренними рабочими процессами или даже службами сторонних систем.</span><span class="sxs-lookup"><span data-stu-id="75843-111">These operations could easily be their own internal workflows or even services from third-party systems.</span></span>

<span data-ttu-id="75843-112">В настоящее время существуют различные шаблоны, которые помогают обеспечить координацию состояния приложения между внутренними и внешними системами.</span><span class="sxs-lookup"><span data-stu-id="75843-112">Various patterns exist today that assist with the coordination of application state between internal and external systems.</span></span> <span data-ttu-id="75843-113">Часто встречаются решения, использующие для управления этим состоянием централизованные системы постановки в очередь, распределенные хранилища пар "ключ — значение" или общие базы данных.</span><span class="sxs-lookup"><span data-stu-id="75843-113">It's common to come across solutions that rely on centralized queuing systems, distributed key-value stores, or shared databases to manage that state.</span></span> <span data-ttu-id="75843-114">Однако все эти дополнительные ресурсы теперь необходимо подготовить к работе и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="75843-114">However, these are all additional resources that now need to be provisioned and managed.</span></span> <span data-ttu-id="75843-115">Если вы будете пытаться вручную координировать эти ресурсы в бессерверной среде, код может стать громоздким.</span><span class="sxs-lookup"><span data-stu-id="75843-115">In a serverless environment, your code could become cumbersome trying to coordinate with these resources manually.</span></span> <span data-ttu-id="75843-116">Функции Azure предлагают альтернативу для создания функций с отслеживанием состояния, которые называются Устойчивыми функциями.</span><span class="sxs-lookup"><span data-stu-id="75843-116">Azure Functions offers an alternative for creating stateful functions called Durable Functions.</span></span>

<span data-ttu-id="75843-117">Устойчивые функции являются расширением среды выполнения Функций Azure, которое обеспечивает внедрение определения рабочих процессов с отслеживанием состояния в коде.</span><span class="sxs-lookup"><span data-stu-id="75843-117">Durable Functions is an extension to the Azure Functions runtime that enables the definition of stateful workflows in code.</span></span> <span data-ttu-id="75843-118">Разбивая рабочие процессы на действия, расширение Устойчивые функции может управлять состоянием, создавать контрольные точки выполнения и обрабатывать распределение вызовов функций между серверами.</span><span class="sxs-lookup"><span data-stu-id="75843-118">By breaking down workflows into activities, the Durable Functions extension can manage state, create progress checkpoints, and handle the distribution of function calls across servers.</span></span> <span data-ttu-id="75843-119">В фоновом режиме используется учетная запись службы хранилища Azure для сохранения журнала выполнения, планирования функций действий и получения ответов.</span><span class="sxs-lookup"><span data-stu-id="75843-119">In the background, it makes use of an Azure Storage account to persist execution history, schedule activity functions and retrieve responses.</span></span> <span data-ttu-id="75843-120">Ваш бессерверный код не должен взаимодействовать с сохраненными сведениями в этой учетной записи хранения, и, как правило, разработчикам это не нужно.</span><span class="sxs-lookup"><span data-stu-id="75843-120">Your serverless code should never interact with persisted information in that storage account, and is typically not something with which developers need to interact.</span></span>

## <a name="triggering-a-stateful-workflow"></a><span data-ttu-id="75843-121">Активация рабочего процесса с отслеживанием состояния</span><span class="sxs-lookup"><span data-stu-id="75843-121">Triggering a stateful workflow</span></span>

<span data-ttu-id="75843-122">Рабочие процессы с отслеживанием состояния в Устойчивых функциях можно разделить на два встроенных компонента: оркестрация и триггеры действия.</span><span class="sxs-lookup"><span data-stu-id="75843-122">Stateful workflows in Durable Functions can be broken down into two intrinsic components; orchestration and activity triggers.</span></span> <span data-ttu-id="75843-123">Триггеры и привязки — это основные компоненты, используемые Функциями Azure для уведомления бессерверных функций о необходимости запуска, получении входных данных и возврате результатов.</span><span class="sxs-lookup"><span data-stu-id="75843-123">Triggers and bindings are core components used by Azure Functions to enable your serverless functions to be notified when to start, receive input, and return results.</span></span>

### <a name="working-with-the-orchestration-client"></a><span data-ttu-id="75843-124">Работа с клиентом оркестрации</span><span class="sxs-lookup"><span data-stu-id="75843-124">Working with the Orchestration client</span></span>

<span data-ttu-id="75843-125">В Функциях Azure оркестрация является уникальной операцией по сравнению с другими стилями активируемых операций.</span><span class="sxs-lookup"><span data-stu-id="75843-125">Orchestrations are unique when compared to other styles of triggered operations in Azure Functions.</span></span> <span data-ttu-id="75843-126">Устойчивые функции позволяют запускать функции, выполнение которых может занять несколько часов или даже дней.</span><span class="sxs-lookup"><span data-stu-id="75843-126">Durable Functions enables the execution of functions that may take hours or even days to complete.</span></span> <span data-ttu-id="75843-127">Такому типу поведения нужна возможность проверять состояние выполняющейся оркестрации, преждевременно завершать и отправлять уведомления о внешних событиях.</span><span class="sxs-lookup"><span data-stu-id="75843-127">That type of behavior comes with the need to able to check the status of a running orchestration, preemptively terminate, or send notifications of external events.</span></span>

<span data-ttu-id="75843-128">В таких случаях расширение "Устойчивые функции" предоставляет класс `DurableOrchestrationClient`, который позволяет взаимодействовать с оркестрируемыми функциями.</span><span class="sxs-lookup"><span data-stu-id="75843-128">For such cases, the Durable Functions extension provides the `DurableOrchestrationClient` class that allows you to interact with orchestrated functions.</span></span> <span data-ttu-id="75843-129">Получить доступ к клиенту оркестрации можно с помощью привязки `OrchestrationClientAttribute`.</span><span class="sxs-lookup"><span data-stu-id="75843-129">You get access to the orchestration client by using the `OrchestrationClientAttribute` binding.</span></span> <span data-ttu-id="75843-130">Обычно, этот атрибут следует включать в другой тип триггера, например `HttpTrigger` или `ServiceBusTrigger`.</span><span class="sxs-lookup"><span data-stu-id="75843-130">Generally, you would include this attribute with another trigger type, such as an `HttpTrigger` or `ServiceBusTrigger`.</span></span> <span data-ttu-id="75843-131">После активации исходной функции клиент оркестрации можно использовать для запуска функции оркестратора.</span><span class="sxs-lookup"><span data-stu-id="75843-131">Once the source function has been triggered, the orchestration client can be used to start an orchestrator function.</span></span>

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

### <a name="the-orchestrator-function"></a><span data-ttu-id="75843-132">Функция оркестратора</span><span class="sxs-lookup"><span data-stu-id="75843-132">The orchestrator function</span></span>

<span data-ttu-id="75843-133">Чтобы пометить функцию как функцию оркестратора, нужно аннотировать ее с помощью атрибута OrchestrationTriggerAttribute в Функциях Azure.</span><span class="sxs-lookup"><span data-stu-id="75843-133">Annotating a function with the OrchestrationTriggerAttribute in Azure Functions marks that function as an orchestrator function.</span></span> <span data-ttu-id="75843-134">Она отвечает за управление различными действиями, которые составляют рабочий процесс с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="75843-134">It's responsible for managing the various activities that make up your stateful workflow.</span></span>

<span data-ttu-id="75843-135">Функции оркестратора не могут использовать привязки, отличные от OrchestrationTriggerAttribute.</span><span class="sxs-lookup"><span data-stu-id="75843-135">Orchestrator functions are unable to make use of bindings other than the OrchestrationTriggerAttribute.</span></span> <span data-ttu-id="75843-136">Этот атрибут может использоваться только с типом параметра DurableOrchestrationContext.</span><span class="sxs-lookup"><span data-stu-id="75843-136">This attribute can only be used with a parameter type of DurableOrchestrationContext.</span></span> <span data-ttu-id="75843-137">Другие входные данные не могут использоваться, так как десериализация входных данных в сигнатуре функции не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="75843-137">No other inputs can be used since deserialization of inputs in the function signature isn't supported.</span></span> <span data-ttu-id="75843-138">Чтобы получить входные данные, предоставляемые клиентом оркестрации, необходимо использовать метод GetInput\<T\>.</span><span class="sxs-lookup"><span data-stu-id="75843-138">To get inputs provided by the orchestration client, the GetInput\<T\> method must be used.</span></span>

<span data-ttu-id="75843-139">Кроме того, типы возвращаемых значений функций оркестрации должны иметь значение void, Task или сериализуемое значение JSON.</span><span class="sxs-lookup"><span data-stu-id="75843-139">Also, the return types of orchestration functions must be either void, Task, or a JSON serializable value.</span></span>

> <span data-ttu-id="75843-140">*Код обработки ошибок опущен для краткости*.</span><span class="sxs-lookup"><span data-stu-id="75843-140">*Error handling code has been left out for brevity*</span></span>

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

<span data-ttu-id="75843-141">Несколько экземпляров оркестрации могут быть запущены и выполняться в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="75843-141">Multiple instances of an orchestration can be started and running at the same time.</span></span> <span data-ttu-id="75843-142">Вызов метода `StartNewAsync` в классе `DurableOrchestrationClient` запускает новый экземпляр оркестрации.</span><span class="sxs-lookup"><span data-stu-id="75843-142">Calling the `StartNewAsync` method on the `DurableOrchestrationClient` launches a new instance of the orchestration.</span></span> <span data-ttu-id="75843-143">Метод возвращает задачу `Task<string>`, которая завершается при запуске оркестрации.</span><span class="sxs-lookup"><span data-stu-id="75843-143">The method returns a `Task<string>` that completes when the orchestration has started.</span></span> <span data-ttu-id="75843-144">Исключение типа `TimeoutException` возникает, если оркестрация не начата в течение 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="75843-144">An exception of type `TimeoutException` gets thrown if the orchestration hasn't started within 30 seconds.</span></span>

<span data-ttu-id="75843-145">Завершенная задача `Task<string>` из метода `StartNewAsync` должна содержать уникальный идентификатор экземпляра оркестрации.</span><span class="sxs-lookup"><span data-stu-id="75843-145">The completed `Task<string>` from `StartNewAsync` should contain the unique ID of the orchestration instance.</span></span> <span data-ttu-id="75843-146">Этот идентификатор экземпляра можно использовать, чтобы вызвать операции для конкретной оркестрации.</span><span class="sxs-lookup"><span data-stu-id="75843-146">This instance ID can be used to invoke operations on that specific orchestration.</span></span> <span data-ttu-id="75843-147">Оркестрацию можно использовать для запроса состояния или отправки уведомлений о событиях.</span><span class="sxs-lookup"><span data-stu-id="75843-147">The orchestration can be queried for the status or sent event notifications.</span></span>

### <a name="the-activity-functions"></a><span data-ttu-id="75843-148">Функции действий</span><span class="sxs-lookup"><span data-stu-id="75843-148">The activity functions</span></span>

<span data-ttu-id="75843-149">Функции действий — это отдельные операции, которые объединяются в функцию оркестрации для создания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="75843-149">Activity functions are the discrete operations that get composed together within an orchestration function to create the workflow.</span></span> <span data-ttu-id="75843-150">Здесь выполняется большая часть реальной работы.</span><span class="sxs-lookup"><span data-stu-id="75843-150">Here is where most of actual work would take place.</span></span> <span data-ttu-id="75843-151">Они представляют собой бизнес-логику, длительные процессы и элементы головоломки, формирующие более крупное решение.</span><span class="sxs-lookup"><span data-stu-id="75843-151">They represent the business logic, long running processes, and the puzzle pieces to a larger solution.</span></span>

<span data-ttu-id="75843-152">`ActivityTriggerAttribute` используется для добавления аннотации в параметр функции типа `DurableActivityContext`.</span><span class="sxs-lookup"><span data-stu-id="75843-152">The `ActivityTriggerAttribute` is used to annotate a function parameter of type `DurableActivityContext`.</span></span> <span data-ttu-id="75843-153">С помощью аннотации среда выполнения информируется о том, что функция предназначена для использования в качестве функции действия.</span><span class="sxs-lookup"><span data-stu-id="75843-153">Using the annotation informs the runtime that the function is intended to be used as an activity function.</span></span> <span data-ttu-id="75843-154">Входные значения для функций действий извлекаются с помощью метода `GetInput<T>` параметра `DurableActivityContext`.</span><span class="sxs-lookup"><span data-stu-id="75843-154">Input values to activity functions are retrieved using the `GetInput<T>` method of the `DurableActivityContext` parameter.</span></span>

<span data-ttu-id="75843-155">Подобно функциям оркестрации типы возвращаемых значений функций действий должны иметь значение void, Task или сериализуемое значение JSON.</span><span class="sxs-lookup"><span data-stu-id="75843-155">Similar to orchestration functions, the return types of activity functions must be either void, Task, or a JSON serializable value.</span></span>

<span data-ttu-id="75843-156">Все необработанные исключения, которые вызываются в функциях действий, будут отправлены в вызывающую функцию оркестратора и представлены как `TaskFailedException`.</span><span class="sxs-lookup"><span data-stu-id="75843-156">Any unhandled exceptions that get thrown within activity functions will get sent up to the calling orchestrator function and presented as a `TaskFailedException`.</span></span> <span data-ttu-id="75843-157">На этом этапе ошибка может быть перехвачена и зарегистрирована в оркестраторе, и действие можно повторить.</span><span class="sxs-lookup"><span data-stu-id="75843-157">At this point, the error can be caught and logged in the orchestrator, and the activity can be retried.</span></span>

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a><span data-ttu-id="75843-158">Рекомендуемые ресурсы</span><span class="sxs-lookup"><span data-stu-id="75843-158">Recommended resources</span></span>

- [<span data-ttu-id="75843-159">Цепочки функций в устойчивых функциях — пример последовательности Hello</span><span class="sxs-lookup"><span data-stu-id="75843-159">Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="75843-160">Привязки для Устойчивых функций (Функции Azure)</span><span class="sxs-lookup"><span data-stu-id="75843-160">Bindings for Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
- [<span data-ttu-id="75843-161">Управление экземплярами в Устойчивых функциях в Azure</span><span class="sxs-lookup"><span data-stu-id="75843-161">Manage instances in Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
><span data-ttu-id="75843-162">[Назад](event-grid.md)
>[Вперед](orchestration-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="75843-162">[Previous](event-grid.md)
[Next](orchestration-patterns.md)</span></span>
