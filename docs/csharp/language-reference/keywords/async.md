---
title: Справочник по C#. Модификатор async
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 30ee13a4174a137481fbcd36ccef721958b94a12
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450860"
---
# <a name="async-c-reference"></a><span data-ttu-id="1726c-102">async (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1726c-102">async (C# Reference)</span></span>

<span data-ttu-id="1726c-103">Модификатор `async` позволяет указать, что метод, [лямбда-выражение](../../programming-guide/statements-expressions-operators/lambda-expressions.md) или [анонимный метод](../operators/delegate-operator.md) является асинхронным.</span><span class="sxs-lookup"><span data-stu-id="1726c-103">Use the `async` modifier to specify that a method, [lambda expression](../../programming-guide/statements-expressions-operators/lambda-expressions.md), or [anonymous method](../operators/delegate-operator.md) is asynchronous.</span></span> <span data-ttu-id="1726c-104">Если этот модификатор используется в методе или выражении, они называются *асинхронными методами*.</span><span class="sxs-lookup"><span data-stu-id="1726c-104">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="1726c-105">Ниже приводится пример асинхронного метода с именем `ExampleMethodAsync`:</span><span class="sxs-lookup"><span data-stu-id="1726c-105">The following example defines an async method named `ExampleMethodAsync`:</span></span>
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  

