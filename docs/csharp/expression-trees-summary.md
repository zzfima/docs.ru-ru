---
title: Сводный обзор деревьев выражений
description: Общие сведения о том, как можно использовать деревья выражений для создания динамических программ, которые интерпретируют код как данные и создают новые функции на основе этого кода.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: eb687ebd-1149-4453-9fc1-12a084495a66
ms.openlocfilehash: 43715c94b70f1cd7f758cde91ae7c8d1b2f70f9f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036756"
---
# <a name="expression-trees-summary"></a><span data-ttu-id="719a5-103">Сводный обзор деревьев выражений</span><span class="sxs-lookup"><span data-stu-id="719a5-103">Expression Trees Summary</span></span>

[<span data-ttu-id="719a5-104">Предыдущий раздел — "Преобразование выражений"</span><span class="sxs-lookup"><span data-stu-id="719a5-104">Previous -- Translating Expressions</span></span>](expression-trees-translating.md)

<span data-ttu-id="719a5-105">В этой серии мы продемонстрировали, как можно использовать *деревья выражений* для создания динамических программ, которые интерпретируют код как данные и создают новые функции на основе этого кода.</span><span class="sxs-lookup"><span data-stu-id="719a5-105">In this series, you've seen how you can use *expression trees* to create dynamic programs that interpret code as data and build new functionality based on that code.</span></span>

<span data-ttu-id="719a5-106">Вы можете изучить деревья выражений, чтобы понять суть алгоритма.</span><span class="sxs-lookup"><span data-stu-id="719a5-106">You can examine expression trees to understand the intent of an algorithm.</span></span> <span data-ttu-id="719a5-107">Но код можно не только просматривать.</span><span class="sxs-lookup"><span data-stu-id="719a5-107">You can not only examine that code.</span></span> <span data-ttu-id="719a5-108">Вы можете создавать новые деревья выражений, представляющие измененные версии исходного кода.</span><span class="sxs-lookup"><span data-stu-id="719a5-108">You can build new expression trees that represent modified versions of the original code.</span></span>

<span data-ttu-id="719a5-109">Кроме того, деревья выражений можно использовать для анализа алгоритма и его преобразования в другой язык или среду.</span><span class="sxs-lookup"><span data-stu-id="719a5-109">You can also use expression trees to look at an algorithm, and translate that algorithm into another language or environment.</span></span> 

## <a name="limitations"></a><span data-ttu-id="719a5-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="719a5-110">Limitations</span></span>

<span data-ttu-id="719a5-111">Существуют некоторые новые элементы языка C#, которые не подходят для преобразования в деревья выражений.</span><span class="sxs-lookup"><span data-stu-id="719a5-111">There are some newer C# language elements that don't translate well into expression trees.</span></span> <span data-ttu-id="719a5-112">Деревья выражений не могут содержать выражения `await` или лямбда-выражения `async`.</span><span class="sxs-lookup"><span data-stu-id="719a5-112">Expression trees cannot contain `await` expressions, or `async` lambda expressions.</span></span> <span data-ttu-id="719a5-113">Многие из функций, добавленных в версии C# 6, не отображаются точно так, как они написаны, в деревьях выражений.</span><span class="sxs-lookup"><span data-stu-id="719a5-113">Many of the features added in the C# 6 release don't appear exactly as written in expression trees.</span></span> <span data-ttu-id="719a5-114">Новые функции будут предоставляться в деревьях выражений в эквивалентном синтаксисе прежних версий.</span><span class="sxs-lookup"><span data-stu-id="719a5-114">Instead, newer features will be exposed in expressions trees in the equivalent, earlier syntax.</span></span> <span data-ttu-id="719a5-115">Однако это не так ограничивает ваши возможности, как может показаться.</span><span class="sxs-lookup"><span data-stu-id="719a5-115">This may not be as much of a limitation as you might think.</span></span> <span data-ttu-id="719a5-116">На самом деле это означает, что код, который интерпретирует деревья выражений, сможет успешно обрабатывать новые возможности языка, которые будут добавлены в будущем.</span><span class="sxs-lookup"><span data-stu-id="719a5-116">In fact, it means that your code that interprets expression trees will likely still work the same when new language features are introduced.</span></span>

<span data-ttu-id="719a5-117">Даже с этими ограничениями деревья выражений позволяют создавать динамические алгоритмы, основанные на интерпретации и изменении кода, представленного в виде структуры данных.</span><span class="sxs-lookup"><span data-stu-id="719a5-117">Even with these limitations, expression trees do enable you to create dynamic algorithms that rely on interpreting and modifying code that is represented as a data structure.</span></span> <span data-ttu-id="719a5-118">Это очень эффективный инструмент и один из компонентов экосистемы .NET, которая обеспечивает преимущества широкого набора библиотек, таких как Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="719a5-118">It's a powerful tool, and it's one of the features of the .NET ecosystem that enables rich libraries such as Entity Framework to accomplish what they do.</span></span>
