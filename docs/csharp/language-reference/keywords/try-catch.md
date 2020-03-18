---
title: Справочник по C#. Оператор try-catch
ms.date: 07/20/2015
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
ms.openlocfilehash: 3d4315a09869b77b4ae8cbb43646f9a96280b678
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173475"
---
# <a name="try-catch-c-reference"></a><span data-ttu-id="e2b9b-102">try-catch (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e2b9b-102">try-catch (C# Reference)</span></span>

<span data-ttu-id="e2b9b-103">Оператор try-catch состоит из блока `try`, за которым следует одно или несколько предложений `catch`, задающих обработчики для различных исключений.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>

<span data-ttu-id="e2b9b-104">При возникновении исключения общеязыковая среда выполнения (CLR) ищет оператор `catch`, который обрабатывает это исключение.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-104">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="e2b9b-105">Если текущий выполняемый метод не содержит такой блок `catch`, среда CLR выполняет поиск в методе, который вызвал текущий метод, и так далее вверх по стеку вызовов.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-105">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="e2b9b-106">Если блок `catch` не находится, то среда CLR отображает пользователю сообщение о необработанном исключении и останавливает выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-106">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>

<span data-ttu-id="e2b9b-107">Блок `try` содержит защищенный код, который может вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-107">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="e2b9b-108">Этот блок выполняется, пока не возникнет исключение или пока он не будет успешно завершен.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-108">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="e2b9b-109">Например, следующая попытка приведения объекта `null` вызывает исключение <xref:System.NullReferenceException>:</span><span class="sxs-lookup"><span data-stu-id="e2b9b-109">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>

```csharp
object o2 = null;
try
{
    int i2 = (int)o2;   // Error
}
```

<span data-ttu-id="e2b9b-110">Хотя предложение `catch` может использоваться без аргументов для перехвата любого типа исключения, такое использование не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-110">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="e2b9b-111">В целом вы должны перехватывать только те исключения, после которых вы знаете, как выполнить восстановление.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-111">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="e2b9b-112">Поэтому всегда следует указывать аргумент объекта, производный от <xref:System.Exception?displayProperty=nameWithType>, например:</span><span class="sxs-lookup"><span data-stu-id="e2b9b-112">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=nameWithType> For example:</span></span>

```csharp
catch (InvalidCastException e)
{
}
```

<span data-ttu-id="e2b9b-113">В одном блоке try-catch можно использовать несколько определенных предложений `catch`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-113">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="e2b9b-114">В этом случае важен порядок предложений `catch`, поскольку предложения `catch` проверяются по порядку.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-114">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="e2b9b-115">Перехватывайте более конкретные исключения перед менее конкретными.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-115">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="e2b9b-116">Компилятор выдает ошибку, если вы расположили блоки catch в таком порядке, что последующий блок может быть никогда не достигнут.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-116">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>

<span data-ttu-id="e2b9b-117">Использование аргументов `catch` представляет один из способов фильтрации исключений, которые требуется обработать.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-117">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="e2b9b-118">Вы также можете использовать фильтр исключений, который дополнительно проверяет исключение, чтобы решить, следует ли его обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-118">You can also use an exception filter that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="e2b9b-119">Если фильтр исключений возвращает значение false, поиск обработчика продолжается.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-119">If the exception filter returns false, then the search for a handler continues.</span></span>

```csharp
catch (ArgumentException e) when (e.ParamName == "…")
{
}
```

<span data-ttu-id="e2b9b-120">Фильтры исключений предпочтительнее перехвата и повторного вызова (объясняется ниже), поскольку фильтры оставляют стек в целости и сохранности.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-120">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="e2b9b-121">Если последующий обработчик разгружает стек, вы можете увидеть, откуда изначально произошло исключение, а не только последнее место, в котором оно было повторно вызвано.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-121">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="e2b9b-122">Обычно выражения фильтра исключений используются для ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-122">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="e2b9b-123">Вы можете создать фильтр, который всегда возвращает значение false, а также записывает выходной результат в журнал, чтобы регистрировать исключения в журнале по мере их поступления без необходимости их обработки и повторного вызова.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-123">You can create a filter that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>

<span data-ttu-id="e2b9b-124">Оператор [throw](throw.md), включенный в блок `catch`, позволяет заново вызвать исключение, перехваченное блоком `catch`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-124">A [throw](throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="e2b9b-125">В следующем примере извлекаются сведения об источнике из исключения <xref:System.IO.IOException>, а затем это исключение вызывается для родительского метода.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-125">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>

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

<span data-ttu-id="e2b9b-126">Вы можете перехватывать одно исключение и вызывать другое исключение.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-126">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="e2b9b-127">При этом следует указать перехватываемое исключение как внутреннее, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-127">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>

