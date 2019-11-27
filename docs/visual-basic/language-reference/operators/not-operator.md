---
title: Оператор Not
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
ms.openlocfilehash: 08b091ccf6c50438b5ad9d6c445510112abe7418
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348299"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="f0ce8-102">Оператор Not (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0ce8-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="f0ce8-103">Выполняет логическое отрицание в выражении `Boolean` или побитовое отрицание в числовом выражении.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ce8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0ce8-104">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="f0ce8-105">Части</span><span class="sxs-lookup"><span data-stu-id="f0ce8-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f0ce8-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-106">Required.</span></span> <span data-ttu-id="f0ce8-107">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="f0ce8-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-108">Required.</span></span> <span data-ttu-id="f0ce8-109">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0ce8-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0ce8-110">Remarks</span></span>  
 <span data-ttu-id="f0ce8-111">Для `Boolean` выражений в следующей таблице показано, как определяется `result`.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="f0ce8-112">Если `expression`</span><span class="sxs-lookup"><span data-stu-id="f0ce8-112">If `expression` is</span></span>|<span data-ttu-id="f0ce8-113">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="f0ce8-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="f0ce8-114">Для числовых выражений оператор `Not` инвертирует битовые значения любого числового выражения и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="f0ce8-115">Если бит в `expression` имеет значение</span><span class="sxs-lookup"><span data-stu-id="f0ce8-115">If bit in `expression` is</span></span>|<span data-ttu-id="f0ce8-116">Бит в `result`</span><span class="sxs-lookup"><span data-stu-id="f0ce8-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="f0ce8-117">1</span><span class="sxs-lookup"><span data-stu-id="f0ce8-117">1</span></span>|<span data-ttu-id="f0ce8-118">0</span><span class="sxs-lookup"><span data-stu-id="f0ce8-118">0</span></span>|  
|<span data-ttu-id="f0ce8-119">0</span><span class="sxs-lookup"><span data-stu-id="f0ce8-119">0</span></span>|<span data-ttu-id="f0ce8-120">1</span><span class="sxs-lookup"><span data-stu-id="f0ce8-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f0ce8-121">Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="f0ce8-122">Типы данных</span><span class="sxs-lookup"><span data-stu-id="f0ce8-122">Data Types</span></span>  
 <span data-ttu-id="f0ce8-123">Для логического отрицания тип данных результата `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="f0ce8-124">Для побитового отрицания тип данных результата такой же, как у `expression`.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="f0ce8-125">Однако если выражение `Decimal`, результатом будет `Long`.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f0ce8-126">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="f0ce8-126">Overloading</span></span>  
 <span data-ttu-id="f0ce8-127">Оператор `Not` может быть *перегружен*, а это означает, что класс или структура могут переопределять свое поведение, когда его операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="f0ce8-128">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f0ce8-129">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f0ce8-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0ce8-130">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ce8-130">Example</span></span>  
 <span data-ttu-id="f0ce8-131">В следующем примере оператор `Not` используется для выполнения логического отрицания в выражении `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="f0ce8-132">Результатом является `Boolean` значение, представляющее обратную величину значения выражения.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="f0ce8-133">В предыдущем примере создаются результаты `False` и `True`соответственно.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0ce8-134">Пример</span><span class="sxs-lookup"><span data-stu-id="f0ce8-134">Example</span></span>  
 <span data-ttu-id="f0ce8-135">В следующем примере оператор `Not` используется для выполнения логического отрицания отдельных битов числового выражения.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="f0ce8-136">Бит в результирующем шаблоне имеет значение, противоположное соответствующему биту в шаблоне операнда, включая бит знака.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="f0ce8-137">В предыдущем примере создаются результаты – 11, – 9 и – 7 соответственно.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ce8-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f0ce8-138">See also</span></span>

- [<span data-ttu-id="f0ce8-139">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0ce8-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="f0ce8-140">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0ce8-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f0ce8-141">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="f0ce8-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f0ce8-142">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0ce8-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
