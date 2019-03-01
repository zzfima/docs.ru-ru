---
title: Практическое руководство. Вычисление числовых значений (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: 036985a7b60afedc1e8ef0854c619ea8515e5ffe
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974306"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="c2e65-102">Практическое руководство. Вычисление числовых значений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2e65-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="c2e65-103">Вы можете вычислить числовые значения с помощью числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="c2e65-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="c2e65-104">Объект *числовое выражение* является выражение, которое содержит литералы, константы и переменные, представляющие числовых значений и операторов, работать с этими значениями.</span><span class="sxs-lookup"><span data-stu-id="c2e65-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="c2e65-105">Вычисление числовых значений</span><span class="sxs-lookup"><span data-stu-id="c2e65-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="c2e65-106">Для вычисления числовое значение</span><span class="sxs-lookup"><span data-stu-id="c2e65-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="c2e65-107">Объединить один или несколько числовых литералов, констант и переменных в числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="c2e65-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="c2e65-108">В следующем примере некоторые допустимые числовые выражения.</span><span class="sxs-lookup"><span data-stu-id="c2e65-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="c2e65-109">Первые три строки отображения литерал, константы и переменной.</span><span class="sxs-lookup"><span data-stu-id="c2e65-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="c2e65-110">Каждый из них forms допустимое числовое выражение, сам по себе.</span><span class="sxs-lookup"><span data-stu-id="c2e65-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="c2e65-111">Последняя строка показывает комбинацию переменной с двумя литералами.</span><span class="sxs-lookup"><span data-stu-id="c2e65-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="c2e65-112">Обратите внимание, что числовое выражение не образует является законченным оператором Visual Basic сам по себе.</span><span class="sxs-lookup"><span data-stu-id="c2e65-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="c2e65-113">Необходимо использовать выражение как часть является законченным оператором.</span><span class="sxs-lookup"><span data-stu-id="c2e65-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="c2e65-114">Для хранения числовое значение</span><span class="sxs-lookup"><span data-stu-id="c2e65-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="c2e65-115">Чтобы назначить значение, представленное числового выражения, переменной, как показано в следующем примере, можно использовать оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="c2e65-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="c2e65-116">В предыдущем примере, значение выражения в правой части оператора равно (`=`) присваивается переменной `j` слева от оператора, поэтому `j` вычисляется как 276.</span><span class="sxs-lookup"><span data-stu-id="c2e65-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="c2e65-117">Дополнительные сведения см. в разделе [Выписки](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="c2e65-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="c2e65-118">Несколько операторов</span><span class="sxs-lookup"><span data-stu-id="c2e65-118">Multiple Operators</span></span>  
 <span data-ttu-id="c2e65-119">Если числовое выражение содержит несколько операторов, порядок, в котором они вычисляются определяется правилами приоритета операторов.</span><span class="sxs-lookup"><span data-stu-id="c2e65-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="c2e65-120">Для переопределения правил приоритета операторов, выражения заключать в круглые скобки, как показано в примере выше; выражения вычисляются первыми.</span><span class="sxs-lookup"><span data-stu-id="c2e65-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="c2e65-121">Чтобы переопределить обычный приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="c2e65-121">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="c2e65-122">Используйте круглые скобки, чтобы включить операции, которые вы хотите сначала необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="c2e65-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="c2e65-123">В следующем примере показано два разных результата с теми же операндов и операторов.</span><span class="sxs-lookup"><span data-stu-id="c2e65-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="c2e65-124">В предыдущем примере, расчет `j` выполняет оператор сложения (`+`) первый так как скобки вокруг `(67 + i)` переопределить обычный приоритет и значение, присваиваемое `j` является 276 (4 раза 69).</span><span class="sxs-lookup"><span data-stu-id="c2e65-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="c2e65-125">Расчет `k` операторы выполняются в обычном порядке (`*` перед `+`) и значение, присваиваемое `k` является 270 (268 плюс 2).</span><span class="sxs-lookup"><span data-stu-id="c2e65-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="c2e65-126">Дополнительные сведения см. в разделе [порядок применения операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="c2e65-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e65-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c2e65-127">See also</span></span>
- [<span data-ttu-id="c2e65-128">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="c2e65-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="c2e65-129">Сравнения значений</span><span class="sxs-lookup"><span data-stu-id="c2e65-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="c2e65-130">Операторы</span><span class="sxs-lookup"><span data-stu-id="c2e65-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="c2e65-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2e65-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c2e65-132">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="c2e65-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="c2e65-133">Эффективное сочетание операторов</span><span class="sxs-lookup"><span data-stu-id="c2e65-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
