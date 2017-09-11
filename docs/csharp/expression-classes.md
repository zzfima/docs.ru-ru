---
title: "Типы платформ, поддерживающие деревья выражений"
description: "Сведения о типах платформ, поддерживающих деревья выражений, создании деревьев выражений и способах работы с API деревьев выражений."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ed89b286eee9b4c2e11bb27d18e50f777f94f33e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="framework-types-supporting-expression-trees"></a><span data-ttu-id="2040b-104">Типы платформ, поддерживающие деревья выражений</span><span class="sxs-lookup"><span data-stu-id="2040b-104">Framework Types Supporting Expression Trees</span></span>

[<span data-ttu-id="2040b-105">Предыдущий раздел: "Описание деревьев выражений"</span><span class="sxs-lookup"><span data-stu-id="2040b-105">Previous -- Expression Trees Explained</span></span>](expression-trees-explained.md)

<span data-ttu-id="2040b-106">Платформа .NET Core содержит множество классов для работы с деревьями выражений.</span><span class="sxs-lookup"><span data-stu-id="2040b-106">There is a large list of classes in the .NET Core framework that work with Expression Trees.</span></span>
<span data-ttu-id="2040b-107">Полный список можно просмотреть в [этом разделе](/dotnet/core/api/System.Linq.Expressions).</span><span class="sxs-lookup"><span data-stu-id="2040b-107">You can see the full list [here](/dotnet/core/api/System.Linq.Expressions).</span></span>
<span data-ttu-id="2040b-108">Вместо того чтобы знакомиться с этим списком, давайте разберемся, как строятся классы платформы.</span><span class="sxs-lookup"><span data-stu-id="2040b-108">Rather than run through the full list, let's understand how the framework classes have been designed.</span></span>

<span data-ttu-id="2040b-109">Согласно принципам языка выражение — это блок кода, который выполняет вычисления и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="2040b-109">In language design, an expression is a body of code that evaluates and returns a value.</span></span> <span data-ttu-id="2040b-110">Выражения могут быть очень простыми: константное выражение `1` всегда возвращает значение 1.</span><span class="sxs-lookup"><span data-stu-id="2040b-110">Expressions may be very simple: the constant expression `1` returns the constant value of 1.</span></span> <span data-ttu-id="2040b-111">Они могут быть более сложными: выражение `(-B + Math.Sqrt(B*B + 4 * A * C)) / (2 * A)` возвращает один корень квадратного уравнения (если у уравнения есть решение).</span><span class="sxs-lookup"><span data-stu-id="2040b-111">They may be more complicated: The expression `(-B + Math.Sqrt(B*B + 4 * A * C)) / (2 * A)` returns one root for a quadratic equation (in the case where the equation has a solution).</span></span>  

## <a name="it-all-starts-with-systemlinqexpression"></a><span data-ttu-id="2040b-112">Все начинается с System.Linq.Expression</span><span class="sxs-lookup"><span data-stu-id="2040b-112">It all starts with System.Linq.Expression</span></span>

