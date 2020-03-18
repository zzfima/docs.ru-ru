---
title: Реализация асинхронной модели, основанной на событиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
ms.openlocfilehash: 9865fa169e0776765f9a97ec0a7b4555bf253886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67663709"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="fa55b-102">Реализация асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="fa55b-102">Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="fa55b-103">Если вы создаете класс и некоторые операции этого класса могут привести к значительным задержкам, подумайте о том, чтобы реализовать асинхронные функции для этого класса с помощью [асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fa55b-103">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>

<span data-ttu-id="fa55b-104">Асинхронная модель на основе событий предоставляет стандартизированный способ упаковки класса, в котором есть асинхронные функции.</span><span class="sxs-lookup"><span data-stu-id="fa55b-104">The Event-based Asynchronous Pattern provides a standardized way to package a class that has asynchronous features.</span></span> <span data-ttu-id="fa55b-105">Если вы реализуете класс с помощью вспомогательных классов, таких как <xref:System.ComponentModel.AsyncOperationManager>, то ваш класс будет работать правильно в любой модели приложения, включая ASP.NET, консольные приложения и приложения Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fa55b-105">If implemented with helper classes like <xref:System.ComponentModel.AsyncOperationManager>, your class will work correctly under any application model, including ASP.NET, Console applications, and Windows Forms applications.</span></span>

