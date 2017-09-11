---
title: "Практическое руководство: вызов процедуры оператора (Visual Basic) | Документы Microsoft"
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
- operator procedures, calling
- procedures, operator
- procedure calls, operator overloading
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- overloaded operators, calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
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
ms.openlocfilehash: cd85a14a6f5534e90497268134f4b2b0cc292249
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="114b4-102">Практическое руководство. Вызов процедуры оператора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="114b4-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="114b4-103">Вызов процедуры оператора с помощью символа оператора в выражении.</span><span class="sxs-lookup"><span data-stu-id="114b4-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="114b4-104">При наличии оператора преобразования следует вызвать [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для преобразования значения из одного типа данных в другой.</span><span class="sxs-lookup"><span data-stu-id="114b4-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="114b4-105">Не вызывайте процедуры оператора явным образом.</span><span class="sxs-lookup"><span data-stu-id="114b4-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="114b4-106">Просто используйте оператор, или `CType` функции, в операторе присваивания или выражении так же, обычно используется оператор.</span><span class="sxs-lookup"><span data-stu-id="114b4-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="114b4-107">выполняет вызов процедуры оператора.</span><span class="sxs-lookup"><span data-stu-id="114b4-107"> makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="114b4-108">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="114b4-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="114b4-109">Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="114b4-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="114b4-110">Используйте символ оператора в выражении обычным образом.</span><span class="sxs-lookup"><span data-stu-id="114b4-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="114b4-111">Убедитесь, что типы данных операндов соответствуют для оператора и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="114b4-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="114b4-112">Оператор относится к значению выражения как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="114b4-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="114b4-113">Вызов процедуры оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="114b4-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="114b4-114">Используйте `CType` внутри выражения.</span><span class="sxs-lookup"><span data-stu-id="114b4-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="114b4-115">Убедитесь, что типы данных операндов соответствуют для преобразования и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="114b4-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="114b4-116">`CType`вызывает процедуру оператора преобразования и возвращает преобразованное значение.</span><span class="sxs-lookup"><span data-stu-id="114b4-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="114b4-117">Пример</span><span class="sxs-lookup"><span data-stu-id="114b4-117">Example</span></span>  
 <span data-ttu-id="114b4-118">В следующем примере создаются два <xref:System.TimeSpan>структур, складывает их и сохраняет результат в третьей <xref:System.TimeSpan>структуры.</xref:System.TimeSpan> </xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="114b4-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="114b4-119"><xref:System.TimeSpan>Структуры определяются процедуры оператора для перегрузки нескольких стандартных операторов.</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="114b4-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 <span data-ttu-id="114b4-120">[!code-vb[VbVbcnProcedures&#29;](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="114b4-120">[!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="114b4-121">Поскольку <xref:System.TimeSpan>перегружает стандартный `+` оператор, в предыдущем примере вызывается процедура оператора при вычислении значения `combinedSpan`.</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="114b4-121">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="114b4-122">Пример вызова процедуры оператора см [Практическое руководство: использование класса преобразования](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="114b4-122">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="114b4-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="114b4-123">Compiling the Code</span></span>  
 <span data-ttu-id="114b4-124">Убедитесь, что класс или структура, которую вы используете определяет оператор, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="114b4-124">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114b4-125">См. также</span><span class="sxs-lookup"><span data-stu-id="114b4-125">See Also</span></span>  
 <span data-ttu-id="114b4-126">[Процедуры операторов](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="114b4-126">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="114b4-127"> [Практическое руководство: определение оператора](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="114b4-127"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="114b4-128"> [Практическое руководство: определение оператора преобразования](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="114b4-128"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="114b4-129"> [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="114b4-129"> [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="114b4-130"> [Расширяющие](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="114b4-130"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="114b4-131"> [Сужающие](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="114b4-131"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="114b4-132"> [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="114b4-132"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="114b4-133"> [Практическое руководство: объявление структуры](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="114b4-133"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="114b4-134"> [Явные и неявные преобразования](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="114b4-134"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="114b4-135"> [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="114b4-135"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
