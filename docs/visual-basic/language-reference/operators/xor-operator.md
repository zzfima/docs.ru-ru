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
ms.openlocfilehash: af6589206232f01b572cd2b965ba1a0f36d462e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527124"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="7daf5-102">Оператор Xor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7daf5-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="7daf5-103">Выполняет логическое исключение над двумя `Boolean` выражений или побитовое Вычитание двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="7daf5-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7daf5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7daf5-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="7daf5-105">Части</span><span class="sxs-lookup"><span data-stu-id="7daf5-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7daf5-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7daf5-106">Required.</span></span> <span data-ttu-id="7daf5-107">Любой `Boolean` или числовой переменной.</span><span class="sxs-lookup"><span data-stu-id="7daf5-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="7daf5-108">Для логического сравнения `result` является логическое исключение (исключающая логическая дизъюнкция) из двух `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="7daf5-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="7daf5-109">Для битовых операций: `result` — это числовое значение, представляющее (поразрядной исключающей побитовое дизъюнкции) из двум битовым шаблонам чисел.</span><span class="sxs-lookup"><span data-stu-id="7daf5-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="7daf5-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7daf5-110">Required.</span></span> <span data-ttu-id="7daf5-111">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="7daf5-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="7daf5-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="7daf5-112">Required.</span></span> <span data-ttu-id="7daf5-113">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="7daf5-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7daf5-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="7daf5-114">Remarks</span></span>  
 <span data-ttu-id="7daf5-115">Логическое сравнение `result` — `True` , только если задан только один из `expression1` и `expression2` принимает значение `True`.</span><span class="sxs-lookup"><span data-stu-id="7daf5-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="7daf5-116">То есть, только если `expression1` и `expression2` оценки на противоположном `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="7daf5-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="7daf5-117">В следующей таблице показано как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="7daf5-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="7daf5-118">Если `expression1` —</span><span class="sxs-lookup"><span data-stu-id="7daf5-118">If `expression1` is</span></span>|<span data-ttu-id="7daf5-119">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="7daf5-119">And `expression2` is</span></span>|<span data-ttu-id="7daf5-120">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="7daf5-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="7daf5-121">В логическое сравнение `Xor` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедуры.</span><span class="sxs-lookup"><span data-stu-id="7daf5-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="7daf5-122">Имеется не сокращенной обработки аналогом `Xor`, так как результат всегда зависит от обоих операндов.</span><span class="sxs-lookup"><span data-stu-id="7daf5-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="7daf5-123">Для *сокращенного вычисления* логические операторы, см. в разделе [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) и [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7daf5-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="7daf5-124">Для битовых операций: `Xor` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7daf5-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="7daf5-125">Если бит в `expression1` —</span><span class="sxs-lookup"><span data-stu-id="7daf5-125">If bit in `expression1` is</span></span>|<span data-ttu-id="7daf5-126">И бит в `expression2` —</span><span class="sxs-lookup"><span data-stu-id="7daf5-126">And bit in `expression2` is</span></span>|<span data-ttu-id="7daf5-127">Бит в `result` —</span><span class="sxs-lookup"><span data-stu-id="7daf5-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="7daf5-128">1</span><span class="sxs-lookup"><span data-stu-id="7daf5-128">1</span></span>|<span data-ttu-id="7daf5-129">1</span><span class="sxs-lookup"><span data-stu-id="7daf5-129">1</span></span>|<span data-ttu-id="7daf5-130">0</span><span class="sxs-lookup"><span data-stu-id="7daf5-130">0</span></span>|  
|<span data-ttu-id="7daf5-131">1</span><span class="sxs-lookup"><span data-stu-id="7daf5-131">1</span></span>|<span data-ttu-id="7daf5-132">0</span><span class="sxs-lookup"><span data-stu-id="7daf5-132">0</span></span>|<span data-ttu-id="7daf5-133">1</span><span class="sxs-lookup"><span data-stu-id="7daf5-133">1</span></span>|  
|<span data-ttu-id="7daf5-134">0</span><span class="sxs-lookup"><span data-stu-id="7daf5-134">0</span></span>|<span data-ttu-id="7daf5-135">1</span><span class="sxs-lookup"><span data-stu-id="7daf5-135">1</span></span>|<span data-ttu-id="7daf5-136">1</span><span class="sxs-lookup"><span data-stu-id="7daf5-136">1</span></span>|  
|<span data-ttu-id="7daf5-137">0</span><span class="sxs-lookup"><span data-stu-id="7daf5-137">0</span></span>|<span data-ttu-id="7daf5-138">0</span><span class="sxs-lookup"><span data-stu-id="7daf5-138">0</span></span>|<span data-ttu-id="7daf5-139">0</span><span class="sxs-lookup"><span data-stu-id="7daf5-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7daf5-140">Поскольку логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, битовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.</span><span class="sxs-lookup"><span data-stu-id="7daf5-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="7daf5-141">Например, 5 `Xor` 3 — 6.</span><span class="sxs-lookup"><span data-stu-id="7daf5-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="7daf5-142">Чтобы узнать, почему это так, преобразуем 5 и 3 в двоичное представление, 101 и 011.</span><span class="sxs-lookup"><span data-stu-id="7daf5-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="7daf5-143">Воспользуйтесь приведенной выше таблице, чтобы определить, что 101 Xor 011-110, являющееся двоичное представление десятичного числа 6.</span><span class="sxs-lookup"><span data-stu-id="7daf5-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="7daf5-144">Типы данных</span><span class="sxs-lookup"><span data-stu-id="7daf5-144">Data Types</span></span>  
 <span data-ttu-id="7daf5-145">Если операнды состоять из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразуют `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="7daf5-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="7daf5-146">Для `Boolean` имеет тип данных результата сравнения, `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7daf5-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="7daf5-147">Побитовое сравнение, тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="7daf5-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="7daf5-148">См. в таблице «Реляционные и побитовое сравнение» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="7daf5-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7daf5-149">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="7daf5-149">Overloading</span></span>  
 <span data-ttu-id="7daf5-150">`Xor` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="7daf5-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7daf5-151">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="7daf5-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="7daf5-152">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7daf5-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7daf5-153">Пример</span><span class="sxs-lookup"><span data-stu-id="7daf5-153">Example</span></span>  
 <span data-ttu-id="7daf5-154">В следующем примере используется `Xor` оператор для выполнения логического исключения (исключающая логическая дизъюнкция) для двух выражений.</span><span class="sxs-lookup"><span data-stu-id="7daf5-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="7daf5-155">В результате `Boolean` значение, которое указывает, находится ли ровно одно из выражений `True`.</span><span class="sxs-lookup"><span data-stu-id="7daf5-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 <span data-ttu-id="7daf5-156">В предыдущем примере получаются результаты `False`, `True`, и `False`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="7daf5-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7daf5-157">Пример</span><span class="sxs-lookup"><span data-stu-id="7daf5-157">Example</span></span>  
 <span data-ttu-id="7daf5-158">В следующем примере используется `Xor` оператор для выполнения логического исключения (исключающая логическая дизъюнкция) с отдельными битами двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="7daf5-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="7daf5-159">Бит в шаблоне результата устанавливается в том случае, если только один из соответствующих бита в операндов имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="7daf5-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 <span data-ttu-id="7daf5-160">Предыдущий пример получаются результаты 2, 12 и 14, соответственно.</span><span class="sxs-lookup"><span data-stu-id="7daf5-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7daf5-161">См. также</span><span class="sxs-lookup"><span data-stu-id="7daf5-161">See also</span></span>
- [<span data-ttu-id="7daf5-162">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7daf5-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="7daf5-163">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7daf5-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7daf5-164">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="7daf5-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7daf5-165">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7daf5-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
