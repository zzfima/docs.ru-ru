---
title: Общие сведения о делегатах
description: Общие сведения о делегатах, обзор связанных с ними основных понятий и обсуждение целей разработки языка для делегатов.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 59b61d77-84e5-457b-8da5-fb5f24ca6ed6
ms.openlocfilehash: fd594f77c034533a1d5aee1d8279e9b727284311
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146233"
---
# <a name="introduction-to-delegates"></a><span data-ttu-id="768a2-103">Общие сведения о делегатах</span><span class="sxs-lookup"><span data-stu-id="768a2-103">Introduction to Delegates</span></span>

<span data-ttu-id="768a2-104">Делегаты предоставляют механизм *позднего связывания* в .NET.</span><span class="sxs-lookup"><span data-stu-id="768a2-104">Delegates provide a *late binding* mechanism in .NET.</span></span> <span data-ttu-id="768a2-105">Позднее связывание означает, что создается алгоритм, где вызывающий объект также предоставляет по крайней мере один метод, который реализует часть алгоритма.</span><span class="sxs-lookup"><span data-stu-id="768a2-105">Late Binding means that you create an algorithm where the caller also supplies at least one method that implements part of the algorithm.</span></span>

<span data-ttu-id="768a2-106">Например, рассмотрим сортировку списка звезд в астрономическом приложении.</span><span class="sxs-lookup"><span data-stu-id="768a2-106">For example, consider sorting a list of stars in an astronomy application.</span></span>
<span data-ttu-id="768a2-107">Можно отсортировать звезды по расстоянию от Земли, по величине или по воспринимаемой яркости.</span><span class="sxs-lookup"><span data-stu-id="768a2-107">You may choose to sort those stars by their distance from the earth, or the magnitude of the star, or their perceived brightness.</span></span>

<span data-ttu-id="768a2-108">Во всех этих случаях метод Sort() выполняет, по сути, одно и то же: упорядочивает элементы в списке на основе некоего сравнения.</span><span class="sxs-lookup"><span data-stu-id="768a2-108">In all those cases, the Sort() method does essentially the same thing: arranges the items in the list based on some comparison.</span></span> <span data-ttu-id="768a2-109">Для каждого порядка сортировки используется разный код, сравнивающий две звезды.</span><span class="sxs-lookup"><span data-stu-id="768a2-109">The code that compares two stars is different for each of the sort orderings.</span></span>

<span data-ttu-id="768a2-110">Такого рода решения использовались в программном обеспечении в течение полувека.</span><span class="sxs-lookup"><span data-stu-id="768a2-110">These kinds of solutions have been used in software for half a century.</span></span>
<span data-ttu-id="768a2-111">Концепция использования делегатов в языке C# обеспечивает первоклассную поддержку языка и безопасность типов.</span><span class="sxs-lookup"><span data-stu-id="768a2-111">The C# language delegate concept provides first class language support, and type safety around the concept.</span></span>

<span data-ttu-id="768a2-112">Как вы увидите далее в этой серии статей, код C#, создаваемый для подобных алгоритмов, является строго типизированным и использует язык и компилятор для соответствия типов аргументам и возвращаемым типам.</span><span class="sxs-lookup"><span data-stu-id="768a2-112">As you'll see later in this series, the C# code you write for algorithms like this is type safe, and leverages the language and the compiler to ensure that the types match for arguments and return types.</span></span>

## <a name="language-design-goals-for-delegates"></a><span data-ttu-id="768a2-113">Цели разработки языка для делегатов</span><span class="sxs-lookup"><span data-stu-id="768a2-113">Language Design Goals for Delegates</span></span>

<span data-ttu-id="768a2-114">Разработчики, использующие язык, определили несколько целей для функций, которые в итоге стали делегатами.</span><span class="sxs-lookup"><span data-stu-id="768a2-114">The language designers enumerated several goals for the feature that eventually became delegates.</span></span>

<span data-ttu-id="768a2-115">Группе разработчиков требовалась общая языковая конструкция, которую можно было бы использовать для любых алгоритмов позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="768a2-115">The team wanted a common language construct that could be used for any late binding algorithms.</span></span> <span data-ttu-id="768a2-116">Разработчикам удалось изучить одну концепцию и применить ее для решения многих самых разных проблем программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="768a2-116">That enables developers to learn one concept, and use that same concept across many different software problems.</span></span>

