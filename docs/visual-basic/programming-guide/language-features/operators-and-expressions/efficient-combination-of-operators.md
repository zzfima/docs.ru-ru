---
title: Эффективное сочетание операторов
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 83ad53e4c75490a75eba0f80a6bf0f078aa4d426
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348992"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="da502-102">Эффективное сочетание операторов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da502-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="da502-103">Сложные выражения могут содержать множество различных операторов.</span><span class="sxs-lookup"><span data-stu-id="da502-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="da502-104">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="da502-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="da502-105">Создание сложных выражений, например, в предыдущем примере, требует тщательного понимания правил приоритета операторов.</span><span class="sxs-lookup"><span data-stu-id="da502-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="da502-106">Дополнительные сведения см. [в разделе приоритет операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="da502-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="da502-107">Выражения в скобках</span><span class="sxs-lookup"><span data-stu-id="da502-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="da502-108">Часто требуется, чтобы операции продвигается в порядке, отличном от того, который определяется приоритетом операторов.</span><span class="sxs-lookup"><span data-stu-id="da502-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="da502-109">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="da502-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="da502-110">Предыдущий пример умножает `z` на `y`, а затем добавляет результат в `4`.</span><span class="sxs-lookup"><span data-stu-id="da502-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="da502-111">Но если вы хотите добавить `y` и `4` до умножения результата `z`, можно переопределить приоритет обычного оператора с помощью круглых скобок.</span><span class="sxs-lookup"><span data-stu-id="da502-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="da502-112">Заключив выражение в круглые скобки, вы принудительно выдаете выражение первым, независимо от приоритета операторов.</span><span class="sxs-lookup"><span data-stu-id="da502-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="da502-113">Чтобы выполнить предыдущий пример для первого добавления, можно переписать его, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="da502-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="da502-114">В предыдущем примере добавляется `y` и `4`, затем сумма умножается на `z`.</span><span class="sxs-lookup"><span data-stu-id="da502-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="da502-115">Вложенные выражения в скобках</span><span class="sxs-lookup"><span data-stu-id="da502-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="da502-116">Можно вкладывать выражения на нескольких уровнях круглых скобок для более детального переопределения приоритета.</span><span class="sxs-lookup"><span data-stu-id="da502-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="da502-117">Выражения, наиболее глубоко вложенные в круглые скобки, сначала оцениваются, за которыми следуют более глубокий уровень вложенности, и так далее, и, наконец, выражения за пределами круглых скобок.</span><span class="sxs-lookup"><span data-stu-id="da502-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="da502-118">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="da502-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="da502-119">В предыдущем примере `z + 2` вычисляется первым, а затем другими выражениями в скобках.</span><span class="sxs-lookup"><span data-stu-id="da502-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="da502-120">Возведение в степень, которое обычно имеет более высокий приоритет, чем сложение или умножение, в этом примере вычисляется последним, так как другие выражения заключаются в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="da502-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da502-121">См. также</span><span class="sxs-lookup"><span data-stu-id="da502-121">See also</span></span>

- [<span data-ttu-id="da502-122">Арифметические операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da502-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="da502-123">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da502-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="da502-124">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da502-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="da502-125">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da502-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="da502-126">Логические выражения</span><span class="sxs-lookup"><span data-stu-id="da502-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="da502-127">Сравнения значений</span><span class="sxs-lookup"><span data-stu-id="da502-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="da502-128">Практическое руководство. Вычисление числовых значений</span><span class="sxs-lookup"><span data-stu-id="da502-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="da502-129">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da502-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
