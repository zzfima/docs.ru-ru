---
title: Expression Trees
description: "Сведения о деревьях выражений в .NET Core, а также о том, как использовать их для представления кода в виде структур, которые можно проверять, изменять и выполнять."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: aceb4719-0d5a-4b19-b01f-b51063bcc54f
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3935906d9fca81a094999eefdd49ae4ed56990bf
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="expression-trees"></a><span data-ttu-id="d5f99-104">Expression Trees</span><span class="sxs-lookup"><span data-stu-id="d5f99-104">Expression Trees</span></span>

<span data-ttu-id="d5f99-105">Если вы использовали LINQ, то у вас есть опыт работы с полнофункциональной библиотекой, в которой типы `Func` являются частью набора API.</span><span class="sxs-lookup"><span data-stu-id="d5f99-105">If you have used LINQ, you have experience with a rich library where the `Func` types are part of the API set.</span></span> <span data-ttu-id="d5f99-106">(Если вы не работали с LINQ, то перед чтением этого раздела рекомендуем ознакомиться с учебниками по [LINQ](linq/index.md) и [лямбда-выражениям](lambda-expressions.md).) *Деревья выражений* обеспечивают более широкие возможности взаимодействия с аргументами, являющимися функциями.</span><span class="sxs-lookup"><span data-stu-id="d5f99-106">(If you are not familiar with LINQ, you probably want to read [the LINQ tutorial](linq/index.md) and the tutorial on [lambda expressions](lambda-expressions.md) before this one.) *Expression Trees* provide richer interaction with the arguments that are functions.</span></span>

<span data-ttu-id="d5f99-107">Аргументы функции применяются (как правило, с помощью лямбда-выражений) при создании запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="d5f99-107">You write function arguments, typically using Lambda Expressions, when you create LINQ queries.</span></span> <span data-ttu-id="d5f99-108">В типичном запросе LINQ аргументы функции преобразуются в делегат, создаваемый компилятором.</span><span class="sxs-lookup"><span data-stu-id="d5f99-108">In a typical LINQ query, those function arguments are transformed into a delegate the compiler creates.</span></span> 

<span data-ttu-id="d5f99-109">Если требуются более широкие возможности взаимодействия, необходимо использовать *деревья выражений*.</span><span class="sxs-lookup"><span data-stu-id="d5f99-109">When you want to have a richer interaction, you need to use *Expression Trees*.</span></span>
<span data-ttu-id="d5f99-110">Деревья выражений представляют код в виде структуры, которую можно анализировать, изменять или выполнять.</span><span class="sxs-lookup"><span data-stu-id="d5f99-110">Expression Trees represent code as a structure that you can examine, modify, or execute.</span></span> <span data-ttu-id="d5f99-111">Это дает возможность управлять кодом во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5f99-111">These tools give you the power to manipulate code during run time.</span></span> <span data-ttu-id="d5f99-112">Вы можете написать код, который анализирует выполняющиеся алгоритмы или добавляет новые возможности.</span><span class="sxs-lookup"><span data-stu-id="d5f99-112">You can write code that examines running algorithms, or injects new capabilities.</span></span> <span data-ttu-id="d5f99-113">В более сложных сценариях вы можете изменять выполняющиеся алгоритмы и даже преобразовывать выражения C# в иную форму для выполнения в другой среде.</span><span class="sxs-lookup"><span data-stu-id="d5f99-113">In more advanced scenarios, you can modify running algorithms, and even translate C# expressions into another form for execution in another environment.</span></span>