<span data-ttu-id="2040b-113">Одна из трудностей при работе с деревьями выражений заключается в том, что выражения различных типов могут использоваться в программах в самых разных местах.</span><span class="sxs-lookup"><span data-stu-id="2040b-113">One of the complexities of working with expression trees is that many different kinds of expressions are valid in many places in programs.</span></span> <span data-ttu-id="2040b-114">Возьмем для примера выражение присваивания.</span><span class="sxs-lookup"><span data-stu-id="2040b-114">Consider an assignment expression.</span></span> <span data-ttu-id="2040b-115">В правой его части может быть константа, переменная, выражение вызова метода или иной элемент.</span><span class="sxs-lookup"><span data-stu-id="2040b-115">The right hand side of an assignment could be a constant value, a variable, a method call expression, or others.</span></span> <span data-ttu-id="2040b-116">Такая гибкость языка означает, что при обходе дерева выражения в его узлах вам могут встретиться различные типы выражений.</span><span class="sxs-lookup"><span data-stu-id="2040b-116">That language flexibility means that you may encounter many different expression types anywhere in the nodes of a tree when you traverse an expression tree.</span></span> <span data-ttu-id="2040b-117">Поэтому, если есть возможность использовать базовый тип выражения, это простейший способ работы.</span><span class="sxs-lookup"><span data-stu-id="2040b-117">Therefore, when you can work with the base expression type, that's the simplest way to work.</span></span> <span data-ttu-id="2040b-118">Однако иногда этого недостаточно.</span><span class="sxs-lookup"><span data-stu-id="2040b-118">However, sometimes you need to know more.</span></span>
<span data-ttu-id="2040b-119">На этот случай базовый класс Expression содержит свойство `NodeType`.</span><span class="sxs-lookup"><span data-stu-id="2040b-119">The base Expression class contains a `NodeType` property for this purpose.</span></span>
<span data-ttu-id="2040b-120">Оно возвращает `ExpressionType` — перечисление возможных типов выражений.</span><span class="sxs-lookup"><span data-stu-id="2040b-120">It returns an `ExpressionType` which is an enumeration of possible expression types.</span></span>
<span data-ttu-id="2040b-121">Если вы знаете тип узла выражения, то можете привести его к этому типу и выполнять с ним определенные действия.</span><span class="sxs-lookup"><span data-stu-id="2040b-121">Once you know the type of the node, you can cast it to that type, and perform specific actions knowing the type of the expression node.</span></span> <span data-ttu-id="2040b-122">Можно выполнить поиск узлов определенных типов, а затем работать со свойствами данного типа выражения.</span><span class="sxs-lookup"><span data-stu-id="2040b-122">You can search for certain node types, and then work with the specific properties of that kind of expression.</span></span>

<span data-ttu-id="2040b-123">Например, приведенный ниже код печатает имя переменной для выражения доступа к переменной.</span><span class="sxs-lookup"><span data-stu-id="2040b-123">For example, this code will print the name of a variable for a variable access expression.</span></span> <span data-ttu-id="2040b-124">В нем используется метод, заключающийся в проверке типа узла, приведении к выражению доступа к переменной и последующей проверке свойств определенного типа выражения.</span><span class="sxs-lookup"><span data-stu-id="2040b-124">I've followed the practice of checking the node type, then casting to a variable access expression and then checking the properties of the specific expression type:</span></span>

```csharp
Expression<Func<int, int>> addFive = (num) => num + 5;

if (addFive.NodeType == ExpressionType.Lambda)
{
    var lambdaExp = (LambdaExpression)addFive;

    var parameter = lambdaExp.Parameters.First();

    Console.WriteLine(parameter.Name);
    Console.WriteLine(parameter.Type);
}
```

## <a name="creating-expression-trees"></a><span data-ttu-id="2040b-125">Создание деревьев выражений</span><span class="sxs-lookup"><span data-stu-id="2040b-125">Creating Expression Trees</span></span>

<span data-ttu-id="2040b-126">Класс `System.Linq.Expression` также содержит множество статических методов для создания выражений.</span><span class="sxs-lookup"><span data-stu-id="2040b-126">The `System.Linq.Expression` class also contains many static methods to create expressions.</span></span> <span data-ttu-id="2040b-127">Эти методы создают узел выражения с помощью аргументов, предоставленных для его дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="2040b-127">These methods create an expression node using the arguments supplied for its children.</span></span> <span data-ttu-id="2040b-128">Таким образом, выражение строится на основе листовых узлов.</span><span class="sxs-lookup"><span data-stu-id="2040b-128">In this way, you build an expression up from its leaf nodes.</span></span> <span data-ttu-id="2040b-129">Например, следующий код создает выражение сложения:</span><span class="sxs-lookup"><span data-stu-id="2040b-129">For example, this code builds an Add expression:</span></span>

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

