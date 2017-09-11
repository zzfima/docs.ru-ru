---
title: "Асинхронные типы возвращаемых значений (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 703d3fc3f503017edf38521d77f9b15a92d0ebf3
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="async-return-types-visual-basic"></a><span data-ttu-id="7f6ad-102">Асинхронные типы возвращаемых значений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f6ad-102">Async Return Types (Visual Basic)</span></span>
<span data-ttu-id="7f6ad-103">Асинхронные методы имеют три возможные возвращаемые типы: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>и void.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="7f6ad-103">Async methods have three possible return types: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, and void.</span></span> <span data-ttu-id="7f6ad-104">В Visual Basic, возвращаемый тип void записывается как [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) процедуры.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-104">In Visual Basic, the void return type is written as a [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure.</span></span> <span data-ttu-id="7f6ad-105">Дополнительные сведения об асинхронных методах см. в разделе [асинхронное программирование с использованием Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="7f6ad-105">For more information about async methods, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="7f6ad-106">Каждый тип возвращаемого значения рассматривается в одном из следующих разделов, а полный пример, в котором используются все три типа, вы найдете в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-106">Each return type is examined in one of the following sections, and you can find a full example that uses all three types at the end of the topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f6ad-107">Чтобы выполнить этот пример, необходимо иметь Visual Studio 2012 или более поздней версии и платформы .NET Framework 4.5 или более новая версия вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-107">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="7f6ad-108"><a name="BKMK_TaskTReturnType"></a>Возвращаемый тип Task(T)</span><span class="sxs-lookup"><span data-stu-id="7f6ad-108"><a name="BKMK_TaskTReturnType"></a> Task(T) Return Type</span></span>  
 <span data-ttu-id="7f6ad-109"><xref:System.Threading.Tasks.Task%601>Возвращаемый тип используется для асинхронного метода, который содержит [вернуть](../../../../visual-basic/language-reference/statements/return-statement.md) инструкции, в которой операнд имеет тип `TResult`.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="7f6ad-109">The <xref:System.Threading.Tasks.Task%601> return type is used for an async method that contains a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement in which the operand has type `TResult`.</span></span>  
  
 <span data-ttu-id="7f6ad-110">В следующем примере `TaskOfT_MethodAsync` асинхронный метод содержит оператор return, который возвращает целое число.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-110">In the following example, the `TaskOfT_MethodAsync` async method contains a return statement that returns an integer.</span></span> <span data-ttu-id="7f6ad-111">Таким образом, в объявлении метода необходимо указать тип возвращаемого значения `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-111">Therefore, the method declaration must specify a return type of `Task(Of Integer)`.</span></span>  
  
