---
title: "Практическое руководство. Вызов процедуры оператора (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0abff0a81ebcdacb59b69d0c307bb4aa219906c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="9be38-102">Практическое руководство. Вызов процедуры оператора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9be38-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="9be38-103">Вызов процедуры оператора с помощью символа оператора в выражении.</span><span class="sxs-lookup"><span data-stu-id="9be38-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="9be38-104">При наличии оператора преобразования следует вызвать [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для преобразования значения из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="9be38-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="9be38-105">Процедуры операторов не вызывается явно.</span><span class="sxs-lookup"><span data-stu-id="9be38-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="9be38-106">Просто используйте оператор, или `CType` функции, в операторе присваивания или выражения, как и вы обычно используется оператор.</span><span class="sxs-lookup"><span data-stu-id="9be38-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9be38-107">выполняет вызов процедуры оператора.</span><span class="sxs-lookup"><span data-stu-id="9be38-107"> makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="9be38-108">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="9be38-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="9be38-109">Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="9be38-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="9be38-110">Используйте символ оператора в выражении обычным образом.</span><span class="sxs-lookup"><span data-stu-id="9be38-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="9be38-111">Убедитесь, что типы данных операндов подходят для оператора и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="9be38-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="9be38-112">Оператор увеличивает значение выражения, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="9be38-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="9be38-113">Вызов процедуры оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="9be38-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="9be38-114">Используйте `CType` внутри выражения.</span><span class="sxs-lookup"><span data-stu-id="9be38-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="9be38-115">Убедитесь, что типы данных операндов подходят для преобразования, а также в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="9be38-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="9be38-116">`CType`вызывает процедуру оператора преобразования и возвращает преобразованное значение.</span><span class="sxs-lookup"><span data-stu-id="9be38-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9be38-117">Пример</span><span class="sxs-lookup"><span data-stu-id="9be38-117">Example</span></span>  
 <span data-ttu-id="9be38-118">В следующем примере создается два <xref:System.TimeSpan> структуры, складывает их и сохраняет результат в третьей <xref:System.TimeSpan> структуры.</span><span class="sxs-lookup"><span data-stu-id="9be38-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="9be38-119"><xref:System.TimeSpan> Структуры определяются процедуры оператора для перегрузки нескольких стандартных операторов.</span><span class="sxs-lookup"><span data-stu-id="9be38-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 <span data-ttu-id="9be38-120">Поскольку <xref:System.TimeSpan> перегружает стандартный `+` оператор, в предыдущем примере вызывается процедура оператора при вычислении значения `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="9be38-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="9be38-121">Пример вызова процедуры оператора преобразования см. в разделе [как: использование класса преобразования](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="9be38-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9be38-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9be38-122">Compiling the Code</span></span>  
 <span data-ttu-id="9be38-123">Убедитесь, что класс или структура, которую вы используете определяет оператор, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="9be38-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be38-124">См. также</span><span class="sxs-lookup"><span data-stu-id="9be38-124">See Also</span></span>  
 [<span data-ttu-id="9be38-125">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="9be38-125">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="9be38-126">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="9be38-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="9be38-127">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="9be38-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="9be38-128">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="9be38-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="9be38-129">Расширение</span><span class="sxs-lookup"><span data-stu-id="9be38-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="9be38-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="9be38-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="9be38-131">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="9be38-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="9be38-132">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="9be38-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="9be38-133">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="9be38-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="9be38-134">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="9be38-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
