---
title: Оператор Or (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 03decb4ad32e8ff2c03e3b64a272bce779282973
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701238"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="d10c1-102">Оператор Or (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10c1-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="d10c1-103">Выполняет логическое сложение двух выражений `Boolean` или побитовое сложение двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="d10c1-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d10c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d10c1-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="d10c1-105">Части</span><span class="sxs-lookup"><span data-stu-id="d10c1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d10c1-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d10c1-106">Required.</span></span> <span data-ttu-id="d10c1-107">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d10c1-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="d10c1-108">Для сравнения `Boolean` `result` является инклюзивным логическим соединением двух значений `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="d10c1-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="d10c1-109">Для побитовых операций `result` — это числовое значение, представляющее включающее побитовое сложение двух числовых битов.</span><span class="sxs-lookup"><span data-stu-id="d10c1-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="d10c1-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d10c1-110">Required.</span></span> <span data-ttu-id="d10c1-111">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d10c1-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="d10c1-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d10c1-112">Required.</span></span> <span data-ttu-id="d10c1-113">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d10c1-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d10c1-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="d10c1-114">Remarks</span></span>  
 <span data-ttu-id="d10c1-115">Для сравнения `Boolean` `result` — `False`, только если оба `expression1` и `expression2` равны `False`.</span><span class="sxs-lookup"><span data-stu-id="d10c1-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="d10c1-116">В следующей таблице показано, как определяется `result`.</span><span class="sxs-lookup"><span data-stu-id="d10c1-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="d10c1-117">Если `expression1` имеет значение</span><span class="sxs-lookup"><span data-stu-id="d10c1-117">If `expression1` is</span></span>|<span data-ttu-id="d10c1-118">И `expression2` является</span><span class="sxs-lookup"><span data-stu-id="d10c1-118">And `expression2` is</span></span>|<span data-ttu-id="d10c1-119">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="d10c1-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="d10c1-120">В сравнении `Boolean` оператор `Or` всегда вычисляет оба выражения, которые могут включать вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="d10c1-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="d10c1-121">[Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет *сокращенное вычисление*, что означает, что если `expression1` имеет `True`, то `expression2` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="d10c1-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="d10c1-122">Для побитовых операций оператор `Or` выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="d10c1-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="d10c1-123">Если бит в `expression1` равен</span><span class="sxs-lookup"><span data-stu-id="d10c1-123">If bit in `expression1` is</span></span>|<span data-ttu-id="d10c1-124">И бит в `expression2` —</span><span class="sxs-lookup"><span data-stu-id="d10c1-124">And bit in `expression2` is</span></span>|<span data-ttu-id="d10c1-125">Бит в `result` является</span><span class="sxs-lookup"><span data-stu-id="d10c1-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="d10c1-126">1</span><span class="sxs-lookup"><span data-stu-id="d10c1-126">1</span></span>|<span data-ttu-id="d10c1-127">1</span><span class="sxs-lookup"><span data-stu-id="d10c1-127">1</span></span>|<span data-ttu-id="d10c1-128">1</span><span class="sxs-lookup"><span data-stu-id="d10c1-128">1</span></span>|  
|<span data-ttu-id="d10c1-129">1</span><span class="sxs-lookup"><span data-stu-id="d10c1-129">1</span></span>|<span data-ttu-id="d10c1-130">0</span><span class="sxs-lookup"><span data-stu-id="d10c1-130">0</span></span>|<span data-ttu-id="d10c1-131">1</span><span class="sxs-lookup"><span data-stu-id="d10c1-131">1</span></span>|  
|<span data-ttu-id="d10c1-132">0</span><span class="sxs-lookup"><span data-stu-id="d10c1-132">0</span></span>|<span data-ttu-id="d10c1-133">1</span><span class="sxs-lookup"><span data-stu-id="d10c1-133">1</span></span>|<span data-ttu-id="d10c1-134">1</span><span class="sxs-lookup"><span data-stu-id="d10c1-134">1</span></span>|  
|<span data-ttu-id="d10c1-135">0</span><span class="sxs-lookup"><span data-stu-id="d10c1-135">0</span></span>|<span data-ttu-id="d10c1-136">0</span><span class="sxs-lookup"><span data-stu-id="d10c1-136">0</span></span>|<span data-ttu-id="d10c1-137">0</span><span class="sxs-lookup"><span data-stu-id="d10c1-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d10c1-138">Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.</span><span class="sxs-lookup"><span data-stu-id="d10c1-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="d10c1-139">Типы данных</span><span class="sxs-lookup"><span data-stu-id="d10c1-139">Data Types</span></span>  
 <span data-ttu-id="d10c1-140">Если операнды состоят из одного выражения `Boolean` и одного числового выражения, Visual Basic преобразует выражение `Boolean` в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="d10c1-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="d10c1-141">Для сравнения `Boolean` тип данных результата `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="d10c1-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="d10c1-142">Для побитового сравнения тип данных результата является числовым типом, подходящим для типов данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="d10c1-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="d10c1-143">См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="d10c1-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d10c1-144">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="d10c1-144">Overloading</span></span>  
 <span data-ttu-id="d10c1-145">Оператор `Or` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d10c1-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d10c1-146">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="d10c1-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d10c1-147">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d10c1-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d10c1-148">Пример</span><span class="sxs-lookup"><span data-stu-id="d10c1-148">Example</span></span>  
 <span data-ttu-id="d10c1-149">В следующем примере оператор `Or` используется для выполнения включающего логического сложения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="d10c1-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="d10c1-150">Результатом является значение `Boolean`, которое показывает, является ли одно из двух выражений `True`.</span><span class="sxs-lookup"><span data-stu-id="d10c1-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="d10c1-151">В предыдущем примере создаются результаты `True`, `True` и `False` соответственно.</span><span class="sxs-lookup"><span data-stu-id="d10c1-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d10c1-152">Пример</span><span class="sxs-lookup"><span data-stu-id="d10c1-152">Example</span></span>  
 <span data-ttu-id="d10c1-153">В следующем примере оператор `Or` используется для выполнения инклюзивного логического сложения по отдельным битам двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="d10c1-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="d10c1-154">Бит в результирующем шаблоне задается, если один из соответствующих битов операндов имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="d10c1-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="d10c1-155">В предыдущем примере выдается результат 10, 14 и 14 соответственно.</span><span class="sxs-lookup"><span data-stu-id="d10c1-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10c1-156">См. также</span><span class="sxs-lookup"><span data-stu-id="d10c1-156">See also</span></span>

- [<span data-ttu-id="d10c1-157">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d10c1-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="d10c1-158">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d10c1-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d10c1-159">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="d10c1-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d10c1-160">Оператор OrElse</span><span class="sxs-lookup"><span data-stu-id="d10c1-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="d10c1-161">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d10c1-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
