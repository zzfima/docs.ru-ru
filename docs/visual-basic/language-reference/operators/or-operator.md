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
ms.openlocfilehash: 1d11a6d009f6ecfea9fb1a86b00c67b87d5555dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955843"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="d5aff-102">Оператор Or (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5aff-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="d5aff-103">Выполняет логическое сложение двух `Boolean` выражений или побитовое сложение двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="d5aff-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5aff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5aff-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="d5aff-105">Части</span><span class="sxs-lookup"><span data-stu-id="d5aff-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d5aff-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d5aff-106">Required.</span></span> <span data-ttu-id="d5aff-107">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d5aff-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="d5aff-108">Для `Boolean` `Boolean` сравнения —этовключающеелогическоесложениедвухзначений.`result`</span><span class="sxs-lookup"><span data-stu-id="d5aff-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="d5aff-109">Для битовых операций `result` — это числовое значение, представляющее включающее побитовое сложение двух числовых битов.</span><span class="sxs-lookup"><span data-stu-id="d5aff-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="d5aff-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d5aff-110">Required.</span></span> <span data-ttu-id="d5aff-111">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d5aff-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="d5aff-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d5aff-112">Required.</span></span> <span data-ttu-id="d5aff-113">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="d5aff-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5aff-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5aff-114">Remarks</span></span>  
 <span data-ttu-id="d5aff-115">Для `Boolean` сравнения параметр `result` имеет `False` значение, только если оба `expression1` значения `expression2` и имеют `False`значение.</span><span class="sxs-lookup"><span data-stu-id="d5aff-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="d5aff-116">В следующей таблице показано, `result` как определяется.</span><span class="sxs-lookup"><span data-stu-id="d5aff-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="d5aff-117">Если `expression1` имеет значение</span><span class="sxs-lookup"><span data-stu-id="d5aff-117">If `expression1` is</span></span>|<span data-ttu-id="d5aff-118">И `expression2` является</span><span class="sxs-lookup"><span data-stu-id="d5aff-118">And `expression2` is</span></span>|<span data-ttu-id="d5aff-119">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="d5aff-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="d5aff-120">В сравнении `Or` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур. `Boolean`</span><span class="sxs-lookup"><span data-stu-id="d5aff-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="d5aff-121">[Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет сокращенное *Вычисление*, означающее, что `expression1` если имеет значение `True`, то `expression2` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="d5aff-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="d5aff-122">Для побитовых операций `Or` оператор выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="d5aff-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="d5aff-123">Если бит в `expression1` имеет значение</span><span class="sxs-lookup"><span data-stu-id="d5aff-123">If bit in `expression1` is</span></span>|<span data-ttu-id="d5aff-124">И bit в `expression2` имеет</span><span class="sxs-lookup"><span data-stu-id="d5aff-124">And bit in `expression2` is</span></span>|<span data-ttu-id="d5aff-125">Бит в `result` имеет значение</span><span class="sxs-lookup"><span data-stu-id="d5aff-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="d5aff-126">1</span><span class="sxs-lookup"><span data-stu-id="d5aff-126">1</span></span>|<span data-ttu-id="d5aff-127">1</span><span class="sxs-lookup"><span data-stu-id="d5aff-127">1</span></span>|<span data-ttu-id="d5aff-128">1</span><span class="sxs-lookup"><span data-stu-id="d5aff-128">1</span></span>|  
|<span data-ttu-id="d5aff-129">1</span><span class="sxs-lookup"><span data-stu-id="d5aff-129">1</span></span>|<span data-ttu-id="d5aff-130">0</span><span class="sxs-lookup"><span data-stu-id="d5aff-130">0</span></span>|<span data-ttu-id="d5aff-131">1</span><span class="sxs-lookup"><span data-stu-id="d5aff-131">1</span></span>|  
|<span data-ttu-id="d5aff-132">0</span><span class="sxs-lookup"><span data-stu-id="d5aff-132">0</span></span>|<span data-ttu-id="d5aff-133">1</span><span class="sxs-lookup"><span data-stu-id="d5aff-133">1</span></span>|<span data-ttu-id="d5aff-134">1</span><span class="sxs-lookup"><span data-stu-id="d5aff-134">1</span></span>|  
|<span data-ttu-id="d5aff-135">0</span><span class="sxs-lookup"><span data-stu-id="d5aff-135">0</span></span>|<span data-ttu-id="d5aff-136">0</span><span class="sxs-lookup"><span data-stu-id="d5aff-136">0</span></span>|<span data-ttu-id="d5aff-137">0</span><span class="sxs-lookup"><span data-stu-id="d5aff-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d5aff-138">Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.</span><span class="sxs-lookup"><span data-stu-id="d5aff-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="d5aff-139">Типы данных</span><span class="sxs-lookup"><span data-stu-id="d5aff-139">Data Types</span></span>  
 <span data-ttu-id="d5aff-140">`Boolean` Если операнды состоят из одного выражения и одного числового выражения, Visual Basic `Boolean` преобразует выражение в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="d5aff-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="d5aff-141">Для сравнения тип данных результата — `Boolean`. `Boolean`</span><span class="sxs-lookup"><span data-stu-id="d5aff-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="d5aff-142">Для побитового сравнения тип данных результата является числовым типом, подходящим для типов `expression1` данных и. `expression2`</span><span class="sxs-lookup"><span data-stu-id="d5aff-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="d5aff-143">См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="d5aff-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d5aff-144">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="d5aff-144">Overloading</span></span>  
 <span data-ttu-id="d5aff-145">Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `Or`</span><span class="sxs-lookup"><span data-stu-id="d5aff-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d5aff-146">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="d5aff-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d5aff-147">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d5aff-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5aff-148">Пример</span><span class="sxs-lookup"><span data-stu-id="d5aff-148">Example</span></span>  
 <span data-ttu-id="d5aff-149">В следующем примере `Or` оператор используется для выполнения включающего логического сложения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="d5aff-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="d5aff-150">Результатом является `Boolean` значение, которое представляет, является `True`ли одно из двух выражений.</span><span class="sxs-lookup"><span data-stu-id="d5aff-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="d5aff-151">В предыдущем примере создаются результаты `True`, `True`и `False`соответственно.</span><span class="sxs-lookup"><span data-stu-id="d5aff-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5aff-152">Пример</span><span class="sxs-lookup"><span data-stu-id="d5aff-152">Example</span></span>  
 <span data-ttu-id="d5aff-153">В следующем примере `Or` оператор используется для выполнения инклюзивного логического сложения по отдельным битам двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="d5aff-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="d5aff-154">Бит в результирующем шаблоне задается, если один из соответствующих битов операндов имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="d5aff-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="d5aff-155">В предыдущем примере выдается результат 10, 14 и 14 соответственно.</span><span class="sxs-lookup"><span data-stu-id="d5aff-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5aff-156">См. также</span><span class="sxs-lookup"><span data-stu-id="d5aff-156">See also</span></span>

- [<span data-ttu-id="d5aff-157">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5aff-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="d5aff-158">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5aff-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d5aff-159">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="d5aff-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d5aff-160">Оператор OrElse</span><span class="sxs-lookup"><span data-stu-id="d5aff-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="d5aff-161">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5aff-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
