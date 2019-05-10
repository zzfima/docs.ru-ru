---
title: Процедуры операторов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: cafc742474d6f7b46fbfb73374a59a350812a2a5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64639103"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="fab61-102">Процедуры операторов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fab61-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="fab61-103">Процедура оператора — это последовательность операторов Visual Basic, которые определяют поведение стандартного оператора (такие как `*`, `<>`, или `And`) для класса или структуры, которые вы определили.</span><span class="sxs-lookup"><span data-stu-id="fab61-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="fab61-104">Это также называется *перегрузка операторов*.</span><span class="sxs-lookup"><span data-stu-id="fab61-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="fab61-105">Когда следует определять процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="fab61-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="fab61-106">После определения класса или структуры, можно объявлять переменные типа этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fab61-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="fab61-107">Иногда такой переменной необходимо участвовать в операции как часть выражения.</span><span class="sxs-lookup"><span data-stu-id="fab61-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="fab61-108">Чтобы сделать это, он должен быть операнд оператора.</span><span class="sxs-lookup"><span data-stu-id="fab61-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="fab61-109">Visual Basic определяет операторы только на его основных типах данных.</span><span class="sxs-lookup"><span data-stu-id="fab61-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="fab61-110">Можно определить поведение оператора, если один или оба операнда имеют тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fab61-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="fab61-111">Дополнительные сведения см. в разделе [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fab61-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="fab61-112">Типы процедур оператора</span><span class="sxs-lookup"><span data-stu-id="fab61-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="fab61-113">Процедура оператора может принимать одно из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="fab61-113">An operator procedure can be one of the following types:</span></span>  
  
- <span data-ttu-id="fab61-114">Определение унарного оператора, где аргумент имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fab61-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="fab61-115">Определение бинарного оператора, где по крайней мере один из аргументов имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fab61-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="fab61-116">Определение оператора преобразования, где аргумент имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fab61-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="fab61-117">Определение оператора преобразования, который возвращает тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fab61-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="fab61-118">Операторы преобразования всегда являются унарными и всегда использовать `CType` как оператор вы определяете.</span><span class="sxs-lookup"><span data-stu-id="fab61-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="fab61-119">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="fab61-119">Declaration Syntax</span></span>  
 <span data-ttu-id="fab61-120">Ниже приведен синтаксис объявления процедуры оператора:</span><span class="sxs-lookup"><span data-stu-id="fab61-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="fab61-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *символ_оператора* `(` *операнд1*`[,`*операнд2* `]) As` *тип данных*</span><span class="sxs-lookup"><span data-stu-id="fab61-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="fab61-122">Использовании `Widening` или `Narrowing` ключевое слово только в операторе преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="fab61-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="fab61-123">Символ оператора является всегда [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для оператора преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="fab61-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="fab61-124">Объявите два операнда, чтобы определить бинарный оператор, и объявите один операнд, чтобы определить унарный оператор, включая оператор преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="fab61-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="fab61-125">Все операнды должны быть объявлены `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="fab61-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="fab61-126">Объявите каждый операнд так же, как объявлять параметры для [подпрограммы](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fab61-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="fab61-127">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fab61-127">Data Type</span></span>  
 <span data-ttu-id="fab61-128">Так как при определении оператора для класса или структуры, которые вы определили, по крайней мере один из операндов должен иметь тип данных этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fab61-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="fab61-129">Для оператора преобразования типа данных типа класса или структуры необходимо операнд или тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="fab61-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="fab61-130">Дополнительные сведения см. в разделе [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fab61-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="fab61-131">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="fab61-131">Calling Syntax</span></span>  
 <span data-ttu-id="fab61-132">Вызовите процедуру оператора неявно с помощью символа оператора в выражении.</span><span class="sxs-lookup"><span data-stu-id="fab61-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="fab61-133">Укажите операнды так же, как и для стандартных операторов.</span><span class="sxs-lookup"><span data-stu-id="fab61-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="fab61-134">Ниже приведен синтаксис для неявный вызов процедуры оператора:</span><span class="sxs-lookup"><span data-stu-id="fab61-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="fab61-135">`Dim testStruct As`  *Имя структуры*</span><span class="sxs-lookup"><span data-stu-id="fab61-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="fab61-136">`Dim testNewStruct As`  *Имя структуры*`= testStruct`*символ_оператора*  `10`</span><span class="sxs-lookup"><span data-stu-id="fab61-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="fab61-137">Пример объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="fab61-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="fab61-138">Следующая структура сохраняет значение 128-битового знакового целого числа в качестве составных частей старшие и младшие.</span><span class="sxs-lookup"><span data-stu-id="fab61-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="fab61-139">Он определяет `+` оператора для добавления двух `veryLong` значения и сформировать результирующий `veryLong` значение.</span><span class="sxs-lookup"><span data-stu-id="fab61-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 <span data-ttu-id="fab61-140">В следующем примере показано типичный вызов `+` оператора, определенного в `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="fab61-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  

## <a name="see-also"></a><span data-ttu-id="fab61-141">См. также</span><span class="sxs-lookup"><span data-stu-id="fab61-141">See also</span></span>

- [<span data-ttu-id="fab61-142">Процедуры</span><span class="sxs-lookup"><span data-stu-id="fab61-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fab61-143">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="fab61-143">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="fab61-144">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="fab61-144">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="fab61-145">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="fab61-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="fab61-146">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="fab61-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fab61-147">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="fab61-147">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="fab61-148">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="fab61-148">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="fab61-149">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="fab61-149">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="fab61-150">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="fab61-150">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="fab61-151">Практическое руководство. Используйте класс, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="fab61-151">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