<span data-ttu-id="d5f99-114">Вероятно, вы уже писали код, в котором используются деревья выражений.</span><span class="sxs-lookup"><span data-stu-id="d5f99-114">You've likely already written code that uses Expression Trees.</span></span> <span data-ttu-id="d5f99-115">Интерфейсы API LINQ платформы Entity Framework принимают деревья выражений в качестве аргументов для модели выражений запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="d5f99-115">Entity Framework's LINQ APIs accept Expression Trees as the arguments for the LINQ Query Expression Pattern.</span></span>
<span data-ttu-id="d5f99-116">Это позволяет платформе [Entity Framework](http://docs.efproject.net/en/latest/) преобразовывать запросы, написанные на C#, в код SQL, который выполняется в ядре СУБД.</span><span class="sxs-lookup"><span data-stu-id="d5f99-116">That enables [Entity Framework](http://docs.efproject.net/en/latest/) to translate the query you wrote in C# into SQL that executes in the database engine.</span></span> <span data-ttu-id="d5f99-117">Другим примером является [Moq](https://github.com/Moq/moq) — популярная платформа прототипирования для .NET.</span><span class="sxs-lookup"><span data-stu-id="d5f99-117">Another example is [Moq](https://github.com/Moq/moq), which is a popular mocking framework for .NET.</span></span>

<span data-ttu-id="d5f99-118">В дальнейших разделах этого учебника описывается, что представляют собой деревья выражений, рассматриваются поддерживающие их классы платформы и демонстрируются способы работы с деревьями выражений.</span><span class="sxs-lookup"><span data-stu-id="d5f99-118">The remaining sections of this tutorial will explore what Expression Trees are, examine the framework classes that support expression trees, and show you how to work with expression trees.</span></span> <span data-ttu-id="d5f99-119">Вы узнаете, как считывать деревья выражений, как создавать их, а также как создавать модифицированные деревья выражений и выполнять код, представленный деревьями выражений.</span><span class="sxs-lookup"><span data-stu-id="d5f99-119">You'll learn how to read expression trees, how to create expression trees, how to create modified expression trees, and how to execute the code represented by expression trees.</span></span> <span data-ttu-id="d5f99-120">После ознакомления с учебником вы будете готовы к использованию этих структур для создания эффективных адаптивных алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="d5f99-120">After reading, you will be ready to use these structures to create rich adaptive algorithms.</span></span>

1. [<span data-ttu-id="d5f99-121">Описание деревьев выражений</span><span class="sxs-lookup"><span data-stu-id="d5f99-121">Expression Trees Explained</span></span>](expression-trees-explained.md)

    <span data-ttu-id="d5f99-122">Описание структуры и принципов использования *деревьев выражений*.</span><span class="sxs-lookup"><span data-stu-id="d5f99-122">Understand the structure and concepts behind *Expression Trees*.</span></span>
    
2. [<span data-ttu-id="d5f99-123">Типы платформ, поддерживающие деревья выражений</span><span class="sxs-lookup"><span data-stu-id="d5f99-123">Framework Types Supporting Expression Trees</span></span>](expression-classes.md)
    
    <span data-ttu-id="d5f99-124">Сведения о структурах и классах, которые служат для определения деревьев выражений и управления ими.</span><span class="sxs-lookup"><span data-stu-id="d5f99-124">Learn about the structures and classes that define and manipulate expression trees.</span></span>
    
3. [<span data-ttu-id="d5f99-125">Выполнение выражений</span><span class="sxs-lookup"><span data-stu-id="d5f99-125">Executing Expressions</span></span>](expression-trees-execution.md)

    <span data-ttu-id="d5f99-126">Сведения о том, как преобразовать дерево выражения, представленное как лямбда-выражение, в делегат и как выполнить полученный делегат.</span><span class="sxs-lookup"><span data-stu-id="d5f99-126">Learn how to convert an expression tree represented as a Lambda Expression into a delegate and execute the resulting delegate.</span></span>

4. [<span data-ttu-id="d5f99-127">Интерпретация выражений</span><span class="sxs-lookup"><span data-stu-id="d5f99-127">Interpreting Expressions</span></span>](expression-trees-interpreting.md)

    <span data-ttu-id="d5f99-128">Сведения об обходе и анализе *деревьев выражений* для получения представления о том, какой код они представляют.</span><span class="sxs-lookup"><span data-stu-id="d5f99-128">Learn how to traverse and examine *expression trees* to understand what code the expression tree represents.</span></span>

5. [<span data-ttu-id="d5f99-129">Построение выражений</span><span class="sxs-lookup"><span data-stu-id="d5f99-129">Building Expressions</span></span>](expression-trees-building.md)

    <span data-ttu-id="d5f99-130">Сведения о построении узлов для дерева выражения и сборке деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="d5f99-130">Learn how to construct the nodes for an expression tree and build expression trees.</span></span>

6. [<span data-ttu-id="d5f99-131">Преобразование выражений</span><span class="sxs-lookup"><span data-stu-id="d5f99-131">Translating Expressions</span></span>](expression-trees-translating.md)

    <span data-ttu-id="d5f99-132">Сведения о создании измененной копии дерева выражения или преобразовании дерева выражения в другой формат.</span><span class="sxs-lookup"><span data-stu-id="d5f99-132">Learn how to build a modified copy of an expression tree, or translate an expression tree into a different format.</span></span>

7. [<span data-ttu-id="d5f99-133">Заключение</span><span class="sxs-lookup"><span data-stu-id="d5f99-133">Summing up</span></span>](expression-trees-summary.md)

    <span data-ttu-id="d5f99-134">Сводные сведения о деревьях выражений.</span><span class="sxs-lookup"><span data-stu-id="d5f99-134">Review the information on expression trees.</span></span>
    

