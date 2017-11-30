---
title: "Использование асинхронного шаблона, основанного на задачах"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90b2a36f0e6bf06b0fefe2191d5b17c9c07d1588
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a><span data-ttu-id="e79d4-102">Использование асинхронного шаблона, основанного на задачах</span><span class="sxs-lookup"><span data-stu-id="e79d4-102">Consuming the Task-based Asynchronous Pattern</span></span>
<span data-ttu-id="e79d4-103">При работе асинхронными операциями с использованием асинхронного шаблона, основанного на задачах, можно использовать обратные вызовы для реализации неблокирующего ожидания.</span><span class="sxs-lookup"><span data-stu-id="e79d4-103">When you use the Task-based Asynchronous Pattern (TAP) to work with asynchronous operations, you can use callbacks to achieve waiting without blocking.</span></span>  <span data-ttu-id="e79d4-104">Для выполнения задач, это достигается с помощью методов например <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e79d4-104">For tasks, this is achieved through methods such as <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e79d4-105">Поддержка асинхронных операций на основе языка скрывает обратные вызовы, разрешая асинхронным операциям находиться в режиме ожидания в нормальном потоке управления, а код, созданный компилятором, предоставляет поддержку на том же уровне API.</span><span class="sxs-lookup"><span data-stu-id="e79d4-105">Language-based asynchronous support hides callbacks by allowing asynchronous operations to be awaited within normal control flow, and compiler-generated code provides this same API-level support.</span></span>  
  
## <a name="suspending-execution-with-await"></a><span data-ttu-id="e79d4-106">Приостановление выполнения с помощью Await</span><span class="sxs-lookup"><span data-stu-id="e79d4-106">Suspending Execution with Await</span></span>  
 <span data-ttu-id="e79d4-107">Начиная с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], можно использовать [await](~/docs/csharp/language-reference/keywords/await.md) ключевого слова C# и [оператор Await](~/docs/visual-basic/language-reference/operators/await-operator.md) в Visual Basic, чтобы асинхронно ожидать <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601> объектов.</span><span class="sxs-lookup"><span data-stu-id="e79d4-107">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], you can use the [await](~/docs/csharp/language-reference/keywords/await.md) keyword in C# and the [Await Operator](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic to asynchronously await <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> objects.</span></span> <span data-ttu-id="e79d4-108">Когда ожидает <xref:System.Threading.Tasks.Task>, `await` выражение имеет тип `void`.</span><span class="sxs-lookup"><span data-stu-id="e79d4-108">When you're awaiting a <xref:System.Threading.Tasks.Task>, the `await` expression is of type `void`.</span></span> <span data-ttu-id="e79d4-109">Когда ожидает <xref:System.Threading.Tasks.Task%601>, `await` выражение имеет тип `TResult`.</span><span class="sxs-lookup"><span data-stu-id="e79d4-109">When you're awaiting a <xref:System.Threading.Tasks.Task%601>, the `await` expression is of type `TResult`.</span></span> <span data-ttu-id="e79d4-110">Выражение `await` должно находиться в теле асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="e79d4-110">An `await` expression must occur inside the body of an asynchronous method.</span></span> <span data-ttu-id="e79d4-111">Дополнительные сведения о поддержке языков C# и Visual Basic в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] см. в спецификациях языка C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e79d4-111">For more information about C# and Visual Basic language support in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], see the C# and Visual Basic language specifications.</span></span>  
  
 <span data-ttu-id="e79d4-112">На самом деле функция ожидания реализуется с помощью установки обратного вызова для задачи с помощью продолжения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-112">Under the covers, the await functionality installs a callback on the task by using a continuation.</span></span>  <span data-ttu-id="e79d4-113">Этот обратный вызов возобновляет асинхронный методы в точке остановки.</span><span class="sxs-lookup"><span data-stu-id="e79d4-113">This callback resumes the asynchronous method at the point of suspension.</span></span> <span data-ttu-id="e79d4-114">Когда асинхронного метода возобновляется, если ожидаемая операция успешно завершена и был <xref:System.Threading.Tasks.Task%601>, ее `TResult` возвращается.</span><span class="sxs-lookup"><span data-stu-id="e79d4-114">When the asynchronous method is resumed, if the awaited operation completed successfully and was a <xref:System.Threading.Tasks.Task%601>, its `TResult` is returned.</span></span>  <span data-ttu-id="e79d4-115">Если <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> инициировав завершился <xref:System.Threading.Tasks.TaskStatus.Canceled> состояние, <xref:System.OperationCanceledException> исключение.</span><span class="sxs-lookup"><span data-stu-id="e79d4-115">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state, an <xref:System.OperationCanceledException> exception is thrown.</span></span>  <span data-ttu-id="e79d4-116">Если <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> инициировав завершился <xref:System.Threading.Tasks.TaskStatus.Faulted> состоянии, возникает исключение, вызвавшее его сбой.</span><span class="sxs-lookup"><span data-stu-id="e79d4-116">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state, the exception that caused it to fault is thrown.</span></span> <span data-ttu-id="e79d4-117">`Task` может завершиться с ошибкой из-за нескольких исключений, но распространяется только одно из этих исключений.</span><span class="sxs-lookup"><span data-stu-id="e79d4-117">A `Task` can fault as a result of multiple exceptions, but only one of these exceptions is propagated.</span></span> <span data-ttu-id="e79d4-118">Тем не менее <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> возвращает <xref:System.AggregateException> исключение, которое содержит все ошибки.</span><span class="sxs-lookup"><span data-stu-id="e79d4-118">However, the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property returns an <xref:System.AggregateException> exception that contains all the errors.</span></span>  
  
 <span data-ttu-id="e79d4-119">Если контекст синхронизации (<xref:System.Threading.SynchronizationContext> объекта) связан с потоком, который выполнялся асинхронный метод во время приостановки (например, если <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> свойство не `null`), продолжается, асинхронный метод же контекст синхронизации, используя контекст <xref:System.Threading.SynchronizationContext.Post%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e79d4-119">If a synchronization context (<xref:System.Threading.SynchronizationContext> object) is associated with the thread that was executing the asynchronous method at the time of suspension (for example, if the <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> property is not `null`), the asynchronous method resumes on that same synchronization context by using the context’s <xref:System.Threading.SynchronizationContext.Post%2A> method.</span></span> <span data-ttu-id="e79d4-120">В противном случае он основывается на планировщик задач (<xref:System.Threading.Tasks.TaskScheduler> объекта), являвшиеся текущими во время приостановки выполнения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-120">Otherwise, it relies on the task scheduler (<xref:System.Threading.Tasks.TaskScheduler> object) that was current at the time of suspension.</span></span> <span data-ttu-id="e79d4-121">Как правило, это планировщик по умолчанию (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), который предназначенный для пула потоков.</span><span class="sxs-lookup"><span data-stu-id="e79d4-121">Typically, this is the default task scheduler (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), which targets the thread pool.</span></span> <span data-ttu-id="e79d4-122">Этот планировщик задач определяет, следует ли возобновить приостановленную асинхронную операцию в тот момент, в который она была завершена, или следует ли запланировать возобновление.</span><span class="sxs-lookup"><span data-stu-id="e79d4-122">This task scheduler determines whether the awaited asynchronous operation should resume where it completed or whether the resumption should be scheduled.</span></span> <span data-ttu-id="e79d4-123">Планировщик по умолчанию обычно разрешает продолжение выполнения в потоке, который был завершен операцией.</span><span class="sxs-lookup"><span data-stu-id="e79d4-123">The default scheduler typically allows the continuation to run on the thread that the awaited operation completed.</span></span>  
  
 <span data-ttu-id="e79d4-124">При вызове асинхронного метода он синхронно выполняет тело функции до первого выражения await для ожидаемого экземпляра, которое еще не было завершено, и в этот момент управление передается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="e79d4-124">When an asynchronous method is called, it synchronously executes the body of the function up until the first await expression on an awaitable instance that has not yet completed, at which point the invocation returns to the caller.</span></span> <span data-ttu-id="e79d4-125">Если асинхронный метод не возвращает `void`, <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> объект возвращается для вычисления текущего представления.</span><span class="sxs-lookup"><span data-stu-id="e79d4-125">If the asynchronous method does not return `void`, a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object is returned to represent the ongoing computation.</span></span> <span data-ttu-id="e79d4-126">В асинхронный метод отличным от void, если встречается оператор return или достижении конца тела метода завершения задачи в <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> конечное состояние.</span><span class="sxs-lookup"><span data-stu-id="e79d4-126">In a non-void asynchronous method, if a return statement is encountered or the end of the method body is reached, the task is completed in the <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> final state.</span></span> <span data-ttu-id="e79d4-127">Если необработанное исключение в результате управления передано из тела асинхронного метода, задача завершается в <xref:System.Threading.Tasks.TaskStatus.Faulted> состояние.</span><span class="sxs-lookup"><span data-stu-id="e79d4-127">If an unhandled exception causes control to leave the body of the asynchronous method, the task ends in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state.</span></span> <span data-ttu-id="e79d4-128">Если это исключение является <xref:System.OperationCanceledException>, задача завершается вместо этого в <xref:System.Threading.Tasks.TaskStatus.Canceled> состояние.</span><span class="sxs-lookup"><span data-stu-id="e79d4-128">If that exception is an <xref:System.OperationCanceledException>, the task instead ends in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state.</span></span> <span data-ttu-id="e79d4-129">Таким образом, результат или исключение в конечном счете будут сформированы.</span><span class="sxs-lookup"><span data-stu-id="e79d4-129">In this manner, the result or exception is eventually published.</span></span>  
  
 <span data-ttu-id="e79d4-130">Существует несколько важных вариантов такого поведения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-130">There are several important variations of this behavior.</span></span>  <span data-ttu-id="e79d4-131">Для повышения производительности, если к моменту ожидания задачи оказывается, что задача уже завершена, то управление не освобождается и функция продолжает выполнение.</span><span class="sxs-lookup"><span data-stu-id="e79d4-131">For performance reasons, if a task has already completed by the time the task is awaited, control is not yielded, and the function continues to execute.</span></span>  <span data-ttu-id="e79d4-132">Кроме того, возврат к исходному контексту не всегда желателен, и такое поведение можно изменить. Подробное описание приведено в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="e79d4-132">Additionally, returning to the original context isn't always the desired behavior and can be changed; this is described in more detail in the next section.</span></span>  
  
### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a><span data-ttu-id="e79d4-133">Настройка приостановки и возобновления с помощью Yield и ConfigureAwait</span><span class="sxs-lookup"><span data-stu-id="e79d4-133">Configuring Suspension and Resumption with Yield and ConfigureAwait</span></span>  
 <span data-ttu-id="e79d4-134">Существуют методы, которые позволяют получить больший контроль над выполнением асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="e79d4-134">Several methods provide more control over an asynchronous method’s execution.</span></span> <span data-ttu-id="e79d4-135">Например, можно использовать <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> метода для внедрения точки yield в асинхронный метод:</span><span class="sxs-lookup"><span data-stu-id="e79d4-135">For example, you can use the <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> method to introduce a yield point into the asynchronous method:</span></span>  
  
```csharp  
public class Task : …  
{  
    public static YieldAwaitable Yield();  
    …  
}  
```  
  
 <span data-ttu-id="e79d4-136">Это аналогично асинхронному размещению или планированию возврата в текущий контекст.</span><span class="sxs-lookup"><span data-stu-id="e79d4-136">This is equivalent to asynchronously posting or scheduling back to the current context.</span></span>  
  
```csharp  
Task.Run(async delegate  
{  
    for(int i=0; i<1000000; i++)  
    {  
        await Task.Yield(); // fork the continuation into a separate work item  
        ...  
    }  
});  
```  
  
 <span data-ttu-id="e79d4-137">Можно также использовать <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> метод для улучшения контроля над приостановку и возобновление в асинхронном методе.</span><span class="sxs-lookup"><span data-stu-id="e79d4-137">You can also use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method for better control over suspension and resumption in an asynchronous method.</span></span>  <span data-ttu-id="e79d4-138">Как упоминалось ранее, по умолчанию текущий контекст записывается в момент приостановки асинхронного метода и используется для вызова продолжения асинхронного метода при возобновлении.</span><span class="sxs-lookup"><span data-stu-id="e79d4-138">As mentioned previously, by default, the current context is captured at the time an asynchronous  method is suspended, and that captured context is used to invoke the asynchronous  method’s continuation upon resumption.</span></span>  <span data-ttu-id="e79d4-139">Во многих случаях это именно то поведение, к которому вы стремитесь.</span><span class="sxs-lookup"><span data-stu-id="e79d4-139">In many cases, this is the exact behavior you want.</span></span>  <span data-ttu-id="e79d4-140">В других случаях можно не заботиться о контексте продолжения. Для повышения производительности нужно избегать подобного размещения обратно в исходный контекст.</span><span class="sxs-lookup"><span data-stu-id="e79d4-140">In other cases, you may not care about the continuation context, and you can achieve better performance by avoiding such posts back to the original context.</span></span>  <span data-ttu-id="e79d4-141">Чтобы включить эту возможность, используйте <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> метод для информирования операция await не для записи и возобновить от контекста, но продолжить выполнение везде, где завершении асинхронной операции ожидаемое:</span><span class="sxs-lookup"><span data-stu-id="e79d4-141">To enable this, use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method to inform the await operation not to capture and resume on the context, but to continue execution wherever the asynchronous operation that was being awaited completed:</span></span>  
  
```csharp  
await someTask.ConfigureAwait(continueOnCapturedContext:false);  
```  
  
## <a name="canceling-an-asynchronous-operation"></a><span data-ttu-id="e79d4-142">Отмена асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="e79d4-142">Canceling an Asynchronous Operation</span></span>  
 <span data-ttu-id="e79d4-143">Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], методы TAP, которые поддерживают отмену укажите по крайней мере один перегрузку, которая принимает токен отмены (<xref:System.Threading.CancellationToken> объекта).</span><span class="sxs-lookup"><span data-stu-id="e79d4-143">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], TAP methods that support cancellation provide at least one overload that accepts a cancellation token (<xref:System.Threading.CancellationToken> object).</span></span>  
  
 <span data-ttu-id="e79d4-144">Токен отмены, который создается через источник токена отмены (<xref:System.Threading.CancellationTokenSource> объекта).</span><span class="sxs-lookup"><span data-stu-id="e79d4-144">A cancellation token is created through a cancellation token source (<xref:System.Threading.CancellationTokenSource> object).</span></span>  <span data-ttu-id="e79d4-145">Источник <xref:System.Threading.CancellationTokenSource.Token%2A> свойство возвращает токен отмены, который будет оповещаться при источника <xref:System.Threading.CancellationTokenSource.Cancel%2A> вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="e79d4-145">The source’s <xref:System.Threading.CancellationTokenSource.Token%2A> property returns the cancellation token that will be signaled when the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method is called.</span></span>  <span data-ttu-id="e79d4-146">Например, если требуется загрузить одной веб-страницы, необходимо иметь возможность отменить операцию создания <xref:System.Threading.CancellationTokenSource> объекта, передается методу TAP свой маркер и вызова источника <xref:System.Threading.CancellationTokenSource.Cancel%2A> метод, когда вы будете готовы для отмены операции:</span><span class="sxs-lookup"><span data-stu-id="e79d4-146">For example, if you want to download a single webpage and you want to be able to cancel the operation, you create a <xref:System.Threading.CancellationTokenSource> object, pass its token to the TAP method, and then call the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method when you're ready to cancel the operation:</span></span>  
  
```csharp  
var cts = new CancellationTokenSource();  
string result = await DownloadStringAsync(url, cts.Token);  
… // at some point later, potentially on another thread  
cts.Cancel();  
```  
  
 <span data-ttu-id="e79d4-147">Чтобы отменить несколько асинхронных вызовов, можно передать один и тот же маркер всем вызовам.</span><span class="sxs-lookup"><span data-stu-id="e79d4-147">To cancel multiple asynchronous invocations, you can pass the same token to all invocations:</span></span>  
  
```csharp  
var cts = new CancellationTokenSource();  
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));  
    // at some point later, potentially on another thread  
    …  
    cts.Cancel();  
```  
  
 <span data-ttu-id="e79d4-148">Также можно передать один и тот же маркер выбранному подмножеству операций.</span><span class="sxs-lookup"><span data-stu-id="e79d4-148">Or, you can pass the same token to a selective subset of operations:</span></span>  
  
```csharp  
var cts = new CancellationTokenSource();  
    byte [] data = await DownloadDataAsync(url, cts.Token);  
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);  
    … // at some point later, potentially on another thread  
    cts.Cancel();  
```  
  
 <span data-ttu-id="e79d4-149">Запрос на отмену может быть запущен из любого потока.</span><span class="sxs-lookup"><span data-stu-id="e79d4-149">Cancellation requests may be initiated from any thread.</span></span>  
  
 <span data-ttu-id="e79d4-150">Можно передать <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> значение для любой метод, который принимает токен отмены, чтобы указать, что никогда не будет выдан запрос отмены.</span><span class="sxs-lookup"><span data-stu-id="e79d4-150">You can pass the <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> value to any method that accepts a cancellation token to indicate that cancellation will never be requested.</span></span>  <span data-ttu-id="e79d4-151">В результате <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> возвращаемое свойство `false`, и соответствующим образом оптимизировать вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="e79d4-151">This causes the <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> property to return `false`, and the called method can optimize accordingly.</span></span>  <span data-ttu-id="e79d4-152">Для тестирования также можно передать маркер отмены, для которого уже была выполнена отмена. Этот маркер инициализируется с помощью конструктора, который принимает логическое значение, означающее, следует ли запустить маркер в уже отмененном или неотменяемом состоянии.</span><span class="sxs-lookup"><span data-stu-id="e79d4-152">For testing purposes, you can also pass in a pre-canceled cancellation token that is instantiated by using the constructor that accepts a Boolean value to indicate whether the token should start in an already-canceled or not-cancelable state.</span></span>  
  
 <span data-ttu-id="e79d4-153">У такого подхода к отмене есть несколько преимуществ.</span><span class="sxs-lookup"><span data-stu-id="e79d4-153">This approach to cancellation has several advantages:</span></span>  
  
