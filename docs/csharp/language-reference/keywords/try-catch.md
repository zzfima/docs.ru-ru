---
title: "try-catch (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
caps.latest.revision: 45
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b7ec6c96ac21ba2115d1e7eead5700b6dbfcc952
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="try-catch-c-reference"></a><span data-ttu-id="63766-102">try-catch (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="63766-102">try-catch (C# Reference)</span></span>
<span data-ttu-id="63766-103">Оператор try-catch состоит из блока `try`, за которым следует одно или несколько предложений `catch`, задающих обработчики для различных исключений.</span><span class="sxs-lookup"><span data-stu-id="63766-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63766-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="63766-104">Remarks</span></span>  
 <span data-ttu-id="63766-105">При возникновении исключения общеязыковая среда выполнения (CLR) ищет оператор `catch`, который обрабатывает это исключение.</span><span class="sxs-lookup"><span data-stu-id="63766-105">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="63766-106">Если текущий выполняемый метод не содержит такой блок `catch`, среда CLR выполняет поиск в методе, который вызвал текущий метод, и так далее вверх по стеку вызовов.</span><span class="sxs-lookup"><span data-stu-id="63766-106">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="63766-107">Если блок `catch` не находится, то среда CLR отображает пользователю сообщение о необработанном исключении и останавливает выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="63766-107">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>  
  
 <span data-ttu-id="63766-108">Блок `try` содержит защищенный код, который может вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="63766-108">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="63766-109">Этот блок выполняется, пока не возникнет исключение или пока он не будет успешно завершен.</span><span class="sxs-lookup"><span data-stu-id="63766-109">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="63766-110">Например, следующая попытка приведения объекта `null` вызывает исключение <xref:System.NullReferenceException>:</span><span class="sxs-lookup"><span data-stu-id="63766-110">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>  
  
```csharp  
object o2 = null;  
try  
{  
    int i2 = (int)o2;   // Error  
}  
```  
  
 <span data-ttu-id="63766-111">Хотя предложение `catch` может использоваться без аргументов для перехвата любого типа исключения, такое использование не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="63766-111">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="63766-112">В целом вы должны перехватывать только те исключения, после которых вы знаете, как выполнить восстановление.</span><span class="sxs-lookup"><span data-stu-id="63766-112">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="63766-113">Поэтому всегда следует указывать аргумент объекта, производный от <xref:System.Exception?displayProperty=fullName>, например:</span><span class="sxs-lookup"><span data-stu-id="63766-113">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=fullName> For example:</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
}  
```  
  
 <span data-ttu-id="63766-114">В одном блоке try-catch можно использовать несколько определенных предложений `catch`.</span><span class="sxs-lookup"><span data-stu-id="63766-114">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="63766-115">В этом случае важен порядок предложений `catch`, поскольку предложения `catch` проверяются по порядку.</span><span class="sxs-lookup"><span data-stu-id="63766-115">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="63766-116">Перехватывайте более конкретные исключения перед менее конкретными.</span><span class="sxs-lookup"><span data-stu-id="63766-116">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="63766-117">Компилятор выдает ошибку, если вы расположили блоки catch в таком порядке, что последующий блок может быть никогда не достигнут.</span><span class="sxs-lookup"><span data-stu-id="63766-117">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>  
  
 <span data-ttu-id="63766-118">Использование аргументов `catch` представляет один из способов фильтрации исключений, которые требуется обработать.</span><span class="sxs-lookup"><span data-stu-id="63766-118">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="63766-119">Вы также можете использовать выражение предиката, которое дополнительно проверяет исключение, чтобы решить, следует ли его обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="63766-119">You can also use a predicate expression that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="63766-120">Если выражение предиката возвращает значение false, поиск обработчика продолжается.</span><span class="sxs-lookup"><span data-stu-id="63766-120">If the predicate expression returns false, then the search for a handler continues.</span></span>  
  
```csharp  
catch (ArgumentException e) when (e.ParamName == "…")  
{  
}  
```  
  
 <span data-ttu-id="63766-121">Фильтры исключений предпочтительнее перехвата и повторного вызова (объясняется ниже), поскольку фильтры оставляют стек в целости и сохранности.</span><span class="sxs-lookup"><span data-stu-id="63766-121">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="63766-122">Если последующий обработчик разгружает стек, вы можете увидеть, откуда изначально произошло исключение, а не только последнее место, в котором оно было повторно вызвано.</span><span class="sxs-lookup"><span data-stu-id="63766-122">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="63766-123">Обычно выражения фильтра исключений используются для ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="63766-123">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="63766-124">Вы можете создать функцию предиката, которая всегда возвращает значение false, а также записывает выходной результат в журнал, чтобы регистрировать исключения в журнале по мере их поступления без необходимости их обработки и повторного вызова.</span><span class="sxs-lookup"><span data-stu-id="63766-124">You can create a predicate function that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>  
  
 <span data-ttu-id="63766-125">Оператор [throw](../../../csharp/language-reference/keywords/throw.md), включенный в блок `catch`, позволяет заново вызвать исключение, перехваченное блоком `catch`.</span><span class="sxs-lookup"><span data-stu-id="63766-125">A [throw](../../../csharp/language-reference/keywords/throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="63766-126">В следующем примере извлекаются сведения об источнике из исключения <xref:System.IO.IOException>, а затем это исключение вызывается для родительского метода.</span><span class="sxs-lookup"><span data-stu-id="63766-126">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>  
  
```csharp  
catch (FileNotFoundException e)  
{  
    // FileNotFoundExceptions are handled here.  
}  
catch (IOException e)  
{  
    // Extract some information from this exception, and then   
    // throw it to the parent method.  
    if (e.Source != null)  
        Console.WriteLine("IOException source: {0}", e.Source);  
    throw;  
}  
```  
  
 <span data-ttu-id="63766-127">Вы можете перехватывать одно исключение и вызывать другое исключение.</span><span class="sxs-lookup"><span data-stu-id="63766-127">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="63766-128">При этом следует указать перехватываемое исключение как внутреннее, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="63766-128">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
    // Perform some action here, and then throw a new exception.  
    throw new YourCustomException("Put your error message here.", e);  
}  
```  
  
 <span data-ttu-id="63766-129">Вы также можете повторно вызывать исключение при выполнении указанного условия, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="63766-129">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)  
{  
    if (e.Data == null)  
    {  
        throw;  
    }  
    else  
    {  
        // Take some action.  
    }  
 }  
