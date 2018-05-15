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
ms.openlocfilehash: cf24d7259ac04f6901497c81558a4d59b340eec7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="95b98-102">Практическое руководство. Вычисление числовых значений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95b98-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="95b98-103">Можно вычислить числовые значения с помощью числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="95b98-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="95b98-104">Объект *числовое выражение* является выражение, которое содержит литералы, константы и переменные, представляющие числовые значения и операторы, выполняющие действия с этими значениями.</span><span class="sxs-lookup"><span data-stu-id="95b98-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="95b98-105">Вычисление числовых значений</span><span class="sxs-lookup"><span data-stu-id="95b98-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="95b98-106">Для вычисления числового значения</span><span class="sxs-lookup"><span data-stu-id="95b98-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="95b98-107">Объединить один или несколько числовых литералов, констант и переменных в числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="95b98-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="95b98-108">В следующем примере показано некоторые допустимые числовые выражения.</span><span class="sxs-lookup"><span data-stu-id="95b98-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="95b98-109">Первые три строки отображение литерал, константы и переменной.</span><span class="sxs-lookup"><span data-stu-id="95b98-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="95b98-110">Каждый из них образует допустимое числовое выражение само по себе.</span><span class="sxs-lookup"><span data-stu-id="95b98-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="95b98-111">Последняя строка показывает комбинацию переменной с двумя литералами.</span><span class="sxs-lookup"><span data-stu-id="95b98-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="95b98-112">Обратите внимание, что числовое выражение не образуют полную инструкцию Visual Basic сам по себе.</span><span class="sxs-lookup"><span data-stu-id="95b98-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="95b98-113">Необходимо использовать выражение как часть является законченным оператором.</span><span class="sxs-lookup"><span data-stu-id="95b98-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="95b98-114">Для получения числового значения</span><span class="sxs-lookup"><span data-stu-id="95b98-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="95b98-115">Чтобы назначить значение, представленное числовое выражение переменной, как показано в следующем примере, можно использовать оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="95b98-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     <span data-ttu-id="95b98-116">В предыдущем примере значение выражения в правой части оператора равно (`=`) присваивается переменной `j` слева от оператора, поэтому `j` вычисляется как 276.</span><span class="sxs-lookup"><span data-stu-id="95b98-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="95b98-117">Дополнительные сведения см. в разделе [Выписки](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="95b98-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="95b98-118">Несколько операторов</span><span class="sxs-lookup"><span data-stu-id="95b98-118">Multiple Operators</span></span>  
 <span data-ttu-id="95b98-119">Если числовое выражение содержит несколько операторов, порядок, в котором они вычисляются определяется правилами приоритета операторов.</span><span class="sxs-lookup"><span data-stu-id="95b98-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="95b98-120">Для переопределения правил приоритета операторов, выражения заключаются в круглые скобки, как показано в приведенном выше примере; такие выражения вычисляются первыми.</span><span class="sxs-lookup"><span data-stu-id="95b98-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="95b98-121">Чтобы переопределить обычный приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="95b98-121">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="95b98-122">Используйте скобки для заключения операции, которые вы хотите сначала необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="95b98-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="95b98-123">В следующем примере показано два разных результата с теми же операндами и операторы.</span><span class="sxs-lookup"><span data-stu-id="95b98-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     <span data-ttu-id="95b98-124">В предыдущем примере, то вычисление для `j` выполняет оператор сложения (`+`) первый так как скобки вокруг `(67 + i)` переопределить обычный приоритет и значение, присваиваемое `j` равно 276 (4 раза 69).</span><span class="sxs-lookup"><span data-stu-id="95b98-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="95b98-125">Расчет `k` операторы выполняются в обычном порядке (`*` перед `+`) и значение, присваиваемое `k` равно 270 (268 плюс 2).</span><span class="sxs-lookup"><span data-stu-id="95b98-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="95b98-126">Дополнительные сведения см. в разделе [операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="95b98-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b98-127">См. также</span><span class="sxs-lookup"><span data-stu-id="95b98-127">See Also</span></span>  
 [<span data-ttu-id="95b98-128">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="95b98-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="95b98-129">Сравнения значений</span><span class="sxs-lookup"><span data-stu-id="95b98-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="95b98-130">Операторы</span><span class="sxs-lookup"><span data-stu-id="95b98-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)  
 [<span data-ttu-id="95b98-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="95b98-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="95b98-132">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="95b98-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="95b98-133">Эффективное сочетание операторов</span><span class="sxs-lookup"><span data-stu-id="95b98-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