<span data-ttu-id="768a2-117">Во-вторых, команде нужна поддержка одиночных и многоадресных вызовов методов.</span><span class="sxs-lookup"><span data-stu-id="768a2-117">Second, the team wanted to support both single and multicast method calls.</span></span> <span data-ttu-id="768a2-118">(Многоадресные делегаты — это делегаты, которые объединяют в цепочку несколько вызовов методов.</span><span class="sxs-lookup"><span data-stu-id="768a2-118">(Multicast delegates are delegates that chain together multiple method calls.</span></span>
<span data-ttu-id="768a2-119">Вы увидите примеры [далее в этой серии](delegate-class.md).)</span><span class="sxs-lookup"><span data-stu-id="768a2-119">You'll see examples [later in this series](delegate-class.md).)</span></span>

<span data-ttu-id="768a2-120">Группа разработчиков хотела, чтобы делегаты поддерживали ту же безопасность типа, ожидаемую от всех конструкций C#.</span><span class="sxs-lookup"><span data-stu-id="768a2-120">The team wanted delegates to support the same type safety that developers expect from all C# constructs.</span></span>

<span data-ttu-id="768a2-121">И, наконец, группа пришла к выводу, что шаблон событий является определенным шаблоном, где использование делегатов (или любого алгоритма позднего связывания) очень эффективно.</span><span class="sxs-lookup"><span data-stu-id="768a2-121">Finally, the team recognized that an event pattern is one specific pattern where delegates, or any late binding algorithm, is very useful.</span></span> <span data-ttu-id="768a2-122">Группе разработчиков требовалось, чтобы код для делегатов служил основой для шаблона событий .NET.</span><span class="sxs-lookup"><span data-stu-id="768a2-122">The team wanted to ensure that the code for delegates could provide the basis for the .NET event pattern.</span></span>

<span data-ttu-id="768a2-123">Результатом всей этой работы стала поддержка делегатов и событий в C# и .NET.</span><span class="sxs-lookup"><span data-stu-id="768a2-123">The result of all that work was the delegate and event support in C# and .NET.</span></span> <span data-ttu-id="768a2-124">В оставшихся статьях в этом разделе будут рассматриваться возможности языка, поддержка библиотек и стандартные практики, которые применяются при работе с делегатами.</span><span class="sxs-lookup"><span data-stu-id="768a2-124">The remaining articles in this section will cover the language features, the library support, and the common idioms that are used when you work with delegates.</span></span>

<span data-ttu-id="768a2-125">Вы узнаете о ключевом слове `delegate` и коде, который он создает.</span><span class="sxs-lookup"><span data-stu-id="768a2-125">You'll learn about the `delegate` keyword and what code it generates.</span></span> <span data-ttu-id="768a2-126">Вы узнаете о функциях в классе `System.Delegate` и их использовании.</span><span class="sxs-lookup"><span data-stu-id="768a2-126">You'll learn about the features in the `System.Delegate` class, and how those features are used.</span></span> <span data-ttu-id="768a2-127">Вы научитесь создавать типобезопасные делегаты и ознакомитесь со способами создания методов, которые можно вызывать с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="768a2-127">You'll learn how to create type safe delegates, and how to create methods that can be invoked through delegates.</span></span> <span data-ttu-id="768a2-128">Вы также узнаете, как работать с делегатами и событиями с помощью лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="768a2-128">You'll also learn how to work with delegates and events by using Lambda expressions.</span></span> <span data-ttu-id="768a2-129">Вы увидите, каким образом делегаты становятся одними из стандартных блоков для LINQ.</span><span class="sxs-lookup"><span data-stu-id="768a2-129">You'll see where delegates become one of the building blocks for LINQ.</span></span> <span data-ttu-id="768a2-130">Вы узнаете, что делегаты являются основой для шаблона событий .NET, и определите их отличия.</span><span class="sxs-lookup"><span data-stu-id="768a2-130">You'll learn how delegates are the basis for the .NET event pattern, and how they are different.</span></span>

<span data-ttu-id="768a2-131">В целом вы получите представление о том, что делегаты являются неотъемлемой частью программирования в .NET и работы с API платформы.</span><span class="sxs-lookup"><span data-stu-id="768a2-131">Overall, you'll see how delegates are an integral part of programming in .NET and working with the framework APIs.</span></span>

<span data-ttu-id="768a2-132">Приступим.</span><span class="sxs-lookup"><span data-stu-id="768a2-132">Let's get started.</span></span>

[<span data-ttu-id="768a2-133">Вперед</span><span class="sxs-lookup"><span data-stu-id="768a2-133">Next</span></span>](delegate-class.md)
