---
title: "Локальные функции или лямбда-выражения"
description: "Узнайте, чем локальные функции могут быть лучше лямбда-выражений."
keywords: "C# .NET, .NET Core, новейшие возможности, новые локальные функции, лямбда-выражения"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 0730e7b7d6e3ef7b5c534d16baacde6a7dafacfc
ms.contentlocale: ru-ru
ms.lasthandoff: 08/25/2017

---
# <a name="local-functions-compared-to-lambda-expressions"></a><span data-ttu-id="a9266-104">Сравнение локальных функций и лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="a9266-104">Local functions compared to Lambda expressions</span></span>

<span data-ttu-id="a9266-105">На первый взгляд [локальные функции](programming-guide/classes-and-structs/local-functions.md) и [лямбда-выражения](lambda-expressions.md) во многом похожи.</span><span class="sxs-lookup"><span data-stu-id="a9266-105">At first glance, [local functions](programming-guide/classes-and-structs/local-functions.md) and [lambda expressions](lambda-expressions.md) are very similar.</span></span>
<span data-ttu-id="a9266-106">В зависимости от ваших требований локальные функции зачастую позволяют реализовать более простое и эффективное решение.</span><span class="sxs-lookup"><span data-stu-id="a9266-106">Depending on your needs, local functions may be a much better and simpler solution.</span></span>

<span data-ttu-id="a9266-107">Рассмотрим различия в реализации алгоритма вычисления факториала с использованием локальной функции и лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="a9266-107">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="a9266-108">В первой версии используется локальная функция:</span><span class="sxs-lookup"><span data-stu-id="a9266-108">First the version using a local function:</span></span>

<span data-ttu-id="a9266-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Рекурсивный факториал с использованием локальной функции")]</span><span class="sxs-lookup"><span data-stu-id="a9266-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]</span></span>

<span data-ttu-id="a9266-110">Сравните эту реализацию с версией, в которой используются лямбда-выражения:</span><span class="sxs-lookup"><span data-stu-id="a9266-110">Contrast that implementation with a version that uses lambda expressions:</span></span>

<span data-ttu-id="a9266-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Рекурсивный факториал с использованием лямбда-выражений")]</span><span class="sxs-lookup"><span data-stu-id="a9266-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]</span></span>

<span data-ttu-id="a9266-112">Во-первых, лямбда-выражения реализуются путем создания экземпляра делегата и вызова этого делегата.</span><span class="sxs-lookup"><span data-stu-id="a9266-112">First, lambda expressions are implemented by instantiating a delegate and invoking that delegate.</span></span> <span data-ttu-id="a9266-113">Локальные функции реализуются как вызовы методов.</span><span class="sxs-lookup"><span data-stu-id="a9266-113">Local functions are implemented as method calls.</span></span>
<span data-ttu-id="a9266-114">Создание экземпляра, необходимое для лямбда-выражений, означает выделение дополнительной памяти, что в критически важном коде может ухудшить производительность.</span><span class="sxs-lookup"><span data-stu-id="a9266-114">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time critical code paths.</span></span>
<span data-ttu-id="a9266-115">Локальные функции не создают этой перегрузки.</span><span class="sxs-lookup"><span data-stu-id="a9266-115">Local functions do not incur this overhead.</span></span> <span data-ttu-id="a9266-116">В приведенном выше примере в версии с локальной функцией используется на 2 меньше операции выделения памяти по сравнению с версией на основе лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="a9266-116">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

<span data-ttu-id="a9266-117">Этот рекурсивный метод настолько прост, что локальная функция реализуется в виде частного метода, имя которого создается компилятором.</span><span class="sxs-lookup"><span data-stu-id="a9266-117">This recursive method is simple enough that the local function is implemented as a private method with a compiler generated name.</span></span> <span data-ttu-id="a9266-118">Единственное отличие от частных методов заключается в том, что семантическая область действия в этом случае находится внутри внешней функции.</span><span class="sxs-lookup"><span data-stu-id="a9266-118">Its only difference from other private methods is that it is semantically scoped inside the outer function.</span></span>