```  
  
 <span data-ttu-id="63766-130">В блоке `try` инициализируйте только те переменные, которые в нем объявлены.</span><span class="sxs-lookup"><span data-stu-id="63766-130">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="63766-131">В противном случае до завершения выполнения блока может возникнуть исключение.</span><span class="sxs-lookup"><span data-stu-id="63766-131">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="63766-132">Например, в следующем примере кода переменная `n` инициализируется внутри блока `try`.</span><span class="sxs-lookup"><span data-stu-id="63766-132">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="63766-133">Попытка использовать данную переменную вне этого блока `try` в инструкции `Write(n)` приведет к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="63766-133">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>  
  
```csharp  
static void Main()   
{  
    int n;  
    try   
    {  
        // Do not initialize this variable here.  
        n = 123;  
    }  
    catch  
    {  
    }  
    // Error: Use of unassigned local variable 'n'.  
    Console.Write(n);  
}  
```  
  
 <span data-ttu-id="63766-134">Дополнительные сведения о перехвате исключений см. в разделе [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="63766-134">For more information about catch, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
## <a name="exceptions-in-async-methods"></a><span data-ttu-id="63766-135">Исключения в асинхронных методах</span><span class="sxs-lookup"><span data-stu-id="63766-135">Exceptions in Async Methods</span></span>  
 <span data-ttu-id="63766-136">Асинхронный метод помечается модификатором [async](../../../csharp/language-reference/keywords/async.md) и обычно содержит одно или несколько выражений или инструкций await.</span><span class="sxs-lookup"><span data-stu-id="63766-136">An async method is marked  by an  [async](../../../csharp/language-reference/keywords/async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="63766-137">Выражение await применяет оператор [await](../../../csharp/language-reference/keywords/await.md) к <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="63766-137">An await expression applies the [await](../../../csharp/language-reference/keywords/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="63766-138">Когда управление достигает `await` в асинхронном методе, выполнение метода приостанавливается до завершения выполнения ожидающей задачи.</span><span class="sxs-lookup"><span data-stu-id="63766-138">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="63766-139">После завершения задачи выполнение в методе может быть возобновлено.</span><span class="sxs-lookup"><span data-stu-id="63766-139">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="63766-140">Дополнительные сведения см. в разделах [Асинхронное программирование с использованием ключевых слов async и await](../../../csharp/programming-guide/concepts/async/index.md) и [Поток управления в асинхронных программах](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="63766-140">For more information, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
 <span data-ttu-id="63766-141">Завершенная задача, к которой применяется `await`, может находиться в состоянии сбоя из-за необработанного исключения в методе, который возвращает эту задачу.</span><span class="sxs-lookup"><span data-stu-id="63766-141">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="63766-142">Ожидание задачи вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="63766-142">Awaiting the task throws an exception.</span></span> <span data-ttu-id="63766-143">Задача также может завершиться в отмененном состоянии, если отменяется асинхронный процесс, возвращающий эту задачу.</span><span class="sxs-lookup"><span data-stu-id="63766-143">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="63766-144">Ожидание отмененной задачи вызывает `OperationCanceledException`.</span><span class="sxs-lookup"><span data-stu-id="63766-144">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="63766-145">Дополнительные сведения о том, как отменить асинхронный процесс, см. в разделе [Точная настройка асинхронного приложения (C# и Visual Basic)](http://msdn.microsoft.com/library/daaa32ea-c84c-4761-8230-c8292ffebd74).</span><span class="sxs-lookup"><span data-stu-id="63766-145">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](http://msdn.microsoft.com/library/daaa32ea-c84c-4761-8230-c8292ffebd74).</span></span>  
  
 <span data-ttu-id="63766-146">Для перехвата исключения ожидайте задачу в блоке `try` и перехватывайте это исключение в соответствующем блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="63766-146">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="63766-147">См. пример в разделе «Пример».</span><span class="sxs-lookup"><span data-stu-id="63766-147">For an example, see the "Example" section.</span></span>  
  
 <span data-ttu-id="63766-148">Задача может быть в состоянии сбоя, если в ожидаемом асинхронном методе произошло несколько исключений.</span><span class="sxs-lookup"><span data-stu-id="63766-148">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="63766-149">Например, задача может быть результатом вызова метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="63766-149">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="63766-150">При ожидании такой задачи перехватывается только одно из исключений и невозможно предсказать, какое исключение будет перехвачено.</span><span class="sxs-lookup"><span data-stu-id="63766-150">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="63766-151">См. пример в разделе «Пример».</span><span class="sxs-lookup"><span data-stu-id="63766-151">For an example, see the "Example" section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63766-152">Пример</span><span class="sxs-lookup"><span data-stu-id="63766-152">Example</span></span>  
 <span data-ttu-id="63766-153">В следующем примере блок `try` содержит вызов метода `ProcessString`, который может вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="63766-153">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="63766-154">Предложение `catch` содержит обработчик исключений, который просто отображает сообщение на экране.</span><span class="sxs-lookup"><span data-stu-id="63766-154">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="63766-155">Когда оператор `throw` вызывается из `MyMethod`, система осуществляет поиск оператора `catch` и отображает сообщение `Exception caught`.</span><span class="sxs-lookup"><span data-stu-id="63766-155">When the `throw` statement is called from inside `MyMethod`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>  
  
 <span data-ttu-id="63766-156">[!code-cs[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="63766-156">[!code-cs[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="63766-157">Пример</span><span class="sxs-lookup"><span data-stu-id="63766-157">Example</span></span>  
 <span data-ttu-id="63766-158">В следующем примере используются два блока catch и перехватывается наиболее конкретное исключение, поступившее первым.</span><span class="sxs-lookup"><span data-stu-id="63766-158">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>  
  
 <span data-ttu-id="63766-159">Чтобы перехватить наименее конкретное исключение, можно заменить оператор throw в `ProcessString` следующим оператором: `throw new Exception()`.</span><span class="sxs-lookup"><span data-stu-id="63766-159">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>  
  
 <span data-ttu-id="63766-160">Если в этом примере первым поместить блок catch для перехвата наименее конкретного исключения, то появится следующее сообщение об ошибке: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span><span class="sxs-lookup"><span data-stu-id="63766-160">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>  
  
 <span data-ttu-id="63766-161">[!code-cs[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="63766-161">[!code-cs[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="63766-162">Пример</span><span class="sxs-lookup"><span data-stu-id="63766-162">Example</span></span>  
 <span data-ttu-id="63766-163">В следующем примере демонстрируется обработка исключений для асинхронных методов.</span><span class="sxs-lookup"><span data-stu-id="63766-163">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="63766-164">Для перехвата исключения, вызванного асинхронной задачей, поместите выражение `await` в блок `try` и перехватывайте это исключение в блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="63766-164">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>  
  
 <span data-ttu-id="63766-165">Раскомментируйте строку `throw new Exception` в этом примере для демонстрации обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="63766-165">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="63766-166">Для свойства `IsFaulted` задачи установлено значение `True`, для свойства `Exception.InnerException` задачи установлено это исключение, а исключение перехватывается в блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="63766-166">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>  
  
 <span data-ttu-id="63766-167">Раскомментируйте строку `throw new OperationCancelledException`, чтобы показать, что происходит при отмене асинхронного процесса.</span><span class="sxs-lookup"><span data-stu-id="63766-167">Uncomment the `throw new OperationCancelledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="63766-168">Для свойства `IsCanceled` задачи устанавливается значение `true`, и исключение перехватывается в блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="63766-168">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="63766-169">В некоторых условиях, которые неприменимы в данном примере, для свойства `IsFaulted` задачи устанавливается значение `true`, а для `IsCanceled` устанавливается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="63766-169">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>  
  
 <span data-ttu-id="63766-170">[!code-cs[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="63766-170">[!code-cs[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="63766-171">Пример</span><span class="sxs-lookup"><span data-stu-id="63766-171">Example</span></span>  
 <span data-ttu-id="63766-172">В следующем примере демонстрируется обработка исключений, когда несколько задач могут привести к нескольким исключениям.</span><span class="sxs-lookup"><span data-stu-id="63766-172">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="63766-173">Блок `try` ожидает задачу, которая возвращается вызовом метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="63766-173">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="63766-174">Эта задача завершается после завершения трех задач, к которым применяется WhenAll.</span><span class="sxs-lookup"><span data-stu-id="63766-174">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>  
  
 <span data-ttu-id="63766-175">Каждая из трех задач вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="63766-175">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="63766-176">Блок `catch` выполняет итерацию по исключениям, которые обнаруживаются в свойстве `Exception.InnerExceptions` задачи, возвращенной методом <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="63766-176">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="63766-177">[!code-cs[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="63766-177">[!code-cs[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="63766-178">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="63766-178">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63766-179">См. также</span><span class="sxs-lookup"><span data-stu-id="63766-179">See Also</span></span>  
 <span data-ttu-id="63766-180">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="63766-180">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="63766-181">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="63766-181">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="63766-182">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="63766-182">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="63766-183">[Операторы try, throw и catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="63766-183">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="63766-184">[Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="63766-184">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="63766-185">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="63766-185">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="63766-186">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="63766-186">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 [<span data-ttu-id="63766-187">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="63766-187">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

