---
title: "Оператор await (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b50b9c7283ddd4d3f8484854bdffff3d76181c9f
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="await-operator-visual-basic"></a><span data-ttu-id="9bffc-102">Оператор Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bffc-102">Await Operator (Visual Basic)</span></span>
<span data-ttu-id="9bffc-103">Можно применить `Await` оператор операндом в асинхронный метод или лямбда-выражения для приостановки выполнения метода завершения ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="9bffc-103">You apply the `Await` operator to an operand in an asynchronous method or lambda expression to suspend execution of the method until the awaited task completes.</span></span> <span data-ttu-id="9bffc-104">Задача представляет выполняющуюся работу.</span><span class="sxs-lookup"><span data-stu-id="9bffc-104">The task represents ongoing work.</span></span>  
  
 <span data-ttu-id="9bffc-105">Метод, в котором `Await` используется должен иметь [Async](../../../visual-basic/language-reference/modifiers/async.md) модификатор.</span><span class="sxs-lookup"><span data-stu-id="9bffc-105">The method in which `Await` is used must have an [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="9bffc-106">Такой метод, определенный с помощью `Async` модификатор и обычно содержит один или несколько `Await` выражения, называется *асинхронный метод*.</span><span class="sxs-lookup"><span data-stu-id="9bffc-106">Such a method, defined by using the `Async` modifier, and usually containing one or more `Await` expressions, is referred to as an *async method*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bffc-107">Ключевые слова `Async` и `Await` появились в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="9bffc-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="9bffc-108">Введение в асинхронном программировании см. в разделе [асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="9bffc-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="9bffc-109">Как правило, задача, к которому применяется `Await` оператор является возвращаемым значением из вызова метода, реализующего [асинхронная модель на основе задач](http://go.microsoft.com/fwlink/?LinkId=204847), то есть, <xref:System.Threading.Tasks.Task>или <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="9bffc-109">Typically, the task to which you apply the `Await` operator is the return value from a call to a method that implements the [Task-Based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=204847), that is, a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="9bffc-110">В следующем коде <xref:System.Net.Http.HttpClient>метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>возвращает `getContentsTask`, `Task(Of Byte())`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="9bffc-110">In the following code, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> returns `getContentsTask`, a `Task(Of Byte())`.</span></span> <span data-ttu-id="9bffc-111">Задача является обещание создать фактическое байтового массива, при завершении операции.</span><span class="sxs-lookup"><span data-stu-id="9bffc-111">The task is a promise to produce the actual byte array when the operation is complete.</span></span> <span data-ttu-id="9bffc-112">Оператор `Await` применяется к `getContentsTask` для приостановки выполнения в `SumPageSizesAsync` до завершения `getContentsTask`.</span><span class="sxs-lookup"><span data-stu-id="9bffc-112">The `Await` operator is applied to `getContentsTask` to suspend execution in `SumPageSizesAsync` until `getContentsTask` is complete.</span></span> <span data-ttu-id="9bffc-113">В то же время управление возвращается вызывающему объекту `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9bffc-113">In the meantime, control is returned to the caller of `SumPageSizesAsync`.</span></span> <span data-ttu-id="9bffc-114">Когда `getContentsTask` завершается, результатом выражения `Await` является массив байтов.</span><span class="sxs-lookup"><span data-stu-id="9bffc-114">When `getContentsTask` is finished, the `Await` expression evaluates to a byte array.</span></span>  
  
<span data-ttu-id="9bffc-115"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="9bffc-115"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
> [!IMPORTANT]
>  <span data-ttu-id="9bffc-116">Полный пример см. в разделе [Пошаговое руководство: доступ к Интернету с помощью Async и Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="9bffc-116">For the complete example, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="9bffc-117">Можно загрузить образец из [примеров кода для разработчиков](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) на веб-сайте Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9bffc-117">You can download the sample from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) on the Microsoft website.</span></span> <span data-ttu-id="9bffc-118">Этот пример представлен в проекте AsyncWalkthrough_HttpClient.</span><span class="sxs-lookup"><span data-stu-id="9bffc-118">The example is in the AsyncWalkthrough_HttpClient project.</span></span>  
  
 <span data-ttu-id="9bffc-119">Если `Await` применяется к результату вызова метода, который возвращает `Task(Of TResult)`, тип `Await` выражение является TResult.</span><span class="sxs-lookup"><span data-stu-id="9bffc-119">If `Await` is applied to the result of a method call that returns a `Task(Of TResult)`, the type of the `Await` expression is TResult.</span></span> <span data-ttu-id="9bffc-120">Если `Await` применяется к результату вызова метода, который возвращает `Task`, `Await` выражение не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="9bffc-120">If `Await` is applied to the result of a method call that returns a `Task`, the `Await` expression doesn't return a value.</span></span> <span data-ttu-id="9bffc-121">В следующем примере демонстрируется это различие.</span><span class="sxs-lookup"><span data-stu-id="9bffc-121">The following example illustrates the difference.</span></span>  
  
<span data-ttu-id="9bffc-122"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="9bffc-122"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="9bffc-123">`Await` Выражения или оператора не блокирует поток, на котором он выполняется.</span><span class="sxs-lookup"><span data-stu-id="9bffc-123">An `Await` expression or statement does not block the thread on which it is executing.</span></span> <span data-ttu-id="9bffc-124">Вместо этого он предписывает компилятору входа остальную часть асинхронного метода после `Await` выражение как продолжение на ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="9bffc-124">Instead, it causes the compiler to sign up the rest of the async method, after the `Await` expression, as a continuation on the awaited task.</span></span> <span data-ttu-id="9bffc-125">Затем управление возвращается в объект, вызывающий асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="9bffc-125">Control then returns to the caller of the async method.</span></span> <span data-ttu-id="9bffc-126">Когда задача завершается, она вызывает свое продолжение и выполнение асинхронного метода возобновляется с того момента, где оно было остановлено.</span><span class="sxs-lookup"><span data-stu-id="9bffc-126">When the task completes, it invokes its continuation, and execution of the async method resumes where it left off.</span></span>  
  
 <span data-ttu-id="9bffc-127">`Await` Выражение может возникать только в теле немедленно включающего метода или лямбда-выражение, помеченного атрибутом `Async` модификатор.</span><span class="sxs-lookup"><span data-stu-id="9bffc-127">An `Await` expression can occur only in the body of an immediately enclosing method or lambda expression that is marked by an `Async` modifier.</span></span> <span data-ttu-id="9bffc-128">Термин *Await* служит ключевое слово только в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="9bffc-128">The term *Await* serves as a keyword only in that context.</span></span> <span data-ttu-id="9bffc-129">В другом месте он интерпретируется как идентификатор.</span><span class="sxs-lookup"><span data-stu-id="9bffc-129">Elsewhere, it is interpreted as an identifier.</span></span> <span data-ttu-id="9bffc-130">В асинхронный метод или лямбда-выражения `Await` выражение не может появляться в выражении запроса в `catch` или `finally` блока [Try... CATCH... Наконец](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) инструкции в цикле управления переменной выражении `For` или `For Each` цикла, или в теле [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) инструкции.</span><span class="sxs-lookup"><span data-stu-id="9bffc-130">Within the async method or lambda expression, an `Await` expression cannot occur in a query expression, in the `catch` or `finally` block of a [Try…Catch…Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) statement, in the loop control variable expression of a `For` or `For Each` loop, or in the body of a [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) statement.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="9bffc-131">Исключения</span><span class="sxs-lookup"><span data-stu-id="9bffc-131">Exceptions</span></span>  
 <span data-ttu-id="9bffc-132">Большинство асинхронные методы возвращают <xref:System.Threading.Tasks.Task>или <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="9bffc-132">Most async methods return a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="9bffc-133">Свойства возвращаемой задачи содержат сведения о ее состоянии и журнале, например завершена ли задача, вызвал ли асинхронный метод исключение или был отменен и каков окончательный результат.</span><span class="sxs-lookup"><span data-stu-id="9bffc-133">The properties of the returned task carry information about its status and history, such as whether the task is complete, whether the async method caused an exception or was canceled, and what the final result is.</span></span> <span data-ttu-id="9bffc-134">Оператор `Await` обращается к этим свойствам.</span><span class="sxs-lookup"><span data-stu-id="9bffc-134">The `Await` operator accesses those properties.</span></span>  
  
 <span data-ttu-id="9bffc-135">Если вы ожидаете возвращающий задачу асинхронный метод, который вызывает исключение, то оператор `Await` повторно создает это исключение.</span><span class="sxs-lookup"><span data-stu-id="9bffc-135">If you await a task-returning async method that causes an exception, the  `Await` operator rethrows the exception.</span></span>  
  
 <span data-ttu-id="9bffc-136">Если ожидать возвращения задач асинхронного метода, отменяется, `Await` <xref:System.OperationCanceledException>.</xref:System.OperationCanceledException> повторно создает оператор</span><span class="sxs-lookup"><span data-stu-id="9bffc-136">If you await a task-returning async method that is canceled, the `Await` operator rethrows an <xref:System.OperationCanceledException>.</span></span>  
  
 <span data-ttu-id="9bffc-137">Одна задача, которая находится в состоянии сбоя, может отражать несколько исключений.</span><span class="sxs-lookup"><span data-stu-id="9bffc-137">A single task that is in a faulted state can reflect multiple exceptions.</span></span>  <span data-ttu-id="9bffc-138">Например задача может быть результатом вызова <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9bffc-138">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="9bffc-139">Если вы ожидаете такую задачу, операция await повторно вызывает только одно из исключений.</span><span class="sxs-lookup"><span data-stu-id="9bffc-139">When you await such a task, the await operation rethrows only one of the exceptions.</span></span> <span data-ttu-id="9bffc-140">Однако невозможно предсказать, какие исключения создаются повторно.</span><span class="sxs-lookup"><span data-stu-id="9bffc-140">However, you can't predict which of the exceptions is rethrown.</span></span>  
  
 <span data-ttu-id="9bffc-141">Примеры для обработки ошибок в асинхронные методы в разделе [Try... CATCH... Оператор Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9bffc-141">For examples of error handling in async methods, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bffc-142">Пример</span><span class="sxs-lookup"><span data-stu-id="9bffc-142">Example</span></span>  
 <span data-ttu-id="9bffc-143">В следующем примере Windows Forms демонстрируется использование `Await` в асинхронном методе `WaitAsynchronouslyAsync`.</span><span class="sxs-lookup"><span data-stu-id="9bffc-143">The following Windows Forms example illustrates the use of `Await` in an async method, `WaitAsynchronouslyAsync`.</span></span> <span data-ttu-id="9bffc-144">Сравните поведение этого метода с поведением `WaitSynchronously`.</span><span class="sxs-lookup"><span data-stu-id="9bffc-144">Contrast the behavior of that method with the behavior of `WaitSynchronously`.</span></span> <span data-ttu-id="9bffc-145">Без `Await` оператор, `WaitSynchronously` выполняется синхронно, несмотря на использование `Async` модификатор в его определение и вызов <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>в его теле.</xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9bffc-145">Without an `Await` operator, `WaitSynchronously` runs synchronously despite the use of the `Async` modifier in its definition and a call to <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> in its body.</span></span>  
  
```vb  
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
    ' Call the method that runs asynchronously.  
    Dim result As String = Await WaitAsynchronouslyAsync()  
  
    ' Call the method that runs synchronously.  
    'Dim result As String = Await WaitSynchronously()  
  
    ' Display the result.  
    TextBox1.Text &= result  
End Sub  
  
' The following method runs asynchronously. The UI thread is not  
' blocked during the delay. You can move or resize the Form1 window   
' while Task.Delay is running.  
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)  
    Await Task.Delay(10000)  
    Return "Finished"  
End Function  
  
' The following method runs synchronously, despite the use of Async.  
' You cannot move or resize the Form1 window while Thread.Sleep  
' is running because the UI thread is blocked.  
Public Async Function WaitSynchronously() As Task(Of String)  
    ' Import System.Threading for the Sleep method.  
    Thread.Sleep(10000)  
    Return "Finished"  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bffc-146">См. также</span><span class="sxs-lookup"><span data-stu-id="9bffc-146">See Also</span></span>  
 <span data-ttu-id="9bffc-147">[Асинхронное программирование с использованием Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="9bffc-147">[Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="9bffc-148"> [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="9bffc-148"> [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="9bffc-149"> [Async](../../../visual-basic/language-reference/modifiers/async.md)</span><span class="sxs-lookup"><span data-stu-id="9bffc-149"> [Async](../../../visual-basic/language-reference/modifiers/async.md)</span></span>
