---
title: "Вывод локального типа (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- local type inference
- vb.TypeInfer
dev_langs:
- VB
helpviewer_keywords:
- Option Infer statement
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: af8de63eb00db917771600f0fca8f200ec451afe
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="2d3d0-102">Вывод локального типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d3d0-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="2d3d0-103">Компилятор Visual Basic использует *вывод типа* для определения типов данных локальных переменных, объявленных без `As` предложения.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="2d3d0-104">Компилятор выводит тип переменной из типа выражения инициализации.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="2d3d0-105">Это позволяет объявлять переменные без явного указания типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="2d3d0-106">В результате объявлений оба `num1` и `num2` являются строго типизированными как целые числа.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 <span data-ttu-id="2d3d0-107">[!code-vb[VbVbalrTypeInference&#1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2d3d0-107">[!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d3d0-108">Если вы не хотите `num2` в предыдущем примере была введена как `Integer`, можно указать другой тип с помощью такого объявления, как `Dim num3 As Object = 3` или `Dim num4 As Double = 3`.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-108">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  
  
 <span data-ttu-id="2d3d0-109">Вывод локального типа происходит на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="2d3d0-110">Он не может использоваться для объявления переменных на уровне модуля (в рамках класса, структуры, модуля или интерфейса, но не внутри процедуры или блока).</span><span class="sxs-lookup"><span data-stu-id="2d3d0-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="2d3d0-111">Если `num2` в предыдущем примере была полем класса вместо локальной переменной в процедуре, объявление привело бы к ошибке с `Option Strict` и было бы классифицировать `num2` как `Object` с `Option Strict` off.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="2d3d0-112">Аналогично, вывод локального типа не применяется к процедуре переменные, объявленные как `Static`.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="2d3d0-113">Определение типа или. Позднее связывание</span><span class="sxs-lookup"><span data-stu-id="2d3d0-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="2d3d0-114">Код, который использует выведение типа напоминает код, основанный на позднем связывании.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="2d3d0-115">Тем не менее, выведение типа строго типизирует переменные вместо оставлять их в качестве `Object`.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="2d3d0-116">Компилятор использует инициализатор переменной для определения типа переменной во время компиляции для создания кода с ранней привязкой.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="2d3d0-117">В предыдущем примере `num2`, например `num1`, типизируется как `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="2d3d0-118">Поведение переменных с ранней привязкой отличается от переменных с поздней привязкой, для которых тип известен только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="2d3d0-119">Знание типа заранее позволяет компилятору выявить проблемы до выполнения, точно выделить память и выполнять другие виды оптимизации.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="2d3d0-120">Раннее связывание также позволяет Visual Basic интегрированной среде разработки (IDE) предоставлять справку IntelliSense об элементах объекта.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="2d3d0-121">Раннее связывание также является предпочтительным для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="2d3d0-122">Это потому, что все данные, хранящиеся в переменной с поздней привязкой должны быть упакованы как тип `Object`, и доступ к членам типа во время выполнения делает программу медленнее.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2d3d0-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="2d3d0-123">Examples</span></span>  
 <span data-ttu-id="2d3d0-124">Вывод типа происходит, когда локальная переменная объявлена без `As` предложения и инициализации.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="2d3d0-125">Компилятор использует тип присвоенного начального значения как тип переменной.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="2d3d0-126">Например, каждый следующий код объявляет переменную типа `String`.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 <span data-ttu-id="2d3d0-127">[!code-vb[VbVbalrTypeInference&#2;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2d3d0-127">[!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]</span></span>  
  
 <span data-ttu-id="2d3d0-128">В следующем коде показано два эквивалентных способа создания массива целых чисел.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-128">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 <span data-ttu-id="2d3d0-129">[!code-vb[VbVbalrTypeInference&#3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="2d3d0-129">[!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]</span></span>  
  
 <span data-ttu-id="2d3d0-130">Удобно использовать вывод типа для определения типа переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-130">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="2d3d0-131">В следующем коде компилятор выводит, что `number` — `Integer` из-за `someNumbers2` из предыдущего примера является массивом целых чисел.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-131">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 <span data-ttu-id="2d3d0-132">[!code-vb[VbVbalrTypeInference&#4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="2d3d0-132">[!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]</span></span>  
  
 <span data-ttu-id="2d3d0-133">Вывод локального типа могут использоваться в `Using` инструкции, чтобы установить тип имени ресурса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-133">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 <span data-ttu-id="2d3d0-134">[!code-vb[VbVbalrTypeInference&#7;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="2d3d0-134">[!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]</span></span>  
  
 <span data-ttu-id="2d3d0-135">Тип переменной также может выводиться из возвращаемых значений функции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-135">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="2d3d0-136">Оба `pList1` и `pList2` являются массивами процессов, так как `Process.GetProcesses` возвращает массив процессов.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-136">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 <span data-ttu-id="2d3d0-137">[!code-vb[VbVbalrTypeInference&#5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="2d3d0-137">[!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]</span></span>  
  
## <a name="option-infer"></a><span data-ttu-id="2d3d0-138">Option Infer</span><span class="sxs-lookup"><span data-stu-id="2d3d0-138">Option Infer</span></span>  
 <span data-ttu-id="2d3d0-139">`Option Infer`позволяет указать, разрешено ли вывод локального типа в конкретном файле.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-139">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="2d3d0-140">Чтобы включить или заблокировать параметр, введите одну из следующих инструкций в начале файла.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-140">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="2d3d0-141">Если не указать значение для `Option Infer` в коде, компилятор по умолчанию является `Option Infer On`.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-141">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="2d3d0-142">В проектах, обновленных из [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] или более ранних версиях компилятора по умолчанию — `Option Infer Off`.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-142">For projects upgraded from [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="2d3d0-143">Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-143">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="2d3d0-144">Дополнительные сведения см. в разделе [Option Infer оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [компиляция, конструктор проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2d3d0-144">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="2d3d0-145">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2d3d0-145">Restrictions</span></span>  
 <span data-ttu-id="2d3d0-146">Определение типа может использоваться только для нестатических локальных переменных; он не может использоваться для определения типа полей класса, свойств или функций.</span><span class="sxs-lookup"><span data-stu-id="2d3d0-146">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3d0-147">См. также</span><span class="sxs-lookup"><span data-stu-id="2d3d0-147">See Also</span></span>  
 <span data-ttu-id="2d3d0-148">[Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="2d3d0-148">[Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="2d3d0-149"> [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span><span class="sxs-lookup"><span data-stu-id="2d3d0-149"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span></span>  
<span data-ttu-id="2d3d0-150"> [Для каждого... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2d3d0-150"> [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="2d3d0-151"> [Для... Следующий оператор](../../../../visual-basic/language-reference/statements/for-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2d3d0-151"> [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md) </span></span>  
<span data-ttu-id="2d3d0-152"> [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2d3d0-152"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="2d3d0-153"> [/ optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="2d3d0-153"> [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="2d3d0-154"> [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="2d3d0-154"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