-   <span data-ttu-id="e79d4-154">Один и тот же маркер отмены можно передать в любое количество асинхронных и синхронных операций.</span><span class="sxs-lookup"><span data-stu-id="e79d4-154">You can pass the same cancellation token to any number of asynchronous and synchronous operations.</span></span>  
  
-   <span data-ttu-id="e79d4-155">Один и тот же запрос отмены можно распространить на любое количество прослушивателей.</span><span class="sxs-lookup"><span data-stu-id="e79d4-155">The same cancellation request may be proliferated to any number of listeners.</span></span>  
  
-   <span data-ttu-id="e79d4-156">Разработчик асинхронного интерфейса API имеет полный контроль над тем, можно ли разрешить запрос отмены и когда ее можно применить.</span><span class="sxs-lookup"><span data-stu-id="e79d4-156">The developer of the asynchronous API is in complete control of whether cancellation may be requested and when it may take effect.</span></span>  
  
-   <span data-ttu-id="e79d4-157">Код, который использует этот интерфейс API, может выборочно определять асинхронные вызовы, на которые будут распространены запросы отмены.</span><span class="sxs-lookup"><span data-stu-id="e79d4-157">The code that consumes the API may selectively determine the asynchronous invocations that cancellation requests will be propagated to.</span></span>  
  
## <a name="monitoring-progress"></a><span data-ttu-id="e79d4-158">Наблюдение за ходом выполнения</span><span class="sxs-lookup"><span data-stu-id="e79d4-158">Monitoring Progress</span></span>  
 <span data-ttu-id="e79d4-159">Некоторые асинхронные методы предоставляют сведения о ходе выполнения с помощью интерфейса хода выполнения, который передается в асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="e79d4-159">Some asynchronous methods expose progress through a progress interface passed into the asynchronous method.</span></span>  <span data-ttu-id="e79d4-160">Например, рассмотрим функцию, которая асинхронно загружает строку текста, одновременно обновляя сведения о ходе загрузки, которые включают долю уже загруженной части строки в процентах ко всей строке.</span><span class="sxs-lookup"><span data-stu-id="e79d4-160">For example, consider a function which asynchronously downloads a string of text, and along the way raises progress updates that include the percentage of the download that has completed thus far.</span></span>  <span data-ttu-id="e79d4-161">Этот метод можно использовать в приложении WPF следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e79d4-161">Such a method could be consumed in a Windows Presentation Foundation (WPF) application as follows:</span></span>  
  
```csharp  
private async void btnDownload_Click(object sender, RoutedEventArgs e)    
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,   
            new Progress<int>(p => pbDownloadProgress.Value = p));  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
```  
  
<a name="combinators"></a>   
## <a name="using-the-built-in-task-based-combinators"></a><span data-ttu-id="e79d4-162">Использование внутренних блоков объединения задач</span><span class="sxs-lookup"><span data-stu-id="e79d4-162">Using the Built-in Task-based Combinators</span></span>  
 <span data-ttu-id="e79d4-163"><xref:System.Threading.Tasks> Пространство имен включает несколько методов для создания и работы с задачами.</span><span class="sxs-lookup"><span data-stu-id="e79d4-163">The <xref:System.Threading.Tasks> namespace includes several methods for composing and working with tasks.</span></span>  
  
### <a name="taskrun"></a><span data-ttu-id="e79d4-164">Task.Run</span><span class="sxs-lookup"><span data-stu-id="e79d4-164">Task.Run</span></span>  
 <span data-ttu-id="e79d4-165"><xref:System.Threading.Tasks.Task> Класс содержит несколько <xref:System.Threading.Tasks.Task.Run%2A> методы, которые позволяют легко разгрузки work в качестве <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601> в пул потоков, например:</span><span class="sxs-lookup"><span data-stu-id="e79d4-165">The <xref:System.Threading.Tasks.Task> class includes several <xref:System.Threading.Tasks.Task.Run%2A> methods that let you easily offload work as a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> to the thread pool, for example:</span></span>  
  
```csharp  
public async void button1_Click(object sender, EventArgs e)  
{  
    textBox1.Text = await Task.Run(() =>  
    {  
        // … do compute-bound work here  
        return answer;  
    });  
}  
```  
  
 <span data-ttu-id="e79d4-166">Некоторые из этих <xref:System.Threading.Tasks.Task.Run%2A> методы, такие как <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> перегрузки, существует как сокращение для <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="e79d4-166">Some of these <xref:System.Threading.Tasks.Task.Run%2A> methods, such as the <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> overload, exist as shorthand for the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="e79d4-167">Другие перегрузки, такие как <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, включить использование ожидать в течение разгруженных работы, например:</span><span class="sxs-lookup"><span data-stu-id="e79d4-167">Other overloads, such as <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, enable you to use await within the offloaded work, for example:</span></span>  
  
```csharp  
public async void button1_Click(object sender, EventArgs e)  
{  
    pictureBox1.Image = await Task.Run(async() =>  
    {  
        using(Bitmap bmp1 = await DownloadFirstImageAsync())  
        using(Bitmap bmp2 = await DownloadSecondImageAsync())  
        return Mashup(bmp1, bmp2);  
    });  
}  
```  
  
 <span data-ttu-id="e79d4-168">Логически эквивалентно использованию таких перегрузок <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> в сочетании с <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> метод расширения в библиотеке параллельных задач.</span><span class="sxs-lookup"><span data-stu-id="e79d4-168">Such overloads are logically equivalent to using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method in conjunction with the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension method in the Task Parallel Library.</span></span>  
  
### <a name="taskfromresult"></a><span data-ttu-id="e79d4-169">Task.FromResult</span><span class="sxs-lookup"><span data-stu-id="e79d4-169">Task.FromResult</span></span>  
 <span data-ttu-id="e79d4-170">Используйте <xref:System.Threading.Tasks.Task.FromResult%2A> метод в сценариях, где данные уже могут быть доступны и просто требуется возвратить из метода возвращающий задачу до <xref:System.Threading.Tasks.Task%601>:</span><span class="sxs-lookup"><span data-stu-id="e79d4-170">Use the <xref:System.Threading.Tasks.Task.FromResult%2A> method in scenarios where data may already be available and just needs to be returned from a task-returning method lifted into a <xref:System.Threading.Tasks.Task%601>:</span></span>  
  
```csharp  
public Task<int> GetValueAsync(string key)  
{  
    int cachedValue;  
    return TryGetCachedValue(out cachedValue) ?  
        Task.FromResult(cachedValue) :  
        GetValueAsyncInternal();  
}  
  
private async Task<int> GetValueAsyncInternal(string key)  
{  
    …  
}  
```  
  
### <a name="taskwhenall"></a><span data-ttu-id="e79d4-171">Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="e79d4-171">Task.WhenAll</span></span>  
 <span data-ttu-id="e79d4-172">Используйте <xref:System.Threading.Tasks.Task.WhenAll%2A> метод асинхронно ожидание несколько асинхронных операций, которые представлены в виде задачи.</span><span class="sxs-lookup"><span data-stu-id="e79d4-172">Use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method to asynchronously wait on multiple asynchronous operations that are represented as tasks.</span></span>  <span data-ttu-id="e79d4-173">У этого метода есть несколько перегрузок, которые поддерживают набор неуниверсальных задач или неоднородный набор универсальных задач (например, асинхронное ожидание нескольких операций, возвращающих void, или асинхронное ожидание несколько методов, возвращающих значение (при этом эти значения могут быть разных типов)), а также поддерживают единый набор универсальных задач (например, асинхронное ожидание нескольких методов, которые возвращают `TResult`).</span><span class="sxs-lookup"><span data-stu-id="e79d4-173">The method has multiple overloads that support a set of non-generic tasks or a non-uniform set of generic tasks (for example, asynchronously waiting for multiple void-returning operations, or asynchronously waiting for multiple value-returning methods where each value may have a different type) and to support a uniform set of generic tasks (such as asynchronously waiting for multiple `TResult`-returning methods).</span></span>  
  
 <span data-ttu-id="e79d4-174">Предположим, что вы хотите отправить сообщения по электронной почте нескольким клиентам.</span><span class="sxs-lookup"><span data-stu-id="e79d4-174">Let's say you want to send email messages to several customers.</span></span> <span data-ttu-id="e79d4-175">Отправку сообщений можно перекрывать, чтобы не ожидать завершения отправки одного сообщения перед отправкой следующего.</span><span class="sxs-lookup"><span data-stu-id="e79d4-175">You can overlap sending the messages so you're not waiting for one message to complete before sending the next.</span></span> <span data-ttu-id="e79d4-176">Также можно узнать, были ли выполнены операции отправки и возникли ли ошибки.</span><span class="sxs-lookup"><span data-stu-id="e79d4-176">You can also find out when the send operations have completed and whether any errors have occurred:</span></span>  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
