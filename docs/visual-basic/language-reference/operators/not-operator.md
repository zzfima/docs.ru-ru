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
ms.openlocfilehash: 5ebc5f9dbf674a9a6560bd96b3e8c9edcae08a81
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701082"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="7e063-102">Оператор Not (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e063-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="7e063-103">Выполняет логическое отрицание в выражении `Boolean` или побитовое отрицание числового выражения.</span><span class="sxs-lookup"><span data-stu-id="7e063-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e063-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e063-104">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="7e063-105">Части</span><span class="sxs-lookup"><span data-stu-id="7e063-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7e063-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7e063-106">Required.</span></span> <span data-ttu-id="7e063-107">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="7e063-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="7e063-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7e063-108">Required.</span></span> <span data-ttu-id="7e063-109">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="7e063-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e063-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e063-110">Remarks</span></span>  
 <span data-ttu-id="7e063-111">Для выражений `Boolean` в следующей таблице показано, как определяется `result`.</span><span class="sxs-lookup"><span data-stu-id="7e063-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="7e063-112">Если `expression` имеет значение</span><span class="sxs-lookup"><span data-stu-id="7e063-112">If `expression` is</span></span>|<span data-ttu-id="7e063-113">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="7e063-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="7e063-114">Для числовых выражений оператор `Not` инвертирует битовые значения любого числового выражения и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="7e063-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="7e063-115">Если бит в `expression` равен</span><span class="sxs-lookup"><span data-stu-id="7e063-115">If bit in `expression` is</span></span>|<span data-ttu-id="7e063-116">Бит в `result` является</span><span class="sxs-lookup"><span data-stu-id="7e063-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="7e063-117">1</span><span class="sxs-lookup"><span data-stu-id="7e063-117">1</span></span>|<span data-ttu-id="7e063-118">0</span><span class="sxs-lookup"><span data-stu-id="7e063-118">0</span></span>|  
|<span data-ttu-id="7e063-119">0</span><span class="sxs-lookup"><span data-stu-id="7e063-119">0</span></span>|<span data-ttu-id="7e063-120">1</span><span class="sxs-lookup"><span data-stu-id="7e063-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7e063-121">Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.</span><span class="sxs-lookup"><span data-stu-id="7e063-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="7e063-122">Типы данных</span><span class="sxs-lookup"><span data-stu-id="7e063-122">Data Types</span></span>  
 <span data-ttu-id="7e063-123">Для логического отрицания тип данных результата — `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7e063-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="7e063-124">Для побитового отрицания тип данных результата такой же, как и в `expression`.</span><span class="sxs-lookup"><span data-stu-id="7e063-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="7e063-125">Однако если выражение имеет значение `Decimal`, результатом будет `Long`.</span><span class="sxs-lookup"><span data-stu-id="7e063-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7e063-126">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="7e063-126">Overloading</span></span>  
 <span data-ttu-id="7e063-127">Оператор `Not` может быть *перегружен*, что означает, что класс или структура может переопределить его поведение, если его операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="7e063-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="7e063-128">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="7e063-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7e063-129">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7e063-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e063-130">Пример</span><span class="sxs-lookup"><span data-stu-id="7e063-130">Example</span></span>  
 <span data-ttu-id="7e063-131">В следующем примере оператор `Not` используется для выполнения логического отрицания в выражении `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7e063-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="7e063-132">Результатом является значение `Boolean`, представляющее обратный результат выражения.</span><span class="sxs-lookup"><span data-stu-id="7e063-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="7e063-133">В предыдущем примере создаются результаты `False` и `True` соответственно.</span><span class="sxs-lookup"><span data-stu-id="7e063-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e063-134">Пример</span><span class="sxs-lookup"><span data-stu-id="7e063-134">Example</span></span>  
 <span data-ttu-id="7e063-135">В следующем примере оператор `Not` используется для выполнения логического отрицания отдельных битов числового выражения.</span><span class="sxs-lookup"><span data-stu-id="7e063-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="7e063-136">Бит в результирующем шаблоне имеет значение, противоположное соответствующему биту в шаблоне операнда, включая бит знака.</span><span class="sxs-lookup"><span data-stu-id="7e063-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="7e063-137">В предыдущем примере создаются результаты – 11, – 9 и – 7 соответственно.</span><span class="sxs-lookup"><span data-stu-id="7e063-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e063-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7e063-138">See also</span></span>

- [<span data-ttu-id="7e063-139">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e063-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="7e063-140">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e063-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7e063-141">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="7e063-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7e063-142">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e063-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