<span data-ttu-id="1726c-106">Если вы только начали заниматься асинхронным программированием или не понимаете, как в асинхронном методе используется [оператор `await`](../operators/await.md) для выполнения потенциально долгой работы без блокировки потока вызывающего объекта, ознакомьтесь с общими сведениями в статье [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="1726c-106">If you're new to asynchronous programming or do not understand how an async method uses the [`await` operator](../operators/await.md) to do potentially long-running work without blocking the caller’s thread, read the introduction in [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="1726c-107">Следующий код размещается внутри асинхронного метода и вызывает метод <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1726c-107">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span>
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
<span data-ttu-id="1726c-108">Асинхронный метод выполняется синхронным образом до тех пор, пока не будет достигнуто первое выражение `await`, после чего метод приостанавливается, пока не будет завершена ожидаемая задача.</span><span class="sxs-lookup"><span data-stu-id="1726c-108">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="1726c-109">В то же время управление возвращается в вызывающий объект метода, как показано в примере в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="1726c-109">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>  
  
<span data-ttu-id="1726c-110">Если метод, который изменяется ключевым словом `async`, не содержит выражения или оператора `await`, метод выполняется синхронно.</span><span class="sxs-lookup"><span data-stu-id="1726c-110">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="1726c-111">Компилятор выводит предупреждения обо всех асинхронных методах, не содержащих операторы `await`, поскольку такая ситуация может указывать на ошибку.</span><span class="sxs-lookup"><span data-stu-id="1726c-111">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="1726c-112">См. раздел [Предупреждение компилятора (уровень 1) CS4014](../compiler-messages/cs4014.md).</span><span class="sxs-lookup"><span data-stu-id="1726c-112">See [Compiler Warning (level 1) CS4014](../compiler-messages/cs4014.md).</span></span>  
  
 <span data-ttu-id="1726c-113">Ключевое слово `async` — это контекстно-зависимо ключевое слово, которое является ключевым словом, когда оно изменяет метод, лямбда-выражение или анонимный метод.</span><span class="sxs-lookup"><span data-stu-id="1726c-113">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="1726c-114">Во всех других контекстах он интерпретируется как идентификатор.</span><span class="sxs-lookup"><span data-stu-id="1726c-114">In all other contexts, it's interpreted as an identifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1726c-115">Пример</span><span class="sxs-lookup"><span data-stu-id="1726c-115">Example</span></span>  
<span data-ttu-id="1726c-116">В следующем примере показана структура и поток управления между обработчиком асинхронных событий `StartButton_Click` и асинхронным методом `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="1726c-116">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="1726c-117">В результате выполнения этого асинхронного метода возвращается число символов на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="1726c-117">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="1726c-118">Код подходит для приложения Windows Presentation Foundation (WPF) или приложения для Магазина Windows Presentation Foundation (WPF), которые создаются в Visual Studio; см. комментарии к коду для настройки приложения.</span><span class="sxs-lookup"><span data-stu-id="1726c-118">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>  

<span data-ttu-id="1726c-119">Этот код можно выполнить в Visual Studio как приложение Windows Presentation Foundation (WPF) или приложение Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="1726c-119">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="1726c-120">Вам понадобятся элементы управления типа "Кнопка" (`StartButton`) и "Текстовое поле" (`ResultsTextBox`).</span><span class="sxs-lookup"><span data-stu-id="1726c-120">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="1726c-121">Не забудьте задать имена и обработчик, чтобы получить код следующего вида:</span><span class="sxs-lookup"><span data-stu-id="1726c-121">Remember to set the names and handler so that you have something like this:</span></span>  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
<span data-ttu-id="1726c-122">Выполнение кода в виде приложения WPF:</span><span class="sxs-lookup"><span data-stu-id="1726c-122">To run the code as a WPF app:</span></span>  

- <span data-ttu-id="1726c-123">Вставьте этот код в класс `MainWindow` в MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="1726c-123">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>  
- <span data-ttu-id="1726c-124">Добавьте ссылку на System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="1726c-124">Add a reference to System.Net.Http.</span></span>  
- <span data-ttu-id="1726c-125">Добавьте директиву `using` для System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="1726c-125">Add a `using` directive for System.Net.Http.</span></span>  
  
<span data-ttu-id="1726c-126">Выполнение кода в виде приложения Магазина Windows:</span><span class="sxs-lookup"><span data-stu-id="1726c-126">To run the code as a Windows Store app:</span></span>  

- <span data-ttu-id="1726c-127">Вставьте этот код в класс `MainPage` в MainPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="1726c-127">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>  
- <span data-ttu-id="1726c-128">Добавьте директивы using для System.Net.Http и System.Threading.Tasks.</span><span class="sxs-lookup"><span data-stu-id="1726c-128">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
> <span data-ttu-id="1726c-129">Дополнительные сведения о задачах и коде, который выполняется во время ожидания задачи, см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="1726c-129">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="1726c-130">Полный пример WPF, в котором используются аналогичные элементы, см. в статье [Пошаговое руководство. Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="1726c-130">For a full WPF example that uses similar elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="1726c-131">Типы возвращаемых значений</span><span class="sxs-lookup"><span data-stu-id="1726c-131">Return Types</span></span>  
<span data-ttu-id="1726c-132">Асинхронные методы могут иметь следующие типы возвращаемых значений:</span><span class="sxs-lookup"><span data-stu-id="1726c-132">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="1726c-133">[void](../builtin-types/void.md).</span><span class="sxs-lookup"><span data-stu-id="1726c-133">[void](../builtin-types/void.md).</span></span> <span data-ttu-id="1726c-134">Методы `async void` обычно рекомендуются для кода, отличного от обработчиков событий, поскольку вызывающие объекты не могут `await` эти методы и должны реализовать другой механизм уведомления об успешном завершении или ошибках.</span><span class="sxs-lookup"><span data-stu-id="1726c-134">`async void` methods are generally discouraged for code other than event handlers because callers cannot `await` those methods and must implement a different mechanism to report successful completion or error conditions.</span></span>
- <span data-ttu-id="1726c-135">Начиная с версии 7.0 в языке C# поддерживаются любые типы с доступным методом `GetAwaiter`.</span><span class="sxs-lookup"><span data-stu-id="1726c-135">Starting with C# 7.0, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="1726c-136">Одной из таких реализаций является тип `System.Threading.Tasks.ValueTask<TResult>`.</span><span class="sxs-lookup"><span data-stu-id="1726c-136">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="1726c-137">Доступ к нему осуществляется посредством пакета NuGet `System.Threading.Tasks.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="1726c-137">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span> 

<span data-ttu-id="1726c-138">Асинхронный метод не может объявлять параметры [in](./in-parameter-modifier.md), [ref](./ref.md) или [out](./out-parameter-modifier.md), а также иметь [ссылочное возвращаемое значение](../../programming-guide/classes-and-structs/ref-returns.md), но он может вызывать методы с такими параметрами.</span><span class="sxs-lookup"><span data-stu-id="1726c-138">The async method can't declare any [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md) parameters, nor can it have a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md), but it can call methods that have such parameters.</span></span>  
  
<span data-ttu-id="1726c-139">`Task<TResult>` указывается в качестве возвращаемого типа асинхронного метода, если оператор [return](./return.md) метода задает операнд типа `TResult`.</span><span class="sxs-lookup"><span data-stu-id="1726c-139">You specify `Task<TResult>` as the return type of an async method if the [return](./return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="1726c-140">Класс `Task` используется при отсутствии содержательного значения, возвращаемого методом при его завершении.</span><span class="sxs-lookup"><span data-stu-id="1726c-140">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="1726c-141">То есть вызов метода возвращает `Task`, однако когда `Task` завершен, любое выражение `await`, которое ожидает `Task`, возвращает значение `void`.</span><span class="sxs-lookup"><span data-stu-id="1726c-141">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>  
  
<span data-ttu-id="1726c-142">Возвращаемый тип `void` используется в основном для определения обработчиков событий, которые требуют этого возвращаемого типа.</span><span class="sxs-lookup"><span data-stu-id="1726c-142">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="1726c-143">Вызывающий объект асинхронного метода, возвращающего `void`, не может ожидать его и перехватывать создаваемые методом исключения.</span><span class="sxs-lookup"><span data-stu-id="1726c-143">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>  

<span data-ttu-id="1726c-144">Начиная с версии C# 7.0, возвращается другой тип, обычно тип значения, с методом `GetAwaiter`, что позволяет свести к минимуму операции выделения памяти в разделах кода с критическими требованиями к производительности.</span><span class="sxs-lookup"><span data-stu-id="1726c-144">Starting with C# 7.0, you return another type, typically a value type, that has a `GetAwaiter` method to minimize memory allocations in performance-critical sections of code.</span></span> 

<span data-ttu-id="1726c-145">Дополнительные сведения и примеры см. в разделе [Асинхронные типы возвращаемых значений](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="1726c-145">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1726c-146">См. также</span><span class="sxs-lookup"><span data-stu-id="1726c-146">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="1726c-147">await</span><span class="sxs-lookup"><span data-stu-id="1726c-147">await</span></span>](../operators/await.md)
- [<span data-ttu-id="1726c-148">Пошаговое руководство: Получение доступа к Интернету с помощью модификатора Async и оператора Await (C#)</span><span class="sxs-lookup"><span data-stu-id="1726c-148">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="1726c-149">Асинхронное программирование с использованием ключевых слов async и await</span><span class="sxs-lookup"><span data-stu-id="1726c-149">Asynchronous Programming with async and await</span></span>](../../programming-guide/concepts/async/index.md)
