---
title: Async (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: 244f468d9432e132c93ae8272d51098f86ad439a
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753348"
---
# <a name="async-visual-basic"></a><span data-ttu-id="eb971-102">Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb971-102">Async (Visual Basic)</span></span>
<span data-ttu-id="eb971-103">`Async` Модификатор указывает, что метод или [лямбда-выражение](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) она изменяет является асинхронным.</span><span class="sxs-lookup"><span data-stu-id="eb971-103">The `Async` modifier indicates that the method or [lambda expression](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) that it modifies is asynchronous.</span></span> <span data-ttu-id="eb971-104">Такие методы называются *асинхронные методы*.</span><span class="sxs-lookup"><span data-stu-id="eb971-104">Such methods are referred to as *async methods*.</span></span>  
  
 <span data-ttu-id="eb971-105">Асинхронный метод представляет собой удобный способ для выполнения работы, которая может занять длительное время, без блокировки потока вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="eb971-105">An async method provides a convenient way to do potentially long-running work without blocking the caller's thread.</span></span> <span data-ttu-id="eb971-106">Код, вызывающий асинхронный метод может возобновить работу без ожидания асинхронного метода завершения.</span><span class="sxs-lookup"><span data-stu-id="eb971-106">The caller of an async method can resume its work without waiting for the async method to finish.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb971-107">Ключевые слова `Async` и `Await` появились в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="eb971-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="eb971-108">Общие сведения об асинхронном программировании см. в разделе [асинхронное программирование с использованием ключевых слов Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="eb971-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="eb971-109">В следующем примере показана структура асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="eb971-109">The following example shows the structure of an async method.</span></span> <span data-ttu-id="eb971-110">По соглашению имена асинхронных методов заканчиваться «Async».</span><span class="sxs-lookup"><span data-stu-id="eb971-110">By convention, async method names end in "Async."</span></span>  
  
```vb  
Public Async Function ExampleMethodAsync() As Task(Of Integer)  
    ' . . .  
  
    ' At the Await expression, execution in this method is suspended and,  
    ' if AwaitedProcessAsync has not already finished, control returns  
    ' to the caller of ExampleMethodAsync. When the awaited task is   
    ' completed, this method resumes execution.   
    Dim exampleInt As Integer = Await AwaitedProcessAsync()  
  
    ' . . .  
  
    ' The return statement completes the task. Any method that is   
    ' awaiting ExampleMethodAsync can now get the integer result.  
    Return exampleInt  
End Function  
```  
  
 <span data-ttu-id="eb971-111">Как правило, метод была изменена `Async` ключевое слово содержит по крайней мере один [Await](../../../visual-basic/language-reference/modifiers/async.md) выражения или оператора.</span><span class="sxs-lookup"><span data-stu-id="eb971-111">Typically, a method modified by the `Async` keyword contains at least one [Await](../../../visual-basic/language-reference/modifiers/async.md) expression or statement.</span></span> <span data-ttu-id="eb971-112">Метод выполняется синхронно, пока не будет достигнут первый `Await`, после чего она приостанавливается до завершения выполнения ожидающей задачи.</span><span class="sxs-lookup"><span data-stu-id="eb971-112">The method runs synchronously until it reaches the first `Await`, at which point it suspends until the awaited task completes.</span></span> <span data-ttu-id="eb971-113">В то же время управление возвращается коду, вызвавшему метод.</span><span class="sxs-lookup"><span data-stu-id="eb971-113">In the meantime, control is returned to the caller of the method.</span></span> <span data-ttu-id="eb971-114">Если метод не содержит `Await` выражения или оператора, метод не приостановлена и выполняется аналогично синхронному методу.</span><span class="sxs-lookup"><span data-stu-id="eb971-114">If the method doesn’t contain an `Await` expression or statement, the method isn’t suspended and executes as a synchronous method does.</span></span> <span data-ttu-id="eb971-115">Предупреждение компилятора оповещает о всех асинхронных методах, которые не содержат `Await` из-за этой ситуации может указывать на ошибку.</span><span class="sxs-lookup"><span data-stu-id="eb971-115">A compiler warning alerts you to any async methods that don't contain `Await` because that situation might indicate an error.</span></span> <span data-ttu-id="eb971-116">Дополнительные сведения см. в разделе [Ошибка компилятора](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="eb971-116">For more information, see the [compiler error](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).</span></span>  
  
 <span data-ttu-id="eb971-117">`Async` Ключевое слово — это незарезервированных ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="eb971-117">The `Async` keyword is an unreserved keyword.</span></span> <span data-ttu-id="eb971-118">Это ключевое слово, когда оно изменяет метод или лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="eb971-118">It is a keyword when it modifies a method or a lambda expression.</span></span> <span data-ttu-id="eb971-119">В других контекстах он интерпретируется как идентификатор.</span><span class="sxs-lookup"><span data-stu-id="eb971-119">In all other contexts, it is interpreted as an identifier.</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="eb971-120">Типы возвращаемых значений</span><span class="sxs-lookup"><span data-stu-id="eb971-120">Return Types</span></span>  
 <span data-ttu-id="eb971-121">Асинхронный метод является либо [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) процедура, или [функция](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) процедуру, которая имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="eb971-121">An async method is either a [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure, or a [Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) procedure that has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="eb971-122">Метод не может объявить все [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) параметров.</span><span class="sxs-lookup"><span data-stu-id="eb971-122">The method cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="eb971-123">Указать `Task(Of TResult)` для возвращаемого типа асинхронного метода Если [возвращают](../../../visual-basic/language-reference/statements/return-statement.md) метода имеет операндом типа TResult.</span><span class="sxs-lookup"><span data-stu-id="eb971-123">You specify `Task(Of TResult)` for the return type of an async method if the [Return](../../../visual-basic/language-reference/statements/return-statement.md) statement of the method has an operand of type TResult.</span></span> <span data-ttu-id="eb971-124">Класс `Task` используется при отсутствии содержательного значения, возвращаемого методом при его завершении.</span><span class="sxs-lookup"><span data-stu-id="eb971-124">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="eb971-125">То есть вызов метода возвращает `Task`, но при `Task` завершения любой `Await` инструкцию, которая ожидает `Task` не возвращающих результирующее значение.</span><span class="sxs-lookup"><span data-stu-id="eb971-125">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `Await` statement that's awaiting the `Task` doesn’t produce a result value.</span></span>  
  
 <span data-ttu-id="eb971-126">Асинхронные подпрограммы, используются в основном для определения обработчиков событий где `Sub` процедуры не требуется.</span><span class="sxs-lookup"><span data-stu-id="eb971-126">Async subroutines are used primarily to define event handlers where a `Sub` procedure is required.</span></span> <span data-ttu-id="eb971-127">Код, вызывающий асинхронный подпрограммы не может ожидать его и не могут перехватывать исключения, которые выдает этот метод.</span><span class="sxs-lookup"><span data-stu-id="eb971-127">The caller of an async subroutine can't await it and can't catch exceptions that the method throws.</span></span>  
  
 <span data-ttu-id="eb971-128">Дополнительные сведения и примеры см. в разделе [Асинхронные типы возвращаемых значений](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="eb971-128">For more information and examples, see [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb971-129">Пример</span><span class="sxs-lookup"><span data-stu-id="eb971-129">Example</span></span>  
 <span data-ttu-id="eb971-130">В следующих примерах асинхронный обработчик событий, асинхронное лямбда-выражение и асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="eb971-130">The following examples show an async event handler, an async lambda expression, and an async method.</span></span> <span data-ttu-id="eb971-131">Полный пример, использующий этих элементов см. в разделе [Пошаговое руководство: доступ к веб-сайте, с помощью Async и Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="eb971-131">For a full example that uses these elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="eb971-132">Код пошагового руководства можно скачать в разделе [Примеры кода от разработчиков](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="eb971-132">You can download the walkthrough code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>  
  
```vb  
' An event handler must be a Sub procedure.  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
    textBox1.Clear()  
    ' SumPageSizesAsync is a method that returns a Task.  
    Await SumPageSizesAsync()  
    textBox1.Text = vbCrLf & "Control returned to button1_Click."  
End Sub  
  
' The following async lambda expression creates an equivalent anonymous  
' event handler.  
AddHandler button1.Click, Async Sub(sender, e)  
                              textBox1.Clear()  
                              ' SumPageSizesAsync is a method that returns a Task.  
                              Await SumPageSizesAsync()  
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."  
                          End Sub  
  
' The following async method returns a Task(Of T).  
' A typical call awaits the Byte array result:  
'      Dim result As Byte() = Await GetURLContents("http://msdn.com")  
Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
    ' The downloaded resource ends up in the variable named content.  
    Dim content = New MemoryStream()  
  
    ' Initialize an HttpWebRequest for the current URL.  
    Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
    ' Send the request to the Internet resource and wait for  
    ' the response.  
    Using response As WebResponse = Await webReq.GetResponseAsync()  
        ' Get the data stream that is associated with the specified URL.  
        Using responseStream As Stream = response.GetResponseStream()  
            ' Read the bytes in responseStream and copy them to content.    
            ' CopyToAsync returns a Task, not a Task<T>.  
            Await responseStream.CopyToAsync(content)  
        End Using  
    End Using  
  
    ' Return the result as a byte array.  
    Return content.ToArray()  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb971-133">См. также</span><span class="sxs-lookup"><span data-stu-id="eb971-133">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>  
 [<span data-ttu-id="eb971-134">Оператор Await</span><span class="sxs-lookup"><span data-stu-id="eb971-134">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="eb971-135">Асинхронное программирование с использованием ключевых слов Async и Await</span><span class="sxs-lookup"><span data-stu-id="eb971-135">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="eb971-136">Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await</span><span class="sxs-lookup"><span data-stu-id="eb971-136">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
