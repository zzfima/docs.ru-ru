---
title: "Процедуры операторов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, operator
- Visual Basic code, operators
- syntax, Operator procedures
- operators [Visual Basic], overloading
- overloaded operators
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
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
ms.openlocfilehash: 3b2e8466ad355521dcec3cf7b2949037e569eb9a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="dc1ab-102">Процедуры операторов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc1ab-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="dc1ab-103">Процедура оператора — это последовательность [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] инструкции, определяющие поведение стандартного оператора (такие как `*`, `<>`, или `And`) в классе или структуре, определенных вами.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-103">An operator procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="dc1ab-104">Это также называется *перегрузка операторов*.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="dc1ab-105">Когда определять процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="dc1ab-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="dc1ab-106">После определения класса или структуры, можно объявлять переменные типа этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="dc1ab-107">Иногда такая переменная должна участвовать в операции как часть выражения.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="dc1ab-108">Чтобы сделать это, ее необходимо операнд оператора.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-108">To do this, it must be an operand of an operator.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="dc1ab-109">Определяет операторы только на его основных типах данных.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-109"> defines operators only on its fundamental data types.</span></span> <span data-ttu-id="dc1ab-110">Можно определить поведение оператора, если один или оба операнда имеют тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="dc1ab-111">Дополнительные сведения см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dc1ab-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="dc1ab-112">Типы процедур оператора</span><span class="sxs-lookup"><span data-stu-id="dc1ab-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="dc1ab-113">Процедура оператора может быть одним из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="dc1ab-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="dc1ab-114">Определение унарного оператора, где аргумент имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="dc1ab-115">Определение бинарного оператора, где по крайней мере один из аргументов имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="dc1ab-116">Определение оператора преобразования, где аргумент имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="dc1ab-117">Определение оператора преобразования, который возвращает тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="dc1ab-118">Операторы преобразования всегда унарные, поэтому всегда использовать `CType` как оператор, который вы определяете.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="dc1ab-119">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="dc1ab-119">Declaration Syntax</span></span>  
 <span data-ttu-id="dc1ab-120">Синтаксис объявления процедуры оператора выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dc1ab-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="dc1ab-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="dc1ab-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="dc1ab-122">Использовать `Widening` или `Narrowing` ключевое слово только в операторе преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="dc1ab-123">Символ оператора является всегда [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для оператора преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="dc1ab-124">Объявите два операнда, чтобы определить бинарный оператор, и объявите один операнд, чтобы определить унарный оператор, включая оператор преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="dc1ab-125">Все операнды должны быть объявлены `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="dc1ab-126">Объявите каждый операнд так же, как вы объявили параметры для [Sub-процедуры](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="dc1ab-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="dc1ab-127">Тип данных</span><span class="sxs-lookup"><span data-stu-id="dc1ab-127">Data Type</span></span>  
 <span data-ttu-id="dc1ab-128">Поскольку вы определяете оператора для класса или структуры, которые были определены, по крайней мере один из операндов должны иметь тип данных класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="dc1ab-129">Для оператора преобразования типа операнд или возвращаемый тип должен быть типа данных класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="dc1ab-130">Дополнительные сведения см. в разделе [оператор](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dc1ab-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="dc1ab-131">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="dc1ab-131">Calling Syntax</span></span>  
 <span data-ttu-id="dc1ab-132">Вызовите процедуру оператора неявно с помощью символа оператора в выражении.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="dc1ab-133">Укажите операнды так же, как для стандартных операторов.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="dc1ab-134">Неявный вызов процедуры оператора синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dc1ab-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="dc1ab-135">`Dim testStruct As`  *Имя структуры*</span><span class="sxs-lookup"><span data-stu-id="dc1ab-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="dc1ab-136">`Dim testNewStruct As`  *Имя структуры*`= testStruct`*operatorsymbol    *  `10`</span><span class="sxs-lookup"><span data-stu-id="dc1ab-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="dc1ab-137">Пример объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="dc1ab-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="dc1ab-138">Следующая структура сохраняет значение 128-разрядное целое число со знаком, как составные части старший и младший.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="dc1ab-139">Он определяет `+` оператор для добавления двух `veryLong` значения и сформировать сканером `veryLong` значение.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 <span data-ttu-id="dc1ab-140">[!code-vb[VbVbcnProcedures&#23;](./codesnippet/VisualBasic/operator-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dc1ab-140">[!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="dc1ab-141">В следующем примере показано типичный вызов `+` оператора, определенного в `veryLong`.</span><span class="sxs-lookup"><span data-stu-id="dc1ab-141">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 <span data-ttu-id="dc1ab-142">[!code-vb[VbVbcnProcedures&#24;](./codesnippet/VisualBasic/operator-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="dc1ab-142">[!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="dc1ab-143">Дополнительные сведения и примеры см. в разделе [перегрузки операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span><span class="sxs-lookup"><span data-stu-id="dc1ab-143">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc1ab-144">См. также</span><span class="sxs-lookup"><span data-stu-id="dc1ab-144">See Also</span></span>  
 <span data-ttu-id="dc1ab-145">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="dc1ab-145">[Procedures](./index.md) </span></span>  
<span data-ttu-id="dc1ab-146"> [Sub-процедуры](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dc1ab-146"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="dc1ab-147"> [Процедуры функций](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dc1ab-147"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="dc1ab-148"> [Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dc1ab-148"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="dc1ab-149"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="dc1ab-149"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="dc1ab-150"> [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dc1ab-150"> [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="dc1ab-151"> [Практическое руководство: определение оператора](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="dc1ab-151"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="dc1ab-152"> [Практическое руководство: определение оператора преобразования](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="dc1ab-152"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="dc1ab-153"> [Практическое руководство: вызов процедуры оператора](./how-to-call-an-operator-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="dc1ab-153"> [How to: Call an Operator Procedure](./how-to-call-an-operator-procedure.md) </span></span>  
<span data-ttu-id="dc1ab-154"> [Практическое руководство. Использование класса, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md)</span><span class="sxs-lookup"><span data-stu-id="dc1ab-154"> [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md)</span></span>
