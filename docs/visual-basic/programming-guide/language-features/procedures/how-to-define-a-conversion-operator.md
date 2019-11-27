---
title: 'How to: Define a Conversion Operator'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344897"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="02b50-102">Практическое руководство. Определение оператора преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02b50-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="02b50-103">Если вы определили класс или структуру, можно определить оператор преобразования типа между типом класса или структуры и другим типом данных (например, `Integer`, `Double`или `String`).</span><span class="sxs-lookup"><span data-stu-id="02b50-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="02b50-104">Определите преобразование типа как процедуру [функции CType](../../../../visual-basic/language-reference/functions/ctype-function.md) в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="02b50-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="02b50-105">Все процедуры преобразования должны быть `Public Shared`, и каждая из них должна указывать либо [расширение](../../../../visual-basic/language-reference/modifiers/widening.md) , либо [сужение](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="02b50-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="02b50-106">Определение оператора для класса или структуры также называется *перегрузкой* оператора.</span><span class="sxs-lookup"><span data-stu-id="02b50-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02b50-107">Пример</span><span class="sxs-lookup"><span data-stu-id="02b50-107">Example</span></span>  
 <span data-ttu-id="02b50-108">В следующем примере определяются операторы преобразования между структурой, именуемой `digit`, и `Byte`.</span><span class="sxs-lookup"><span data-stu-id="02b50-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="02b50-109">Вы можете проверить структуру `digit` с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="02b50-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="02b50-110">См. также</span><span class="sxs-lookup"><span data-stu-id="02b50-110">See also</span></span>

- [<span data-ttu-id="02b50-111">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="02b50-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="02b50-112">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="02b50-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="02b50-113">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="02b50-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="02b50-114">Практическое руководство. Использование класса, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="02b50-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="02b50-115">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="02b50-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="02b50-116">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="02b50-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="02b50-117">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="02b50-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="02b50-118">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="02b50-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="02b50-119">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="02b50-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