```csharp
catch (InvalidCastException e)
{
    // Perform some action here, and then throw a new exception.
    throw new YourCustomException("Put your error message here.", e);
}
```

<span data-ttu-id="e2b9b-128">Вы также можете повторно вызывать исключение при выполнении указанного условия, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-128">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>

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

> [!NOTE]
> <span data-ttu-id="e2b9b-129">Вы можете использовать фильтр исключений, чтобы получить тот же результат, но проще (при этом не изменяя стек, как описано ранее в этом документе).</span><span class="sxs-lookup"><span data-stu-id="e2b9b-129">It is also possible to use an exception filter to get a similar result in an often cleaner fashion (as well as not modifying the stack, as explained earlier in this document).</span></span> <span data-ttu-id="e2b9b-130">В следующем примере показано такое же поведение для вызывающих объектов, как и в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-130">The following example has a similar behavior for callers as the previous example.</span></span> <span data-ttu-id="e2b9b-131">Эта функция отправляет исключение `InvalidCastException` обратно вызывающему объекту, если `e.Data` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-131">The function throws the `InvalidCastException` back to the caller when `e.Data` is `null`.</span></span>
>
> ```csharp
> catch (InvalidCastException e) when (e.Data != null)
> {
>     // Take some action.
> }
> ```

<span data-ttu-id="e2b9b-132">В блоке `try` инициализируйте только те переменные, которые в нем объявлены.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-132">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="e2b9b-133">В противном случае до завершения выполнения блока может возникнуть исключение.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-133">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="e2b9b-134">Например, в следующем примере кода переменная `n` инициализируется внутри блока `try`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-134">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="e2b9b-135">Попытка использовать данную переменную вне этого блока `try` в инструкции `Write(n)` приведет к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-135">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>

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

