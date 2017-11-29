---
title: "Операторы в C#. Краткий обзор языка C#"
description: "Все действия в программе C# определяются с помощью операторов"
keywords: ".NET, c#, операторы, синтаксис"
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.openlocfilehash: 99ec2489daf89926da9b8c4e148965412826a8a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="statements"></a><span data-ttu-id="ef3ed-104">Операторы</span><span class="sxs-lookup"><span data-stu-id="ef3ed-104">Statements</span></span>

<span data-ttu-id="ef3ed-105">Действия программы выражаются с помощью *операторов*.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-105">The actions of a program are expressed using *statements*.</span></span> <span data-ttu-id="ef3ed-106">C# поддерживает несколько типов операторов, некоторые из которых определяются как внедренные операторы.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-106">C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.</span></span>

<span data-ttu-id="ef3ed-107">С помощью *блоков* можно использовать несколько операторов в таких контекстах, где ожидается только один оператор.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-107">A *block* permits multiple statements to be written in contexts where a single statement is allowed.</span></span> <span data-ttu-id="ef3ed-108">Блок состоит из списка инструкций, заключенных между разделителями `{` и `}`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-108">A block consists of a list of statements written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="ef3ed-109">*Операторы объявления* используются для объявления локальных переменных и констант.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-109">*Declaration statements* are used to declare local variables and constants.</span></span>

<span data-ttu-id="ef3ed-110">*Операторы выражений* позволяют вычислять выражения.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-110">*Expression statements* are used to evaluate expressions.</span></span> <span data-ttu-id="ef3ed-111">В качестве оператора можно использовать такие выражения, как вызовы методов, выделение объектов с помощью оператора `new`, назначения с помощью `=` и составных операторов присваивания, операторы `++` и `--` для приращения и уменьшения, а также выражения `await`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-111">Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and `await` expressions.</span></span>

<span data-ttu-id="ef3ed-112">*Операторы выбора* используются для выбора одного оператора из нескольких возможных вариантов в зависимости от значения какого-либо выражения.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-112">*Selection statements* are used to select one of a number of possible statements for execution based on the value of some expression.</span></span> <span data-ttu-id="ef3ed-113">К этой группе относятся операторы `if` и `switch`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-113">In this group are the `if` and `switch` statements.</span></span>

<span data-ttu-id="ef3ed-114">*Операторы итерации* используются для многократного выполнения внедренного оператора.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-114">*Iteration statements* are used to execute repeatedly an embedded statement.</span></span> <span data-ttu-id="ef3ed-115">К этой группе относятся операторы `while`, `do`, `for` и `foreach`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-115">In this group are the `while`, `do`, `for`, and `foreach` statements.</span></span>

<span data-ttu-id="ef3ed-116">*Операторы перехода* используются для передачи управления.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-116">*Jump statements* are used to transfer control.</span></span> <span data-ttu-id="ef3ed-117">К этой группе относятся операторы `break`, `continue`, `goto`, `throw`, `return` и `yield`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-117">In this group are the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.</span></span>

<span data-ttu-id="ef3ed-118">Операторы `try`...`catch` позволяют перехватывать исключения, создаваемые при выполнении блока кода, а оператор `try`...`finally` используется для указания кода завершения, который выполняется всегда, независимо от появления исключений.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-118">The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.</span></span>

<span data-ttu-id="ef3ed-119">Операторы `checked` и `unchecked` операторы позволяют управлять контекстом проверки переполнения для целочисленных арифметических операций и преобразований.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-119">The `checked` and `unchecked` statements are used to control the overflow-checking context for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="ef3ed-120">Оператор `lock` позволяет создать взаимоисключающую блокировку заданного объекта перед выполнением определенных операторов, а затем снять блокировку.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-120">The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.</span></span>

<span data-ttu-id="ef3ed-121">Оператор `using` используется для получения ресурса перед определенным оператором, и для удаления ресурса после его завершения.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-121">The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.</span></span>

<span data-ttu-id="ef3ed-122">Ниже перечислены виды операторов, которые вы можете использовать, и представлены примеры для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-122">The following lists the kinds of statements that can be used, and provides an example for each.</span></span>

* <span data-ttu-id="ef3ed-123">Объявление локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-123">Local variable declaration:</span></span>

 [!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]

* <span data-ttu-id="ef3ed-124">Объявление локальной константы.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-124">Local constant declaration:</span></span>

 [!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]

* <span data-ttu-id="ef3ed-125">Оператор выражения.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-125">Expression statement:</span></span>

 [!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]

* <span data-ttu-id="ef3ed-126">Оператор `if`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-126">`if` statement:</span></span>

 [!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]

* <span data-ttu-id="ef3ed-127">Оператор `switch`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-127">`switch` statement:</span></span>

 [!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]

* <span data-ttu-id="ef3ed-128">Оператор `while`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-128">`while` statement:</span></span>

 [!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]

* <span data-ttu-id="ef3ed-129">Оператор `do`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-129">`do` statement:</span></span>

 [!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]

* <span data-ttu-id="ef3ed-130">Оператор `for`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-130">`for` statement:</span></span>

 [!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]

* <span data-ttu-id="ef3ed-131">Оператор `foreach`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-131">`foreach` statement:</span></span>

 [!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]

* <span data-ttu-id="ef3ed-132">Оператор `break`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-132">`break` statement:</span></span>

 [!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]

* <span data-ttu-id="ef3ed-133">Оператор `continue`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-133">`continue` statement:</span></span>

 [!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]

* <span data-ttu-id="ef3ed-134">Оператор `goto`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-134">`goto` statement:</span></span>

 [!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]

* <span data-ttu-id="ef3ed-135">Оператор `return`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-135">`return` statement:</span></span>

 [!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]

* <span data-ttu-id="ef3ed-136">Оператор `yield`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-136">`yield` statement:</span></span>

 [!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]

* <span data-ttu-id="ef3ed-137">Операторы `throw` и операторы `try`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-137">`throw` statements and `try` statements:</span></span>

 [!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]

* <span data-ttu-id="ef3ed-138">Операторы `checked` и `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-138">`checked` and `unchecked` statements:</span></span>

 [!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]

* <span data-ttu-id="ef3ed-139">Оператор `lock`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-139">`lock` statement:</span></span>

 [!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]

* <span data-ttu-id="ef3ed-140">Оператор `using`.</span><span class="sxs-lookup"><span data-stu-id="ef3ed-140">`using` statement:</span></span>

 [!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]

>[!div class="step-by-step"]
<span data-ttu-id="ef3ed-141">[Назад](expressions.md)
[Вперед](classes-and-objects.md)</span><span class="sxs-lookup"><span data-stu-id="ef3ed-141">[Previous](expressions.md)
[Next](classes-and-objects.md)</span></span>
