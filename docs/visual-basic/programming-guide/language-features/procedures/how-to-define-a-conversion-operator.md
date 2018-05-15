---
title: Практическое руководство. Определение оператора преобразования (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 24bbe41af67f757cae661a78d482a423ff0ffd85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="13381-102">Практическое руководство. Определение оператора преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13381-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="13381-103">Если вы определили класс или структура, можно определить оператор преобразования типа между типом класса или структуры и другим типом данных (таких как `Integer`, `Double`, или `String`).</span><span class="sxs-lookup"><span data-stu-id="13381-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="13381-104">Определите преобразование типа как [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) процедура внутри класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="13381-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="13381-105">Все процедуры преобразования должны быть `Public Shared`, и каждый из них необходимо указать либо [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) или [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="13381-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="13381-106">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="13381-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13381-107">Пример</span><span class="sxs-lookup"><span data-stu-id="13381-107">Example</span></span>  
 <span data-ttu-id="13381-108">В следующем примере определяются операторы преобразования между структурой `digit` и `Byte`.</span><span class="sxs-lookup"><span data-stu-id="13381-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 <span data-ttu-id="13381-109">Можно проверить структуру `digit` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="13381-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="13381-110">См. также</span><span class="sxs-lookup"><span data-stu-id="13381-110">See Also</span></span>  
 [<span data-ttu-id="13381-111">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="13381-111">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="13381-112">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="13381-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="13381-113">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="13381-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="13381-114">Практическое руководство. Использование класса, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="13381-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)  
 [<span data-ttu-id="13381-115">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="13381-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="13381-116">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="13381-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="13381-117">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="13381-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="13381-118">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="13381-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="13381-119">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="13381-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
