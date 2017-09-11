---
title: "await (Справочник по C#)"
ms.date: 2017-05-22
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- await_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
caps.latest.revision: 36
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 38b41e2cde3c0c22c1c5bd609f1ab8fcd2685355
ms.openlocfilehash: 7255d170c8b27ba29817b6355c0cf6a9c593a09f
ms.contentlocale: ru-ru
ms.lasthandoff: 08/01/2017

---
# <a name="await-c-reference"></a><span data-ttu-id="2e6cf-102">await (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2e6cf-102">await (C# Reference)</span></span>
<span data-ttu-id="2e6cf-103">Оператор `await` применяется к задаче в асинхронном методе для вставки точки приостановки выполнения метода до завершения выполнения ожидаемой задачи.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-103">The `await` operator is applied to a task in an asynchronous method to insert a suspension point in the execution of the method until the awaited task completes.</span></span> <span data-ttu-id="2e6cf-104">Задача представляет выполняющуюся работу.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-104">The task represents ongoing work.</span></span>  
  
<span data-ttu-id="2e6cf-105">Оператор `await` можно использовать только в асинхронном методе, измененном с использованием ключевого слова [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="2e6cf-105">`await` can only be used in an asynchronous method modified by the [async](../../../csharp/language-reference/keywords/async.md) keyword.</span></span> <span data-ttu-id="2e6cf-106">Такой метод, определенный с помощью модификатора `async` и обычно содержащий одно или несколько выражений `await`, называется *асинхронным методом*.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-106">Such a method, defined by using the `async` modifier and usually containing one or more `await` expressions, is referred to as an *async method*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e6cf-107">Ключевые слова `async` и `await` появились в версии C# 5.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-107">The `async` and `await` keywords were introduced in C# 5.</span></span> <span data-ttu-id="2e6cf-108">Общие сведения об асинхронном программировании см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="2e6cf-108">For an introduction to async programming, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
<span data-ttu-id="2e6cf-109">Задача, к которой применяется оператор `await`, обычно является возвращаемым значением из вызова метода, реализующего [асинхронную модель на основе задач](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="2e6cf-109">The task to which the `await` operator is applied typically is returned by a call to a method that implements the [Task-Based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span> <span data-ttu-id="2e6cf-110">К ним относятся методы, возвращающие объекты <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> и `System.Threading.Tasks.ValueType<TResult>`.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-110">They include methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, and `System.Threading.Tasks.ValueType<TResult>` objects.</span></span>  

  
 <span data-ttu-id="2e6cf-111">В следующем примере метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=fullName> возвращает `Task<byte[]>`.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-111">In the following example, the <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=fullName> method returns a `Task<byte[]>`.</span></span> <span data-ttu-id="2e6cf-112">Задача является обещанием создать фактический массив байтов после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-112">The task is a promise to produce the actual byte array when the task is complete.</span></span> <span data-ttu-id="2e6cf-113">Оператор `await` приостанавливает выполнение до тех пор, пока не завершится работа метода <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-113">The `await` operator suspends execution until the work of the <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> method is complete.</span></span> <span data-ttu-id="2e6cf-114">В то же время управление возвращается вызывающему объекту `GetPageSizeAsync`.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-114">In the meantime, control is returned to the caller of `GetPageSizeAsync`.</span></span> <span data-ttu-id="2e6cf-115">После завершения выполнения задачи выражение `await` вычисляется как массив байтов.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-115">When the task finishes execution, the `await` expression evaluates to a byte array.</span></span>  

<span data-ttu-id="2e6cf-116">[!code-cs[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2e6cf-116">[!code-cs[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await1.cs)]</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="2e6cf-117">Полный пример см. в разделе [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="2e6cf-117">For the complete example, see [Walkthrough: Accessing the Web by Using Async and Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="2e6cf-118">Вы можете скачать этот пример в разделе [Примеры кода для разработчиков](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) на веб-сайте Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-118">You can download the sample from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) on the Microsoft website.</span></span> <span data-ttu-id="2e6cf-119">Этот пример представлен в проекте AsyncWalkthrough_HttpClient.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-119">The example is in the AsyncWalkthrough_HttpClient project.</span></span>  
  
<span data-ttu-id="2e6cf-120">Как показано в предыдущем примере, если `await` применяется к результату вызова метода, который возвращает `Task<TResult>`, то типом выражения `await` является `TResult`.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-120">As shown in the previous example, if `await` is applied to the result of a method call that returns a `Task<TResult>`, then the type of the `await` expression is `TResult`.</span></span> <span data-ttu-id="2e6cf-121">Если `await` применяется к результату вызова метода, который возвращает `Task`, то типом выражения `await` является `void`.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-121">If `await` is applied to the result of a method call that returns a `Task`, then the type of the `await` expression is `void`.</span></span> <span data-ttu-id="2e6cf-122">В следующем примере демонстрируется это различие.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-122">The following example illustrates the difference.</span></span>  
  
```csharp  
// await keyword used with a method that returns a Task<TResult>.  
TResult result = await AsyncMethodThatReturnsTaskTResult();  
  
// await keyword used with a method that returns a Task.  
await AsyncMethodThatReturnsTask();  

// await keyword used with a method that returns a ValueTask<TResult>.
TResult result = await AsyncMethodThatReturnsValueTaskTResult();
```  
  
<span data-ttu-id="2e6cf-123">Выражение `await` не блокирует поток, в котором оно выполняется.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-123">An `await` expression does not block the thread on which it is executing.</span></span> <span data-ttu-id="2e6cf-124">Вместо этого оно приводит к тому, что компилятор регистрирует остальную часть асинхронного метода как продолжение ожидаемой задачи.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-124">Instead, it causes the compiler to sign up the rest of the async method as a continuation on the awaited task.</span></span> <span data-ttu-id="2e6cf-125">Затем управление возвращается в объект, вызывающий асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-125">Control then returns to the caller of the async method.</span></span> <span data-ttu-id="2e6cf-126">Когда задача завершается, она вызывает свое продолжение и выполнение асинхронного метода возобновляется с того момента, где оно было остановлено.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-126">When the task completes, it invokes its continuation, and execution of the async method resumes where it left off.</span></span>  
  
<span data-ttu-id="2e6cf-127">Выражение `await` может находиться только в теле включающего метода, лямбда-выражения или анонимного метода, помеченного модификатором `async`.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-127">An `await` expression can occur only in the body of its enclosing method, lambda expression, or anonymous method, which must be marked with an `async` modifier.</span></span> <span data-ttu-id="2e6cf-128">Термин *await* служит как ключевое слово только в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-128">The term *await* serves as a keyword only in that context.</span></span> <span data-ttu-id="2e6cf-129">В другом месте он интерпретируется как идентификатор.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-129">Elsewhere, it is interpreted as an identifier.</span></span> <span data-ttu-id="2e6cf-130">Внутри метода, лямбда-выражения или анонимного метода выражение `await` не может использоваться в теле синхронной функции, в выражении запроса, в блоке [оператора lock](../../../csharp/language-reference/keywords/lock-statement.md) или в [небезопасном](../../../csharp/language-reference/keywords/unsafe.md) контексте.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-130">Within the method, lambda expression, or anonymous method, an `await` expression cannot occur in the body of a synchronous function, in a query expression, in the block of a [lock statement](../../../csharp/language-reference/keywords/lock-statement.md), or in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="2e6cf-131">Исключения</span><span class="sxs-lookup"><span data-stu-id="2e6cf-131">Exceptions</span></span>  
<span data-ttu-id="2e6cf-132">Большинство асинхронных методов возвращает <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-132">Most async methods return a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="2e6cf-133">Свойства возвращаемой задачи содержат сведения о ее состоянии и журнале, например завершена ли задача, вызвал ли асинхронный метод исключение или был отменен и каков окончательный результат.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-133">The properties of the returned task carry information about its status and history, such as whether the task is complete, whether the async method caused an exception or was canceled, and what the final result is.</span></span> <span data-ttu-id="2e6cf-134">Оператор `await` обращается к этим свойствам путем вызова методов для объекта, возвращенного методом `GetAwaiter`.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-134">The `await` operator accesses those properties by calling methods on the object returned by the `GetAwaiter` method.</span></span>  
  
<span data-ttu-id="2e6cf-135">Если вы ожидаете возвращающий задачу асинхронный метод, который вызывает исключение, то оператор `await` повторно создает это исключение.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-135">If you await a task-returning async method that causes an exception, the `await` operator rethrows the exception.</span></span>  
  
<span data-ttu-id="2e6cf-136">Если вы ожидаете возвращающий задачу асинхронный метод, который отменяется, то оператор `await` повторно создает исключение <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-136">If you await a task-returning async method that's canceled, the `await` operator rethrows an <xref:System.OperationCanceledException>.</span></span>  
  
<span data-ttu-id="2e6cf-137">Одна задача, которая находится в состоянии сбоя, может отражать несколько исключений.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-137">A single task that is in a faulted state can reflect multiple exceptions.</span></span> <span data-ttu-id="2e6cf-138">Например, задача может быть результатом вызова метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-138">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="2e6cf-139">Если вы ожидаете такую задачу, операция await повторно вызывает только одно из исключений.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-139">When you await such a task, the await operation rethrows only one of the exceptions.</span></span> <span data-ttu-id="2e6cf-140">Однако невозможно предсказать, какие исключения создаются повторно.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-140">However, you can't predict which of the exceptions is rethrown.</span></span>  
  
<span data-ttu-id="2e6cf-141">Примеры обработки ошибок в асинхронных методах см. в разделе [try-catch](../../../csharp/language-reference/keywords/try-catch.md).</span><span class="sxs-lookup"><span data-stu-id="2e6cf-141">For examples of error handling in async methods, see [try-catch](../../../csharp/language-reference/keywords/try-catch.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e6cf-142">Пример</span><span class="sxs-lookup"><span data-stu-id="2e6cf-142">Example</span></span>  
<span data-ttu-id="2e6cf-143">В следующем примере возвращается общее число символов на страницах, URL-адреса которых были переданы в качестве аргументов командной строки.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-143">The following example returns the total number of characters in the pages whose URLs are passed to it as command line arguments.</span></span> <span data-ttu-id="2e6cf-144">В этом примере вызывается метод `GetPageLengthsAsync`, помеченный с использованием ключевого слова `async`.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-144">The example calls the `GetPageLengthsAsync` method, which is marked with the `async` keyword.</span></span> <span data-ttu-id="2e6cf-145">В свою очередь, метод `GetPageLengthsAsync` использует ключевое слово `await` для ожидания вызовов метода <xref:System.Net.Http.HttpClient.GetStringAsync%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-145">The `GetPageLengthsAsync` method in turn uses the `await` keyword to await calls to the <xref:System.Net.Http.HttpClient.GetStringAsync%2A?displayProperty=fullName> method.</span></span>  

<span data-ttu-id="2e6cf-146">[!code-cs[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2e6cf-146">[!code-cs[await-example](../../../../samples/snippets/csharp/language-reference/keywords/await/await2.cs)]</span></span>  

<span data-ttu-id="2e6cf-147">Поскольку использование ключевых слов `async` и `await` в точках входа приложения не поддерживается, атрибут `async` нельзя применить к методу `Main`, а также нельзя реализовать ожидание вызова метода `GetPageLengthsAsync`.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-147">Because the use of `async` and `await` in an application entry point is not supported, we cannot apply the `async` attribute to the `Main` method, nor can we await the `GetPageLengthsAsync` method call.</span></span> <span data-ttu-id="2e6cf-148">Чтобы реализовать ожидание методом `Main` завершения асинхронной операции, можно извлечь значение свойства <xref:System.Threading.Tasks.Task%601.Result?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-148">We can ensure that the `Main` method waits for the async operation to complete by retrieving the value of the <xref:System.Threading.Tasks.Task%601.Result?displayProperty=fullName> property.</span></span> <span data-ttu-id="2e6cf-149">Для задач, которые не возвращают значение, можно вызвать метод <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2e6cf-149">For tasks that do not return a value, you can call the <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> method.</span></span> 

## <a name="see-also"></a><span data-ttu-id="2e6cf-150">См. также</span><span class="sxs-lookup"><span data-stu-id="2e6cf-150">See also</span></span>  
<span data-ttu-id="2e6cf-151">[Асинхронное программирование с использованием ключевых слов Async и Await](../../../csharp/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e6cf-151">[Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="2e6cf-152">[Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="2e6cf-152">[Walkthrough: Accessing the Web by Using Async and Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
[<span data-ttu-id="2e6cf-153">async</span><span class="sxs-lookup"><span data-stu-id="2e6cf-153">async</span></span>](../../../csharp/language-reference/keywords/async.md)

