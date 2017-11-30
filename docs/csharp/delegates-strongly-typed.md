---
title: "Строго типизированные делегаты"
description: "Сведения об использовании универсальных типов делегатов для объявления настраиваемых типов при создании функции, использующей делегаты."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
ms.openlocfilehash: 467ba18f8e032b9b3b8f480d4b10c92d0d7ba3b9
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2017
---
# <a name="strongly-typed-delegates"></a><span data-ttu-id="44289-104">Строго типизированные делегаты</span><span class="sxs-lookup"><span data-stu-id="44289-104">Strongly Typed Delegates</span></span>

[<span data-ttu-id="44289-105">Назад</span><span class="sxs-lookup"><span data-stu-id="44289-105">Previous</span></span>](delegate-class.md)

<span data-ttu-id="44289-106">Из предыдущей статьи вы узнали, как создавать определенные типы делегатов с помощью ключевого слова `delegate`.</span><span class="sxs-lookup"><span data-stu-id="44289-106">In the previous article, you saw that you create specific delegate types using the `delegate` keyword.</span></span> 

<span data-ttu-id="44289-107">Абстрактный класс делегата предоставляет инфраструктуру для неплотной привязки и вызова.</span><span class="sxs-lookup"><span data-stu-id="44289-107">The abstract Delegate class provide the infrastructure for loose coupling and invocation.</span></span> <span data-ttu-id="44289-108">Конкретные типы делегата становятся гораздо полезнее, поскольку включают и обеспечивают безопасность типов для методов, добавляемых в список вызовов для объекта делегата.</span><span class="sxs-lookup"><span data-stu-id="44289-108">Concrete Delegate types become much more useful by embracing and enforcing type safety for the methods that are added to the invocation list for a delegate object.</span></span> <span data-ttu-id="44289-109">Компилятор создает эти методы, если вы используете ключевое слово `delegate` и определяете конкретный тип делегата.</span><span class="sxs-lookup"><span data-stu-id="44289-109">When you use the `delegate` keyword and define a concrete delegate type, the compiler generates those methods.</span></span>

<span data-ttu-id="44289-110">В результате новые типы делегатов создаются всякий раз, когда возникает необходимость в новой сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="44289-110">In practice, this would lead to creating new delegate types whenever you need a different method signature.</span></span> <span data-ttu-id="44289-111">Со временем эта работа может стать слишком громоздкой.</span><span class="sxs-lookup"><span data-stu-id="44289-111">This work could get tedious after a time.</span></span> <span data-ttu-id="44289-112">Для каждого нового компонента требуются новые типы делегатов.</span><span class="sxs-lookup"><span data-stu-id="44289-112">Every new feature requires new delegate types.</span></span>

<span data-ttu-id="44289-113">К счастью, это необязательно.</span><span class="sxs-lookup"><span data-stu-id="44289-113">Thankfully, this isn't necessary.</span></span> <span data-ttu-id="44289-114">Платформа .NET Core содержит несколько типов, которые можно использовать всякий раз, когда вам нужно делегировать типы.</span><span class="sxs-lookup"><span data-stu-id="44289-114">The .NET Core framework contains several types that you can reuse whenever you need delegate types.</span></span> <span data-ttu-id="44289-115">Эти определения [универсальны](programming-guide/generics/index.md), поэтому всякий раз, когда вам нужно объявить новый метод, можно объявить настройку.</span><span class="sxs-lookup"><span data-stu-id="44289-115">These are [generic](programming-guide/generics/index.md) definitions so you can declare customizations when you need new method declarations.</span></span> 

<span data-ttu-id="44289-116">Первый из этих типов — это тип <xref:System.Action> и несколько вариантов:</span><span class="sxs-lookup"><span data-stu-id="44289-116">The first of these types is the <xref:System.Action> type, and several variations:</span></span>

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

<span data-ttu-id="44289-117">Модификатор `in` для аргумента универсального типа рассматривается в статье о ковариации.</span><span class="sxs-lookup"><span data-stu-id="44289-117">The `in` modifier on the generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="44289-118">Существуют различные виды `Action` делегат, который будет содержать до 16 аргументов, например <xref:System.Action%6016>.</span><span class="sxs-lookup"><span data-stu-id="44289-118">There are variations of the `Action` delegate that contain up to 16 arguments such as <xref:System.Action%6016>.</span></span>
<span data-ttu-id="44289-119">Очень важно, чтобы для каждого из аргументов делегата в этих определениях использовались универсальные аргументы — это дает максимальную гибкость.</span><span class="sxs-lookup"><span data-stu-id="44289-119">It's important that these definitions use different generic arguments for each of the delegate arguments: That gives you maximum flexibility.</span></span> <span data-ttu-id="44289-120">Аргументы метода могут быть одного типа, однако это необязательно.</span><span class="sxs-lookup"><span data-stu-id="44289-120">The method arguments need not be, but may be, the same type.</span></span>

<span data-ttu-id="44289-121">В качестве типа делегата используйте один из типов `Action` с типом возвращаемого значения void.</span><span class="sxs-lookup"><span data-stu-id="44289-121">Use one of the `Action` types for any delegate type that has a void return type.</span></span>

