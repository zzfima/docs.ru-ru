---
title: Вывод локального типа
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: f79ac70aecb5805a3a4a4fea8f7e7ccd3f8243fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351835"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="6b047-102">Вывод локального типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b047-102">Local Type Inference (Visual Basic)</span></span>

<span data-ttu-id="6b047-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span><span class="sxs-lookup"><span data-stu-id="6b047-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="6b047-104">The compiler infers the type of the variable from the type of the initialization expression.</span><span class="sxs-lookup"><span data-stu-id="6b047-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="6b047-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span><span class="sxs-lookup"><span data-stu-id="6b047-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="6b047-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span><span class="sxs-lookup"><span data-stu-id="6b047-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="6b047-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span><span class="sxs-lookup"><span data-stu-id="6b047-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>

> [!NOTE]
> <span data-ttu-id="6b047-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span><span class="sxs-lookup"><span data-stu-id="6b047-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>

<span data-ttu-id="6b047-109">Local type inference applies at procedure level.</span><span class="sxs-lookup"><span data-stu-id="6b047-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="6b047-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span><span class="sxs-lookup"><span data-stu-id="6b047-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="6b047-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span><span class="sxs-lookup"><span data-stu-id="6b047-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="6b047-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span><span class="sxs-lookup"><span data-stu-id="6b047-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>

## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="6b047-113">Type Inference vs. Late Binding</span><span class="sxs-lookup"><span data-stu-id="6b047-113">Type Inference vs. Late Binding</span></span>

<span data-ttu-id="6b047-114">Code that uses type inference resembles code that relies on late binding.</span><span class="sxs-lookup"><span data-stu-id="6b047-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="6b047-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span><span class="sxs-lookup"><span data-stu-id="6b047-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="6b047-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span><span class="sxs-lookup"><span data-stu-id="6b047-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="6b047-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span><span class="sxs-lookup"><span data-stu-id="6b047-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>

<span data-ttu-id="6b047-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span><span class="sxs-lookup"><span data-stu-id="6b047-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="6b047-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span><span class="sxs-lookup"><span data-stu-id="6b047-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="6b047-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span><span class="sxs-lookup"><span data-stu-id="6b047-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="6b047-121">Early binding is also preferred for performance.</span><span class="sxs-lookup"><span data-stu-id="6b047-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="6b047-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span><span class="sxs-lookup"><span data-stu-id="6b047-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>

## <a name="examples"></a><span data-ttu-id="6b047-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="6b047-123">Examples</span></span>

<span data-ttu-id="6b047-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span><span class="sxs-lookup"><span data-stu-id="6b047-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="6b047-125">The compiler uses the type of the assigned initial value as the type of the variable.</span><span class="sxs-lookup"><span data-stu-id="6b047-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="6b047-126">For example, each of the following lines of code declares a variable of type `String`.</span><span class="sxs-lookup"><span data-stu-id="6b047-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

<span data-ttu-id="6b047-127">The following code demonstrates two equivalent ways to create an array of integers.</span><span class="sxs-lookup"><span data-stu-id="6b047-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

<span data-ttu-id="6b047-128">It is convenient to use type inference to determine the type of a loop control variable.</span><span class="sxs-lookup"><span data-stu-id="6b047-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="6b047-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span><span class="sxs-lookup"><span data-stu-id="6b047-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

<span data-ttu-id="6b047-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span><span class="sxs-lookup"><span data-stu-id="6b047-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

<span data-ttu-id="6b047-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span><span class="sxs-lookup"><span data-stu-id="6b047-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="6b047-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span><span class="sxs-lookup"><span data-stu-id="6b047-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a><span data-ttu-id="6b047-133">Option Infer</span><span class="sxs-lookup"><span data-stu-id="6b047-133">Option Infer</span></span>

<span data-ttu-id="6b047-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span><span class="sxs-lookup"><span data-stu-id="6b047-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="6b047-135">To enable or to block the option, type one of the following statements at the start of the file.</span><span class="sxs-lookup"><span data-stu-id="6b047-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>

`Option Infer On`

`Option Infer Off`

<span data-ttu-id="6b047-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span><span class="sxs-lookup"><span data-stu-id="6b047-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span>

<span data-ttu-id="6b047-137">Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.</span><span class="sxs-lookup"><span data-stu-id="6b047-137">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="6b047-138">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6b047-138">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b047-139">См. также</span><span class="sxs-lookup"><span data-stu-id="6b047-139">See also</span></span>

- [<span data-ttu-id="6b047-140">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="6b047-140">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="6b047-141">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="6b047-141">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="6b047-142">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="6b047-142">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="6b047-143">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="6b047-143">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="6b047-144">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="6b047-144">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="6b047-145">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="6b047-145">-optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- <span data-ttu-id="6b047-146">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b047-146">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