<span data-ttu-id="e2b9b-136">Дополнительные сведения о перехвате исключений см. в разделе [try-catch-finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="e2b9b-136">For more information about catch, see [try-catch-finally](try-catch-finally.md).</span></span>

## <a name="exceptions-in-async-methods"></a><span data-ttu-id="e2b9b-137">Исключения в асинхронных методах</span><span class="sxs-lookup"><span data-stu-id="e2b9b-137">Exceptions in async methods</span></span>

<span data-ttu-id="e2b9b-138">Асинхронный метод помечается модификатором [async](async.md) и обычно содержит одно или несколько выражений или инструкций await.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-138">An async method is marked  by an  [async](async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="e2b9b-139">Выражение await применяет оператор [await](../operators/await.md) к <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-139">An await expression applies the [await](../operators/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="e2b9b-140">Когда управление достигает `await` в асинхронном методе, выполнение метода приостанавливается до завершения выполнения ожидающей задачи.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-140">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="e2b9b-141">После завершения задачи выполнение в методе может быть возобновлено.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-141">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="e2b9b-142">Дополнительные сведения см. в разделах [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md) и [Поток управления в асинхронных программах](../../programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="e2b9b-142">For more information, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>

<span data-ttu-id="e2b9b-143">Завершенная задача, к которой применяется `await`, может находиться в состоянии сбоя из-за необработанного исключения в методе, который возвращает эту задачу.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-143">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="e2b9b-144">Ожидание задачи вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-144">Awaiting the task throws an exception.</span></span> <span data-ttu-id="e2b9b-145">Задача также может завершиться в отмененном состоянии, если отменяется асинхронный процесс, возвращающий эту задачу.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-145">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="e2b9b-146">Ожидание отмененной задачи вызывает `OperationCanceledException`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-146">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="e2b9b-147">Дополнительные сведения о том, как отменить асинхронный процесс, см. в разделе [Точная настройка асинхронного приложения (C# и Visual Basic)](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="e2b9b-147">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="e2b9b-148">Для перехвата исключения ожидайте задачу в блоке `try` и перехватывайте это исключение в соответствующем блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-148">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="e2b9b-149">См. пример в разделе [Пример асинхронного метода](#async-method-example).</span><span class="sxs-lookup"><span data-stu-id="e2b9b-149">For an example, see the [Async method example](#async-method-example) section.</span></span>

<span data-ttu-id="e2b9b-150">Задача может быть в состоянии сбоя, если в ожидаемом асинхронном методе произошло несколько исключений.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-150">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="e2b9b-151">Например, задача может быть результатом вызова метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-151">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e2b9b-152">При ожидании такой задачи перехватывается только одно из исключений и невозможно предсказать, какое исключение будет перехвачено.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-152">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="e2b9b-153">См. пример в разделе [Пример Task.WhenAll](#taskwhenall-example).</span><span class="sxs-lookup"><span data-stu-id="e2b9b-153">For an example, see the [Task.WhenAll example](#taskwhenall-example) section.</span></span>

## <a name="example"></a><span data-ttu-id="e2b9b-154">Пример</span><span class="sxs-lookup"><span data-stu-id="e2b9b-154">Example</span></span>

<span data-ttu-id="e2b9b-155">В следующем примере блок `try` содержит вызов метода `ProcessString`, который может вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-155">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="e2b9b-156">Предложение `catch` содержит обработчик исключений, который просто отображает сообщение на экране.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-156">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="e2b9b-157">Когда оператор `throw` вызывается из `MyMethod`, система осуществляет поиск оператора `catch` и отображает сообщение `Exception caught`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-157">When the `throw` statement is called from inside `MyMethod`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>

[!code-csharp[csrefKeywordsExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#2)]

## <a name="two-catch-blocks-example"></a><span data-ttu-id="e2b9b-158">Пример двух блоков catch</span><span class="sxs-lookup"><span data-stu-id="e2b9b-158">Two catch blocks example</span></span>

<span data-ttu-id="e2b9b-159">В следующем примере используются два блока catch и перехватывается наиболее конкретное исключение, поступившее первым.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-159">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>

<span data-ttu-id="e2b9b-160">Чтобы перехватить наименее конкретное исключение, можно заменить оператор throw в `ProcessString` следующим оператором: `throw new Exception()`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-160">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>

<span data-ttu-id="e2b9b-161">Если в этом примере первым поместить блок catch для перехвата наименее конкретного исключения, то появится следующее сообщение об ошибке: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-161">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>

[!code-csharp[csrefKeywordsExceptions#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#3)]

## <a name="async-method-example"></a><span data-ttu-id="e2b9b-162">Пример асинхронного метода</span><span class="sxs-lookup"><span data-stu-id="e2b9b-162">Async method example</span></span>

<span data-ttu-id="e2b9b-163">В следующем примере демонстрируется обработка исключений для асинхронных методов.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-163">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="e2b9b-164">Для перехвата исключения, вызванного асинхронной задачей, поместите выражение `await` в блок `try` и перехватывайте это исключение в блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-164">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>

<span data-ttu-id="e2b9b-165">Раскомментируйте строку `throw new Exception` в этом примере для демонстрации обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-165">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="e2b9b-166">Для свойства `IsFaulted` задачи установлено значение `True`, для свойства `Exception.InnerException` задачи установлено это исключение, а исключение перехватывается в блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-166">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>

<span data-ttu-id="e2b9b-167">Раскомментируйте строку `throw new OperationCanceledException`, чтобы показать, что происходит при отмене асинхронного процесса.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-167">Uncomment the `throw new OperationCanceledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="e2b9b-168">Для свойства `IsCanceled` задачи устанавливается значение `true`, и исключение перехватывается в блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-168">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="e2b9b-169">В некоторых условиях, которые неприменимы в данном примере, для свойства `IsFaulted` задачи устанавливается значение `true`, а для `IsCanceled` устанавливается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-169">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>

[!code-csharp[csAsyncExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#2)]  

## <a name="taskwhenall-example"></a><span data-ttu-id="e2b9b-170">Пример Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="e2b9b-170">Task.WhenAll example</span></span>

<span data-ttu-id="e2b9b-171">В следующем примере демонстрируется обработка исключений, когда несколько задач могут привести к нескольким исключениям.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-171">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="e2b9b-172">Блок `try` ожидает задачу, которая возвращается вызовом метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-172">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e2b9b-173">Эта задача завершается после завершения трех задач, к которым применяется WhenAll.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-173">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>

<span data-ttu-id="e2b9b-174">Каждая из трех задач вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-174">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="e2b9b-175">Блок `catch` выполняет итерацию по исключениям, которые обнаруживаются в свойстве `Exception.InnerExceptions` задачи, возвращенной методом <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-175">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span>

[!code-csharp[csAsyncExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="e2b9b-176">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e2b9b-176">C# language specification</span></span>

<span data-ttu-id="e2b9b-177">Дополнительные сведения см. в разделе [Оператор try](~/_csharplang/spec/statements.md#the-try-statement) в документации [Спецификация C# 6.0](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e2b9b-177">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2b9b-178">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e2b9b-178">See also</span></span>

- [<span data-ttu-id="e2b9b-179">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e2b9b-179">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e2b9b-180">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e2b9b-180">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e2b9b-181">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e2b9b-181">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e2b9b-182">Операторы try, throw и catch (C++)</span><span class="sxs-lookup"><span data-stu-id="e2b9b-182">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="e2b9b-183">throw</span><span class="sxs-lookup"><span data-stu-id="e2b9b-183">throw</span></span>](throw.md)
- [<span data-ttu-id="e2b9b-184">try-finally</span><span class="sxs-lookup"><span data-stu-id="e2b9b-184">try-finally</span></span>](try-finally.md)
- [<span data-ttu-id="e2b9b-185">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="e2b9b-185">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
