---
title: Как выполнить Определить оператор преобразования (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 76d0769456e30766b830023c1f27381ceca59cbb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521534"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="fa47d-102">Как выполнить Определить оператор преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa47d-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="fa47d-103">Если вы определили, класса или структуры, можно определить оператор преобразования типа между типом класса или структуры и другой тип данных (таких как `Integer`, `Double`, или `String`).</span><span class="sxs-lookup"><span data-stu-id="fa47d-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="fa47d-104">Определите преобразование типа как [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) процедуры внутри класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fa47d-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="fa47d-105">Все процедуры преобразования должны быть `Public Shared`, и каждый из них необходимо указать либо [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) или [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="fa47d-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="fa47d-106">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="fa47d-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa47d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="fa47d-107">Example</span></span>  
 <span data-ttu-id="fa47d-108">В следующем примере определяется операторы преобразования между структурой `digit` и `Byte`.</span><span class="sxs-lookup"><span data-stu-id="fa47d-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 <span data-ttu-id="fa47d-109">Вы можете проверить структуру `digit` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="fa47d-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fa47d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="fa47d-110">See also</span></span>
- [<span data-ttu-id="fa47d-111">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="fa47d-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="fa47d-112">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="fa47d-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="fa47d-113">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="fa47d-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="fa47d-114">Практическое руководство. Используйте класс, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="fa47d-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="fa47d-115">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="fa47d-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="fa47d-116">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="fa47d-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="fa47d-117">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="fa47d-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="fa47d-118">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="fa47d-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="fa47d-119">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="fa47d-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
