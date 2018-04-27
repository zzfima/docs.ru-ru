---
title: Процедуры операторов (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8fba5180da6498d280fa4192937c39d3e33168e8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="3c789-102">Процедуры операторов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c789-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="3c789-103">Процедура оператора — это последовательность операторов Visual Basic, определяющих поведение стандартного оператора (например, `*`, `<>`, или `And`) в классе или структуре, определенных вами.</span><span class="sxs-lookup"><span data-stu-id="3c789-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="3c789-104">Это также называется *перегрузка операторов*.</span><span class="sxs-lookup"><span data-stu-id="3c789-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="3c789-105">Когда определять процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="3c789-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="3c789-106">После определения класса или структуры, можно объявлять переменные типа этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3c789-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="3c789-107">Иногда такая переменная должна участвовать в операции как часть выражения.</span><span class="sxs-lookup"><span data-stu-id="3c789-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="3c789-108">Сделать это, он должен быть операндом оператора.</span><span class="sxs-lookup"><span data-stu-id="3c789-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="3c789-109">Visual Basic определяет операторы только на его основных типах данных.</span><span class="sxs-lookup"><span data-stu-id="3c789-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="3c789-110">Можно определить поведение оператора, если один или оба операнда имеют тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3c789-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="3c789-111">Дополнительные сведения см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3c789-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="3c789-112">Типы процедур оператора</span><span class="sxs-lookup"><span data-stu-id="3c789-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="3c789-113">Процедура оператора может принимать одно из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="3c789-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="3c789-114">Определение унарного оператора, где аргумент имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3c789-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="3c789-115">Определение бинарного оператора, где по крайней мере один из аргументов имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3c789-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="3c789-116">Определение оператора преобразования, где аргумент имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3c789-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="3c789-117">Определение оператора преобразования, который возвращает тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3c789-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="3c789-118">Операторы преобразования всегда являются унарными и всегда использовать `CType` как оператор вы определяете.</span><span class="sxs-lookup"><span data-stu-id="3c789-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="3c789-119">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="3c789-119">Declaration Syntax</span></span>  
 <span data-ttu-id="3c789-120">Ниже приведен синтаксис объявления процедуры оператора:</span><span class="sxs-lookup"><span data-stu-id="3c789-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="3c789-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *символ_оператора* `(` *операнд_1*`[,`*операнд_2* `]) As` *тип данных* </span><span class="sxs-lookup"><span data-stu-id="3c789-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="3c789-122">Вы используете `Widening` или `Narrowing` ключевое слово только в операторе преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="3c789-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="3c789-123">Символ оператора является всегда [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для оператора преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="3c789-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="3c789-124">Объявите два операнда, чтобы определить бинарный оператор и объявить один операнд, чтобы определить унарный оператор, включая оператор преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="3c789-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="3c789-125">Все операнды должны быть объявлены `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="3c789-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="3c789-126">Объявите каждый операнд так же, как объявлять параметры для [Sub-процедуры](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3c789-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="3c789-127">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3c789-127">Data Type</span></span>  
 <span data-ttu-id="3c789-128">Поскольку в определении оператора в классе или структуре, определенных вами по крайней мере один из операндов должны иметь тип данных этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3c789-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="3c789-129">Для оператора преобразования типа операнд или возвращаемый тип должен иметь тип данных класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="3c789-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="3c789-130">Дополнительные сведения см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3c789-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="3c789-131">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="3c789-131">Calling Syntax</span></span>  
 <span data-ttu-id="3c789-132">Вызовите процедуру оператора неявно с помощью символа оператора в выражении.</span><span class="sxs-lookup"><span data-stu-id="3c789-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="3c789-133">Укажите операнды так же, как для стандартных операторов.</span><span class="sxs-lookup"><span data-stu-id="3c789-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="3c789-134">Ниже приведен синтаксис для неявный вызов процедуры оператора:</span><span class="sxs-lookup"><span data-stu-id="3c789-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="3c789-135">`Dim testStruct As`  *Имя структуры*</span><span class="sxs-lookup"><span data-stu-id="3c789-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="3c789-136">`Dim testNewStruct As`  *Имя структуры*`= testStruct`*символ_оператора*   `10`</span><span class="sxs-lookup"><span data-stu-id="3c789-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="3c789-137">Пример объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="3c789-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="3c789-138">Следующая структура сохраняет значение 128-разрядное целое число со знаком, как составные части старших и младших.</span><span class="sxs-lookup"><span data-stu-id="3c789-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="3c789-139">Он определяет `+` оператор для добавления двух `veryLong` значения и сформировать результирующий `veryLong` значение.</span><span class="sxs-lookup"><span data-stu-id="3c789-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 <span data-ttu-id="3c789-140">В примере показан типичный вызов `+` оператора, определенного в `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="3c789-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 <span data-ttu-id="3c789-141">Дополнительные сведения и примеры см. в разделе [Перегрузка операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span><span class="sxs-lookup"><span data-stu-id="3c789-141">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c789-142">См. также</span><span class="sxs-lookup"><span data-stu-id="3c789-142">See Also</span></span>  
 [<span data-ttu-id="3c789-143">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3c789-143">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="3c789-144">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="3c789-144">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="3c789-145">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="3c789-145">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="3c789-146">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="3c789-146">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="3c789-147">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="3c789-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="3c789-148">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="3c789-148">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="3c789-149">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="3c789-149">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="3c789-150">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="3c789-150">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="3c789-151">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="3c789-151">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="3c789-152">Практическое руководство. Использование класса, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="3c789-152">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
