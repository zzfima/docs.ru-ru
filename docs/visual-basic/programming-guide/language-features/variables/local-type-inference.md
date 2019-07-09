---
title: Вывод локального типа (Visual Basic)
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
ms.openlocfilehash: 786466cb0b94a96e629a1f173388ed7d40be7256
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661908"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="afa78-102">Вывод локального типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afa78-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="afa78-103">Компилятор Visual Basic использует *вывод типа* для определения типов данных локальных переменных, объявленных без `As` предложение.</span><span class="sxs-lookup"><span data-stu-id="afa78-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="afa78-104">Компилятор выводит тип переменной из типа выражения инициализации.</span><span class="sxs-lookup"><span data-stu-id="afa78-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="afa78-105">Это позволяет объявлять переменные без явного указания типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="afa78-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="afa78-106">В результате объявлений оба `num1` и `num2` являются строго типизированными как целые числа.</span><span class="sxs-lookup"><span data-stu-id="afa78-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
 
> [!NOTE]
>  <span data-ttu-id="afa78-107">Если вы не хотите `num2` в предыдущем примере была введена как `Integer`, можно указать другой тип, используя объявление, подобное `Dim num3 As Object = 3` или `Dim num4 As Double = 3`.</span><span class="sxs-lookup"><span data-stu-id="afa78-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  

> [!NOTE]
>  <span data-ttu-id="afa78-108">Определение типа может использоваться только для нестатических локальных переменных; он не может использоваться для определения типа поля класса, свойства или функции.</span><span class="sxs-lookup"><span data-stu-id="afa78-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>
 
 <span data-ttu-id="afa78-109">Вывод локального типа применяется на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="afa78-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="afa78-110">Он не может использоваться для объявления переменных на уровне модуля (в пределах класса, структуры, модуля или интерфейса, но не внутри процедуры или блока).</span><span class="sxs-lookup"><span data-stu-id="afa78-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="afa78-111">Если `num2` в предыдущем примере были полем класса, а не локальную переменную в процедуре, объявление приведет к ошибке с `Option Strict` и было бы классифицировать `num2` как `Object` с `Option Strict` off.</span><span class="sxs-lookup"><span data-stu-id="afa78-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="afa78-112">Аналогичным образом, вывод локального типа не применяется к процедуре уровня переменные, объявленные как `Static`.</span><span class="sxs-lookup"><span data-stu-id="afa78-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="afa78-113">Определение типа или. Позднее связывание</span><span class="sxs-lookup"><span data-stu-id="afa78-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="afa78-114">Код, который использует выведение типа напоминает код, который полагается на динамическое связывание.</span><span class="sxs-lookup"><span data-stu-id="afa78-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="afa78-115">Тем не менее, выведение типа строго типизирует переменной не оставляйте его как `Object`.</span><span class="sxs-lookup"><span data-stu-id="afa78-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="afa78-116">Компилятор использует инициализатор переменной для определения типа переменной во время компиляции для создания кода с ранним связыванием.</span><span class="sxs-lookup"><span data-stu-id="afa78-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="afa78-117">В предыдущем примере `num2`, например `num1`, типизируется как `Integer`.</span><span class="sxs-lookup"><span data-stu-id="afa78-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="afa78-118">Поведение переменных с ранним связыванием отличается от переменных с поздним связыванием, для которых тип известен только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="afa78-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="afa78-119">Знание типа заранее позволяет компилятору определить проблемы до выполнения, точно выделить память и выполнять другие виды оптимизации.</span><span class="sxs-lookup"><span data-stu-id="afa78-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="afa78-120">Раннее связывание позволяет Visual Basic интегрированной среде разработки (IDE) для предоставления IntelliSense справки о членах класса объекта.</span><span class="sxs-lookup"><span data-stu-id="afa78-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="afa78-121">Раннее связывание также является предпочтительным для производительности.</span><span class="sxs-lookup"><span data-stu-id="afa78-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="afa78-122">Это обусловлено тем, все данные, хранящиеся в переменной с поздним связыванием, которые должны быть упакованы как тип `Object`, и доступ к членам типа во время выполнения делает программу медленнее.</span><span class="sxs-lookup"><span data-stu-id="afa78-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="afa78-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="afa78-123">Examples</span></span>  
 <span data-ttu-id="afa78-124">Вывод типа происходит, когда локальная переменная объявлена без `As` предложение и инициализируется.</span><span class="sxs-lookup"><span data-stu-id="afa78-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="afa78-125">Компилятор использует тип присвоенного начального значения как тип переменной.</span><span class="sxs-lookup"><span data-stu-id="afa78-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="afa78-126">Например, каждый из следующих строк кода объявляется переменная типа `String`.</span><span class="sxs-lookup"><span data-stu-id="afa78-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]  
  
 <span data-ttu-id="afa78-127">В следующем коде показано два равнозначных способа создать массив целых чисел.</span><span class="sxs-lookup"><span data-stu-id="afa78-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]  
  
 <span data-ttu-id="afa78-128">Удобно использовать определение типа для определения типа переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="afa78-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="afa78-129">В следующем коде, компилятор выводит, что `number` — `Integer` поскольку `someNumbers2` из предыдущего примера представляет собой массив целых чисел.</span><span class="sxs-lookup"><span data-stu-id="afa78-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]  
  
 <span data-ttu-id="afa78-130">Вывод локального типа могут использоваться в `Using` инструкции, чтобы установить тип имени ресурса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="afa78-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]  
  
 <span data-ttu-id="afa78-131">Также удается определить тип переменной из возвращаемого значения функции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="afa78-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="afa78-132">Оба `pList1` и `pList2` представляют собой массивы процессов, так как `Process.GetProcesses` возвращает массив из процессов.</span><span class="sxs-lookup"><span data-stu-id="afa78-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]  
  
## <a name="option-infer"></a><span data-ttu-id="afa78-133">Option Infer</span><span class="sxs-lookup"><span data-stu-id="afa78-133">Option Infer</span></span>  
 <span data-ttu-id="afa78-134">`Option Infer` позволяет указать, разрешено ли вывод локального типа в файле.</span><span class="sxs-lookup"><span data-stu-id="afa78-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="afa78-135">Чтобы включить или заблокировать параметр, введите одну из следующих инструкций в начале файла.</span><span class="sxs-lookup"><span data-stu-id="afa78-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="afa78-136">Если не указать значение для `Option Infer` в коде, компилятор по умолчанию используется `Option Infer On`.</span><span class="sxs-lookup"><span data-stu-id="afa78-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> 
  
 <span data-ttu-id="afa78-137">Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.</span><span class="sxs-lookup"><span data-stu-id="afa78-137">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="afa78-138">Дополнительные сведения см. в разделе [оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="afa78-138">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa78-139">См. также</span><span class="sxs-lookup"><span data-stu-id="afa78-139">See also</span></span>

- [<span data-ttu-id="afa78-140">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="afa78-140">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="afa78-141">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="afa78-141">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="afa78-142">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="afa78-142">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="afa78-143">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="afa78-143">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="afa78-144">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="afa78-144">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="afa78-145">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="afa78-145">/optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- <span data-ttu-id="afa78-146">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afa78-146">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
