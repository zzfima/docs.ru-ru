---
title: Типы платформ, поддерживающие деревья выражений
description: Сведения о типах платформ, поддерживающих деревья выражений, создании деревьев выражений и способах работы с API деревьев выражений.
ms.date: 06/20/2016
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.openlocfilehash: c18bbfb1273156a4b070d1f195d9e823256fde9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198469"
---
# <a name="framework-types-supporting-expression-trees"></a><span data-ttu-id="bc513-103">Типы платформ, поддерживающие деревья выражений</span><span class="sxs-lookup"><span data-stu-id="bc513-103">Framework Types Supporting Expression Trees</span></span>

[<span data-ttu-id="bc513-104">Предыдущий раздел: "Описание деревьев выражений"</span><span class="sxs-lookup"><span data-stu-id="bc513-104">Previous -- Expression Trees Explained</span></span>](expression-trees-explained.md)

<span data-ttu-id="bc513-105">Платформа .NET Core содержит множество классов для работы с деревьями выражений.</span><span class="sxs-lookup"><span data-stu-id="bc513-105">There is a large list of classes in the .NET Core framework that work with Expression Trees.</span></span>
<span data-ttu-id="bc513-106">Полный список можно просмотреть в разделе <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="bc513-106">You can see the full list at <xref:System.Linq.Expressions>.</span></span>
<span data-ttu-id="bc513-107">Вместо того чтобы знакомиться с этим списком, давайте разберемся, как строятся классы платформы.</span><span class="sxs-lookup"><span data-stu-id="bc513-107">Rather than run through the full list, let's understand how the framework classes have been designed.</span></span>

<span data-ttu-id="bc513-108">Согласно принципам языка выражение — это блок кода, который выполняет вычисления и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="bc513-108">In language design, an expression is a body of code that evaluates and returns a value.</span></span> <span data-ttu-id="bc513-109">Выражения могут быть очень простыми: константное выражение `1` всегда возвращает значение 1.</span><span class="sxs-lookup"><span data-stu-id="bc513-109">Expressions may be very simple: the constant expression `1` returns the constant value of 1.</span></span> <span data-ttu-id="bc513-110">Они могут быть более сложными: выражение `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` возвращает один корень квадратного уравнения (если у уравнения есть решение).</span><span class="sxs-lookup"><span data-stu-id="bc513-110">They may be more complicated: The expression `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` returns one root for a quadratic equation (in the case where the equation has a solution).</span></span>  

## <a name="it-all-starts-with-systemlinqexpression"></a><span data-ttu-id="bc513-111">Все начинается с System.Linq.Expression</span><span class="sxs-lookup"><span data-stu-id="bc513-111">It all starts with System.Linq.Expression</span></span>

<span data-ttu-id="bc513-112">Одна из трудностей при работе с деревьями выражений заключается в том, что выражения различных типов могут использоваться в программах в самых разных местах.</span><span class="sxs-lookup"><span data-stu-id="bc513-112">One of the complexities of working with expression trees is that many different kinds of expressions are valid in many places in programs.</span></span> <span data-ttu-id="bc513-113">Возьмем для примера выражение присваивания.</span><span class="sxs-lookup"><span data-stu-id="bc513-113">Consider an assignment expression.</span></span> <span data-ttu-id="bc513-114">В правой его части может быть константа, переменная, выражение вызова метода или иной элемент.</span><span class="sxs-lookup"><span data-stu-id="bc513-114">The right hand side of an assignment could be a constant value, a variable, a method call expression, or others.</span></span> <span data-ttu-id="bc513-115">Такая гибкость языка означает, что при обходе дерева выражения в его узлах вам могут встретиться различные типы выражений.</span><span class="sxs-lookup"><span data-stu-id="bc513-115">That language flexibility means that you may encounter many different expression types anywhere in the nodes of a tree when you traverse an expression tree.</span></span> <span data-ttu-id="bc513-116">Поэтому, если есть возможность использовать базовый тип выражения, это простейший способ работы.</span><span class="sxs-lookup"><span data-stu-id="bc513-116">Therefore, when you can work with the base expression type, that's the simplest way to work.</span></span> <span data-ttu-id="bc513-117">Однако иногда этого недостаточно.</span><span class="sxs-lookup"><span data-stu-id="bc513-117">However, sometimes you need to know more.</span></span>
<span data-ttu-id="bc513-118">На этот случай базовый класс Expression содержит свойство `NodeType`.</span><span class="sxs-lookup"><span data-stu-id="bc513-118">The base Expression class contains a `NodeType` property for this purpose.</span></span>
<span data-ttu-id="bc513-119">Оно возвращает `ExpressionType` — перечисление возможных типов выражений.</span><span class="sxs-lookup"><span data-stu-id="bc513-119">It returns an `ExpressionType` which is an enumeration of possible expression types.</span></span>
<span data-ttu-id="bc513-120">Если вы знаете тип узла выражения, то можете привести его к этому типу и выполнять с ним определенные действия.</span><span class="sxs-lookup"><span data-stu-id="bc513-120">Once you know the type of the node, you can cast it to that type, and perform specific actions knowing the type of the expression node.</span></span> <span data-ttu-id="bc513-121">Можно выполнить поиск узлов определенных типов, а затем работать со свойствами данного типа выражения.</span><span class="sxs-lookup"><span data-stu-id="bc513-121">You can search for certain node types, and then work with the specific properties of that kind of expression.</span></span>

