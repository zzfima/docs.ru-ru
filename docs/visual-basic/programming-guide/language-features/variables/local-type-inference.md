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
ms.openlocfilehash: 2b239e17ba7fa0b6a6b08d52f4394541eaa08b28
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775723"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="f6c30-102">Вывод локального типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6c30-102">Local Type Inference (Visual Basic)</span></span>

<span data-ttu-id="f6c30-103">Компилятор Visual Basic использует *Определение типа* для определения типов данных локальных переменных, объявленных без предложения `As`.</span><span class="sxs-lookup"><span data-stu-id="f6c30-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="f6c30-104">Компилятор выводит тип переменной из типа выражения инициализации.</span><span class="sxs-lookup"><span data-stu-id="f6c30-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="f6c30-105">Это позволяет объявлять переменные без явного указания типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f6c30-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="f6c30-106">В результате объявления и `num1`, и `num2` строго типизированы как целые числа.</span><span class="sxs-lookup"><span data-stu-id="f6c30-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="f6c30-107">Если вы не хотите, чтобы `num2` в предыдущем примере вводились как `Integer`, можно указать другой тип с помощью объявления, например `Dim num3 As Object = 3` или `Dim num4 As Double = 3`.</span><span class="sxs-lookup"><span data-stu-id="f6c30-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>

> [!NOTE]
> <span data-ttu-id="f6c30-108">Определение типа может использоваться только для нестатических локальных переменных. его нельзя использовать для определения типа полей, свойств или функций класса.</span><span class="sxs-lookup"><span data-stu-id="f6c30-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>

<span data-ttu-id="f6c30-109">Локальное определение типа применяется на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="f6c30-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="f6c30-110">Его нельзя использовать для объявления переменных на уровне модуля (внутри класса, структуры, модуля или интерфейса, но не внутри процедуры или блока).</span><span class="sxs-lookup"><span data-stu-id="f6c30-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="f6c30-111">Если `num2` в предыдущем примере являлось полем класса, а не локальной переменной в процедуре, это объявление вызовет ошибку с `Option Strict` и классифицирует `num2` как `Object` с `Option Strict` Off.</span><span class="sxs-lookup"><span data-stu-id="f6c30-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="f6c30-112">Аналогичным образом, локальное определение типа не применяется к переменным уровня процедуры, объявленным как `Static`.</span><span class="sxs-lookup"><span data-stu-id="f6c30-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>

## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="f6c30-113">Определение типа и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="f6c30-113">Type Inference vs. Late Binding</span></span>

<span data-ttu-id="f6c30-114">Код, использующий вывод типа, напоминает код, основанный на позднем связывании.</span><span class="sxs-lookup"><span data-stu-id="f6c30-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="f6c30-115">Однако вывод типа строго вводит переменную вместо того, чтобы покинуть ее как `Object`.</span><span class="sxs-lookup"><span data-stu-id="f6c30-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="f6c30-116">Компилятор использует инициализатор переменной для определения типа переменной во время компиляции для создания кода с ранней привязкой.</span><span class="sxs-lookup"><span data-stu-id="f6c30-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="f6c30-117">В предыдущем примере `num2`, как `num1`, типизирован как `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f6c30-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>

<span data-ttu-id="f6c30-118">Поведение переменных с ранней привязкой отличается от поведения переменных с поздним связыванием, для которых тип известен только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f6c30-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="f6c30-119">Знание типа на раннем этапе позволяет компилятору определить проблемы перед выполнением, выделить память точно и выполнить другие оптимизации.</span><span class="sxs-lookup"><span data-stu-id="f6c30-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="f6c30-120">Раннее связывание также включает Visual Basic интегрированную среду разработки (IDE) для предоставления справки IntelliSense об элементах объекта.</span><span class="sxs-lookup"><span data-stu-id="f6c30-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="f6c30-121">Раннее связывание также предпочтительно для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="f6c30-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="f6c30-122">Это связано с тем, что все данные, хранящиеся в переменной с поздним связыванием, должны быть упакованы как тип `Object` и доступ к элементам типа во время выполнения замедляет выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="f6c30-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>

## <a name="examples"></a><span data-ttu-id="f6c30-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="f6c30-123">Examples</span></span>

<span data-ttu-id="f6c30-124">Вывод типа происходит, когда локальная переменная объявлена без предложения `As` и не инициализирована.</span><span class="sxs-lookup"><span data-stu-id="f6c30-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="f6c30-125">Компилятор использует тип присвоенного начального значения в качестве типа переменной.</span><span class="sxs-lookup"><span data-stu-id="f6c30-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="f6c30-126">Например, каждая из следующих строк кода объявляет переменную типа `String`.</span><span class="sxs-lookup"><span data-stu-id="f6c30-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

<span data-ttu-id="f6c30-127">В следующем коде показаны два эквивалентных способа создания массива целых чисел.</span><span class="sxs-lookup"><span data-stu-id="f6c30-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

<span data-ttu-id="f6c30-128">Для определения типа управляющей переменной цикла удобно использовать определение типа.</span><span class="sxs-lookup"><span data-stu-id="f6c30-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="f6c30-129">В следующем коде компилятор выводит, что `number` является `Integer`, поскольку `someNumbers2` из предыдущего примера является массивом целых чисел.</span><span class="sxs-lookup"><span data-stu-id="f6c30-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

<span data-ttu-id="f6c30-130">Определение локального типа можно использовать в инструкциях `Using` для определения типа имени ресурса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f6c30-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

<span data-ttu-id="f6c30-131">Тип переменной также может выводиться из возвращаемых значений функций, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f6c30-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="f6c30-132">Как `pList1`, так `pList2` являются массивами процессов, так как `Process.GetProcesses` возвращает массив процессов.</span><span class="sxs-lookup"><span data-stu-id="f6c30-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a><span data-ttu-id="f6c30-133">Параметр Infer</span><span class="sxs-lookup"><span data-stu-id="f6c30-133">Option Infer</span></span>

<span data-ttu-id="f6c30-134">`Option Infer` позволяет указать, разрешено ли определение локального типа в конкретном файле.</span><span class="sxs-lookup"><span data-stu-id="f6c30-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="f6c30-135">Чтобы включить или заблокировать параметр, введите одну из следующих инструкций в начале файла.</span><span class="sxs-lookup"><span data-stu-id="f6c30-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>

`Option Infer On`

`Option Infer Off`

<span data-ttu-id="f6c30-136">Если не указать значение для `Option Infer` в коде, компилятор по умолчанию будет `Option Infer On`.</span><span class="sxs-lookup"><span data-stu-id="f6c30-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span>

<span data-ttu-id="f6c30-137">Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.</span><span class="sxs-lookup"><span data-stu-id="f6c30-137">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="f6c30-138">Дополнительные сведения см. в статьях [выборка инструкций](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [компиляции в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f6c30-138">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6c30-139">См. также</span><span class="sxs-lookup"><span data-stu-id="f6c30-139">See also</span></span>

- [<span data-ttu-id="f6c30-140">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="f6c30-140">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="f6c30-141">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="f6c30-141">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="f6c30-142">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="f6c30-142">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="f6c30-143">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="f6c30-143">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="f6c30-144">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="f6c30-144">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="f6c30-145">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="f6c30-145">-optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- <span data-ttu-id="f6c30-146">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6c30-146">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
