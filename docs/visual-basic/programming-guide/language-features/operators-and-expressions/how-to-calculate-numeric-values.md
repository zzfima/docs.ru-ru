---
title: "Практическое руководство: вычисление числовых значений (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations, numeric expressions
- precedence, of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fe781cca8f716c792d3af153b2004c716bc87f90
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="ac5a4-102">Практическое руководство. Вычисление числовых значений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac5a4-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="ac5a4-103">Можно вычислить числовых значений с помощью числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="ac5a4-104">Объект *числовое выражение* является выражение, которое содержит литералы, константы и переменные, представляющие числовые значения, а также операторы, действующие на эти значения.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="ac5a4-105">Вычисление числовых значений</span><span class="sxs-lookup"><span data-stu-id="ac5a4-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="ac5a4-106">Для вычисления числового значения</span><span class="sxs-lookup"><span data-stu-id="ac5a4-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="ac5a4-107">Объединение числовых литералов, констант и переменных в числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="ac5a4-108">В следующем примере показано некоторые допустимые числовые выражения.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="ac5a4-109">Первые три строки показывают литерал, константа и переменная.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="ac5a4-110">Каждая из форм допустимое числовое выражение само по себе.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="ac5a4-111">Последняя строка показывает комбинацию переменной с двумя литералами.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="ac5a4-112">Обратите внимание, что числовое выражение не образуют полный [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] инструкции сама по себе.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-112">Note that a numeric expression does not form a complete [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statement by itself.</span></span> <span data-ttu-id="ac5a4-113">Необходимо использовать выражение как часть полной инструкции.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="ac5a4-114">Для хранения числовых значений</span><span class="sxs-lookup"><span data-stu-id="ac5a4-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="ac5a4-115">Оператор присваивания можно использовать для назначения значения, представленного числового выражения переменной, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     <span data-ttu-id="ac5a4-116">[!code-vb[VbVbalrOperators&#82;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac5a4-116">[!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span></span>  
  
     <span data-ttu-id="ac5a4-117">В предыдущем примере значение выражения в правой части оператора равно (`=`) назначается переменной `j` слева от оператора, поэтому `j` вычисляется как 276.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-117">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="ac5a4-118">Дополнительные сведения см. в разделе [инструкции](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="ac5a4-118">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="ac5a4-119">Несколько операторов</span><span class="sxs-lookup"><span data-stu-id="ac5a4-119">Multiple Operators</span></span>  
 <span data-ttu-id="ac5a4-120">Если числовое выражение содержит несколько операторов, порядок, в котором они вычисляются определяется правилами приоритета операторов.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-120">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="ac5a4-121">Для переопределения правил приоритета операторов выражения заключаются в круглые скобки, как показано в предыдущем примере. такие выражения вычисляются первыми.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-121">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="ac5a4-122">Чтобы переопределить обычный приоритет операторов</span><span class="sxs-lookup"><span data-stu-id="ac5a4-122">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="ac5a4-123">Использование скобок для заключения операции, которые вы хотите сначала необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-123">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="ac5a4-124">В следующем примере показано два разных результата с теми же операндов и операторов.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-124">The following example shows two different results with the same operands and operators.</span></span>  
  
     <span data-ttu-id="ac5a4-125">[!code-vb[VbVbalrOperators&#83;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac5a4-125">[!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span></span>  
  
     <span data-ttu-id="ac5a4-126">В предыдущем примере, то вычисление для `j` выполняет оператор сложения (`+`) первого из-за скобки вокруг `(67 + i)` переопределить обычный приоритет и значение, присваиваемое `j` равно 276 (4 раза по 69).</span><span class="sxs-lookup"><span data-stu-id="ac5a4-126">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="ac5a4-127">Расчет `k` операторы выполняются в обычном порядке (`*` перед `+`) и значение, присваиваемое `k` равно 270 (268 плюс 2).</span><span class="sxs-lookup"><span data-stu-id="ac5a4-127">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="ac5a4-128">Дополнительные сведения см. в разделе [операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="ac5a4-128">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5a4-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ac5a4-129">See Also</span></span>  
 <span data-ttu-id="ac5a4-130">[Операторы и выражения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac5a4-130">[Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span></span>  
<span data-ttu-id="ac5a4-131"> [Сравнение значений](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="ac5a4-131"> [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="ac5a4-132"> [Инструкции](../../../../visual-basic/language-reference/statements/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac5a4-132"> [Statements](../../../../visual-basic/language-reference/statements/index.md) </span></span>  
<span data-ttu-id="ac5a4-133"> [Приоритет операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="ac5a4-133"> [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="ac5a4-134"> [Арифметические операторы](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="ac5a4-134"> [Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="ac5a4-135"> [Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span><span class="sxs-lookup"><span data-stu-id="ac5a4-135"> [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span></span>