await Task.WhenAll(asyncOps);  
```  
  
 <span data-ttu-id="e79d4-177">Этот код явно не обрабатывает исключения, которые могут возникать, но позволяет распространить из исключения `await` в результирующую задачу из <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="e79d4-177">This code doesn't explicitly handle exceptions that may occur, but lets exceptions propagate out of the `await` on the resulting task from <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span></span>  <span data-ttu-id="e79d4-178">Для обработки исключений можно использовать следующий код.</span><span class="sxs-lookup"><span data-stu-id="e79d4-178">To handle the exceptions, you can use code such as the following:</span></span>  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
try  
{  
    await Task.WhenAll(asyncOps);  
}  
catch(Exception exc)  
{  
    ...  
}  
```  
  
 <span data-ttu-id="e79d4-179">В этом случае при сбое любой асинхронной операции, все исключения, будут объединены в <xref:System.AggregateException> исключение, которое хранится в <xref:System.Threading.Tasks.Task> возвращенный <xref:System.Threading.Tasks.Task.WhenAll%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e79d4-179">In this case, if any asynchronous operation fails, all the exceptions will be consolidated in an <xref:System.AggregateException> exception, which is stored in the <xref:System.Threading.Tasks.Task> that is returned from the <xref:System.Threading.Tasks.Task.WhenAll%2A> method.</span></span>  <span data-ttu-id="e79d4-180">Однако с помощью ключевого слова `await` распространяется только одно из этих исключений.</span><span class="sxs-lookup"><span data-stu-id="e79d4-180">However, only one of those exceptions is propagated by the `await` keyword.</span></span>  <span data-ttu-id="e79d4-181">Если вы хотите изучить все исключения, можно переписать предыдущий код следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e79d4-181">If you want to examine all the exceptions, you can rewrite the previous code as follows:</span></span>  
  
```csharp  
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();  
try  
{  
    await Task.WhenAll(asyncOps);  
}  
catch(Exception exc)  
{  
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))  
    {  
        … // work with faulted and faulted.Exception  
    }  
}  
```  
  
 <span data-ttu-id="e79d4-182">Рассмотрим в качестве примера асинхронную загрузку нескольких файлов из Интернета.</span><span class="sxs-lookup"><span data-stu-id="e79d4-182">Let's consider an example of downloading multiple files from the web asynchronously.</span></span>  <span data-ttu-id="e79d4-183">В этом случае все асинхронные операции имеют результаты одного типа, и к этим результатам легко получить доступ.</span><span class="sxs-lookup"><span data-stu-id="e79d4-183">In this case, all the asynchronous operations have homogeneous result types, and it's easy to access the results:</span></span>  
  
```csharp  
string [] pages = await Task.WhenAll(  
    from url in urls select DownloadStringAsync(url));  
```  
  
 <span data-ttu-id="e79d4-184">Можно использовать те же способы обработки исключений, которые были рассмотрены в предыдущем сценарии с возвратом void.</span><span class="sxs-lookup"><span data-stu-id="e79d4-184">You can use the same exception-handling techniques we discussed in the previous void-returning scenario:</span></span>  
  
```csharp  
Task [] asyncOps =   
    (from url in urls select DownloadStringAsync(url)).ToArray();  
try  
{  
    string [] pages = await Task.WhenAll(asyncOps);  
    ...  
}  
catch(Exception exc)  
{  
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))  
    {  
        … // work with faulted and faulted.Exception  
    }  
}  
```  
  
### <a name="taskwhenany"></a><span data-ttu-id="e79d4-185">Task.WhenAny</span><span class="sxs-lookup"><span data-stu-id="e79d4-185">Task.WhenAny</span></span>  
 <span data-ttu-id="e79d4-186">Можно использовать <xref:System.Threading.Tasks.Task.WhenAny%2A> метод, чтобы асинхронно ожидать только один из нескольких асинхронных операций в виде задачи для выполнения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-186">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to asynchronously wait for just one of multiple asynchronous operations represented as tasks to complete.</span></span>  <span data-ttu-id="e79d4-187">Этот метод допускает четыре основных варианта использования.</span><span class="sxs-lookup"><span data-stu-id="e79d4-187">This method serves four primary use cases:</span></span>  
  
-   <span data-ttu-id="e79d4-188">Избыточность: многократный запуск одной операции и выбор первой завершенной операции (например, обращение к нескольким веб-сервисам котировок акций с целью получить один результат и выбор операции, которая завершилась первой).</span><span class="sxs-lookup"><span data-stu-id="e79d4-188">Redundancy:  Performing an operation multiple times and selecting the one that completes first (for example, contacting multiple stock quote web services that will produce a single result and selecting the one that completes the fastest).</span></span>  
  
-   <span data-ttu-id="e79d4-189">Чередование: запуск и ожидание завершения нескольких операций, но обработка операций по мере выполнения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-189">Interleaving:  Launching multiple operations and waiting for all of them to complete, but processing them as they complete.</span></span>  
  
-   <span data-ttu-id="e79d4-190">Регулирование: добавление новых операций по мере завершения предыдущих.</span><span class="sxs-lookup"><span data-stu-id="e79d4-190">Throttling:  Allowing additional operations to begin as others complete.</span></span>  <span data-ttu-id="e79d4-191">Это расширение сценария с чередованием.</span><span class="sxs-lookup"><span data-stu-id="e79d4-191">This is an extension of the interleaving scenario.</span></span>  
  
-   <span data-ttu-id="e79d4-192">Ранняя остановка: например, операция, представленная задачей t1, может сгруппироваться в задачу <xref:System.Threading.Tasks.Task.WhenAny%2A> с другой задачей t2, после чего можно ожидать задачу <xref:System.Threading.Tasks.Task.WhenAny%2A>.</span><span class="sxs-lookup"><span data-stu-id="e79d4-192">Early bailout:  For example, an operation represented by task t1 can be grouped in a <xref:System.Threading.Tasks.Task.WhenAny%2A> task with another task t2, and you can wait on the <xref:System.Threading.Tasks.Task.WhenAny%2A> task.</span></span> <span data-ttu-id="e79d4-193">Задача t2 может представлять собой тайм-аут, или отмену или других сигнала, которое вызывает <xref:System.Threading.Tasks.Task.WhenAny%2A> завершения до t1 завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="e79d4-193">Task t2 could represent a time-out, or cancellation, or some other signal that causes the <xref:System.Threading.Tasks.Task.WhenAny%2A> task to complete before t1 completes.</span></span>  
  
#### <a name="redundancy"></a><span data-ttu-id="e79d4-194">Избыточность</span><span class="sxs-lookup"><span data-stu-id="e79d4-194">Redundancy</span></span>  
 <span data-ttu-id="e79d4-195">Рассмотрим случай, когда вам требуется принять решение о необходимости покупки акций.</span><span class="sxs-lookup"><span data-stu-id="e79d4-195">Consider a case where you want to make a decision about whether to buy a stock.</span></span>  <span data-ttu-id="e79d4-196">Существует несколько стандартных веб-служб с рекомендациями по покупке акций, которым вы доверяете, но в зависимости от ежедневной нагрузки каждая из этих служб иногда может работать медленно.</span><span class="sxs-lookup"><span data-stu-id="e79d4-196">There are several stock recommendation web services that you trust, but depending on daily load, each service can end up being slow at different times.</span></span>  <span data-ttu-id="e79d4-197">Можно использовать <xref:System.Threading.Tasks.Task.WhenAny%2A> метод, чтобы получать уведомления при завершении выполнения любой операции:</span><span class="sxs-lookup"><span data-stu-id="e79d4-197">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to receive a notification when any operation completes:</span></span>  
  
```csharp  
var recommendations = new List<Task<bool>>()   
{   
    GetBuyRecommendation1Async(symbol),   
    GetBuyRecommendation2Async(symbol),  
    GetBuyRecommendation3Async(symbol)  
};  
Task<bool> recommendation = await Task.WhenAny(recommendations);  
if (await recommendation) BuyStock(symbol);  
```  
  
 <span data-ttu-id="e79d4-198">В отличие от <xref:System.Threading.Tasks.Task.WhenAll%2A>, возвращающий распаковать результаты всех задач, которые выполнены успешно, <xref:System.Threading.Tasks.Task.WhenAny%2A> Возвращает задачу, которая была завершена.</span><span class="sxs-lookup"><span data-stu-id="e79d4-198">Unlike <xref:System.Threading.Tasks.Task.WhenAll%2A>, which returns the unwrapped results of all tasks that completed successfully, <xref:System.Threading.Tasks.Task.WhenAny%2A> returns the task that completed.</span></span> <span data-ttu-id="e79d4-199">Если задача завершилась сбоем, важно знать, что она завершилась сбоем, а если она завершилась успешно, важно знать, с какой задачей связано возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="e79d4-199">If a task fails, it’s important to know that it failed, and if a task succeeds, it’s important to know which task the return value is associated with.</span></span>  <span data-ttu-id="e79d4-200">Поэтому необходимо получить доступ к результату, возвращаемому задачей, или продолжить ожидание, как показано в данном примере.</span><span class="sxs-lookup"><span data-stu-id="e79d4-200">Therefore, you need to access the result of the returned task, or further await it, as  this example shows.</span></span>  
  
 <span data-ttu-id="e79d4-201">Как и в <xref:System.Threading.Tasks.Task.WhenAll%2A>, необходимо поддерживать исключения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-201">As with <xref:System.Threading.Tasks.Task.WhenAll%2A>, you have to be able to accommodate exceptions.</span></span>  <span data-ttu-id="e79d4-202">Так как вы получаете управление от завершенной задачи, вы можете подождать, пока не будут распространены ошибки для возвращенной задачи и `try/catch` их соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e79d4-202">Because you receive the completed task back, you can await the returned task to have errors propagated, and `try/catch` them appropriately; for example:</span></span>  
  
