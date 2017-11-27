---
title: "Вывод локального типа (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "43"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d753d1fbdc60f70dcf0513d809f28a112243c111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="9cb69-102">Вывод локального типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cb69-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="9cb69-103">Компилятор Visual Basic использует *вывод типа* для определения типов данных локальных переменных, объявленных без `As` предложения.</span><span class="sxs-lookup"><span data-stu-id="9cb69-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="9cb69-104">Компилятор выводит тип переменной из типа выражения инициализации.</span><span class="sxs-lookup"><span data-stu-id="9cb69-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="9cb69-105">Это позволяет объявлять переменные без явного указания типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9cb69-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="9cb69-106">В результате объявлений оба `num1` и `num2` являются строго типизированными как целые числа.</span><span class="sxs-lookup"><span data-stu-id="9cb69-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
 
> [!NOTE]
>  <span data-ttu-id="9cb69-107">Если вы не хотите `num2` в предыдущем примере была введена как `Integer`, можно указать другой тип с помощью объявления, такие как `Dim num3 As Object = 3` или `Dim num4 As Double = 3`.</span><span class="sxs-lookup"><span data-stu-id="9cb69-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  

> [!NOTE]
>  <span data-ttu-id="9cb69-108">Определение типа может использоваться только для нестатических локальных переменных; он не может использоваться для определения типа полей класса, свойства или функции.</span><span class="sxs-lookup"><span data-stu-id="9cb69-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>
 
 <span data-ttu-id="9cb69-109">Вывод локального типа происходит на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="9cb69-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="9cb69-110">Он не может использоваться для объявления переменных на уровне модуля (в пределах класса, структуры, модуля или интерфейса, но не внутри процедуры или блока).</span><span class="sxs-lookup"><span data-stu-id="9cb69-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="9cb69-111">Если `num2` в предыдущем примере были полем класса, а не локальную переменную в процедуре, объявление привело бы к ошибке с `Option Strict` и было бы классифицировать `num2` как `Object` с `Option Strict` off.</span><span class="sxs-lookup"><span data-stu-id="9cb69-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="9cb69-112">Аналогичным образом, вывод локального типа не применяется к процедуре уровня переменным, объявленным как `Static`.</span><span class="sxs-lookup"><span data-stu-id="9cb69-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="9cb69-113">Определение типа или. Позднее связывание</span><span class="sxs-lookup"><span data-stu-id="9cb69-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="9cb69-114">Код, который использует выведение типа напоминает код, основанный на позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="9cb69-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="9cb69-115">Тем не менее, выведение типа строго типизирует переменной не оставляйте его как `Object`.</span><span class="sxs-lookup"><span data-stu-id="9cb69-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="9cb69-116">Компилятор использует инициализатор переменной для определения типа переменной во время компиляции для создания кода с ранней привязкой.</span><span class="sxs-lookup"><span data-stu-id="9cb69-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="9cb69-117">В предыдущем примере `num2`, таких как `num1`, типизируется как `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9cb69-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="9cb69-118">Переменные с ранней привязкой поведение отличается от переменных позднего связывания, для которых тип известен только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9cb69-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="9cb69-119">Знание типа заранее позволяет компилятору выявить проблемы до выполнения, точно выделить память и выполнять другие виды оптимизации.</span><span class="sxs-lookup"><span data-stu-id="9cb69-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="9cb69-120">Раннее связывание также позволяет Visual Basic интегрированной среде разработки (IDE) для предоставления IntelliSense справки о членах класса объекта.</span><span class="sxs-lookup"><span data-stu-id="9cb69-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="9cb69-121">Раннее связывание также является предпочтительным для производительности.</span><span class="sxs-lookup"><span data-stu-id="9cb69-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="9cb69-122">Это, поскольку все данные, хранящиеся в переменной с поздним связыванием должны быть упакованы как тип `Object`, и доступ к членам типа во время выполнения делает программу медленнее.</span><span class="sxs-lookup"><span data-stu-id="9cb69-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9cb69-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="9cb69-123">Examples</span></span>  
 <span data-ttu-id="9cb69-124">Вывод типа происходит, когда локальная переменная объявлена без `As` предложения и инициализации.</span><span class="sxs-lookup"><span data-stu-id="9cb69-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="9cb69-125">Компилятор использует тип присвоенного начального значения в качестве типа переменной.</span><span class="sxs-lookup"><span data-stu-id="9cb69-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="9cb69-126">Например, все следующие строки кода объявляет переменную типа `String`.</span><span class="sxs-lookup"><span data-stu-id="9cb69-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 <span data-ttu-id="9cb69-127">В следующем коде показано два эквивалентных способа создания массива целых чисел.</span><span class="sxs-lookup"><span data-stu-id="9cb69-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 <span data-ttu-id="9cb69-128">Удобно использовать определение типа для определения типа переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="9cb69-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="9cb69-129">В следующем коде, компилятор выводит, `number` — `Integer` из-за `someNumbers2` из предыдущего примера является массивом целых чисел.</span><span class="sxs-lookup"><span data-stu-id="9cb69-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 <span data-ttu-id="9cb69-130">Вывод локального типа могут использоваться в `Using` инструкции, чтобы установить тип имени ресурса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9cb69-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 <span data-ttu-id="9cb69-131">Тип переменной можно также выведены из возвращаемого значения функции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9cb69-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="9cb69-132">Оба `pList1` и `pList2` представляют собой массивы процессов, так как `Process.GetProcesses` возвращает массив процессов.</span><span class="sxs-lookup"><span data-stu-id="9cb69-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## <a name="option-infer"></a><span data-ttu-id="9cb69-133">Option Infer</span><span class="sxs-lookup"><span data-stu-id="9cb69-133">Option Infer</span></span>  
 <span data-ttu-id="9cb69-134">`Option Infer`позволяет указать, разрешено ли вывод локального типа в файле.</span><span class="sxs-lookup"><span data-stu-id="9cb69-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="9cb69-135">Чтобы разрешить или заблокировать параметр, введите одну из следующих инструкций в начале файла.</span><span class="sxs-lookup"><span data-stu-id="9cb69-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="9cb69-136">Если не указать значение для `Option Infer` в коде, компилятор по умолчанию является `Option Infer On`.</span><span class="sxs-lookup"><span data-stu-id="9cb69-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="9cb69-137">В проектах, обновленных из [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] или более ранней версии, компилятор по умолчанию, `Option Infer Off`.</span><span class="sxs-lookup"><span data-stu-id="9cb69-137">For projects upgraded from [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="9cb69-138">Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.</span><span class="sxs-lookup"><span data-stu-id="9cb69-138">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="9cb69-139">Дополнительные сведения см. в разделе [Option Infer-оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9cb69-139">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb69-140">См. также</span><span class="sxs-lookup"><span data-stu-id="9cb69-140">See Also</span></span>  
 [<span data-ttu-id="9cb69-141">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="9cb69-141">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="9cb69-142">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="9cb69-142">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [<span data-ttu-id="9cb69-143">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="9cb69-143">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="9cb69-144">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="9cb69-144">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="9cb69-145">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="9cb69-145">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="9cb69-146">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="9cb69-146">/optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 <span data-ttu-id="9cb69-147">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cb69-147">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
