---
title: Практическое руководство. Вызов процедуры оператора
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
ms.openlocfilehash: a685be7cc3b346b271413e2c29faae5a839313f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340246"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="eb33d-102">Практическое руководство. Вызов процедуры оператора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb33d-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="eb33d-103">Для вызова процедуры оператора используется символ оператора в выражении.</span><span class="sxs-lookup"><span data-stu-id="eb33d-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="eb33d-104">В случае оператора преобразования вызывается [Функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) для преобразования значения из одного типа данных в другой.</span><span class="sxs-lookup"><span data-stu-id="eb33d-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="eb33d-105">Процедуры оператора не вызываются явным образом.</span><span class="sxs-lookup"><span data-stu-id="eb33d-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="eb33d-106">Вы просто используете оператор или функцию `CType` в операторе присваивания или выражении так же, как обычно используется оператор.</span><span class="sxs-lookup"><span data-stu-id="eb33d-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="eb33d-107">Visual Basic выполняет вызов процедуры оператора.</span><span class="sxs-lookup"><span data-stu-id="eb33d-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="eb33d-108">Определение оператора для класса или структуры также называется *перегрузкой* оператора.</span><span class="sxs-lookup"><span data-stu-id="eb33d-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="eb33d-109">Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="eb33d-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="eb33d-110">Используйте символ оператора в выражении обычным образом.</span><span class="sxs-lookup"><span data-stu-id="eb33d-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="eb33d-111">Убедитесь, что типы данных операндов подходят для оператора, и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="eb33d-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="eb33d-112">Оператор влияет на значение выражения, как и ожидалось.</span><span class="sxs-lookup"><span data-stu-id="eb33d-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="eb33d-113">Вызов процедуры оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="eb33d-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="eb33d-114">Используйте `CType` внутри выражения.</span><span class="sxs-lookup"><span data-stu-id="eb33d-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="eb33d-115">Убедитесь, что типы данных операндов подходят для преобразования, и в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="eb33d-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="eb33d-116">`CType` вызывает процедуру оператора преобразования и возвращает преобразованное значение.</span><span class="sxs-lookup"><span data-stu-id="eb33d-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb33d-117">Пример</span><span class="sxs-lookup"><span data-stu-id="eb33d-117">Example</span></span>  
 <span data-ttu-id="eb33d-118">Следующий пример создает две структуры <xref:System.TimeSpan>, добавляет их вместе и сохраняет результат в третьей структуре <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="eb33d-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="eb33d-119">Структура <xref:System.TimeSpan> определяет процедуры операторов для перегрузки нескольких стандартных операторов.</span><span class="sxs-lookup"><span data-stu-id="eb33d-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="eb33d-120">Поскольку <xref:System.TimeSpan> перегружает стандартный оператор `+`, в предыдущем примере вызывается процедура оператора при вычислении значения `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="eb33d-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="eb33d-121">Пример вызова процедуры оператора диалога см. [в разделе как использовать класс, определяющий операторы](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="eb33d-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eb33d-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="eb33d-122">Compiling the Code</span></span>  
 <span data-ttu-id="eb33d-123">Убедитесь, что используемый класс или структура определяет оператор, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="eb33d-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb33d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="eb33d-124">See also</span></span>

- [<span data-ttu-id="eb33d-125">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="eb33d-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="eb33d-126">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="eb33d-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="eb33d-127">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="eb33d-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="eb33d-128">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="eb33d-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="eb33d-129">Расширение</span><span class="sxs-lookup"><span data-stu-id="eb33d-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="eb33d-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="eb33d-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="eb33d-131">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="eb33d-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="eb33d-132">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="eb33d-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="eb33d-133">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="eb33d-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="eb33d-134">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="eb33d-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