```csharp  
Task<bool> [] recommendations = …;  
while(recommendations.Count > 0)  
{   
    Task<bool> recommendation = await Task.WhenAny(recommendations);      
    try  
    {  
        if (await recommendation) BuyStock(symbol);  
        break;  
    }  
    catch(WebException exc)  
    {  
        recommendations.Remove(recommendation);  
    }  
}  
```  
  
 <span data-ttu-id="e79d4-203">Кроме того, даже если первая задача завершается успешно, следующие задачи могут завершиться сбоем.</span><span class="sxs-lookup"><span data-stu-id="e79d4-203">Additionally, even if a first task completes successfully, subsequent tasks may fail.</span></span>  <span data-ttu-id="e79d4-204">В этом случае есть несколько вариантов обработки исключений: можно ждать, пока не завершатся все задачи, используя метод <xref:System.Threading.Tasks.Task.WhenAll%2A>, или решить, что все исключения важны и должны быть записаны в журнал.</span><span class="sxs-lookup"><span data-stu-id="e79d4-204">At this point, you have several options for dealing with exceptions:  You can wait until all the launched tasks have completed, in which case you can use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method, or you can decide that all exceptions are important and must be logged.</span></span>  <span data-ttu-id="e79d4-205">В этом случае используется продолжение для получения уведомлений об успешном завершении задач.</span><span class="sxs-lookup"><span data-stu-id="e79d4-205">For this, you can use continuations to receive a notification when tasks have completed asynchronously:</span></span>  
  
```csharp  
foreach(Task recommendation in recommendations)  
{  
    var ignored = recommendation.ContinueWith(  
        t => { if (t.IsFaulted) Log(t.Exception); });  
}  
```  
  
 <span data-ttu-id="e79d4-206">или</span><span class="sxs-lookup"><span data-stu-id="e79d4-206">or:</span></span>  
  
```csharp  
foreach(Task recommendation in recommendations)  
{  
    var ignored = recommendation.ContinueWith(  
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);  
}  
```  
  
 <span data-ttu-id="e79d4-207">или даже:</span><span class="sxs-lookup"><span data-stu-id="e79d4-207">or even:</span></span>  
  
```  
private static async void LogCompletionIfFailed(IEnumerable<Task> tasks)  
{  
    foreach(var task in tasks)  
    {  
        try { await task; }  
        catch(Exception exc) { Log(exc); }  
    }  
}  
…  
LogCompletionIfFailed(recommendations);  
```  
  
 <span data-ttu-id="e79d4-208">Наконец, вы можете отменить все остальные операции.</span><span class="sxs-lookup"><span data-stu-id="e79d4-208">Finally, you may want to cancel all the remaining operations:</span></span>  
  
```csharp  
var cts = new CancellationTokenSource();  
var recommendations = new List<Task<bool>>()   
{   
    GetBuyRecommendation1Async(symbol, cts.Token),   
    GetBuyRecommendation2Async(symbol, cts.Token),  
    GetBuyRecommendation3Async(symbol, cts.Token)  
};  
  
Task<bool> recommendation = await Task.WhenAny(recommendations);  
cts.Cancel();  
if (await recommendation) BuyStock(symbol);  
```  
  
#### <a name="interleaving"></a><span data-ttu-id="e79d4-209">Чередование</span><span class="sxs-lookup"><span data-stu-id="e79d4-209">Interleaving</span></span>  
 <span data-ttu-id="e79d4-210">Рассмотрим ситуацию, в которой вы загружаете изображения из Интернета и обрабатываете каждое изображение (например, добавляете изображение в элемент управления пользовательского интерфейса).</span><span class="sxs-lookup"><span data-stu-id="e79d4-210">Consider a case where you're downloading images from the web and processing each image (for example, adding the image to a UI control).</span></span>  <span data-ttu-id="e79d4-211">Обработку изображений необходимо выполнять последовательно в потоке пользовательского интерфейса, но загружать их следует по возможности параллельно.</span><span class="sxs-lookup"><span data-stu-id="e79d4-211">You have to do the processing sequentially on the UI thread, but you want to download the images as concurrently as possible.</span></span> <span data-ttu-id="e79d4-212">Кроме того, для добавления изображений в пользовательский интерфейс не стоит ждать, пока все они будут загружены — удобнее добавлять каждое изображение после его загрузки.</span><span class="sxs-lookup"><span data-stu-id="e79d4-212">Also, you don’t want to hold up adding the images to the UI until they’re all downloaded—you want to add them as they complete:</span></span>  
  
```csharp  
List<Task<Bitmap>> imageTasks =   
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch{}  
}  
```  
  
 <span data-ttu-id="e79d4-213">Можно также применить чередование сценарий, в котором подразумевает обработку с большим объемом вычислений на <xref:System.Threading.ThreadPool> загруженных образов, например:</span><span class="sxs-lookup"><span data-stu-id="e79d4-213">You can also apply interleaving to a scenario that involves computationally intensive processing on the <xref:System.Threading.ThreadPool> of the downloaded images; for example:</span></span>  
  
```csharp  
List<Task<Bitmap>> imageTasks =   
    (from imageUrl in urls select GetBitmapAsync(imageUrl)  
         .ContinueWith(t => ConvertImage(t.Result)).ToList();  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch{}  
}  
```  
  
#### <a name="throttling"></a><span data-ttu-id="e79d4-214">Регулирование</span><span class="sxs-lookup"><span data-stu-id="e79d4-214">Throttling</span></span>  
 <span data-ttu-id="e79d4-215">Рассмотрим пример с чередованием с тем исключением, что на этот раз пользователь загружает так много изображений, что загрузку необходимо регулировать; например, вы можете ограничить максимальное количество параллельных загрузок.</span><span class="sxs-lookup"><span data-stu-id="e79d4-215">Consider the interleaving example, except that the user is downloading so many images that the downloads have to be throttled; for example, you want only a specific number of downloads to happen concurrently.</span></span> <span data-ttu-id="e79d4-216">Для этого можно запустить подмножество асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="e79d4-216">To achieve this, you can start a subset of the asynchronous operations.</span></span>  <span data-ttu-id="e79d4-217">По завершении операций можно запускать дополнительные операции, которые займут их место.</span><span class="sxs-lookup"><span data-stu-id="e79d4-217">As operations complete, you can start additional operations to take their place:</span></span>  
  
```csharp  
const int CONCURRENCY_LEVEL = 15;  
Uri [] urls = …;  
int nextIndex = 0;  
var imageTasks = new List<Task<Bitmap>>();  
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)  
{  
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));  
    nextIndex++;  
}  
  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch(Exception exc) { Log(exc); }  
  
    if (nextIndex < urls.Length)  
    {  
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));  
        nextIndex++;  
    }  
}  
```  
  
#### <a name="early-bailout"></a><span data-ttu-id="e79d4-218">Ранняя остановка</span><span class="sxs-lookup"><span data-stu-id="e79d4-218">Early Bailout</span></span>  
 <span data-ttu-id="e79d4-219">Рассмотрим, что вы асинхронно ожидаете завершения операции и одновременно отвечаете на запрос отмены пользователя (например, если пользователь нажал кнопку "Отмена").</span><span class="sxs-lookup"><span data-stu-id="e79d4-219">Consider that you're waiting asynchronously for an operation to complete while simultaneously responding to a user’s cancellation request (for example, the user clicked a cancel button).</span></span> <span data-ttu-id="e79d4-220">Этот сценарий иллюстрируется в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e79d4-220">The following code illustrates this scenario:</span></span>  
  
```csharp  
private CancellationTokenSource m_cts;   
  
public void btnCancel_Click(object sender, EventArgs e)  
{  
    if (m_cts != null) m_cts.Cancel();  
}  
  
public async void btnRun_Click(object sender, EventArgs e)  
{  
    m_cts = new CancellationTokenSource();  
    btnRun.Enabled = false;  
    try  
    {  
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);   
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);  
        if (imageDownload.IsCompleted)  
        {  
            Bitmap image = await imageDownload;  
            panel.AddImage(image);  
        }  
        else imageDownload.ContinueWith(t => Log(t));  
    }  
    finally { btnRun.Enabled = true; }  
}  
  
private static async Task UntilCompletionOrCancellation(  
    Task asyncOp, CancellationToken ct)  
{  
    var tcs = new TaskCompletionSource<bool>();  
    using(ct.Register(() => tcs.TrySetResult(true)))  
        await Task.WhenAny(asyncOp, tcs.Task);  
    return asyncOp;  
}  
```  
  
 <span data-ttu-id="e79d4-221">В этой реализации сразу же после отмены загрузки отображается пользовательский интерфейс, но базовые асинхронные операции не отменяются.</span><span class="sxs-lookup"><span data-stu-id="e79d4-221">This implementation re-enables the user interface as soon as you decide to bail out, but doesn't cancel the underlying asynchronous operations.</span></span>  <span data-ttu-id="e79d4-222">В качестве альтернативы можно отменить ожидающие операции после отмены загрузки, но не отображать пользовательский интерфейс, пока операции на самом деле не завершатся (возможно, из-за раннего завершения, вызванного запросом отмены).</span><span class="sxs-lookup"><span data-stu-id="e79d4-222">Another alternative would be to cancel the pending operations when you decide to bail out, but not reestablish the user interface until the operations actually complete, potentially due to ending early due to the cancellation request:</span></span>  
  