```vb  
' TASK(OF T) EXAMPLE  
Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.FromResult is a placeholder for actual work that returns a string.  
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
    ' The method then can process the result in some way.  
    Dim leisureHours As Integer  
    If today.First() = "S" Then  
        leisureHours = 16  
    Else  
        leisureHours = 5  
    End If  
  
    ' Because the return statement specifies an operand of type Integer, the   
    ' method must have a return type of Task(Of Integer).   
    Return leisureHours  
End Function  
```  
  
 <span data-ttu-id="7f6ad-112">При `TaskOfT_MethodAsync` вызывается из в выражении await выражения await извлекает целочисленное значение (значение `leisureHours`), хранящегося в задачу, которая возвращается `TaskOfT_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-112">When `TaskOfT_MethodAsync` is called from within an await expression, the await expression retrieves the integer value (the value of `leisureHours`) that's stored in the task that's returned by `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="7f6ad-113">Дополнительные сведения о выражений ожидания см. в разделе [оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7f6ad-113">For more information about await expressions, see [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md).</span></span>  
  
 <span data-ttu-id="7f6ad-114">Следующий код вызывает и ожидает метод `TaskOfT_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-114">The following code calls and awaits method `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="7f6ad-115">Результат присваивается `result1` переменной.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-115">The result is assigned to the `result1` variable.</span></span>  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 <span data-ttu-id="7f6ad-116">Позволяет лучше понять, как это происходит, разделяя вызов `TaskOfT_MethodAsync` от применения `Await`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-116">You can better understand how this happens by separating the call to `TaskOfT_MethodAsync` from the application of `Await`, as the following code shows.</span></span> <span data-ttu-id="7f6ad-117">Вызов метода `TaskOfT_MethodAsync` , не возвращает ожидаемый немедленно `Task(Of Integer)`, как и следовало ожидать из объявления метода.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-117">A call to method `TaskOfT_MethodAsync` that isn't immediately awaited returns a `Task(Of Integer)`, as you would expect from the declaration of the method.</span></span> <span data-ttu-id="7f6ad-118">Назначенные задачи `integerTask` переменной в примере.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-118">The task is assigned to the `integerTask` variable in the example.</span></span> <span data-ttu-id="7f6ad-119">Поскольку `integerTask` — <xref:System.Threading.Tasks.Task%601>, он содержит <xref:System.Threading.Tasks.Task%601.Result>свойство типа `TResult`.</xref:System.Threading.Tasks.Task%601.Result> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="7f6ad-119">Because `integerTask` is a <xref:System.Threading.Tasks.Task%601>, it contains a <xref:System.Threading.Tasks.Task%601.Result> property of type `TResult`.</span></span> <span data-ttu-id="7f6ad-120">В этом примере TResult представляет собой целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-120">In this case, TResult represents an integer type.</span></span> <span data-ttu-id="7f6ad-121">Когда `Await` применяется к `integerTask`, выражение await содержимого <xref:System.Threading.Tasks.Task%601.Result%2A>Свойства `integerTask`.</xref:System.Threading.Tasks.Task%601.Result%2A></span><span class="sxs-lookup"><span data-stu-id="7f6ad-121">When `Await` is applied to `integerTask`, the await expression evaluates to the contents of the <xref:System.Threading.Tasks.Task%601.Result%2A> property of `integerTask`.</span></span> <span data-ttu-id="7f6ad-122">Значение присваивается `result2` переменной.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-122">The value is assigned to the `result2` variable.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7f6ad-123"><xref:System.Threading.Tasks.Task%601.Result%2A>Свойство является свойством блокировки.</xref:System.Threading.Tasks.Task%601.Result%2A></span><span class="sxs-lookup"><span data-stu-id="7f6ad-123">The <xref:System.Threading.Tasks.Task%601.Result%2A> property is a blocking property.</span></span> <span data-ttu-id="7f6ad-124">При попытке доступа к нему до завершения его задачи поток, который в текущий момент активен, блокируется до того момента, пока задача не будет завершена, а ее значение не станет доступным.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-124">If you try to access it before its task is finished, the thread that's currently active is blocked until the task completes and the value is available.</span></span> <span data-ttu-id="7f6ad-125">В большинстве случаев следует доступа к значению с помощью `Await` вместо прямого доступа к свойству.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-125">In most cases, you should access the value by using `Await` instead of accessing the property directly.</span></span>  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 <span data-ttu-id="7f6ad-126">Убедитесь, что отображаемое инструкции в следующем коде значения `result1` переменной, `result2` переменной и `Result` свойства совпадают.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-126">The display statements in the following code verify that the values of the `result1` variable, the `result2` variable, and the `Result` property are the same.</span></span> <span data-ttu-id="7f6ad-127">Помните, что `Result` свойство является свойством блокировки и не должно осуществляться до задачи получено.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-127">Remember that the `Result` property is a blocking property and shouldn't be accessed before its task has been awaited.</span></span>  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <span data-ttu-id="7f6ad-128"><a name="BKMK_TaskReturnType"></a>Возвращаемый тип задачи</span><span class="sxs-lookup"><span data-stu-id="7f6ad-128"><a name="BKMK_TaskReturnType"></a> Task Return Type</span></span>  
 <span data-ttu-id="7f6ad-129">Асинхронные методы, не содержит оператор return или содержит оператор return, который обычно не возвращает операнд имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="7f6ad-129">Async methods that don't contain a return statement or that contain a return statement that doesn't return an operand usually have a return type of <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="7f6ad-130">Такие методы будут [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) процедуры, если они были написаны для выполнения в синхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-130">Such methods would be [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedures if they were written to run synchronously.</span></span> <span data-ttu-id="7f6ad-131">При использовании `Task` тип возвращаемого значения для асинхронного метода, можно использовать вызывающий метод `Await` оператор для приостановки вызывающего завершения до завершения вызванной асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-131">If you use a `Task` return type for an async method, a calling method can use an `Await` operator to suspend the caller's completion until the called async method has finished.</span></span>  
  
 <span data-ttu-id="7f6ad-132">В следующем примере асинхронный метод `Task_MethodAsync` не содержит оператор return.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-132">In the following example, async method `Task_MethodAsync` doesn't contain a return statement.</span></span> <span data-ttu-id="7f6ad-133">Таким образом, укажите тип возвращаемого значения `Task` для метода, который позволяет `Task_MethodAsync` чтобы ожидать.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-133">Therefore, you specify a return type of `Task` for the method, which enables `Task_MethodAsync` to be awaited.</span></span> <span data-ttu-id="7f6ad-134">Определение `Task` тип не содержит `Result` свойство для хранения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-134">The definition of the `Task` type doesn't include a `Result` property to store a return value.</span></span>  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 <span data-ttu-id="7f6ad-135">`Task_MethodAsync`вызывается и ожидать при помощи оператора await вместо выражение await, аналогично вызывающий оператор для синхронной `Sub` или метода, возвращающего void.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-135">`Task_MethodAsync` is called and awaited by using an await statement instead of an await expression, similar to the calling statement for a synchronous `Sub` or void-returning method.</span></span> <span data-ttu-id="7f6ad-136">Применение `Await` оператор в этом случае не создает значение.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-136">The application of an `Await` operator in this case doesn't produce a value.</span></span>  
  
 <span data-ttu-id="7f6ad-137">Следующий код вызывает и ожидает метод `Task_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-137">The following code calls and awaits method `Task_MethodAsync`.</span></span>  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 <span data-ttu-id="7f6ad-138">Как в предыдущем <xref:System.Threading.Tasks.Task%601>пример, можно разделить вызов `Task_MethodAsync` от применения `Await` оператор, как показано в следующем коде.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="7f6ad-138">As in the previous <xref:System.Threading.Tasks.Task%601> example, you can separate the call to `Task_MethodAsync` from the application of an `Await` operator, as the following code shows.</span></span> <span data-ttu-id="7f6ad-139">Однако следует помнить, что `Task` не имеет `Result` свойство, и что значение не создается, когда оператор await применяется к `Task`.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-139">However, remember that a `Task` doesn't have a `Result` property, and that no value is produced when an await operator is applied to a `Task`.</span></span>  
  
 <span data-ttu-id="7f6ad-140">Следующий код отделяет вызова `Task_MethodAsync` из ожидает задачу, `Task_MethodAsync` возвращает.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-140">The following code separates calling `Task_MethodAsync` from awaiting the task that `Task_MethodAsync` returns.</span></span>  
  
<span data-ttu-id="7f6ad-141"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7f6ad-141"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
##  <span data-ttu-id="7f6ad-142"><a name="BKMK_VoidReturnType"></a>Возвращаемый тип void</span><span class="sxs-lookup"><span data-stu-id="7f6ad-142"><a name="BKMK_VoidReturnType"></a> Void Return Type</span></span>  
 <span data-ttu-id="7f6ad-143">Основное назначение `Sub` процедур заключается в обработчиках событий, где нет возвращаемого типа (называется типом возвращаемого значения void в других языках).</span><span class="sxs-lookup"><span data-stu-id="7f6ad-143">The primary use of `Sub` procedures is in event handlers, where there is no return type (referred to as a void return type in other languages).</span></span> <span data-ttu-id="7f6ad-144">Тип возврата void также можно использовать для переопределения методов, возвращающих void, или для методов, выполняющих действия, которые можно классифицировать как "запустить и забыть".</span><span class="sxs-lookup"><span data-stu-id="7f6ad-144">A void return also can be used to override void-returning methods or for methods that perform activities that can be categorized as "fire and forget."</span></span> <span data-ttu-id="7f6ad-145">Тем не менее, следует вернуть `Task` везде, где это возможно, поскольку невозможно ожидать асинхронного метода, возвращающего void.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-145">However, you should return a `Task` wherever possible, because a void-returning async method can't be awaited.</span></span> <span data-ttu-id="7f6ad-146">Любой вызывающий объект такого метода должен иметь возможность завершить свою работу, не дожидаясь завершения вызванного асинхронного метода, и он не должен зависеть ни от каких значений и исключений, создаваемых асинхронным методом.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-146">Any caller of such a method must be able to continue to completion without waiting for the called async method to finish, and the caller must be independent of any values or exceptions that the async method generates.</span></span>  
  
 <span data-ttu-id="7f6ad-147">Вызывающий объект асинхронного метода, возвращающего void, не может перехватывать исключения, создаваемые методом, и такие необработанные исключения могут привести к сбою приложения.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-147">The caller of a void-returning async method can't catch exceptions that are thrown from the method, and such unhandled exceptions are likely to cause your application to fail.</span></span> <span data-ttu-id="7f6ad-148">Если исключение возникает в асинхронный метод, который возвращает <xref:System.Threading.Tasks.Task>или <xref:System.Threading.Tasks.Task%601>, исключение хранится в возвращенной задаче и повторно при ожидании задачи.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="7f6ad-148">If an exception occurs in an async method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>, the exception is stored in the returned task, and rethrown when the task is awaited.</span></span> <span data-ttu-id="7f6ad-149">Поэтому убедитесь, что любой асинхронный метод, который может вызвать исключение имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task>или <xref:System.Threading.Tasks.Task%601>и что вызовы метода будут ожидать.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="7f6ad-149">Therefore, make sure that any async method that can produce an exception has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> and that calls to the method are awaited.</span></span>  
  
 <span data-ttu-id="7f6ad-150">Дополнительные сведения о том, как перехватывать исключения в асинхронных методах см. в разделе [Try... CATCH... Оператор Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7f6ad-150">For more information about how to catch exceptions in async methods, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="7f6ad-151">Следующий код определяет асинхронный обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-151">The following code defines an async event handler.</span></span>  
  
<span data-ttu-id="7f6ad-152"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7f6ad-152"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
##  <span data-ttu-id="7f6ad-153"><a name="BKMK_Example"></a>Полный пример</span><span class="sxs-lookup"><span data-stu-id="7f6ad-153"><a name="BKMK_Example"></a> Complete Example</span></span>  
 <span data-ttu-id="7f6ad-154">Следующий проект Windows Presentation Foundation (WPF) содержит примеры кода из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-154">The following Windows Presentation Foundation (WPF) project contains the code examples from this topic.</span></span>  
  
 <span data-ttu-id="7f6ad-155">Чтобы запустить проект, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-155">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="7f6ad-156">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-156">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="7f6ad-157">В строке меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-157">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="7f6ad-158">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="7f6ad-158">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="7f6ad-159">В **установленные**, **шаблоны** категории, выберите **Visual Basic**, а затем выберите **Windows**.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-159">In the **Installed**, **Templates** category, choose **Visual Basic**, and then choose **Windows**.</span></span> <span data-ttu-id="7f6ad-160">Выберите **приложение WPF** в списке типов проектов.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-160">Choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="7f6ad-161">Введите `AsyncReturnTypes` как имя проекта, а затем выберите **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-161">Enter `AsyncReturnTypes` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="7f6ad-162">Появится новый проект в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-162">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="7f6ad-163">В редакторе кода Visual Studio перейдите на вкладку **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="7f6ad-163">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="7f6ad-164">Если вкладка не отображается, откройте контекстное меню для MainWindow.xaml в **обозревателе решений**, а затем выберите **откройте**.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-164">If the tab is not visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **Open**.</span></span>  
  
6.  <span data-ttu-id="7f6ad-165">В **XAML** окно MainWindow.XAML, замените код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-165">In the **XAML** window of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     <span data-ttu-id="7f6ad-166">Появится простое окно, содержащее текстовое поле и кнопку в **разработки** окно MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-166">A simple window that contains a text box and a button appears in the **Design** window of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="7f6ad-167">В **обозревателе решений**, откройте контекстное меню для MainWindow.xaml.vb и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-167">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
8.  <span data-ttu-id="7f6ad-168">Замените код в MainWindow.xaml.vb на приведенный далее.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-168">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' SUB EXAMPLE  
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
            textBox1.Clear()  
  
            ' Start the process and await its completion. DriverAsync is a   
            ' Task-returning async method.  
            Await DriverAsync()  
  
            ' Say goodbye.  
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
        End Sub  
  
        Async Function DriverAsync() As Task  
  
            ' Task(Of T)   
            ' Call and await the Task(Of T)-returning async method in the same statement.  
            Dim result1 As Integer = Await TaskOfT_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
            ' You can do other work that does not rely on resultTask before awaiting.  
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
            Await simpleTask  
        End Function  
  
        ' TASK(OF T) EXAMPLE  
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.FromResult is a placeholder for actual work that returns a string.  
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
            ' The method then can process the result in some way.  
            Dim leisureHours As Integer  
            If today.First() = "S" Then  
                leisureHours = 16  
            Else  
                leisureHours = 5  
            End If  
  
            ' Because the return statement specifies an operand of type Integer, the   
            ' method must have a return type of Task(Of Integer).   
            Return leisureHours  
        End Function  
  
        ' TASK EXAMPLE  
        Async Function Task_MethodAsync() As Task  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.Delay is a placeholder for actual work.  
            Await Task.Delay(2000)  
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
    ```  
  
9. <span data-ttu-id="7f6ad-169">Нажмите клавишу F5, чтобы запустить программу, а затем нажмите кнопку **Start** .</span><span class="sxs-lookup"><span data-stu-id="7f6ad-169">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="7f6ad-170">Должен появиться следующий результат.</span><span class="sxs-lookup"><span data-stu-id="7f6ad-170">The following output should appear.</span></span>  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7f6ad-171">См. также</span><span class="sxs-lookup"><span data-stu-id="7f6ad-171">See Also</span></span>  
 <span data-ttu-id="7f6ad-172"><xref:System.Threading.Tasks.Task.FromResult%2A></xref:System.Threading.Tasks.Task.FromResult%2A></span><span class="sxs-lookup"><span data-stu-id="7f6ad-172"><xref:System.Threading.Tasks.Task.FromResult%2A></span></span>   
<span data-ttu-id="7f6ad-173"> [Пошаговое руководство: Доступ к Интернету с помощью модификатора Async и Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="7f6ad-173"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="7f6ad-174"> [Поток управления в асинхронных программах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md) </span><span class="sxs-lookup"><span data-stu-id="7f6ad-174"> [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md) </span></span>  
<span data-ttu-id="7f6ad-175"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span><span class="sxs-lookup"><span data-stu-id="7f6ad-175"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span></span>  
<span data-ttu-id="7f6ad-176"> [Оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md)</span><span class="sxs-lookup"><span data-stu-id="7f6ad-176"> [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md)</span></span>