<span data-ttu-id="a9266-119">Во-вторых, локальные функции можно вызывать до того, как они будут определены.</span><span class="sxs-lookup"><span data-stu-id="a9266-119">Second, local functions can be called before they are defined.</span></span> <span data-ttu-id="a9266-120">Лямбда-выражения перед определением необходимо объявлять.</span><span class="sxs-lookup"><span data-stu-id="a9266-120">Lambda expressions must be declared before they are defined.</span></span> <span data-ttu-id="a9266-121">Это значит, что локальные функции проще использовать в рекурсивных алгоритмах, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="a9266-121">This means local functions are easier to use in recursive algorithms, as shown above.</span></span>

<span data-ttu-id="a9266-122">Обратите внимание на то, что версия с использованием лямбда-выражения должна объявить и инициализировать лямбда-выражение `nthFactorial`, прежде чем его определить.</span><span class="sxs-lookup"><span data-stu-id="a9266-122">Notice that the version using the lambda expression must declare and initialize the lambda expression, `nthFactorial` before defining it.</span></span> <span data-ttu-id="a9266-123">В противном случае возникает ошибка компилятора, связанная со ссылкой на объект `nthFactorial`, который еще не был назначен.</span><span class="sxs-lookup"><span data-stu-id="a9266-123">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span>
<span data-ttu-id="a9266-124">Рекурсивные алгоритмы легче создавать, используя локальные функции.</span><span class="sxs-lookup"><span data-stu-id="a9266-124">Recursive algorithms are easier to create using local functions.</span></span>

<span data-ttu-id="a9266-125">В-третьих, для лямбда-выражений компилятору необходимо всегда создавать анонимный класс и экземпляр этого класса, в котором будут храниться все переменные, попавшие в замыкание.</span><span class="sxs-lookup"><span data-stu-id="a9266-125">Third, for lambda expressions, the compiler must always create an anonymous class and an instance of that class to store any variables captured by the closure.</span></span> <span data-ttu-id="a9266-126">Рассмотрим следующий асинхронный пример:</span><span class="sxs-lookup"><span data-stu-id="a9266-126">Consider this async example:</span></span>

<span data-ttu-id="a9266-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Метод с лямбда-выражением, возвращающий задачу")]</span><span class="sxs-lookup"><span data-stu-id="a9266-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]</span></span>

<span data-ttu-id="a9266-128">Замыкание для этого лямбда-выражения содержит переменные `address`, `index` и `name`.</span><span class="sxs-lookup"><span data-stu-id="a9266-128">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="a9266-129">При использовании локальных функций объект, который реализует замыкание, может иметь тип `struct`.</span><span class="sxs-lookup"><span data-stu-id="a9266-129">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="a9266-130">Это позволит сократить объем выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="a9266-130">That would save on an allocation.</span></span>

> [!NOTE]
> <span data-ttu-id="a9266-131">В эквивалентном этому методе на основе локальной функции также используется класс для замыкания.</span><span class="sxs-lookup"><span data-stu-id="a9266-131">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="a9266-132">Реализация замыкания для локальной функции в формате `class` или `struct` зависит от особенностей реализации.</span><span class="sxs-lookup"><span data-stu-id="a9266-132">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="a9266-133">Локальная функция может использовать `struct`, тогда как в лямбда-выражениях всегда используется `class`.</span><span class="sxs-lookup"><span data-stu-id="a9266-133">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

<span data-ttu-id="a9266-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Метод с локальной функцией, возвращающий задачу")]</span><span class="sxs-lookup"><span data-stu-id="a9266-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]</span></span>

<span data-ttu-id="a9266-135">Еще одно преимущество локальных функций, которое не показано в этом примере, заключается в том, что они могут быть реализованы в качестве итераторов с использованием синтаксиса `yield return` для создания последовательности значений.</span><span class="sxs-lookup"><span data-stu-id="a9266-135">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span>

<span data-ttu-id="a9266-136">Локальные функции могут показаться избыточными для лямбда-выражений, поскольку обычно применяются иначе и в других целях.</span><span class="sxs-lookup"><span data-stu-id="a9266-136">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span>
<span data-ttu-id="a9266-137">Локальные функции более эффективны в случаях, когда вам нужно написать функцию, которая будет вызываться только из контекста другого метода.</span><span class="sxs-lookup"><span data-stu-id="a9266-137">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>

