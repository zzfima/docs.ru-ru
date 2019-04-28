---
title: Практическое руководство. Вызов процедуры оператора (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: d68781aa12ab7c1c717031ca252c5f3120649edc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863939"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="55c12-102">Практическое руководство. Вызов процедуры оператора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55c12-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="55c12-103">Вызов процедуры оператора, используя символ оператора в выражении.</span><span class="sxs-lookup"><span data-stu-id="55c12-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="55c12-104">При наличии оператора преобразования следует вызвать [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для преобразования значения из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="55c12-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="55c12-105">Процедуры операторов не вызывается явно.</span><span class="sxs-lookup"><span data-stu-id="55c12-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="55c12-106">Просто используйте оператор, или `CType` функции, в операторе присваивания или выражение, так же, вы обычно используется оператор.</span><span class="sxs-lookup"><span data-stu-id="55c12-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="55c12-107">Visual Basic выполняет вызов процедуры оператора.</span><span class="sxs-lookup"><span data-stu-id="55c12-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="55c12-108">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="55c12-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="55c12-109">Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="55c12-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="55c12-110">Используйте символ оператора в выражении обычным образом.</span><span class="sxs-lookup"><span data-stu-id="55c12-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="55c12-111">Убедитесь, что типы данных операндов подходят для оператора и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="55c12-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="55c12-112">Оператор относится к значению выражения должным образом.</span><span class="sxs-lookup"><span data-stu-id="55c12-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="55c12-113">Вызов процедуры оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="55c12-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="55c12-114">Используйте `CType` внутри выражения.</span><span class="sxs-lookup"><span data-stu-id="55c12-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="55c12-115">Убедитесь, что типы данных операндов подходят для преобразования и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="55c12-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="55c12-116">`CType` вызывает процедуру оператора преобразования и возвращает преобразованное значение.</span><span class="sxs-lookup"><span data-stu-id="55c12-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55c12-117">Пример</span><span class="sxs-lookup"><span data-stu-id="55c12-117">Example</span></span>  
 <span data-ttu-id="55c12-118">В следующем примере создается два <xref:System.TimeSpan> структуры, складывает их и сохраняет результат в третьей <xref:System.TimeSpan> структуры.</span><span class="sxs-lookup"><span data-stu-id="55c12-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="55c12-119"><xref:System.TimeSpan> Структура определяет процедуры оператора для перегрузки нескольких стандартных операторов.</span><span class="sxs-lookup"><span data-stu-id="55c12-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="55c12-120">Так как <xref:System.TimeSpan> перегружает стандартный `+` оператор, в предыдущем примере вызывается процедура оператора при вычислении значения `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="55c12-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="55c12-121">Пример вызова процедуры оператора, см. в разделе [как: Используйте класс, в котором определяются операторы](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="55c12-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55c12-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="55c12-122">Compiling the Code</span></span>  
 <span data-ttu-id="55c12-123">Убедитесь, что класс или структура, которую вы используете определяет оператор, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="55c12-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c12-124">См. также</span><span class="sxs-lookup"><span data-stu-id="55c12-124">See also</span></span>

- [<span data-ttu-id="55c12-125">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="55c12-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="55c12-126">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="55c12-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="55c12-127">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="55c12-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="55c12-128">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="55c12-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="55c12-129">Расширение</span><span class="sxs-lookup"><span data-stu-id="55c12-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="55c12-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="55c12-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="55c12-131">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="55c12-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="55c12-132">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="55c12-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="55c12-133">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="55c12-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="55c12-134">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="55c12-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