<span data-ttu-id="2040b-130">На этом простом примере видно, что в создании деревьев выражений и работе с ними задействовано множество типов.</span><span class="sxs-lookup"><span data-stu-id="2040b-130">You can see from this simple example that many types are involved in creating and working with expression trees.</span></span> <span data-ttu-id="2040b-131">Такая сложность необходима для предоставления широких возможностей словаря C#.</span><span class="sxs-lookup"><span data-stu-id="2040b-131">That complexity is necessary to provide the capabilities of the rich vocabulary provided by the C# language.</span></span>

## <a name="navigating-the-apis"></a><span data-ttu-id="2040b-132">Перемещение по API</span><span class="sxs-lookup"><span data-stu-id="2040b-132">Navigating the APIs</span></span>
<span data-ttu-id="2040b-133">Существуют типы узлов выражений, которые сопоставляются почти со всеми элементами синтаксиса языка C#.</span><span class="sxs-lookup"><span data-stu-id="2040b-133">There are Expression node types that map to almost all of the syntax elements of the C# language.</span></span> <span data-ttu-id="2040b-134">Каждый тип имеет определенные методы для конкретного типа элементов языка.</span><span class="sxs-lookup"><span data-stu-id="2040b-134">Each type has specific methods for that type of language element.</span></span> <span data-ttu-id="2040b-135">Держать в голове приходится слишком многое.</span><span class="sxs-lookup"><span data-stu-id="2040b-135">It's a lot to keep in your head at one time.</span></span> <span data-ttu-id="2040b-136">Вместо того чтобы запоминать все это, при работе с деревьями выражений можно применять описанные ниже приемы.</span><span class="sxs-lookup"><span data-stu-id="2040b-136">Rather than try to memorize everything, here are the techniques I use to work with Expression trees:</span></span>
1. <span data-ttu-id="2040b-137">Просмотрите элементы перечисления `ExpressionType`, чтобы определить возможные узлы для анализа.</span><span class="sxs-lookup"><span data-stu-id="2040b-137">Look at the members of the `ExpressionType` enum to determine possible nodes you should be examining.</span></span> <span data-ttu-id="2040b-138">Это очень полезно, если нужно выполнить обход дерева и изучить его.</span><span class="sxs-lookup"><span data-stu-id="2040b-138">This really helps when you want to traverse and understand an expression tree.</span></span>
2. <span data-ttu-id="2040b-139">Просмотрите статические члены класса `Expression`, которые служат для создания выражения.</span><span class="sxs-lookup"><span data-stu-id="2040b-139">Look at the static members of the `Expression` class to build an expression.</span></span> <span data-ttu-id="2040b-140">С помощью этих методов можно создать выражение любого типа на основе набора дочерних узлов.</span><span class="sxs-lookup"><span data-stu-id="2040b-140">Those methods can build any expression type from a set of its child nodes.</span></span>
3. <span data-ttu-id="2040b-141">Обратите внимание на класс `ExpressionVisitor`, который служит для создания измененного дерева выражения.</span><span class="sxs-lookup"><span data-stu-id="2040b-141">Look at the `ExpressionVisitor` class to build a modified expression tree.</span></span>

<span data-ttu-id="2040b-142">В каждой из этих трех областей доступны и другие возможности.</span><span class="sxs-lookup"><span data-stu-id="2040b-142">You'll find more as you look at each of those three areas.</span></span> <span data-ttu-id="2040b-143">Вы обязательно найдете то, что вам нужно, если начнете с этих трех основных шагов.</span><span class="sxs-lookup"><span data-stu-id="2040b-143">Invariably, you will find what you need when you start with one of those three steps.</span></span>
 
 [<span data-ttu-id="2040b-144">Следующий раздел: "Выполнение деревьев выражений"</span><span class="sxs-lookup"><span data-stu-id="2040b-144">Next -- Executing Expression Trees</span></span>](expression-trees-execution.md)
 

