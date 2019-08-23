---
title: Оператор Xor (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: 59f27b92996e1506be5967de88c22fb88e06f5b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965846"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="c05b8-102">Оператор Xor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c05b8-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="c05b8-103">Выполняет логическое исключение для двух `Boolean` выражений или побитовое исключение для двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="c05b8-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c05b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c05b8-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c05b8-105">Части</span><span class="sxs-lookup"><span data-stu-id="c05b8-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c05b8-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c05b8-106">Required.</span></span> <span data-ttu-id="c05b8-107">Любая `Boolean` или числовая переменная.</span><span class="sxs-lookup"><span data-stu-id="c05b8-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="c05b8-108">Для логического сравнения `result` — это логическое исключение (исключающее логическое сложение) двух `Boolean` значений.</span><span class="sxs-lookup"><span data-stu-id="c05b8-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="c05b8-109">Для битовых операций `result` — это числовое значение, представляющее побитовое исключение (исключающее побитовое сложение) двух числовых битов.</span><span class="sxs-lookup"><span data-stu-id="c05b8-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="c05b8-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c05b8-110">Required.</span></span> <span data-ttu-id="c05b8-111">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="c05b8-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="c05b8-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c05b8-112">Required.</span></span> <span data-ttu-id="c05b8-113">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="c05b8-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c05b8-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="c05b8-114">Remarks</span></span>  
 <span data-ttu-id="c05b8-115">Для логического сравнения `result` параметр имеет `True` значение, только `expression2` если в `True`точности один `expression1` из значений равен.</span><span class="sxs-lookup"><span data-stu-id="c05b8-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="c05b8-116">То есть, если и только если `expression1` и `expression2` имеют противоположные `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="c05b8-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="c05b8-117">В следующей таблице показано, `result` как определяется.</span><span class="sxs-lookup"><span data-stu-id="c05b8-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c05b8-118">Если `expression1` имеет значение</span><span class="sxs-lookup"><span data-stu-id="c05b8-118">If `expression1` is</span></span>|<span data-ttu-id="c05b8-119">И `expression2` является</span><span class="sxs-lookup"><span data-stu-id="c05b8-119">And `expression2` is</span></span>|<span data-ttu-id="c05b8-120">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="c05b8-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="c05b8-121">При логическом сравнении `Xor` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="c05b8-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="c05b8-122">Не существует аналога `Xor`сокращенного выражения, поскольку результат всегда зависит от обоих операндов.</span><span class="sxs-lookup"><span data-stu-id="c05b8-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="c05b8-123">Дополнительные операторы для сокращенного вычисления логических операторов см. в разделе [оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) и [оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c05b8-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="c05b8-124">Для побитовых операций `Xor` оператор выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="c05b8-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="c05b8-125">Если бит в `expression1` имеет значение</span><span class="sxs-lookup"><span data-stu-id="c05b8-125">If bit in `expression1` is</span></span>|<span data-ttu-id="c05b8-126">И bit в `expression2` имеет</span><span class="sxs-lookup"><span data-stu-id="c05b8-126">And bit in `expression2` is</span></span>|<span data-ttu-id="c05b8-127">Бит в `result` имеет значение</span><span class="sxs-lookup"><span data-stu-id="c05b8-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="c05b8-128">1</span><span class="sxs-lookup"><span data-stu-id="c05b8-128">1</span></span>|<span data-ttu-id="c05b8-129">1</span><span class="sxs-lookup"><span data-stu-id="c05b8-129">1</span></span>|<span data-ttu-id="c05b8-130">0</span><span class="sxs-lookup"><span data-stu-id="c05b8-130">0</span></span>|  
|<span data-ttu-id="c05b8-131">1</span><span class="sxs-lookup"><span data-stu-id="c05b8-131">1</span></span>|<span data-ttu-id="c05b8-132">0</span><span class="sxs-lookup"><span data-stu-id="c05b8-132">0</span></span>|<span data-ttu-id="c05b8-133">1</span><span class="sxs-lookup"><span data-stu-id="c05b8-133">1</span></span>|  
|<span data-ttu-id="c05b8-134">0</span><span class="sxs-lookup"><span data-stu-id="c05b8-134">0</span></span>|<span data-ttu-id="c05b8-135">1</span><span class="sxs-lookup"><span data-stu-id="c05b8-135">1</span></span>|<span data-ttu-id="c05b8-136">1</span><span class="sxs-lookup"><span data-stu-id="c05b8-136">1</span></span>|  
|<span data-ttu-id="c05b8-137">0</span><span class="sxs-lookup"><span data-stu-id="c05b8-137">0</span></span>|<span data-ttu-id="c05b8-138">0</span><span class="sxs-lookup"><span data-stu-id="c05b8-138">0</span></span>|<span data-ttu-id="c05b8-139">0</span><span class="sxs-lookup"><span data-stu-id="c05b8-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c05b8-140">Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.</span><span class="sxs-lookup"><span data-stu-id="c05b8-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="c05b8-141">Например, 5 `Xor` 3 — 6.</span><span class="sxs-lookup"><span data-stu-id="c05b8-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="c05b8-142">Чтобы узнать, почему это так, преобразуйте значения 5 и 3 в двоичные представления, 101 и 011.</span><span class="sxs-lookup"><span data-stu-id="c05b8-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="c05b8-143">Затем используйте предыдущую таблицу, чтобы определить, что 101 Xor 011 имеет значение 110, которое является двоичным представлением десятичного числа 6.</span><span class="sxs-lookup"><span data-stu-id="c05b8-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="c05b8-144">Типы данных</span><span class="sxs-lookup"><span data-stu-id="c05b8-144">Data Types</span></span>  
 <span data-ttu-id="c05b8-145">`Boolean` Если операнды состоят из одного выражения и одного числового выражения, Visual Basic `Boolean` преобразует выражение в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="c05b8-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="c05b8-146">Для сравнения тип данных результата — `Boolean`. `Boolean`</span><span class="sxs-lookup"><span data-stu-id="c05b8-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="c05b8-147">Для побитового сравнения тип данных результата является числовым типом, подходящим для типов `expression1` данных и. `expression2`</span><span class="sxs-lookup"><span data-stu-id="c05b8-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="c05b8-148">См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="c05b8-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c05b8-149">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="c05b8-149">Overloading</span></span>  
 <span data-ttu-id="c05b8-150">Оператор можно перегрузить, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. `Xor`</span><span class="sxs-lookup"><span data-stu-id="c05b8-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c05b8-151">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="c05b8-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="c05b8-152">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c05b8-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c05b8-153">Пример</span><span class="sxs-lookup"><span data-stu-id="c05b8-153">Example</span></span>  
 <span data-ttu-id="c05b8-154">В следующем примере `Xor` оператор используется для выполнения логического исключения (исключающее логическое сложение) в двух выражениях.</span><span class="sxs-lookup"><span data-stu-id="c05b8-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="c05b8-155">Результатом является `Boolean` значение, указывающее, имеет `True`ли только одно из выражений.</span><span class="sxs-lookup"><span data-stu-id="c05b8-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="c05b8-156">В предыдущем примере создаются результаты `False`, `True`и `False`соответственно.</span><span class="sxs-lookup"><span data-stu-id="c05b8-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c05b8-157">Пример</span><span class="sxs-lookup"><span data-stu-id="c05b8-157">Example</span></span>  
 <span data-ttu-id="c05b8-158">В следующем примере `Xor` оператор используется для выполнения логического исключения (исключающее логическое сложение) для отдельных битов двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="c05b8-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="c05b8-159">Бит в результирующем шаблоне устанавливается, если только один из соответствующих битов операндов имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="c05b8-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="c05b8-160">В предыдущем примере выдается результат 2, 12 и 14 соответственно.</span><span class="sxs-lookup"><span data-stu-id="c05b8-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c05b8-161">См. также</span><span class="sxs-lookup"><span data-stu-id="c05b8-161">See also</span></span>

- [<span data-ttu-id="c05b8-162">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c05b8-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="c05b8-163">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c05b8-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c05b8-164">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="c05b8-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c05b8-165">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c05b8-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
