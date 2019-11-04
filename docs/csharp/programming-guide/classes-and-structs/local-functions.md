---
title: Руководство по программированию на C#. Локальные функции
ms.custom: seodec18
ms.date: 06/14/2017
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: 7b6b46a33430a4a58c78245a0ab3bed1e0fbcd9c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455372"
---
# <a name="local-functions-c-programming-guide"></a><span data-ttu-id="b4a09-102">Локальные функции (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b4a09-102">Local functions (C# Programming Guide)</span></span>

<span data-ttu-id="b4a09-103">Начиная с версии 7.0 в языке C# поддерживаются *локальные функции*.</span><span class="sxs-lookup"><span data-stu-id="b4a09-103">Starting with C# 7.0, C# supports *local functions*.</span></span> <span data-ttu-id="b4a09-104">Локальные функции представляют собой частные методы типа, вложенные в другой элемент.</span><span class="sxs-lookup"><span data-stu-id="b4a09-104">Local functions are private methods of a type that are nested in another member.</span></span> <span data-ttu-id="b4a09-105">Они могут вызываться только из того элемента, в который вложены.</span><span class="sxs-lookup"><span data-stu-id="b4a09-105">They can only be called from their containing member.</span></span> <span data-ttu-id="b4a09-106">Ниже перечислены элементы, в которых можно объявлять и из которых можно вызывать локальные функции:</span><span class="sxs-lookup"><span data-stu-id="b4a09-106">Local functions can be declared in and called from:</span></span>

- <span data-ttu-id="b4a09-107">Методы, в частности методы итератора и асинхронные методы</span><span class="sxs-lookup"><span data-stu-id="b4a09-107">Methods, especially iterator methods and async methods</span></span>
- <span data-ttu-id="b4a09-108">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="b4a09-108">Constructors</span></span>
- <span data-ttu-id="b4a09-109">Методы доступа свойств</span><span class="sxs-lookup"><span data-stu-id="b4a09-109">Property accessors</span></span>
- <span data-ttu-id="b4a09-110">Методы доступа событий</span><span class="sxs-lookup"><span data-stu-id="b4a09-110">Event accessors</span></span>
- <span data-ttu-id="b4a09-111">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="b4a09-111">Anonymous methods</span></span>
- <span data-ttu-id="b4a09-112">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="b4a09-112">Lambda expressions</span></span>
- <span data-ttu-id="b4a09-113">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="b4a09-113">Finalizers</span></span>
- <span data-ttu-id="b4a09-114">Другие локальные функции</span><span class="sxs-lookup"><span data-stu-id="b4a09-114">Other local functions</span></span>

<span data-ttu-id="b4a09-115">Тем не менее локальные функции нельзя объявлять внутри элемента, воплощающего выражение.</span><span class="sxs-lookup"><span data-stu-id="b4a09-115">However, local functions can't be declared inside an expression-bodied member.</span></span>

> [!NOTE]
> <span data-ttu-id="b4a09-116">В некоторых случаях для реализации возможностей, поддерживаемых локальными функциями, также можно использовать лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="b4a09-116">In some cases, you can use a lambda expression to implement functionality also supported by a local function.</span></span> <span data-ttu-id="b4a09-117">Дополнительные сведения см. в разделе [Сравнение локальных функций и лямбда-выражений](../../local-functions-vs-lambdas.md).</span><span class="sxs-lookup"><span data-stu-id="b4a09-117">For a comparison, see [Local functions compared to Lambda expressions](../../local-functions-vs-lambdas.md).</span></span>

<span data-ttu-id="b4a09-118">Применение локальных функций позволяет сделать предназначение кода более понятным.</span><span class="sxs-lookup"><span data-stu-id="b4a09-118">Local functions make the intent of your code clear.</span></span> <span data-ttu-id="b4a09-119">Другие пользователи, читающие ваш код, смогут видеть, что соответствующий метод вызывается только внутри того метода, в который он вложен.</span><span class="sxs-lookup"><span data-stu-id="b4a09-119">Anyone reading your code can see that the method is not callable except by the containing method.</span></span> <span data-ttu-id="b4a09-120">В случае с командными проектами это также гарантирует, что другой разработчик не сможет ошибочно вызвать метод напрямую из любого другого места в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="b4a09-120">For team projects, they also make it impossible for another developer to mistakenly call the method directly from elsewhere in the class or struct.</span></span>
 
