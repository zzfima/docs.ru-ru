---
title: Оператор Not (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
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
ms.openlocfilehash: cd93316ada1fcf0997922f71a8efc5a3cf411d09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614619"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="47d42-102">Оператор Not (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47d42-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="47d42-103">Выполняет логическое отрицание `Boolean` выражения или побитовое отрицание в числовом выражении.</span><span class="sxs-lookup"><span data-stu-id="47d42-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d42-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47d42-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="47d42-105">Части</span><span class="sxs-lookup"><span data-stu-id="47d42-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="47d42-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="47d42-106">Required.</span></span> <span data-ttu-id="47d42-107">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="47d42-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="47d42-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="47d42-108">Required.</span></span> <span data-ttu-id="47d42-109">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="47d42-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47d42-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="47d42-110">Remarks</span></span>  
 <span data-ttu-id="47d42-111">Для `Boolean` выражения, в следующей таблице показано как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="47d42-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="47d42-112">Если `expression` —</span><span class="sxs-lookup"><span data-stu-id="47d42-112">If `expression` is</span></span>|<span data-ttu-id="47d42-113">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="47d42-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="47d42-114">Для числовых выражений `Not` оператор инвертирует значения битов числового выражения и устанавливает значение соответствующего бита в `result` согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="47d42-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="47d42-115">Если бит в `expression` —</span><span class="sxs-lookup"><span data-stu-id="47d42-115">If bit in `expression` is</span></span>|<span data-ttu-id="47d42-116">Бит в `result` —</span><span class="sxs-lookup"><span data-stu-id="47d42-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="47d42-117">1</span><span class="sxs-lookup"><span data-stu-id="47d42-117">1</span></span>|<span data-ttu-id="47d42-118">0</span><span class="sxs-lookup"><span data-stu-id="47d42-118">0</span></span>|  
|<span data-ttu-id="47d42-119">0</span><span class="sxs-lookup"><span data-stu-id="47d42-119">0</span></span>|<span data-ttu-id="47d42-120">1</span><span class="sxs-lookup"><span data-stu-id="47d42-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="47d42-121">Поскольку логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, битовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.</span><span class="sxs-lookup"><span data-stu-id="47d42-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="47d42-122">Типы данных</span><span class="sxs-lookup"><span data-stu-id="47d42-122">Data Types</span></span>  
 <span data-ttu-id="47d42-123">Для логического отрицания тип данных результата — `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="47d42-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="47d42-124">Для поразрядного отрицания, тип данных результата будет таким же, как `expression`.</span><span class="sxs-lookup"><span data-stu-id="47d42-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="47d42-125">Тем не менее если выражение является `Decimal`, в результате `Long`.</span><span class="sxs-lookup"><span data-stu-id="47d42-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="47d42-126">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="47d42-126">Overloading</span></span>  
 <span data-ttu-id="47d42-127">`Not` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="47d42-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="47d42-128">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="47d42-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="47d42-129">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="47d42-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="47d42-130">Пример</span><span class="sxs-lookup"><span data-stu-id="47d42-130">Example</span></span>  
 <span data-ttu-id="47d42-131">В следующем примере используется `Not` оператор логического отрицания `Boolean` выражение.</span><span class="sxs-lookup"><span data-stu-id="47d42-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="47d42-132">В результате `Boolean` значение, которое представляет обратное значение выражения.</span><span class="sxs-lookup"><span data-stu-id="47d42-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="47d42-133">В предыдущем примере получался результат `False` и `True`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="47d42-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47d42-134">Пример</span><span class="sxs-lookup"><span data-stu-id="47d42-134">Example</span></span>  
 <span data-ttu-id="47d42-135">В следующем примере используется `Not` оператор для выполнения логического отрицания отдельных битов числового выражения.</span><span class="sxs-lookup"><span data-stu-id="47d42-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="47d42-136">Бит в шаблоне результат присваивается обратное соответствующий бит в шаблоне операнда, включая бит знака.</span><span class="sxs-lookup"><span data-stu-id="47d42-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="47d42-137">В предыдущем примере получался результаты – 11, – 9 и – 7 соответственно.</span><span class="sxs-lookup"><span data-stu-id="47d42-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d42-138">См. также</span><span class="sxs-lookup"><span data-stu-id="47d42-138">See also</span></span>
- [<span data-ttu-id="47d42-139">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47d42-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="47d42-140">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47d42-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="47d42-141">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="47d42-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="47d42-142">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47d42-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