<span data-ttu-id="44289-122">Платформа включает также несколько типов универсальных делегатов, которые можно использовать в качестве типов делегатов, возвращающих значения:</span><span class="sxs-lookup"><span data-stu-id="44289-122">The framework also includes several generic delegate types that you can use for delegate types that return values:</span></span>

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

<span data-ttu-id="44289-123">Модификатор `out` для аргумента универсального типа результата рассматривается в статье о ковариации.</span><span class="sxs-lookup"><span data-stu-id="44289-123">The `out` modifier on the result generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="44289-124">Существуют различные виды `Func` делегат со до 16 входных аргументов, например <xref:System.Func%6017>.</span><span class="sxs-lookup"><span data-stu-id="44289-124">There are variations of the `Func` delegate with up to 16 input arguments such as <xref:System.Func%6017>.</span></span>
<span data-ttu-id="44289-125">Как правило, тип результата должен быть последним параметром типа во всех объявлениях `Func`.</span><span class="sxs-lookup"><span data-stu-id="44289-125">The type of the result is always the last type parameter in all the `Func` declarations, by convention.</span></span>

<span data-ttu-id="44289-126">В качестве типа делегата, возвращающего значение, используйте один из типов `Func`.</span><span class="sxs-lookup"><span data-stu-id="44289-126">Use one of the `Func` types for any delegate type that returns a value.</span></span>

<span data-ttu-id="44289-127">Существует также специальный <xref:System.Predicate%601> тип делегата, который возвращает тест с одним значением:</span><span class="sxs-lookup"><span data-stu-id="44289-127">There's also a specialized <xref:System.Predicate%601> type for a delegate that returns a test on a single value:</span></span>

```csharp
public delegate bool Predicate<in T>(T obj);
```

<span data-ttu-id="44289-128">Можно заметить, что для каждого типа `Predicate` существует структурно эквивалентный тип `Func`, например:</span><span class="sxs-lookup"><span data-stu-id="44289-128">You may notice that for any `Predicate` type, a structurally equivalent `Func` type exists For example:</span></span>

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

<span data-ttu-id="44289-129">Можно подумать, что два эти типа эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="44289-129">You might think these two types are equivalent.</span></span> <span data-ttu-id="44289-130">Это не так.</span><span class="sxs-lookup"><span data-stu-id="44289-130">They are not.</span></span>
<span data-ttu-id="44289-131">Эти две переменные не заменяют друг друга.</span><span class="sxs-lookup"><span data-stu-id="44289-131">These two variables cannot be used interchangeably.</span></span> <span data-ttu-id="44289-132">Переменную одного типа нельзя назначить другому типу.</span><span class="sxs-lookup"><span data-stu-id="44289-132">A variable of one type cannot be assigned the other type.</span></span> <span data-ttu-id="44289-133">В системе типов C# используются имена определенных типов, а не структуры.</span><span class="sxs-lookup"><span data-stu-id="44289-133">The C# type system uses the names of the defined types, not the structure.</span></span>

<span data-ttu-id="44289-134">Все эти определения типов делегатов в библиотеке .NET Core должны означать, что новый тип делегата для каждой создаваемой функции, которой требуются делегаты, создавать не нужно.</span><span class="sxs-lookup"><span data-stu-id="44289-134">All these delegate type definitions in the .NET Core Library should mean that you do not need to define a new delegate type for any new feature you create that requires delegates.</span></span> <span data-ttu-id="44289-135">Эти универсальные определения должны предоставлять типы делегатов, необходимые в большинстве ситуаций.</span><span class="sxs-lookup"><span data-stu-id="44289-135">These generic definitions should provide all the delegate types you need under most situations.</span></span> <span data-ttu-id="44289-136">Можно просто создать экземпляр одного из этих типов с необходимыми параметрами типа.</span><span class="sxs-lookup"><span data-stu-id="44289-136">You can simply instantiate one of these types with the required type parameters.</span></span> <span data-ttu-id="44289-137">Если алгоритмы можно сделать универсальными, эти делегаты можно использовать как универсальные типы.</span><span class="sxs-lookup"><span data-stu-id="44289-137">In the case of algorithms that can be made generic, these delegates can be used as generic types.</span></span> 

<span data-ttu-id="44289-138">Это позволит сэкономить время и свести к минимуму число новых типов, которые нужно создать для работы с делегатами.</span><span class="sxs-lookup"><span data-stu-id="44289-138">This should save time, and minimize the number of new types that you need to create in order to work with delegates.</span></span>

<span data-ttu-id="44289-139">В следующей статье представлено несколько общих шаблонов для работы с делегатами на практике.</span><span class="sxs-lookup"><span data-stu-id="44289-139">In the next article, you'll see several common patterns for working with delegates in practice.</span></span>

[<span data-ttu-id="44289-140">Далее</span><span class="sxs-lookup"><span data-stu-id="44289-140">Next</span></span>](delegates-patterns.md)
