---
title: "Сводный обзор деревьев выражений"
description: "Общие сведения о том, как можно использовать деревья выражений для создания динамических программ, которые интерпретируют код как данные и создают новые функции на основе этого кода."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.openlocfilehash: d2754493c782c2550a8b0bd0de274cb8100c78af
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="expression-trees-summary"></a><span data-ttu-id="0cdfd-104">Сводный обзор деревьев выражений</span><span class="sxs-lookup"><span data-stu-id="0cdfd-104">Expression Trees Summary</span></span>

[<span data-ttu-id="0cdfd-105">Предыдущий раздел — "Преобразование выражений"</span><span class="sxs-lookup"><span data-stu-id="0cdfd-105">Previous -- Translating Expressions</span></span>](expression-trees-translating.md)

<span data-ttu-id="0cdfd-106">В этой серии мы продемонстрировали, как можно использовать *деревья выражений* для создания динамических программ, которые интерпретируют код как данные и создают новые функции на основе этого кода.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-106">In this series, you've seen how you can use *expression trees* to create dynamic programs that interpret code as data and build new functionality based on that code.</span></span>

<span data-ttu-id="0cdfd-107">Вы можете изучить деревья выражений, чтобы понять суть алгоритма.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-107">You can examine expression trees to understand the intent of an algorithm.</span></span> <span data-ttu-id="0cdfd-108">Но код можно не только просматривать.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-108">You can not only examine that code.</span></span> <span data-ttu-id="0cdfd-109">Вы можете создавать новые деревья выражений, представляющие измененные версии исходного кода.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-109">You can build new expression trees that represent modified versions of the original code.</span></span>

<span data-ttu-id="0cdfd-110">Кроме того, деревья выражений можно использовать для анализа алгоритма и его преобразования в другой язык или среду.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-110">You can also use expression trees to look at an algorithm, and translate that algorithm into another language or environment.</span></span> 

## <a name="limitations"></a><span data-ttu-id="0cdfd-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0cdfd-111">Limitations</span></span>

<span data-ttu-id="0cdfd-112">Существуют некоторые новые элементы языка C#, которые не подходят для преобразования в деревья выражений.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-112">There are some newer C# language elements that don't translate well into expression trees.</span></span> <span data-ttu-id="0cdfd-113">Деревья выражений не могут содержать выражения `await` или лямбда-выражения `async`.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-113">Expression trees cannot contain `await` expressions, or `async` lambda expressions.</span></span> <span data-ttu-id="0cdfd-114">Многие из функций, добавленных в версии C# 6, не отображаются точно так, как они написаны, в деревьях выражений.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-114">Many of the features added in the C# 6 release don't appear exactly as written in expression trees.</span></span> <span data-ttu-id="0cdfd-115">Новые функции будут предоставляться в деревьях выражений в эквивалентном синтаксисе прежних версий.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-115">Instead, newer features will be exposed in expressions trees in the equivalent, earlier syntax.</span></span> <span data-ttu-id="0cdfd-116">Однако это не так ограничивает ваши возможности, как может показаться.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-116">This may not be as much of a limitation as you might think.</span></span> <span data-ttu-id="0cdfd-117">На самом деле это означает, что код, который интерпретирует деревья выражений, сможет успешно обрабатывать новые возможности языка, которые будут добавлены в будущем.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-117">In fact, it means that your code that interprets expression trees will likely still work the same when new language features are introduced.</span></span>

<span data-ttu-id="0cdfd-118">Даже с этими ограничениями деревья выражений позволяют создавать динамические алгоритмы, основанные на интерпретации и изменении кода, представленного в виде структуры данных.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-118">Even with these limitations, expression trees do enable you to create dynamic algorithms that rely on interpreting and modifying code that is represented as a data structure.</span></span> <span data-ttu-id="0cdfd-119">Это очень эффективный инструмент и один из компонентов экосистемы .NET, которая обеспечивает преимущества широкого набора библиотек, таких как Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="0cdfd-119">It's a powerful tool, and it's one of the features of the .NET ecosystem that enables rich libraries such as Entity Framework to accomplish what they do.</span></span>