```csharp  
private CancellationTokenSource m_cts;  
  
public async void btnRun_Click(object sender, EventArgs e)  
{  
    m_cts = new CancellationTokenSource();  
  
    btnRun.Enabled = false;  
    try  
    {  
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);   
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);  
        Bitmap image = await imageDownload;  
        panel.AddImage(image);  
    }  
    catch(OperationCanceledException) {}  
    finally { btnRun.Enabled = true; }  
}  
```  
  
 <span data-ttu-id="e79d4-223">Еще один пример ранняя остановка предполагает использование <xref:System.Threading.Tasks.Task.WhenAny%2A> в сочетании с <xref:System.Threading.Tasks.Task.Delay%2A> метода, как описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="e79d4-223">Another example of early bailout involves using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method in conjunction with the <xref:System.Threading.Tasks.Task.Delay%2A> method, as discussed in the next section.</span></span>  
  
### <a name="taskdelay"></a><span data-ttu-id="e79d4-224">Task.Delay</span><span class="sxs-lookup"><span data-stu-id="e79d4-224">Task.Delay</span></span>  
 <span data-ttu-id="e79d4-225">Можно использовать <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> метод представить приостанавливает выполнения асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="e79d4-225">You can use the <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method to introduce pauses into an asynchronous method’s execution.</span></span>  <span data-ttu-id="e79d4-226">Это удобно для реализации различных функций, включая создание циклов опроса и задержку обработки ввода пользователя на заданный период времени.</span><span class="sxs-lookup"><span data-stu-id="e79d4-226">This is useful for many kinds of functionality, including building polling loops and delaying the handling of user input for a predetermined period of time.</span></span>  <span data-ttu-id="e79d4-227"><xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> Метод также можно использовать в сочетании с <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> для реализации тайм-аутов на ожидание.</span><span class="sxs-lookup"><span data-stu-id="e79d4-227">The <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method can also be useful in combination with <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> for implementing time-outs on awaits.</span></span>  
  
 <span data-ttu-id="e79d4-228">Если на выполнение задачи, которая является частью большой асинхронной операции (например, веб-служба ASP.NET), требуется слишком много времени, то это может негативно сказаться на всей операции, особенно если это приведет к неудачному завершению операции.</span><span class="sxs-lookup"><span data-stu-id="e79d4-228">If a task that’s part of a larger asynchronous operation (for example, an ASP.NET web service) takes too long to complete, the overall operation could suffer, especially if it fails to ever complete.</span></span>  <span data-ttu-id="e79d4-229">Поэтому важно иметь возможность задавать время ожидания для асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="e79d4-229">For this reason, it’s important to be able to time out when waiting on an asynchronous operation.</span></span>  <span data-ttu-id="e79d4-230">Синхронный <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>, и <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> методы принимают значения времени ожидания, но соответствующий <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> и упомянутых ранее <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>методы — нет.</span><span class="sxs-lookup"><span data-stu-id="e79d4-230">The synchronous <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> methods accept time-out values, but the corresponding <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> and the previously mentioned <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> methods do not.</span></span>  <span data-ttu-id="e79d4-231">Вместо этого можно использовать <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> в сочетании для реализации тайм-аута.</span><span class="sxs-lookup"><span data-stu-id="e79d4-231">Instead, you can use <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in combination to implement a time-out.</span></span>  
  
 <span data-ttu-id="e79d4-232">Например, предположим, что вы хотите загрузить приложение и отключить пользовательский интерфейс на время загрузки.</span><span class="sxs-lookup"><span data-stu-id="e79d4-232">For example, in your UI application, let's say that you want to download an image and disable the UI while the image is downloading.</span></span> <span data-ttu-id="e79d4-233">Однако если загрузка занимает слишком много времени, вы можете отменить загрузку и вернуться в пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e79d4-233">However, if the download takes too long, you want to re-enable the UI and discard the download:</span></span>  
  
```csharp  
public async void btnDownload_Click(object sender, EventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap> download = GetBitmapAsync(url);  
        if (download == await Task.WhenAny(download, Task.Delay(3000)))  
        {  
            Bitmap bmp = await download;  
            pictureBox.Image = bmp;  
            status.Text = "Downloaded";  
        }  
        else  
        {  
            pictureBox.Image = null;  
            status.Text = "Timed out";  
            var ignored = download.ContinueWith(  
                t => Trace("Task finally completed"));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
```  
  
 <span data-ttu-id="e79d4-234">То же самое происходит скачать несколько файлов, так как <xref:System.Threading.Tasks.Task.WhenAll%2A> Возвращает задачу:</span><span class="sxs-lookup"><span data-stu-id="e79d4-234">The same applies to multiple downloads, because <xref:System.Threading.Tasks.Task.WhenAll%2A> returns a task:</span></span>  
  
```csharp  
public async void btnDownload_Click(object sender, RoutedEventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap[]> downloads =   
            Task.WhenAll(from url in urls select GetBitmapAsync(url));  
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))  
        {  
            foreach(var bmp in downloads) panel.AddImage(bmp);  
            status.Text = "Downloaded";  
        }  
        else  
        {  
            status.Text = "Timed out";  
            downloads.ContinueWith(t => Log(t));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
```  
  
## <a name="building-task-based-combinators"></a><span data-ttu-id="e79d4-235">Создание блоков объединения на основе задач</span><span class="sxs-lookup"><span data-stu-id="e79d4-235">Building Task-based Combinators</span></span>  
 <span data-ttu-id="e79d4-236">Поскольку задача может полностью представлять асинхронную операцию и предоставляет синхронные и асинхронные функции для соединения с операцией, получения ее результатов и т. д., то вы можете создавать полезные библиотеки блоков объединения, которые объединяют задачи для создания шаблонов большего размера.</span><span class="sxs-lookup"><span data-stu-id="e79d4-236">Because a task is able to completely represent an asynchronous operation and provide synchronous and asynchronous capabilities for joining with the operation, retrieving its results, and so on, you can build useful libraries of combinators that compose tasks to build larger patterns.</span></span>  <span data-ttu-id="e79d4-237">Как уже обсуждалось в предыдущем разделе, в платформе .NET Framework есть несколько встроенных блоков объединения, но вы можете создать и собственные.</span><span class="sxs-lookup"><span data-stu-id="e79d4-237">As discussed in the previous section, the .NET Framework includes several built-in combinators, but you can also build your own.</span></span> <span data-ttu-id="e79d4-238">В следующих разделах приведено несколько примеров возможных методов и типов блоков объединения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-238">The following sections provide several examples of potential combinator methods and types.</span></span>  
  
### <a name="retryonfault"></a><span data-ttu-id="e79d4-239">RetryOnFault</span><span class="sxs-lookup"><span data-stu-id="e79d4-239">RetryOnFault</span></span>  
 <span data-ttu-id="e79d4-240">Во многих ситуациях может потребоваться повторить операцию, если предыдущая попытка завершилась неудачно.</span><span class="sxs-lookup"><span data-stu-id="e79d4-240">In many situations, you may want to retry an operation if a previous attempt fails.</span></span>  <span data-ttu-id="e79d4-241">Для решения этой задачи в синхронном коде можно использовать вспомогательный метод, например `RetryOnFault` в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e79d4-241">For synchronous code, you might build a helper method such as `RetryOnFault` in the following example to accomplish this:</span></span>  
  
```csharp  
public static T RetryOnFault<T>(  
    Func<T> function, int maxTries)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return function(); }  
        catch { if (i == maxTries-1) throw; }  
    }  
    return default(T);  
}  
```  
  
 <span data-ttu-id="e79d4-242">Вы можете создать почти такой же вспомогательный метод для асинхронных операций, которые реализованы в TAP и таким образом вернуть задачи.</span><span class="sxs-lookup"><span data-stu-id="e79d4-242">You can build an almost identical helper method for asynchronous operations that are implemented with TAP and thus return tasks:</span></span>  
  
```csharp  
public static async Task<T> RetryOnFault<T>(  
    Func<Task<T>> function, int maxTries)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return await function().ConfigureAwait(false); }  
        catch { if (i == maxTries-1) throw; }  
    }  
    return default(T);  
}  
```  
  
 <span data-ttu-id="e79d4-243">Этот блок объединения также можно использовать для анализа повторных попыток в логике приложения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-243">You can then use this combinator to encode retries into the application’s logic; for example:</span></span>  
  
```csharp  
// Download the URL, trying up to three times in case of failure  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3);  
```  
  
 <span data-ttu-id="e79d4-244">Функцию `RetryOnFault` можно улучшить.</span><span class="sxs-lookup"><span data-stu-id="e79d4-244">You could extend the `RetryOnFault` function further.</span></span> <span data-ttu-id="e79d4-245">Например, функция может принимать другой `Func<Task>`, который будет вызываться между повторными попытками, чтобы определить, когда операцию нужно повторить.</span><span class="sxs-lookup"><span data-stu-id="e79d4-245">For example, the function could accept another `Func<Task>` that will be invoked between retries to determine when to try the operation again; for example:</span></span>  
  