<span data-ttu-id="bc513-122">Например, приведенный ниже код печатает имя переменной для выражения доступа к переменной.</span><span class="sxs-lookup"><span data-stu-id="bc513-122">For example, this code will print the name of a variable for a variable access expression.</span></span> <span data-ttu-id="bc513-123">В нем используется метод, заключающийся в проверке типа узла, приведении к выражению доступа к переменной и последующей проверке свойств определенного типа выражения.</span><span class="sxs-lookup"><span data-stu-id="bc513-123">I've followed the practice of checking the node type, then casting to a variable access expression and then checking the properties of the specific expression type:</span></span>

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

## <a name="creating-expression-trees"></a><span data-ttu-id="bc513-124">Создание деревьев выражений</span><span class="sxs-lookup"><span data-stu-id="bc513-124">Creating Expression Trees</span></span>

<span data-ttu-id="bc513-125">Класс `System.Linq.Expression` также содержит множество статических методов для создания выражений.</span><span class="sxs-lookup"><span data-stu-id="bc513-125">The `System.Linq.Expression` class also contains many static methods to create expressions.</span></span> <span data-ttu-id="bc513-126">Эти методы создают узел выражения с помощью аргументов, предоставленных для его дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="bc513-126">These methods create an expression node using the arguments supplied for its children.</span></span> <span data-ttu-id="bc513-127">Таким образом, выражение строится на основе листовых узлов.</span><span class="sxs-lookup"><span data-stu-id="bc513-127">In this way, you build an expression up from its leaf nodes.</span></span> <span data-ttu-id="bc513-128">Например, следующий код создает выражение сложения:</span><span class="sxs-lookup"><span data-stu-id="bc513-128">For example, this code builds an Add expression:</span></span>

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

<span data-ttu-id="bc513-129">На этом простом примере видно, что в создании деревьев выражений и работе с ними задействовано множество типов.</span><span class="sxs-lookup"><span data-stu-id="bc513-129">You can see from this simple example that many types are involved in creating and working with expression trees.</span></span> <span data-ttu-id="bc513-130">Такая сложность необходима для предоставления широких возможностей словаря C#.</span><span class="sxs-lookup"><span data-stu-id="bc513-130">That complexity is necessary to provide the capabilities of the rich vocabulary provided by the C# language.</span></span>

## <a name="navigating-the-apis"></a><span data-ttu-id="bc513-131">Перемещение по API</span><span class="sxs-lookup"><span data-stu-id="bc513-131">Navigating the APIs</span></span>
<span data-ttu-id="bc513-132">Существуют типы узлов выражений, которые сопоставляются почти со всеми элементами синтаксиса языка C#.</span><span class="sxs-lookup"><span data-stu-id="bc513-132">There are Expression node types that map to almost all of the syntax elements of the C# language.</span></span> <span data-ttu-id="bc513-133">Каждый тип имеет определенные методы для конкретного типа элементов языка.</span><span class="sxs-lookup"><span data-stu-id="bc513-133">Each type has specific methods for that type of language element.</span></span> <span data-ttu-id="bc513-134">Держать в голове приходится слишком многое.</span><span class="sxs-lookup"><span data-stu-id="bc513-134">It's a lot to keep in your head at one time.</span></span> <span data-ttu-id="bc513-135">Вместо того чтобы запоминать все это, при работе с деревьями выражений можно применять описанные ниже приемы.</span><span class="sxs-lookup"><span data-stu-id="bc513-135">Rather than try to memorize everything, here are the techniques I use to work with Expression trees:</span></span>
1. <span data-ttu-id="bc513-136">Просмотрите элементы перечисления `ExpressionType`, чтобы определить возможные узлы для анализа.</span><span class="sxs-lookup"><span data-stu-id="bc513-136">Look at the members of the `ExpressionType` enum to determine possible nodes you should be examining.</span></span> <span data-ttu-id="bc513-137">Это очень полезно, если нужно выполнить обход дерева и изучить его.</span><span class="sxs-lookup"><span data-stu-id="bc513-137">This really helps when you want to traverse and understand an expression tree.</span></span>
2. <span data-ttu-id="bc513-138">Просмотрите статические члены класса `Expression`, которые служат для создания выражения.</span><span class="sxs-lookup"><span data-stu-id="bc513-138">Look at the static members of the `Expression` class to build an expression.</span></span> <span data-ttu-id="bc513-139">С помощью этих методов можно создать выражение любого типа на основе набора дочерних узлов.</span><span class="sxs-lookup"><span data-stu-id="bc513-139">Those methods can build any expression type from a set of its child nodes.</span></span>
3. <span data-ttu-id="bc513-140">Обратите внимание на класс `ExpressionVisitor`, который служит для создания измененного дерева выражения.</span><span class="sxs-lookup"><span data-stu-id="bc513-140">Look at the `ExpressionVisitor` class to build a modified expression tree.</span></span>

<span data-ttu-id="bc513-141">В каждой из этих трех областей доступны и другие возможности.</span><span class="sxs-lookup"><span data-stu-id="bc513-141">You'll find more as you look at each of those three areas.</span></span> <span data-ttu-id="bc513-142">Вы обязательно найдете то, что вам нужно, если начнете с этих трех основных шагов.</span><span class="sxs-lookup"><span data-stu-id="bc513-142">Invariably, you will find what you need when you start with one of those three steps.</span></span>
 
 [<span data-ttu-id="bc513-143">Следующий раздел: "Выполнение деревьев выражений"</span><span class="sxs-lookup"><span data-stu-id="bc513-143">Next -- Executing Expression Trees</span></span>](expression-trees-execution.md)
