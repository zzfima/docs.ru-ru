---
title: Сравнение значений (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 6e1eda09784814d139ef94b6720b538aef30e5e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649611"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="40444-102">Сравнение значений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40444-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="40444-103">Операторы сравнения можно использовать для создания выражений, которые сравнивают значения числовых переменных.</span><span class="sxs-lookup"><span data-stu-id="40444-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="40444-104">Эти выражения возвращают `Boolean` значение на основании результат сравнения-ИСТИНА или ЛОЖЬ.</span><span class="sxs-lookup"><span data-stu-id="40444-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="40444-105">Ниже приводятся примеры таких выражений.</span><span class="sxs-lookup"><span data-stu-id="40444-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="40444-106">Первое выражение, результатом которого является `True`, поскольку 45 больше 26.</span><span class="sxs-lookup"><span data-stu-id="40444-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="40444-107">Во втором примере вычисляется `False`, поскольку 26 не больше 45.</span><span class="sxs-lookup"><span data-stu-id="40444-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="40444-108">Вы также можете сравнить числовых выражений таким образом.</span><span class="sxs-lookup"><span data-stu-id="40444-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="40444-109">Выражения могут быть сложными, как в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="40444-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="40444-110">Сложное выражение содержит литералы, переменные и вызовы функций.</span><span class="sxs-lookup"><span data-stu-id="40444-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="40444-111">Вычисляются выражения с обеих сторон оператора сравнения, а полученные значения сравниваются с помощью `>=` оператор сравнения.</span><span class="sxs-lookup"><span data-stu-id="40444-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="40444-112">Если значение выражения в левой части больше или равно значению выражения справа, все выражение принимает значение `True`; в противном случае он возвращает `False`.</span><span class="sxs-lookup"><span data-stu-id="40444-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="40444-113">Выражения, сравнивающие значения чаще всего используются в `If...Then` конструкциях, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="40444-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 <span data-ttu-id="40444-114">`=` Входа является оператором сравнения, а также оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="40444-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="40444-115">При использовании в качестве оператора сравнения, он определяет, является ли значение слева равно значению справа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="40444-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 <span data-ttu-id="40444-116">Можно также использовать выражения сравнения в любом `Boolean` значение, например, как и в `If`, `While`, `Loop`, или `ElseIf` инструкции, или при назначении или передачи значения `Boolean` переменной.</span><span class="sxs-lookup"><span data-stu-id="40444-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="40444-117">В следующем примере присваивается значение, возвращаемое выражением сравнения `Boolean` переменной.</span><span class="sxs-lookup"><span data-stu-id="40444-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="40444-118">См. также</span><span class="sxs-lookup"><span data-stu-id="40444-118">See Also</span></span>  
 [<span data-ttu-id="40444-119">Логические выражения</span><span class="sxs-lookup"><span data-stu-id="40444-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="40444-120">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="40444-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="40444-121">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40444-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="40444-122">Практическое руководство. Вычисление числовых значений</span><span class="sxs-lookup"><span data-stu-id="40444-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [<span data-ttu-id="40444-123">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40444-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