```csharp  
public static async Task<T> RetryOnFault<T>(  
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return await function().ConfigureAwait(false); }  
        catch { if (i == maxTries-1) throw; }  
        await retryWhen().ConfigureAwait(false);  
    }  
    return default(T);  
}  
```  
  
 <span data-ttu-id="e79d4-246">Чтобы подождать одну секунду перед повтором операции, эту функцию можно использовать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e79d4-246">You could then use the function as follows to wait for a second before retrying the operation:</span></span>  
  
```csharp  
// Download the URL, trying up to three times in case of failure,  
// and delaying for a second between retries  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));  
```  
  
### <a name="needonlyone"></a><span data-ttu-id="e79d4-247">NeedOnlyOne</span><span class="sxs-lookup"><span data-stu-id="e79d4-247">NeedOnlyOne</span></span>  
 <span data-ttu-id="e79d4-248">В некоторых случаях для повышения задержки и вероятности успешного завершения операции можно воспользоваться преимуществами избыточности.</span><span class="sxs-lookup"><span data-stu-id="e79d4-248">Sometimes, you can take advantage of redundancy to improve an operation’s latency and chances for success.</span></span>  <span data-ttu-id="e79d4-249">Рассмотрим несколько веб-служб, которые предоставляют котировки акций в разное время дня, и каждая служба обеспечивает различный уровень качества и время отклика.</span><span class="sxs-lookup"><span data-stu-id="e79d4-249">Consider multiple web services that provide stock quotes, but at various times of the day, each service may provide different levels of quality and response times.</span></span>  <span data-ttu-id="e79d4-250">Чтобы справиться с неравномерным характером поступления данных, вы можете отправлять запросы ко всем веб-службам и при получении ответа от одной из веб-служб отменять оставшиеся запросы.</span><span class="sxs-lookup"><span data-stu-id="e79d4-250">To deal with these fluctuations, you may issue requests to all the web services, and as soon as you get a response from one, cancel the remaining requests.</span></span>  <span data-ttu-id="e79d4-251">Вы можете реализовать вспомогательную функцию для более удобной реализации этого распространенного шаблона с запуском нескольких операций, ожидания завершения любой операции и последующей отмены остальных.</span><span class="sxs-lookup"><span data-stu-id="e79d4-251">You can implement a helper function to make it easier to implement this common pattern of launching multiple operations, waiting for any, and then canceling the rest.</span></span> <span data-ttu-id="e79d4-252">Функция `NeedOnlyOne` в следующем примере иллюстрирует этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="e79d4-252">The `NeedOnlyOne` function in the following example illustrates this scenario:</span></span>  
  
```csharp  
public static async Task<T> NeedOnlyOne(  
    params Func<CancellationToken,Task<T>> [] functions)  
{  
    var cts = new CancellationTokenSource();  
    var tasks = (from function in functions  
                 select function(cts.Token)).ToArray();  
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);  
    cts.Cancel();  
    foreach(var task in tasks)   
    {  
        var ignored = task.ContinueWith(  
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);  
    }  
    return completed;  
}  
```  
  
 <span data-ttu-id="e79d4-253">Затем можно использовать эту функцию следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e79d4-253">You can then use this function as follows:</span></span>  
  
```csharp  
double currentPrice = await NeedOnlyOne(  
    ct => GetCurrentPriceFromServer1Async("msft", ct),  
    ct => GetCurrentPriceFromServer2Async("msft", ct),  
    ct => GetCurrentPriceFromServer3Async("msft", ct));  
```  
  
### <a name="interleaved-operations"></a><span data-ttu-id="e79d4-254">Операции с чередованием</span><span class="sxs-lookup"><span data-stu-id="e79d4-254">Interleaved Operations</span></span>  
 <span data-ttu-id="e79d4-255">Отсутствует на потенциальную проблему производительности с помощью <xref:System.Threading.Tasks.Task.WhenAny%2A> метод для поддержки чередующихся сценарии при работе с очень большими наборами задач.</span><span class="sxs-lookup"><span data-stu-id="e79d4-255">There is a potential performance problem with using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to support an interleaving scenario when you're working with very large sets of tasks.</span></span>  <span data-ttu-id="e79d4-256">Каждый вызов <xref:System.Threading.Tasks.Task.WhenAny%2A> приводит к регистрации в каждой задачи продолжения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-256">Every call to <xref:System.Threading.Tasks.Task.WhenAny%2A> results in a continuation being registered with each task.</span></span> <span data-ttu-id="e79d4-257">Для N задач это приводит к созданию O(N2) продолжений в течение времени существования операции чередования.</span><span class="sxs-lookup"><span data-stu-id="e79d4-257">For N number of tasks, this results in O(N2) continuations created over the lifetime of the interleaving operation.</span></span>  <span data-ttu-id="e79d4-258">При работе с большим набором задач можно использовать комбинатор (`Interleaved` в следующем примере), чтобы решить проблему производительности.</span><span class="sxs-lookup"><span data-stu-id="e79d4-258">If you're working with a large set of tasks, you can use a combinator  (`Interleaved` in the following example) to address the performance issue:</span></span>  
  
```csharp  
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputTasks = tasks.ToList();  
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)   
                   select new TaskCompletionSource<T>()).ToList();  
    int nextTaskIndex = -1;  
    foreach (var inputTask in inputTasks)  
    {  
        inputTask.ContinueWith(completed =>  
        {  
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];  
            if (completed.IsFaulted)   
                source.TrySetException(completed.Exception.InnerExceptions);  
            else if (completed.IsCanceled)   
                source.TrySetCanceled();  
            else   
                source.TrySetResult(completed.Result);  
        }, CancellationToken.None,   
           TaskContinuationOptions.ExecuteSynchronously,   
           TaskScheduler.Default);  
    }  
    return from source in sources   
           select source.Task;  
}  
```  
  
 <span data-ttu-id="e79d4-259">Затем с помощью блоков объединения можно объединять результаты задач по мере их завершения.</span><span class="sxs-lookup"><span data-stu-id="e79d4-259">You can then use the combinator to process the results of tasks as they complete; for example:</span></span>  
  
```csharp  
IEnumerable<Task<int>> tasks = ...;  
foreach(var task in Interleaved(tasks))  
{  
    int result = await task;  
    …  
}  
```  
  
### <a name="whenallorfirstexception"></a><span data-ttu-id="e79d4-260">WhenAllOrFirstException</span><span class="sxs-lookup"><span data-stu-id="e79d4-260">WhenAllOrFirstException</span></span>  
 <span data-ttu-id="e79d4-261">В некоторых сценариях распределения и объединения вы можете ожидать, пока одна из задач в наборе не завершится сбоем, в этом случае ожидание прекращается, так как выдается исключение.</span><span class="sxs-lookup"><span data-stu-id="e79d4-261">In certain scatter/gather scenarios, you might want to wait for all tasks in a set, unless one of them faults, in which case you want to stop waiting as soon as the exception occurs.</span></span>  <span data-ttu-id="e79d4-262">Для этого можно использовать такой блок объединения как `WhenAllOrFirstException`, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e79d4-262">You can accomplish that with a combinator method such as `WhenAllOrFirstException` in the following example:</span></span>  
  
```csharp  
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputs = tasks.ToList();  
    var ce = new CountdownEvent(inputs.Count);  
    var tcs = new TaskCompletionSource<T[]>();  
  
    Action<Task> onCompleted = (Task completed) =>  
    {  
        if (completed.IsFaulted)   
            tcs.TrySetException(completed.Exception.InnerExceptions);  
        if (ce.Signal() && !tcs.Task.IsCompleted)  
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());  
    };  
  
    foreach (var t in inputs) t.ContinueWith(onCompleted);  
    return tcs.Task;  
}  
```  
  
## <a name="building-task-based-data-structures"></a><span data-ttu-id="e79d4-263">Создание структур данных на основе задач</span><span class="sxs-lookup"><span data-stu-id="e79d4-263">Building Task-based Data Structures</span></span>  
 <span data-ttu-id="e79d4-264">Помимо возможности для построения пользовательских методами объединения на основе задач, имеет структуру данных <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601> , представляющий результаты асинхронной операции и синхронизации, необходимой для соединения с ним делает его очень мощный Введите для построения пользовательских структур данных для использования в скриптах асинхронной.</span><span class="sxs-lookup"><span data-stu-id="e79d4-264">In addition to the ability to build custom task-based combinators, having a data structure in <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> that represents both the results of an asynchronous operation and the necessary synchronization to join with it makes it a very powerful type on which to build custom data structures to be used in asynchronous scenarios.</span></span>  
  