## <a name="local-function-syntax"></a><span data-ttu-id="b4a09-121">Синтаксис локальной функции</span><span class="sxs-lookup"><span data-stu-id="b4a09-121">Local function syntax</span></span>

<span data-ttu-id="b4a09-122">Локальная функция определяется как вложенный метод внутри содержащего ее элемента.</span><span class="sxs-lookup"><span data-stu-id="b4a09-122">A local function is defined as a nested method inside a containing member.</span></span> <span data-ttu-id="b4a09-123">Ниже приведен синтаксис определения локальной функции:</span><span class="sxs-lookup"><span data-stu-id="b4a09-123">Its definition has the following syntax:</span></span>

```csharp
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

<span data-ttu-id="b4a09-124">Локальные функции могут использовать модификаторы [async](../../language-reference/keywords/async.md) и [unsafe](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="b4a09-124">Local functions can use the [async](../../language-reference/keywords/async.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span> 

<span data-ttu-id="b4a09-125">Обратите внимание, что все локальные переменные, определенные в содержащем функцию элементе (включая параметры метода), доступны в локальной функции.</span><span class="sxs-lookup"><span data-stu-id="b4a09-125">Note that all local variables that are defined in the containing member, including its method parameters, are accessible in the local function.</span></span> 

<span data-ttu-id="b4a09-126">В отличие от определения метода, определение локальной функции не может содержать следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="b4a09-126">Unlike a method definition, a local function definition cannot include the following elements:</span></span>

- <span data-ttu-id="b4a09-127">Модификатор доступа элемента.</span><span class="sxs-lookup"><span data-stu-id="b4a09-127">The member access modifier.</span></span> <span data-ttu-id="b4a09-128">Поскольку все локальные функции являются частными, при использовании модификатора доступа (например, ключевого слова `private`) возникает ошибка компилятора CS0106, "Модификатор "private" недопустим для этого элемента".</span><span class="sxs-lookup"><span data-stu-id="b4a09-128">Because all local functions are private, including an access modifier, such as the `private` keyword, generates compiler error CS0106, "The modifier 'private' is not valid for this item."</span></span>
 
- <span data-ttu-id="b4a09-129">Ключевое слово [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="b4a09-129">The [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="b4a09-130">При использовании ключевого слова `static` возникает ошибка компилятора CS0106, "Модификатор "static" недопустим для этого элемента".</span><span class="sxs-lookup"><span data-stu-id="b4a09-130">Including the `static` keyword generates compiler error CS0106, "The modifier 'static' is not valid for this item."</span></span>

<span data-ttu-id="b4a09-131">Кроме того, к локальной функции, а также ее параметрам и параметрам типа, нельзя применять атрибуты.</span><span class="sxs-lookup"><span data-stu-id="b4a09-131">In addition, attributes can't be applied to the local function or to its parameters and type parameters.</span></span> 
 
<span data-ttu-id="b4a09-132">В следующем примере определяется локальная функция `AppendPathSeparator`, которая является частной для метода `GetText`:</span><span class="sxs-lookup"><span data-stu-id="b4a09-132">The following example defines a local function named `AppendPathSeparator` that is private to a method named `GetText`:</span></span>
   
[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  
   
## <a name="local-functions-and-exceptions"></a><span data-ttu-id="b4a09-133">Локальные функции и исключения</span><span class="sxs-lookup"><span data-stu-id="b4a09-133">Local functions and exceptions</span></span>

<span data-ttu-id="b4a09-134">Полезной особенностью локальных функций является то, что они допускают немедленную обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="b4a09-134">One of the useful features of local functions is that they can allow exceptions to surface immediately.</span></span> <span data-ttu-id="b4a09-135">В случае с итераторами метода исключения обрабатываются только после перечисления возвращаемой последовательности, а не в момент извлечения итератора.</span><span class="sxs-lookup"><span data-stu-id="b4a09-135">For method iterators, exceptions are surfaced only when the returned sequence is enumerated, and not when the iterator is retrieved.</span></span> <span data-ttu-id="b4a09-136">В случае с асинхронными методами любые исключения, возникшие в таком методе, наблюдаются в тот момент, когда возвращаемая задача находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="b4a09-136">For async methods, any exceptions thrown in an async method are observed when the returned task is awaited.</span></span> 

<span data-ttu-id="b4a09-137">В следующем примере определяется метод `OddSequence`, который перечисляет нечетные числа в заданном диапазоне.</span><span class="sxs-lookup"><span data-stu-id="b4a09-137">The following example defines an `OddSequence` method that enumerates odd numbers between a specified range.</span></span> <span data-ttu-id="b4a09-138">Поскольку он передает в метод перечислителя `OddSequence` число больше 100, этот метод вызывает исключение <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="b4a09-138">Because it passes a number greater than 100 to the `OddSequence` enumerator method, the method throws an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="b4a09-139">Как видно из выходных данных этого примера, исключение обрабатывается только в момент перебора чисел, а не при извлечении перечислителя.</span><span class="sxs-lookup"><span data-stu-id="b4a09-139">As the output from the example shows, the exception surfaces only when you iterate the numbers, and not when you retrieve the enumerator.</span></span>

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)] 

<span data-ttu-id="b4a09-140">Вместо этого исключение может быть вызвано при выполнении проверки до того, как будет извлечен итератор, путем возврата итератора из локальной функции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b4a09-140">Instead, you can throw an exception when performing validation and before retrieving the iterator by returning the iterator from a local function, as the following example shows.</span></span>

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

<span data-ttu-id="b4a09-141">Локальные функции можно использовать аналогичным образом для обработки исключений вне асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="b4a09-141">Local functions can be used in a similar way to handle exceptions outside of the asynchronous operation.</span></span> <span data-ttu-id="b4a09-142">Как правило, при возникновении исключения в асинхронном методе требуется проверить внутренние исключения в <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="b4a09-142">Ordinarily, exceptions thrown in async method require that you examine the inner exceptions of an <xref:System.AggregateException>.</span></span> <span data-ttu-id="b4a09-143">Локальная функция реализует моментальный сбой кода, синхронно обеспечивая вызов исключения и наблюдение за ним.</span><span class="sxs-lookup"><span data-stu-id="b4a09-143">Local functions allow your code to fail fast and allow your exception to be both thrown and observed synchronously.</span></span>

<span data-ttu-id="b4a09-144">В следующем примере асинхронный метод `GetMultipleAsync` выполняет приостановку на указанное число секунд, возвращая значение, представляющее собой произведение случайного множителя на это число секунд.</span><span class="sxs-lookup"><span data-stu-id="b4a09-144">The following example uses an asynchronous method named `GetMultipleAsync` to pause for a specified number of seconds and return a value that is a random multiple of that number of seconds.</span></span> <span data-ttu-id="b4a09-145">Максимальная задержка составляет 5 с. Результат <xref:System.ArgumentOutOfRangeException> возвращается в том случае, если значение больше 5.</span><span class="sxs-lookup"><span data-stu-id="b4a09-145">The maximum delay is 5 seconds; an <xref:System.ArgumentOutOfRangeException> results if the value is greater than 5.</span></span> <span data-ttu-id="b4a09-146">Как видно из следующего примера, исключение, которое возникает при передаче в метод `GetMultipleAsync` значения 6, инкапсулируется в <xref:System.AggregateException> после того, как начинается выполнение метода `GetMultipleAsync`.</span><span class="sxs-lookup"><span data-stu-id="b4a09-146">As the following example shows, the exception that is thrown when a value of 6 is passed to the `GetMultipleAsync` method is wrapped in an <xref:System.AggregateException> after the `GetMultipleAsync` method begins execution.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)] 

<span data-ttu-id="b4a09-147">Как и в случае с итератором метода, можно выполнить рефакторинг кода из этого примера таким образом, чтобы реализовать проверку перед вызовом асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="b4a09-147">As we did with the method iterator, we can refactor the code from this example to perform the validation before calling the asynchronous method.</span></span> <span data-ttu-id="b4a09-148">Как видно из результатов следующего примера, <xref:System.ArgumentOutOfRangeException> не инкапсулируется в <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="b4a09-148">As the output from the following example shows, the <xref:System.ArgumentOutOfRangeException> is not wrapped in a <xref:System.AggregateException>.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)] 

## <a name="see-also"></a><span data-ttu-id="b4a09-149">См. также</span><span class="sxs-lookup"><span data-stu-id="b4a09-149">See also</span></span>

- [<span data-ttu-id="b4a09-150">Методы</span><span class="sxs-lookup"><span data-stu-id="b4a09-150">Methods</span></span>](methods.md)
