---
title: Практическое руководство. Вычисление числовых значений
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
ms.openlocfilehash: d213f6b5a4abf8c52d8872ae36e89796183ff27c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348965"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="f1e75-102">Практическое руководство. Вычисление числовых значений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1e75-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="f1e75-103">Числовые значения можно вычислить с помощью числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="f1e75-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="f1e75-104">*Числовое выражение* представляет собой выражение, которое содержит литералы, константы и переменные, представляющие числовые значения, и операторы, действующие на эти значения.</span><span class="sxs-lookup"><span data-stu-id="f1e75-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="f1e75-105">Вычисление числовых значений</span><span class="sxs-lookup"><span data-stu-id="f1e75-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="f1e75-106">Вычисление числового значения</span><span class="sxs-lookup"><span data-stu-id="f1e75-106">To calculate a numeric value</span></span>  
  
- <span data-ttu-id="f1e75-107">Объедините один или несколько числовых литералов, констант и переменных в числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="f1e75-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="f1e75-108">В следующем примере показаны некоторые допустимые числовые выражения.</span><span class="sxs-lookup"><span data-stu-id="f1e75-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="f1e75-109">Первые три строки показывают литерал, константу и переменную.</span><span class="sxs-lookup"><span data-stu-id="f1e75-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="f1e75-110">Каждый из них формирует допустимое числовое выражение самим собой.</span><span class="sxs-lookup"><span data-stu-id="f1e75-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="f1e75-111">В последней строке показано сочетание переменной с двумя литералами.</span><span class="sxs-lookup"><span data-stu-id="f1e75-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="f1e75-112">Обратите внимание, что числовое выражение не формирует полную инструкцию Visual Basic сам по себе.</span><span class="sxs-lookup"><span data-stu-id="f1e75-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="f1e75-113">Выражение необходимо использовать как часть полной инструкции.</span><span class="sxs-lookup"><span data-stu-id="f1e75-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="f1e75-114">Сохранение числового значения</span><span class="sxs-lookup"><span data-stu-id="f1e75-114">To store a numeric value</span></span>  
  
- <span data-ttu-id="f1e75-115">Оператор присваивания можно использовать для назначения переменной значения, представленного числовым выражением, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f1e75-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="f1e75-116">В предыдущем примере значение выражения в правой части оператора равенства (`=`) присваивается переменной `j` в левой части оператора, поэтому `j` вычисляется как 276.</span><span class="sxs-lookup"><span data-stu-id="f1e75-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="f1e75-117">Дополнительные сведения см. в разделе [Выписки](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="f1e75-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="f1e75-118">Несколько операторов</span><span class="sxs-lookup"><span data-stu-id="f1e75-118">Multiple Operators</span></span>  
 <span data-ttu-id="f1e75-119">Если числовое выражение содержит более одного оператора, порядок их вычисления определяется правилами приоритета операторов.</span><span class="sxs-lookup"><span data-stu-id="f1e75-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="f1e75-120">Чтобы переопределить правила приоритета операторов, заключите выражения в круглые скобки, как в приведенном выше примере. выражения, заключенные в кавычки, оцениваются первыми.</span><span class="sxs-lookup"><span data-stu-id="f1e75-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="f1e75-121">Переопределение приоритета обычного оператора</span><span class="sxs-lookup"><span data-stu-id="f1e75-121">To override normal operator precedence</span></span>  
  
- <span data-ttu-id="f1e75-122">Используйте круглые скобки, чтобы заключать операции, которые необходимо выполнить первыми.</span><span class="sxs-lookup"><span data-stu-id="f1e75-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="f1e75-123">В следующем примере показаны два разных результата с одинаковыми операндами и операторами.</span><span class="sxs-lookup"><span data-stu-id="f1e75-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="f1e75-124">В предыдущем примере вычисление для `j` выполняет сначала оператор сложения (`+`), так как круглые скобки вокруг `(67 + i)` переопределяют нормальный приоритет, а значение, присваиваемое `j`, — 276 (4 раза 69).</span><span class="sxs-lookup"><span data-stu-id="f1e75-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="f1e75-125">Вычисление для `k` выполняет операторы с нормальным приоритетом (`*` до `+`), а значение, назначенное `k`, равно 270 (268 плюс 2).</span><span class="sxs-lookup"><span data-stu-id="f1e75-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="f1e75-126">Дополнительные сведения см. [в разделе приоритет операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="f1e75-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e75-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f1e75-127">See also</span></span>

- [<span data-ttu-id="f1e75-128">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="f1e75-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="f1e75-129">Сравнения значений</span><span class="sxs-lookup"><span data-stu-id="f1e75-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="f1e75-130">Операторы</span><span class="sxs-lookup"><span data-stu-id="f1e75-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="f1e75-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1e75-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f1e75-132">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="f1e75-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f1e75-133">Эффективное сочетание операторов</span><span class="sxs-lookup"><span data-stu-id="f1e75-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
