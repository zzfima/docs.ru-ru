---
title: "Операторы и выражения в Visual Basic"
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
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands, definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
caps.latest.revision: 18
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3675af3ac8a0a80b5fb5f208c1679dc28ab77acf
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="operators-and-expressions-in-visual-basic"></a><span data-ttu-id="18c2c-102">Операторы и выражения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18c2c-102">Operators and Expressions in Visual Basic</span></span>
<span data-ttu-id="18c2c-103">*Оператор* представляет собой элемент кода, который выполняет операцию с одним элементом кода или несколькими, содержащими значения.</span><span class="sxs-lookup"><span data-stu-id="18c2c-103">An *operator* is a code element that performs an operation on one or more code elements that hold values.</span></span> <span data-ttu-id="18c2c-104">К элементам значений относятся переменные, константы, литералы, свойства, возвращаемые значения из процедур `Function` и `Operator`, а также выражения.</span><span class="sxs-lookup"><span data-stu-id="18c2c-104">Value elements include variables, constants, literals, properties, returns from `Function` and `Operator` procedures, and expressions.</span></span>  
  
 <span data-ttu-id="18c2c-105">*Выражение* представляет собой набор элементов значений в сочетании с операторами, результатом которого является новое значение.</span><span class="sxs-lookup"><span data-stu-id="18c2c-105">An *expression* is a series of value elements combined with operators, which yields a new value.</span></span> <span data-ttu-id="18c2c-106">Операторы работают с элементами значений, выполняя вычисления, сравнения и другие операции.</span><span class="sxs-lookup"><span data-stu-id="18c2c-106">The operators act on the value elements by performing calculations, comparisons, or other operations.</span></span>  
  
## <a name="types-of-operators"></a><span data-ttu-id="18c2c-107">Типы операторов</span><span class="sxs-lookup"><span data-stu-id="18c2c-107">Types of Operators</span></span>  
 <span data-ttu-id="18c2c-108">В [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] доступны следующие типы операторов:</span><span class="sxs-lookup"><span data-stu-id="18c2c-108">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] provides the following types of operators:</span></span>  
  
-   <span data-ttu-id="18c2c-109">[Арифметические операторы](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) выполняют обычные вычисления с числовыми значениями, включая сдвиг их битовых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="18c2c-109">[Arithmetic Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) perform familiar calculations on numeric values, including shifting their bit patterns.</span></span>  
  
-   <span data-ttu-id="18c2c-110">[Операторы сравнения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) сравнивают два выражения и возвращают значение `Boolean`, соответствующее результату сравнения.</span><span class="sxs-lookup"><span data-stu-id="18c2c-110">[Comparison Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) compare two expressions and return a `Boolean` value representing the result of the comparison.</span></span>  
  
-   <span data-ttu-id="18c2c-111">[Операторы объединения](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) соединяют несколько строк в одну.</span><span class="sxs-lookup"><span data-stu-id="18c2c-111">[Concatenation Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) join multiple strings into a single string.</span></span>  
  
-   <span data-ttu-id="18c2c-112">[Логические и побитовые операторы в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) объединяют `Boolean` или числовые значения и возвращают результат того же типа данных, что и значения.</span><span class="sxs-lookup"><span data-stu-id="18c2c-112">[Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combine `Boolean` or numeric values and return a result of the same data type as the values.</span></span>  
  
 <span data-ttu-id="18c2c-113">Элементы значений, объединенные с оператором, называются *операндами* этого оператора.</span><span class="sxs-lookup"><span data-stu-id="18c2c-113">The value elements that are combined with an operator are called *operands* of that operator.</span></span> <span data-ttu-id="18c2c-114">Операторы, объединенные с элементами значений, формируют выражения. Исключением является оператор присваивания, который образует *инструкцию*.</span><span class="sxs-lookup"><span data-stu-id="18c2c-114">Operators combined with value elements form expressions, except for the assignment operator, which forms a *statement*.</span></span> <span data-ttu-id="18c2c-115">Дополнительные сведения см. в разделе [Выписки](../../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="18c2c-115">For more information, see [Statements](../../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
## <a name="evaluation-of-expressions"></a><span data-ttu-id="18c2c-116">Вычисление выражений</span><span class="sxs-lookup"><span data-stu-id="18c2c-116">Evaluation of Expressions</span></span>  
 <span data-ttu-id="18c2c-117">Конечный результат выражения представляет собой значение, которое обычно имеет знакомый тип данных, например `Boolean`, `String` или числовой тип.</span><span class="sxs-lookup"><span data-stu-id="18c2c-117">The end result of an expression represents a value, which is typically of a familiar data type such as `Boolean`, `String`, or a numeric type.</span></span>  
  
 <span data-ttu-id="18c2c-118">Ниже приведены примеры выражений.</span><span class="sxs-lookup"><span data-stu-id="18c2c-118">The following are examples of expressions.</span></span>  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 <span data-ttu-id="18c2c-119">Несколько операторов могут выполнять действия в одном выражении или инструкции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="18c2c-119">Several operators can perform actions in a single expression or statement, as the following example illustrates.</span></span>  
  
 <span data-ttu-id="18c2c-120">[!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="18c2c-120">[!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]</span></span>  
  
 <span data-ttu-id="18c2c-121">В приведенном выше примере [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] выполняет операции, содержащиеся в выражении из правой части оператора присваивания (`=`), а затем присваивает результирующее значение переменной `x` в левой части.</span><span class="sxs-lookup"><span data-stu-id="18c2c-121">In the preceding example, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] performs the operations in the expression on the right side of the assignment operator (`=`), then assigns the resulting value to the variable `x` on the left.</span></span> <span data-ttu-id="18c2c-122">С практической точки зрения в выражение можно объединять сколько угодно операторов, но следует учитывать [приоритет операторов в Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) для получения желаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="18c2c-122">There is no practical limit to the number of operators that can be combined into an expression, but an understanding of [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) is necessary to ensure that you get the results you expect.</span></span>  
  
 <span data-ttu-id="18c2c-123">Дополнительные сведения и примеры см. в разделе [Перегрузка операторов в Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span><span class="sxs-lookup"><span data-stu-id="18c2c-123">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c2c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="18c2c-124">See Also</span></span>  
 <span data-ttu-id="18c2c-125">[Операторы](../../../../visual-basic/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="18c2c-125">[Operators](../../../../visual-basic/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="18c2c-126">[Эффективное сочетание операторов](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md) </span><span class="sxs-lookup"><span data-stu-id="18c2c-126">[Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md) </span></span>  
 [<span data-ttu-id="18c2c-127">Операторы</span><span class="sxs-lookup"><span data-stu-id="18c2c-127">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)

