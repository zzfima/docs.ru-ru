---
title: "Практическое руководство. Определение оператора (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51921ee38204fd528ed19436806fc9433abbdc5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="ca7b0-102">Практическое руководство. Определение оператора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca7b0-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="ca7b0-103">Если вы определили класс или структура, можно определить поведение стандартного оператора (например, `*`, `<>`, или `And`) Если один или оба операнда имеет тип класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="ca7b0-104">Определите стандартного оператора как процедура оператора в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="ca7b0-105">Все процедуры оператора должны быть `Public` `Shared`.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="ca7b0-106">Определение оператора в классе или структуре также называется *перегрузка* оператора.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca7b0-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ca7b0-107">Example</span></span>  
 <span data-ttu-id="ca7b0-108">В следующем примере определяется `+` вызван оператор для структуры `height`.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="ca7b0-109">Структура использует высоту в метрах и дюйма.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="ca7b0-110">Один *дюйма* 2,54 сантиметра и одна *foot* -12 дюймов.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="ca7b0-111">Чтобы обеспечить нормализованные значения (в дюймах < 12.0), конструктор выполняет *остаток от деления* арифметические 12.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="ca7b0-112">`+` Оператор использует конструктор для создания нормализованных значений.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 <span data-ttu-id="ca7b0-113">Можно проверить структуру `height` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="ca7b0-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 <span data-ttu-id="ca7b0-114">Дополнительные сведения и примеры см. в разделе [Перегрузка операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span><span class="sxs-lookup"><span data-stu-id="ca7b0-114">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7b0-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ca7b0-115">See Also</span></span>  
 [<span data-ttu-id="ca7b0-116">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="ca7b0-116">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="ca7b0-117">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="ca7b0-117">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="ca7b0-118">Практическое руководство. Вызов процедуры оператора</span><span class="sxs-lookup"><span data-stu-id="ca7b0-118">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="ca7b0-119">Практическое руководство. Использование класса, в котором определяются операторы</span><span class="sxs-lookup"><span data-stu-id="ca7b0-119">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)  
 [<span data-ttu-id="ca7b0-120">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="ca7b0-120">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="ca7b0-121">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="ca7b0-121">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="ca7b0-122">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="ca7b0-122">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="ca7b0-123">Оператор Mod</span><span class="sxs-lookup"><span data-stu-id="ca7b0-123">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