<span data-ttu-id="fa55b-106">Пример реализации асинхронной модели на основе событий см. в разделе [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="fa55b-106">For an example that implements the Event-based Asynchronous Pattern, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="fa55b-107">Для простых асинхронных операций компонент <xref:System.ComponentModel.BackgroundWorker> может оказаться подходящим вариантом.</span><span class="sxs-lookup"><span data-stu-id="fa55b-107">For simple asynchronous operations, you may find the <xref:System.ComponentModel.BackgroundWorker> component suitable.</span></span> <span data-ttu-id="fa55b-108">Дополнительные сведения о <xref:System.ComponentModel.BackgroundWorker> см. в статье [Практическое руководство. Фоновое выполнение операции](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="fa55b-108">For more information about <xref:System.ComponentModel.BackgroundWorker>, see [How to: Run an Operation in the Background](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>

<span data-ttu-id="fa55b-109">Ниже перечислены функции асинхронной модели на основе событий, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="fa55b-109">The following list describes the features of the Event-based Asynchronous Pattern discussed in this topic.</span></span>

- <span data-ttu-id="fa55b-110">Возможности для реализации асинхронной модели на основе событий</span><span class="sxs-lookup"><span data-stu-id="fa55b-110">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

- <span data-ttu-id="fa55b-111">Именование асинхронных методов</span><span class="sxs-lookup"><span data-stu-id="fa55b-111">Naming Asynchronous Methods</span></span>

- <span data-ttu-id="fa55b-112">Возможная поддержка отмены</span><span class="sxs-lookup"><span data-stu-id="fa55b-112">Optionally Support Cancellation</span></span>

- <span data-ttu-id="fa55b-113">Возможная поддержка свойства IsBusy</span><span class="sxs-lookup"><span data-stu-id="fa55b-113">Optionally Support the IsBusy Property</span></span>

- <span data-ttu-id="fa55b-114">Возможная поддержка отчетов о ходе выполнения</span><span class="sxs-lookup"><span data-stu-id="fa55b-114">Optionally Provide Support for Progress Reporting</span></span>

- <span data-ttu-id="fa55b-115">Возможная поддержка возврата добавочных результатов</span><span class="sxs-lookup"><span data-stu-id="fa55b-115">Optionally Provide Support for Returning Incremental Results</span></span>

- <span data-ttu-id="fa55b-116">Обработка выходных и ссылочных параметров в методах</span><span class="sxs-lookup"><span data-stu-id="fa55b-116">Handling Out and Ref Parameters in Methods</span></span>

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="fa55b-117">Возможности для реализации асинхронной модели на основе событий</span><span class="sxs-lookup"><span data-stu-id="fa55b-117">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="fa55b-118">Подумайте о реализации асинхронной модели на основе событий при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="fa55b-118">Consider implementing the Event-based Asynchronous Pattern when:</span></span>

- <span data-ttu-id="fa55b-119">Клиентам вашего класса не нужна доступность объектов <xref:System.Threading.WaitHandle> и <xref:System.IAsyncResult> для асинхронных операций. Это значит, что механизм опросов и <xref:System.Threading.WaitHandle.WaitAll%2A> (или <xref:System.Threading.WaitHandle.WaitAny%2A>) нужно создать на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="fa55b-119">Clients of your class do not need <xref:System.Threading.WaitHandle> and <xref:System.IAsyncResult> objects available for asynchronous operations, meaning that polling and <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> will need to be built up by the client.</span></span>

- <span data-ttu-id="fa55b-120">Асинхронными операциями должен управлять клиент с использованием известной модели событий или делегатов.</span><span class="sxs-lookup"><span data-stu-id="fa55b-120">You want asynchronous operations to be managed by the client with the familiar event/delegate model.</span></span>

<span data-ttu-id="fa55b-121">Любую операцию можно реализовать асинхронно, но следует выбирать те операции, которые будут включать большие задержки.</span><span class="sxs-lookup"><span data-stu-id="fa55b-121">Any operation is a candidate for an asynchronous implementation, but those you expect to incur long latencies should be considered.</span></span> <span data-ttu-id="fa55b-122">Особенно подходят те операции, при которых клиенты вызывают метод и получают оповещение о его выполнении и никакого другого вмешательства в работу метода не требуется.</span><span class="sxs-lookup"><span data-stu-id="fa55b-122">Especially appropriate are operations in which clients call a method and are notified on completion, with no further intervention required.</span></span> <span data-ttu-id="fa55b-123">Также подходят операции, которые работают постоянно и периодически уведомляют клиентов о ходе выполнения, об изменении состояния или отправляют им промежуточные результаты.</span><span class="sxs-lookup"><span data-stu-id="fa55b-123">Also appropriate are operations which run continuously, periodically notifying clients of progress, incremental results, or state changes.</span></span>

<span data-ttu-id="fa55b-124">Дополнительные сведения о выборе асинхронной модели на основе событий см. в разделе [Выбор асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="fa55b-124">For more information on deciding when to support the Event-based Asynchronous Pattern, see [Deciding When to Implement the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="naming-asynchronous-methods"></a><span data-ttu-id="fa55b-125">Именование асинхронных методов</span><span class="sxs-lookup"><span data-stu-id="fa55b-125">Naming Asynchronous Methods</span></span>

<span data-ttu-id="fa55b-126">Для каждого синхронного метода *имя_метода*, для которого необходимо предоставить асинхронный эквивалент, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fa55b-126">For each synchronous method *MethodName* for which you want to provide an asynchronous counterpart:</span></span>

<span data-ttu-id="fa55b-127">Определите метод _MethodName_**Async**, который отвечает за выполнение следующих действий:</span><span class="sxs-lookup"><span data-stu-id="fa55b-127">Define a _MethodName_**Async** method that:</span></span>

- <span data-ttu-id="fa55b-128">Возвращает `void`.</span><span class="sxs-lookup"><span data-stu-id="fa55b-128">Returns `void`.</span></span>

- <span data-ttu-id="fa55b-129">принимает те же параметры, что и метод *имя_метода*;</span><span class="sxs-lookup"><span data-stu-id="fa55b-129">Takes the same parameters as the *MethodName* method.</span></span>

- <span data-ttu-id="fa55b-130">поддерживает несколько вызовов.</span><span class="sxs-lookup"><span data-stu-id="fa55b-130">Accepts multiple invocations.</span></span>

<span data-ttu-id="fa55b-131">Вы также можете определить перегрузку _MethodName_**Async**, которая идентична методу _MethodName_**Async**, но принимает дополнительный параметр `userState`, зависящий от объекта.</span><span class="sxs-lookup"><span data-stu-id="fa55b-131">Optionally define a _MethodName_**Async** overload, identical to _MethodName_**Async**, but with an additional object-valued parameter called `userState`.</span></span> <span data-ttu-id="fa55b-132">Реализуйте эту перегрузку, если необходимо управлять несколькими параллельными вызовами метода. В этом случае значение `userState` будет отправляться обратно во все обработчики событий, чтобы различать вызовы метода.</span><span class="sxs-lookup"><span data-stu-id="fa55b-132">Do this if you're prepared to manage multiple concurrent invocations of your method, in which case the `userState` value will be delivered back to all event handlers to distinguish invocations of the method.</span></span> <span data-ttu-id="fa55b-133">Такую перегрузку также можно использовать для хранения и последующего извлечения состояния пользователя.</span><span class="sxs-lookup"><span data-stu-id="fa55b-133">You may also choose to do this simply as a place to store user state for later retrieval.</span></span>

<span data-ttu-id="fa55b-134">Для каждой отдельной сигнатуры метода _MethodName_**Async** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fa55b-134">For each separate _MethodName_**Async** method signature:</span></span>

1. <span data-ttu-id="fa55b-135">Определите следующее событие в том же классе, в котором находится метод.</span><span class="sxs-lookup"><span data-stu-id="fa55b-135">Define the following event in the same class as the method:</span></span>

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. <span data-ttu-id="fa55b-136">Определите следующий делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fa55b-136">Define the following delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span></span> <span data-ttu-id="fa55b-137">Обычно они определяются за пределами класса, но в том же пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="fa55b-137">These will likely be defined outside of the class itself, but in the same namespace.</span></span>

    ```vb
    Public Delegate Sub MethodNameCompletedEventHandler( _
        ByVal sender As Object, _
        ByVal e As MethodNameCompletedEventArgs)

    Public Class MethodNameCompletedEventArgs
        Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As MyReturnType
    End Property
    ```

    ```csharp
    public delegate void MethodNameCompletedEventHandler(object sender,
        MethodNameCompletedEventArgs e);

    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
    {
        public MyReturnType Result { get; }
    }
    ```

    - <span data-ttu-id="fa55b-138">Убедитесь, что класс _MethodName_**CompletedEventArgs** предоставляет свои члены в виде свойств только для чтения, а не в виде полей, которые не поддерживают привязку данных.</span><span class="sxs-lookup"><span data-stu-id="fa55b-138">Ensure that the _MethodName_**CompletedEventArgs** class exposes its members as read-only properties, and not fields, as fields prevent data binding.</span></span>

    - <span data-ttu-id="fa55b-139">Не определяйте производные от <xref:System.ComponentModel.AsyncCompletedEventArgs> классы для методов, которые не возвращают результатов.</span><span class="sxs-lookup"><span data-stu-id="fa55b-139">Do not define any <xref:System.ComponentModel.AsyncCompletedEventArgs>-derived classes for methods that do not produce results.</span></span> <span data-ttu-id="fa55b-140">Используйте в этой ситуации непосредственно экземпляр <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fa55b-140">Simply use an instance of <xref:System.ComponentModel.AsyncCompletedEventArgs> itself.</span></span>

      > [!NOTE]
      > <span data-ttu-id="fa55b-141">Также полностью допустимо использовать делегат и типы <xref:System.ComponentModel.AsyncCompletedEventArgs> повторно во всех случаях, когда это возможно и уместно.</span><span class="sxs-lookup"><span data-stu-id="fa55b-141">It is perfectly acceptable, when feasible and appropriate, to reuse delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> types.</span></span> <span data-ttu-id="fa55b-142">В этом случае имя делегата не будет согласовано с именем метода, так как делегат и <xref:System.ComponentModel.AsyncCompletedEventArgs> не привязаны к одному методу.</span><span class="sxs-lookup"><span data-stu-id="fa55b-142">In this case, the naming will not be as consistent with the method name, since a given delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> won't be tied to a single method.</span></span>

## <a name="optionally-support-cancellation"></a><span data-ttu-id="fa55b-143">Возможная поддержка отмены</span><span class="sxs-lookup"><span data-stu-id="fa55b-143">Optionally Support Cancellation</span></span>

<span data-ttu-id="fa55b-144">Если ваш класс будет поддерживать отмену асинхронных операций, возможность отмены должна быть предоставлена клиенту, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="fa55b-144">If your class will support canceling asynchronous operations, cancellation should be exposed to the client as described below.</span></span> <span data-ttu-id="fa55b-145">Перед тем как определить, будет ли реализована возможность отмены, необходимо ответить на два вопроса.</span><span class="sxs-lookup"><span data-stu-id="fa55b-145">Note that there are two decision points that need to be reached before defining your cancellation support:</span></span>

- <span data-ttu-id="fa55b-146">Будет ли в вашем классе и во всех его будущих версиях всего одна асинхронная операция, которая поддерживает отмену?</span><span class="sxs-lookup"><span data-stu-id="fa55b-146">Does your class, including future anticipated additions to it, have only one asynchronous operation that supports cancellation?</span></span>

- <span data-ttu-id="fa55b-147">Может ли асинхронная операция с возможностью отмены поддерживать несколько ожидающих операций?</span><span class="sxs-lookup"><span data-stu-id="fa55b-147">Can the asynchronous operations that support cancellation support multiple pending operations?</span></span> <span data-ttu-id="fa55b-148">То есть принимает ли метод _MethodName_**Async** параметр `userState` и позволяет ли он создать несколько вызовов перед ожиданием завершения любого из них?</span><span class="sxs-lookup"><span data-stu-id="fa55b-148">That is, does the _MethodName_**Async** method take a `userState` parameter, and does it allow multiple invocations before waiting for any to finish?</span></span>

<span data-ttu-id="fa55b-149">С помощью ответов на эти вопросы и приведенной ниже таблицы определите сигнатуру метода отмены.</span><span class="sxs-lookup"><span data-stu-id="fa55b-149">Use the answers to these two questions in the table below to determine what the signature for your cancellation method should be.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="fa55b-150">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa55b-150">Visual Basic</span></span>

||<span data-ttu-id="fa55b-151">Поддерживается несколько одновременных операций</span><span class="sxs-lookup"><span data-stu-id="fa55b-151">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="fa55b-152">Только одна операция в один момент времени</span><span class="sxs-lookup"><span data-stu-id="fa55b-152">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="fa55b-153">Одна асинхронная операция во всем классе</span><span class="sxs-lookup"><span data-stu-id="fa55b-153">One Async Operation in entire class</span></span>|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|<span data-ttu-id="fa55b-154">Несколько асинхронных операций в классе</span><span class="sxs-lookup"><span data-stu-id="fa55b-154">Multiple Async Operations in class</span></span>|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a><span data-ttu-id="fa55b-155">C\#</span><span class="sxs-lookup"><span data-stu-id="fa55b-155">C\#</span></span>

||<span data-ttu-id="fa55b-156">Поддерживается несколько одновременных операций</span><span class="sxs-lookup"><span data-stu-id="fa55b-156">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="fa55b-157">Только одна операция в один момент времени</span><span class="sxs-lookup"><span data-stu-id="fa55b-157">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="fa55b-158">Одна асинхронная операция во всем классе</span><span class="sxs-lookup"><span data-stu-id="fa55b-158">One Async Operation in entire class</span></span>|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|<span data-ttu-id="fa55b-159">Несколько асинхронных операций в классе</span><span class="sxs-lookup"><span data-stu-id="fa55b-159">Multiple Async Operations in class</span></span>|`void CancelAsync(object userState);`|`void CancelAsync();`|

<span data-ttu-id="fa55b-160">При определении метода `CancelAsync(object userState)` следует быть внимательным при выборе значений состояния клиента. Эти значения должны различаться не только для всех вызовов одного асинхронного метода, но и для всех вызываемых асинхронных методов объекта.</span><span class="sxs-lookup"><span data-stu-id="fa55b-160">If you define the `CancelAsync(object userState)` method, clients must be careful when choosing their state values to make them capable of distinguishing among all asynchronous methods invoked on the object, and not just between all invocations of a single asynchronous method.</span></span>

<span data-ttu-id="fa55b-161">Для версии метода с одной асинхронной операцией выбрано имя _MethodName_**AsyncCancel**, чтобы его было удобнее искать в среде разработки, например в IntelliSense для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa55b-161">The decision to name the single-async-operation version _MethodName_**AsyncCancel** is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span></span> <span data-ttu-id="fa55b-162">При этом связанные элементы группируются и отделяются от других элементов, которые не связаны с асинхронными операциями.</span><span class="sxs-lookup"><span data-stu-id="fa55b-162">This groups the related members and distinguishes them from other members that have nothing to do with asynchronous functionality.</span></span> <span data-ttu-id="fa55b-163">Если в дальнейшем могут быть добавлены новые асинхронные операции, рекомендуется определить `CancelAsync`.</span><span class="sxs-lookup"><span data-stu-id="fa55b-163">If you expect that there may be additional asynchronous operations added in subsequent versions, it is better to define `CancelAsync`.</span></span>

<span data-ttu-id="fa55b-164">Не определяйте несколько методов из приведенной выше таблицы в одном и том же классе.</span><span class="sxs-lookup"><span data-stu-id="fa55b-164">Do not define multiple methods from the table above in the same class.</span></span> <span data-ttu-id="fa55b-165">В этом не будет никакого смысла, к тому же интерфейс класса будет загроможден лишними методами.</span><span class="sxs-lookup"><span data-stu-id="fa55b-165">That will not make sense, or it will clutter the class interface with a proliferation of methods.</span></span>

<span data-ttu-id="fa55b-166">Эти методы обычно возвращают управление немедленно, и на самом деле операция может не быть отменена.</span><span class="sxs-lookup"><span data-stu-id="fa55b-166">These methods typically will return immediately, and the operation may or may not actually cancel.</span></span> <span data-ttu-id="fa55b-167">В обработчике события _MethodName_**Completed** объект _MethodName_**CompletedEventArgs** содержит поле `Cancelled`, которое позволяет клиентам определить, была ли отменена операция.</span><span class="sxs-lookup"><span data-stu-id="fa55b-167">In the event handler for the _MethodName_**Completed** event, the _MethodName_**CompletedEventArgs** object contains a `Cancelled` field, which clients can use to determine whether the cancellation occurred.</span></span>

<span data-ttu-id="fa55b-168">Придерживайтесь семантики отмены, которая описана в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="fa55b-168">Abide by the cancellation semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-support-the-isbusy-property"></a><span data-ttu-id="fa55b-169">Возможная поддержка свойства IsBusy</span><span class="sxs-lookup"><span data-stu-id="fa55b-169">Optionally Support the IsBusy Property</span></span>

<span data-ttu-id="fa55b-170">Если ваш класс поддерживает несколько одновременных вызовов, попробуйте предоставить свойство `IsBusy`.</span><span class="sxs-lookup"><span data-stu-id="fa55b-170">If your class does not support multiple concurrent invocations, consider exposing an `IsBusy` property.</span></span> <span data-ttu-id="fa55b-171">Это позволяет разработчикам определить, выполняется ли метод _MethodName_**Async**, не перехватывая исключение из метода _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="fa55b-171">This allows developers to determine whether a _MethodName_**Async** method is running without catching an exception from the _MethodName_**Async** method.</span></span>

<span data-ttu-id="fa55b-172">Придерживайтесь семантики `IsBusy`, которая описана в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="fa55b-172">Abide by the `IsBusy` semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-progress-reporting"></a><span data-ttu-id="fa55b-173">Возможная поддержка отчетов о ходе выполнения</span><span class="sxs-lookup"><span data-stu-id="fa55b-173">Optionally Provide Support for Progress Reporting</span></span>

<span data-ttu-id="fa55b-174">Часто желательно, чтобы асинхронная операция сообщала о ходе своего выполнения.</span><span class="sxs-lookup"><span data-stu-id="fa55b-174">It is frequently desirable for an asynchronous operation to report progress during its operation.</span></span> <span data-ttu-id="fa55b-175">При использовании асинхронной модели на основе событий это можно реализовать.</span><span class="sxs-lookup"><span data-stu-id="fa55b-175">The Event-based Asynchronous Pattern provides a guideline for doing so.</span></span>

- <span data-ttu-id="fa55b-176">При необходимости определите событие, которое будет выдаваться асинхронной операцией и вызываться в соответствующем потоке.</span><span class="sxs-lookup"><span data-stu-id="fa55b-176">Optionally define an event to be raised by the asynchronous operation and invoked on the appropriate thread.</span></span> <span data-ttu-id="fa55b-177">Объект <xref:System.ComponentModel.ProgressChangedEventArgs> содержит целочисленный индикатор хода выполнения, который может принимать значения от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="fa55b-177">The <xref:System.ComponentModel.ProgressChangedEventArgs> object carries an integer-valued progress indicator that is expected to be between 0 and 100.</span></span>

- <span data-ttu-id="fa55b-178">Укажите следующее имя для этого события:</span><span class="sxs-lookup"><span data-stu-id="fa55b-178">Name this event as follows:</span></span>

  - <span data-ttu-id="fa55b-179">`ProgressChanged`, если в классе есть несколько асинхронных операций (или ожидается в будущих версиях);</span><span class="sxs-lookup"><span data-stu-id="fa55b-179">`ProgressChanged` if the class has multiple asynchronous operations (or is expected to grow to include multiple asynchronous operations in future versions);</span></span>

  - <span data-ttu-id="fa55b-180">_MethodName_**ProgressChanged**, если в классе есть одна асинхронная операция.</span><span class="sxs-lookup"><span data-stu-id="fa55b-180">_MethodName_**ProgressChanged** if the class has a single asynchronous operation.</span></span>

  <span data-ttu-id="fa55b-181">Выбор имени события соответствует выбору имени для метода отмены, как описано в разделе "Возможная поддержка отмены".</span><span class="sxs-lookup"><span data-stu-id="fa55b-181">This naming choice parallels that made for the cancellation method, as described in the Optionally Support Cancellation section.</span></span>

<span data-ttu-id="fa55b-182">В этом событии следует использовать сигнатуру делегата <xref:System.ComponentModel.ProgressChangedEventHandler> и класс <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fa55b-182">This event should use the <xref:System.ComponentModel.ProgressChangedEventHandler> delegate signature and the <xref:System.ComponentModel.ProgressChangedEventArgs> class.</span></span> <span data-ttu-id="fa55b-183">Кроме того, если есть возможность создать индикатор хода выполнения с более точной привязкой к домену (например, основанный на количестве полученных байт и общем количестве байт при операции скачивания), следует определить класс, производный от <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fa55b-183">Alternatively, if a more domain-specific progress indicator can be provided (for instance, bytes read and total bytes for a download operation), then you should define a derived class of <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span>

<span data-ttu-id="fa55b-184">Обратите внимание, что для этого класса существует только одно событие `ProgressChanged` или _MethodName_**ProgressChanged**, независимо от количества поддерживаемых асинхронных методов.</span><span class="sxs-lookup"><span data-stu-id="fa55b-184">Note that there is only one `ProgressChanged` or _MethodName_**ProgressChanged** event for the class, regardless of the number of asynchronous methods it supports.</span></span> <span data-ttu-id="fa55b-185">Чтобы различать изменения хода выполнения для нескольких одновременных операций, клиентам следует использовать объект `userState`, который передается в метод _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="fa55b-185">Clients are expected to use the `userState` object that is passed to the _MethodName_**Async** methods to distinguish among progress updates on multiple concurrent operations.</span></span>

<span data-ttu-id="fa55b-186">Возможны ситуации, при которых несколько операций поддерживают ход выполнения и каждая операция возвращает собственный индикатор хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="fa55b-186">There may be situations in which multiple operations support progress and each returns a different indicator for progress.</span></span> <span data-ttu-id="fa55b-187">В этом случае одним событием `ProgressChanged` не обойтись и необходимо рассмотреть поддержку нескольких событий `ProgressChanged`.</span><span class="sxs-lookup"><span data-stu-id="fa55b-187">In this case, a single `ProgressChanged` event is not appropriate, and you may consider supporting multiple `ProgressChanged` events.</span></span> <span data-ttu-id="fa55b-188">В этом случае используйте шаблон именования _MethodName_**ProgressChanged** для каждого метода _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="fa55b-188">In this case use a naming pattern of _MethodName_**ProgressChanged** for each _MethodName_**Async** method.</span></span>

<span data-ttu-id="fa55b-189">Придерживайтесь семантики отчета о ходе выполнения, которая описана в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="fa55b-189">Abide by the progress-reporting semantics described [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-returning-incremental-results"></a><span data-ttu-id="fa55b-190">Возможная поддержка возврата добавочных результатов</span><span class="sxs-lookup"><span data-stu-id="fa55b-190">Optionally Provide Support for Returning Incremental Results</span></span>

<span data-ttu-id="fa55b-191">Иногда асинхронная операция может возвращать добавочные результаты до своего завершения.</span><span class="sxs-lookup"><span data-stu-id="fa55b-191">Sometimes an asynchronous operation can return incremental results prior to completion.</span></span> <span data-ttu-id="fa55b-192">Поддержку этого сценария можно реализовать различными способами.</span><span class="sxs-lookup"><span data-stu-id="fa55b-192">There are a number of options that can be used to support this scenario.</span></span> <span data-ttu-id="fa55b-193">Ниже приведены некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="fa55b-193">Some examples follow.</span></span>

### <a name="single-operation-class"></a><span data-ttu-id="fa55b-194">Класс с одной операцией</span><span class="sxs-lookup"><span data-stu-id="fa55b-194">Single-operation Class</span></span>

<span data-ttu-id="fa55b-195">Если ваш класс поддерживает только одну асинхронную операцию и эта операция может возвращать добавочные результаты, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fa55b-195">If your class only supports a single asynchronous operation, and that operation is able to return incremental results, then:</span></span>

- <span data-ttu-id="fa55b-196">Расширьте тип <xref:System.ComponentModel.ProgressChangedEventArgs>, включив в него результаты с приращением, и определите событие _MethodName_**ProgressChanged** с использованием этих дополнительных данных.</span><span class="sxs-lookup"><span data-stu-id="fa55b-196">Extend the <xref:System.ComponentModel.ProgressChangedEventArgs> type to carry the incremental result data, and define a _MethodName_**ProgressChanged** event with this extended data.</span></span>

- <span data-ttu-id="fa55b-197">Создавайте это событие _MethodName_**ProgressChanged** при каждом появлении сведений о результатах.</span><span class="sxs-lookup"><span data-stu-id="fa55b-197">Raise this _MethodName_**ProgressChanged** event when there is an incremental result to report.</span></span>

<span data-ttu-id="fa55b-198">Это решение применимо только к классам с одной асинхронной операцией, чтобы не возникало конфликтов с информированием о добавочных результатах "по всем операциям" в том же событии, как в случае с событием _имя_метода_**ProgressChanged**.</span><span class="sxs-lookup"><span data-stu-id="fa55b-198">This solution applies specifically to a single-async-operation class because there is no problem with the same event occurring to return incremental results on "all operations", as the _MethodName_**ProgressChanged** event does.</span></span>

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a><span data-ttu-id="fa55b-199">Класс с несколькими операциями, предоставляющий однородные добавочные результаты</span><span class="sxs-lookup"><span data-stu-id="fa55b-199">Multiple-operation Class with Homogeneous Incremental Results</span></span>

<span data-ttu-id="fa55b-200">В данном случае класс поддерживает несколько асинхронных методов, каждый из которых может возвращать добавочные результаты, и эти добавочные результаты имеют одинаковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="fa55b-200">In this case, your class supports multiple asynchronous methods, each capable of returning incremental results, and these incremental results all have the same type of data.</span></span>

<span data-ttu-id="fa55b-201">Используйте модель, описанную выше для классов с одной операцией, так как эта же структура <xref:System.EventArgs> подойдет для любых добавочных результатов.</span><span class="sxs-lookup"><span data-stu-id="fa55b-201">Follow the model described above for single-operation classes, as the same <xref:System.EventArgs> structure will work for all incremental results.</span></span> <span data-ttu-id="fa55b-202">Определите событие `ProgressChanged` вместо события _MethodName_**ProgressChanged**, так как оно применяется к нескольким асинхронным методам.</span><span class="sxs-lookup"><span data-stu-id="fa55b-202">Define a `ProgressChanged` event instead of a _MethodName_**ProgressChanged** event, since it applies to multiple asynchronous methods.</span></span>

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a><span data-ttu-id="fa55b-203">Класс с несколькими операциями, предоставляющий неоднородные добавочные результаты</span><span class="sxs-lookup"><span data-stu-id="fa55b-203">Multiple-operation Class with Heterogeneous Incremental Results</span></span>

<span data-ttu-id="fa55b-204">Если ваш класс поддерживает несколько асинхронных методов, которые возвращают данные различных типов, необходимо сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="fa55b-204">If your class supports multiple asynchronous methods, each returning a different type of data, you should:</span></span>

- <span data-ttu-id="fa55b-205">Разделите отправляемые отчеты о добавочных результатах и отчеты о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="fa55b-205">Separate your incremental result reporting from your progress reporting.</span></span>

- <span data-ttu-id="fa55b-206">Определите отдельное событие _MethodName_**ProgressChanged** с соответствующими аргументами <xref:System.EventArgs> для каждого асинхронного метода, чтобы обрабатывать добавочные сведения о результатах для этого метода.</span><span class="sxs-lookup"><span data-stu-id="fa55b-206">Define a separate _MethodName_**ProgressChanged** event with appropriate <xref:System.EventArgs> for each asynchronous method to handle that method's incremental result data.</span></span>

<span data-ttu-id="fa55b-207">Вызовите этот обработчик события в соответствующем потоке, как описано в разделе [Рекомендации по реализации асинхронной модели на основе событий](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="fa55b-207">Invoke that event handler on the appropriate thread as described in [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="handling-out-and-ref-parameters-in-methods"></a><span data-ttu-id="fa55b-208">Обработка выходных и ссылочных параметров в методах</span><span class="sxs-lookup"><span data-stu-id="fa55b-208">Handling Out and Ref Parameters in Methods</span></span>

<span data-ttu-id="fa55b-209">Хотя на платформе .NET Framework в целом не рекомендуется использовать `out` или `ref`, это можно сделать при соблюдении некоторых правил.</span><span class="sxs-lookup"><span data-stu-id="fa55b-209">Although the use of `out` and `ref` is, in general, discouraged in the .NET Framework, here are the rules to follow when they are present:</span></span>

<span data-ttu-id="fa55b-210">Для данного синхронного метода *имя_метода*:</span><span class="sxs-lookup"><span data-stu-id="fa55b-210">Given a synchronous method *MethodName*:</span></span>

- <span data-ttu-id="fa55b-211">параметры `out` метода *MethodName* не должны быть частью метода _MethodName_**Async**.</span><span class="sxs-lookup"><span data-stu-id="fa55b-211">`out` parameters to *MethodName* should not be part of _MethodName_**Async**.</span></span> <span data-ttu-id="fa55b-212">Вместо этого они должны входить в метод _MethodName_**CompletedEventArgs** с тем же именем, что и аналогичные параметры для *MethodName* (если нет более подходящего имени).</span><span class="sxs-lookup"><span data-stu-id="fa55b-212">Instead, they should be part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

- <span data-ttu-id="fa55b-213">Параметры `ref`, передаваемые в метод *MethodName* должны входить в метод _MethodName_**Async** и _MethodName_**CompletedEventArgs** с тем же именем, что и аналогичные параметры для *MethodName* (если нет более подходящего имени).</span><span class="sxs-lookup"><span data-stu-id="fa55b-213">`ref` parameters to *MethodName* should appear as part of _MethodName_**Async**, and as part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

<span data-ttu-id="fa55b-214">Например, если учитывать, что:</span><span class="sxs-lookup"><span data-stu-id="fa55b-214">For example, given:</span></span>

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

<span data-ttu-id="fa55b-215">Асинхронный метод и его класс <xref:System.ComponentModel.AsyncCompletedEventArgs> будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fa55b-215">Your asynchronous method and its <xref:System.ComponentModel.AsyncCompletedEventArgs> class would look like this:</span></span>

```vb
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)

Public Class MethodNameCompletedEventArgs
    Inherits System.ComponentModel.AsyncCompletedEventArgs
    Public ReadOnly Property Result() As Integer
    End Property
    Public ReadOnly Property Arg2() As String
    End Property
    Public ReadOnly Property Arg3() As String
    End Property
End Class
```

```csharp
public void MethodNameAsync(string arg1, string arg2);

public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs
{
    public int Result { get; };
    public string Arg2 { get; };
    public string Arg3 { get; };
}
```

## <a name="see-also"></a><span data-ttu-id="fa55b-216">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fa55b-216">See also</span></span>

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [<span data-ttu-id="fa55b-217">Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий</span><span class="sxs-lookup"><span data-stu-id="fa55b-217">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="fa55b-218">Практическое руководство. Фоновое выполнение операции</span><span class="sxs-lookup"><span data-stu-id="fa55b-218">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="fa55b-219">Практическое руководство. Реализация формы, в которой выполняется фоновая операция</span><span class="sxs-lookup"><span data-stu-id="fa55b-219">How to: Implement a Form That Uses a Background Operation</span></span>](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="fa55b-220">Определение, когда следует реализовать асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="fa55b-220">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="fa55b-221">Рекомендации по реализации асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="fa55b-221">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="fa55b-222">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="fa55b-222">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
