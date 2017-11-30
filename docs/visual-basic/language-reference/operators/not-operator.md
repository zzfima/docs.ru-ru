---
title: "Оператор Not (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac160aef7b7dc8acb8bf0211b403599692f2373c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="8c17e-102">Оператор Not (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c17e-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="8c17e-103">Выполняет логическое отрицание `Boolean` выражения или побитовое отрицание в числовом выражении.</span><span class="sxs-lookup"><span data-stu-id="8c17e-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c17e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c17e-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="8c17e-105">Части</span><span class="sxs-lookup"><span data-stu-id="8c17e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="8c17e-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8c17e-106">Required.</span></span> <span data-ttu-id="8c17e-107">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="8c17e-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="8c17e-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8c17e-108">Required.</span></span> <span data-ttu-id="8c17e-109">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="8c17e-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c17e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c17e-110">Remarks</span></span>  
 <span data-ttu-id="8c17e-111">Для `Boolean` выражения, в следующей таблице показано как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="8c17e-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8c17e-112">Если `expression` является</span><span class="sxs-lookup"><span data-stu-id="8c17e-112">If `expression` is</span></span>|<span data-ttu-id="8c17e-113">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="8c17e-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="8c17e-114">Для числовых выражений `Not` оператор инвертирует значения битов числового выражения и задает соответствующий бит в `result` согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8c17e-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="8c17e-115">Если бит в `expression` —</span><span class="sxs-lookup"><span data-stu-id="8c17e-115">If bit in `expression` is</span></span>|<span data-ttu-id="8c17e-116">Бит в `result` —</span><span class="sxs-lookup"><span data-stu-id="8c17e-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="8c17e-117">1</span><span class="sxs-lookup"><span data-stu-id="8c17e-117">1</span></span>|<span data-ttu-id="8c17e-118">0</span><span class="sxs-lookup"><span data-stu-id="8c17e-118">0</span></span>|  
|<span data-ttu-id="8c17e-119">0</span><span class="sxs-lookup"><span data-stu-id="8c17e-119">0</span></span>|<span data-ttu-id="8c17e-120">1</span><span class="sxs-lookup"><span data-stu-id="8c17e-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8c17e-121">Поскольку логические и битовые операторы имеют более низкий приоритет, чем другие арифметических операторов и операторов отношения, побитовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.</span><span class="sxs-lookup"><span data-stu-id="8c17e-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="8c17e-122">Типы данных</span><span class="sxs-lookup"><span data-stu-id="8c17e-122">Data Types</span></span>  
 <span data-ttu-id="8c17e-123">Для логического отрицания тип данных результата является `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8c17e-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="8c17e-124">Для поразрядного отрицания, тип данных результата относится так же, как `expression`.</span><span class="sxs-lookup"><span data-stu-id="8c17e-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="8c17e-125">Тем не менее если выражение является `Decimal`, в результате `Long`.</span><span class="sxs-lookup"><span data-stu-id="8c17e-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8c17e-126">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="8c17e-126">Overloading</span></span>  
 <span data-ttu-id="8c17e-127">`Not` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="8c17e-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="8c17e-128">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="8c17e-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8c17e-129">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8c17e-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c17e-130">Пример</span><span class="sxs-lookup"><span data-stu-id="8c17e-130">Example</span></span>  
 <span data-ttu-id="8c17e-131">В следующем примере используется `Not` оператор логического отрицания `Boolean` выражение.</span><span class="sxs-lookup"><span data-stu-id="8c17e-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="8c17e-132">В результате `Boolean` значение, представляющее обратное значение выражения.</span><span class="sxs-lookup"><span data-stu-id="8c17e-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="8c17e-133">В предыдущем примере получаются результаты `False` и `True`соответственно.</span><span class="sxs-lookup"><span data-stu-id="8c17e-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c17e-134">Пример</span><span class="sxs-lookup"><span data-stu-id="8c17e-134">Example</span></span>  
 <span data-ttu-id="8c17e-135">В следующем примере используется `Not` оператор для выполнения логического отрицания отдельных битов числового выражения.</span><span class="sxs-lookup"><span data-stu-id="8c17e-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="8c17e-136">Бит в шаблоне результат присваивается обратное соответствующий бит в шаблоне операнда, включая бит знака.</span><span class="sxs-lookup"><span data-stu-id="8c17e-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="8c17e-137">В предыдущем примере получаются результаты – 11, – 9 и – 7 соответственно.</span><span class="sxs-lookup"><span data-stu-id="8c17e-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c17e-138">См. также</span><span class="sxs-lookup"><span data-stu-id="8c17e-138">See Also</span></span>  
 [<span data-ttu-id="8c17e-139">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c17e-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="8c17e-140">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c17e-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="8c17e-141">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="8c17e-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="8c17e-142">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c17e-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
