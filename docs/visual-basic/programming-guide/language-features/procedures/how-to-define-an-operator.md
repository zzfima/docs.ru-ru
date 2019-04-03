---
title: Практическое руководство. Определение оператора (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: 3a09657ee7a79b7f590adba0e4fb0c04a8e89043
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843647"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="7b1c4-102">Практическое руководство. Определение оператора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b1c4-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="7b1c4-103">Если вы определили, класса или структуры, можно определить поведение стандартного оператора (такие как `*`, `<>`, или `And`) Если один или оба операнда имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="7b1c4-104">Определите стандартного оператора как процедура оператора в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="7b1c4-105">Все процедуры оператора должны быть `Public` `Shared`.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="7b1c4-106">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b1c4-107">Пример</span><span class="sxs-lookup"><span data-stu-id="7b1c4-107">Example</span></span>  
 <span data-ttu-id="7b1c4-108">В следующем примере определяется `+` вызывается оператор для структуры `height`.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="7b1c4-109">Структура использует высоту в футах и дюйма.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="7b1c4-110">Один *дюйм* — 2,54 сантиметра и одна *foot* — 12 дюймов.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="7b1c4-111">Чтобы обеспечить нормализованные значения (дюймы < 12.0), конструктор выполняет *остаток от деления* арифметические 12.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="7b1c4-112">`+` Оператор использует конструктор для создания нормализованных значений.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="7b1c4-113">Вы можете проверить структуру `height` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="7b1c4-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  
  
  
## <a name="see-also"></a><span data-ttu-id="7b1c4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7b1c4-114">See also</span></span>

- [<span data-ttu-id="7b1c4-115">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="7b1c4-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="7b1c4-116">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="7b1c4-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="7b1c4-117">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="7b1c4-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="7b1c4-118">Практическое руководство. Используйте класс, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="7b1c4-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="7b1c4-119">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="7b1c4-119">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="7b1c4-120">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="7b1c4-120">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="7b1c4-121">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="7b1c4-121">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="7b1c4-122">Оператор Mod</span><span class="sxs-lookup"><span data-stu-id="7b1c4-122">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