### <a name="asynccache"></a><span data-ttu-id="e79d4-265">AsyncCache</span><span class="sxs-lookup"><span data-stu-id="e79d4-265">AsyncCache</span></span>  
 <span data-ttu-id="e79d4-266">Одним важным аспектом задачи является, он может обрабатываться нескольким получателям, каждый из которых может ожидание, продолжений регистра, с ее помощью получить его результат или исключения (в случае использования <xref:System.Threading.Tasks.Task%601>), и т. д.</span><span class="sxs-lookup"><span data-stu-id="e79d4-266">One important aspect of a task is that it may be handed out to multiple consumers, all of whom may await it, register continuations with it, get its result or exceptions (in the case of <xref:System.Threading.Tasks.Task%601>), and so on.</span></span>  <span data-ttu-id="e79d4-267">Это делает <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601> идеально подходит для использования в асинхронной инфраструктура кэширования.</span><span class="sxs-lookup"><span data-stu-id="e79d4-267">This makes <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> perfectly suited to be used in an asynchronous caching infrastructure.</span></span>  <span data-ttu-id="e79d4-268">Ниже приведен пример небольшой, но мощные асинхронный кэш построены на основе <xref:System.Threading.Tasks.Task%601>:</span><span class="sxs-lookup"><span data-stu-id="e79d4-268">Here’s an example of a small but powerful asynchronous cache built on top of <xref:System.Threading.Tasks.Task%601>:</span></span>  
  
```csharp  
public class AsyncCache<TKey, TValue>  
{  
    private readonly Func<TKey, Task<TValue>> _valueFactory;  
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;  
  
    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)  
    {  
        if (valueFactory == null) throw new ArgumentNullException("loader");  
        _valueFactory = valueFactory;  
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();  
    }  
  
    public Task<TValue> this[TKey key]  
    {  
        get  
        {  
            if (key == null) throw new ArgumentNullException("key");  
            return _map.GetOrAdd(key, toAdd =>   
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="e79d4-269">[AsyncCache\<TKey, TValue >](http://go.microsoft.com/fwlink/p/?LinkId=251941) класса принимает в качестве его конструктору делегат функции, принимающей `TKey` и возвращает <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="e79d4-269">The [AsyncCache\<TKey,TValue>](http://go.microsoft.com/fwlink/p/?LinkId=251941) class accepts as a delegate to its constructor a function that takes a `TKey` and returns a <xref:System.Threading.Tasks.Task%601>.</span></span>  <span data-ttu-id="e79d4-270">Ранее запрошенные из кэша значения хранятся во внутреннем словаре, и `AsyncCache` гарантирует, что для одного ключа создается только одна задача, даже при одновременном доступе к кэшу.</span><span class="sxs-lookup"><span data-stu-id="e79d4-270">Any previously accessed values from the cache are stored in the internal dictionary, and the `AsyncCache` ensures that only one task is generated per key, even if the cache is accessed concurrently.</span></span>  
  
 <span data-ttu-id="e79d4-271">Например, можно создать кэш для загруженных веб-страниц.</span><span class="sxs-lookup"><span data-stu-id="e79d4-271">For example, you can build a cache for downloaded web pages:</span></span>  
  
```csharp  
private AsyncCache<string,string> m_webPages =   
    new AsyncCache<string,string>(DownloadStringAsync);  
```  
  
 <span data-ttu-id="e79d4-272">Затем можно использовать этот кэш в асинхронных методах каждый раз, когда вам потребуется содержимое какой-либо веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="e79d4-272">You can then use this cache in asynchronous methods whenever you need the contents of a web page.</span></span> <span data-ttu-id="e79d4-273">Класс `AsyncCache` гарантирует, что будет загружено минимальное число страниц, и кэширует результаты.</span><span class="sxs-lookup"><span data-stu-id="e79d4-273">The `AsyncCache` class ensures that you’re downloading as few pages as possible, and caches the results.</span></span>  
  
```csharp  
private async void btnDownload_Click(object sender, RoutedEventArgs e)   
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtContents.Text = await m_webPages["http://www.microsoft.com"];  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
```  
  
### <a name="asyncproducerconsumercollection"></a><span data-ttu-id="e79d4-274">AsyncProducerConsumerCollection</span><span class="sxs-lookup"><span data-stu-id="e79d4-274">AsyncProducerConsumerCollection</span></span>  
 <span data-ttu-id="e79d4-275">Задачи также можно использовать для создания структур данных для координации асинхронных действий.</span><span class="sxs-lookup"><span data-stu-id="e79d4-275">You can also use tasks to build data structures for coordinating asynchronous activities.</span></span>  <span data-ttu-id="e79d4-276">Рассмотрим один из классических шаблонов параллельных систем: производитель/потребитель.</span><span class="sxs-lookup"><span data-stu-id="e79d4-276">Consider one of the classic parallel design patterns: producer/consumer.</span></span>  <span data-ttu-id="e79d4-277">В этой схеме производители создают данные, которые используются потребителями и производители и потребители могут работать параллельно.</span><span class="sxs-lookup"><span data-stu-id="e79d4-277">In this pattern, producers generate data that is consumed by consumers, and the producers and consumers may run in parallel.</span></span> <span data-ttu-id="e79d4-278">Например, потребитель обрабатывает элемент 1, который ранее был создан производителем, который в это же время создает элемент 2.</span><span class="sxs-lookup"><span data-stu-id="e79d4-278">For example, the consumer processes item 1, which was previously generated by a producer who is now producing item 2.</span></span>  <span data-ttu-id="e79d4-279">Для схемы "производитель/потребитель" в любом случае потребуется некоторая структура данных, в которой будут храниться объекты, создаваемые производителем. Эта структура необходима для того, чтобы потребитель мог узнать о новых данных и получить их, когда они будут доступны.</span><span class="sxs-lookup"><span data-stu-id="e79d4-279">For the producer/consumer pattern, you invariably need some data structure to store the work created by producers so that the consumers may be notified of new data and find it when available.</span></span>  
  
 <span data-ttu-id="e79d4-280">Вот простая структура данных на основе задач, которая позволяет использовать асинхронные методы в качестве производителей и потребителей.</span><span class="sxs-lookup"><span data-stu-id="e79d4-280">Here’s a simple data structure built on top of tasks that enables asynchronous methods to be used as producers and consumers:</span></span>  
  
```csharp  
public class AsyncProducerConsumerCollection<T>  
{  
    private readonly Queue<T> m_collection = new Queue<T>();  
    private readonly Queue<TaskCompletionSource<T>> m_waiting =   
        new Queue<TaskCompletionSource<T>>();  
  
    public void Add(T item)  
    {  
        TaskCompletionSource<T> tcs = null;  
        lock (m_collection)  
        {  
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();  
            else m_collection.Enqueue(item);  
        }  
        if (tcs != null) tcs.TrySetResult(item);  
    }  
  
    public Task<T> Take()  
    {  
        lock (m_collection)  
        {  
            if (m_collection.Count > 0)   
            {  
                return Task.FromResult(m_collection.Dequeue());   
            }  
            else   
            {  
                var tcs = new TaskCompletionSource<T>();  
                m_waiting.Enqueue(tcs);  
                return tcs.Task;  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="e79d4-281">С этой структурой данных на месте можно написать следующий код.</span><span class="sxs-lookup"><span data-stu-id="e79d4-281">With that data structure in place, you can write code such as the following:</span></span>  
  
```csharp  
private static AsyncProducerConsumerCollection<int> m_data = …;  
…  
private static async Task ConsumerAsync()  
{  
    while(true)  
    {  
        int nextItem = await m_data.Take();  
        ProcessNextItem(nextItem);  
    }  
}  
…  
private static void Produce(int data)  
{  
    m_data.Add(data);  
}  
```  
  
 <span data-ttu-id="e79d4-282"><xref:System.Threading.Tasks.Dataflow> Пространство имен включает <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> тип, который можно использовать так же, но без необходимости построения пользовательского типа коллекции:</span><span class="sxs-lookup"><span data-stu-id="e79d4-282">The <xref:System.Threading.Tasks.Dataflow> namespace includes the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> type, which you can use in a similar manner, but without having to build a custom collection type:</span></span>  
  
```csharp  
private static BufferBlock<int> m_data = …;  
…  
private static async Task ConsumerAsync()  
{  
    while(true)  
    {  
        int nextItem = await m_data.ReceiveAsync();  
        ProcessNextItem(nextItem);  
    }  
}  
…  
private static void Produce(int data)  
{  
    m_data.Post(data);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="e79d4-283"><xref:System.Threading.Tasks.Dataflow> Пространство имен доступно в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] через **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e79d4-283">The <xref:System.Threading.Tasks.Dataflow> namespace is available in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] through **NuGet**.</span></span> <span data-ttu-id="e79d4-284">Чтобы установить сборку, содержащую <xref:System.Threading.Tasks.Dataflow> пространства имен, откройте проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите **управление пакетами NuGet** меню проекта и выполните поиск пакета Microsoft.Tpl.Dataflow.</span><span class="sxs-lookup"><span data-stu-id="e79d4-284">To install the assembly that contains the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the Microsoft.Tpl.Dataflow package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e79d4-285">См. также</span><span class="sxs-lookup"><span data-stu-id="e79d4-285">See Also</span></span>  
 <span data-ttu-id="e79d4-286">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Асинхронный шаблон, основанный на задачах (TAP))</span><span class="sxs-lookup"><span data-stu-id="e79d4-286">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span></span>  
 [<span data-ttu-id="e79d4-287">Реализация асинхронной модели на основе задач</span><span class="sxs-lookup"><span data-stu-id="e79d4-287">Implementing the Task-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)  
 [<span data-ttu-id="e79d4-288">Взаимодействие с другими асинхронными шаблонами и типами</span><span class="sxs-lookup"><span data-stu-id="e79d4-288">Interop with Other Asynchronous Patterns and Types</span></span>](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
