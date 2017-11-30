---
title: "Практическое руководство. Определение оператора преобразования (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0f9e63ba039a48226186fa4ce118d3e47b5673e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="07620-102">Практическое руководство. Определение оператора преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07620-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="07620-103">Если вы определили класс или структура, можно определить оператор преобразования типа между типом класса или структуры и другим типом данных (таких как `Integer`, `Double`, или `String`).</span><span class="sxs-lookup"><span data-stu-id="07620-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="07620-104">Определите преобразование типа как [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md) процедура внутри класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="07620-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="07620-105">Все процедуры преобразования должны быть `Public Shared`, и каждый из них необходимо указать либо [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) или [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="07620-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="07620-106">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="07620-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07620-107">Пример</span><span class="sxs-lookup"><span data-stu-id="07620-107">Example</span></span>  
 <span data-ttu-id="07620-108">В следующем примере определяются операторы преобразования между структурой `digit` и `Byte`.</span><span class="sxs-lookup"><span data-stu-id="07620-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 <span data-ttu-id="07620-109">Можно проверить структуру `digit` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="07620-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="07620-110">См. также</span><span class="sxs-lookup"><span data-stu-id="07620-110">See Also</span></span>  
 [<span data-ttu-id="07620-111">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="07620-111">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="07620-112">Практическое руководство. Определение оператора</span><span class="sxs-lookup"><span data-stu-id="07620-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="07620-113">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="07620-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="07620-114">Практическое руководство. Использование класса, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="07620-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)  
 [<span data-ttu-id="07620-115">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="07620-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="07620-116">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="07620-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="07620-117">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="07620-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="07620-118">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="07620-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="07620-119">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="07620-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
