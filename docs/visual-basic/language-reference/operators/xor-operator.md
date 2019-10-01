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
ms.openlocfilehash: d82018a3018e2cf4362b9904ed127c20f56f6f0c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701269"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="9dc0d-102">Оператор Xor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9dc0d-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="9dc0d-103">Выполняет логическое исключение в двух выражениях `Boolean` или побитовое исключение для двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9dc0d-104">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="9dc0d-105">Части</span><span class="sxs-lookup"><span data-stu-id="9dc0d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="9dc0d-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-106">Required.</span></span> <span data-ttu-id="9dc0d-107">Любая переменная `Boolean` или numeric.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="9dc0d-108">Для логического сравнения `result` является логическим исключением (исключающее логическое сложение) двух значений `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="9dc0d-109">Для побитовых операций `result` — это числовое значение, представляющее побитовое исключение (исключающее побитовое сложение) двух числовых битов.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="9dc0d-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-110">Required.</span></span> <span data-ttu-id="9dc0d-111">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="9dc0d-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-112">Required.</span></span> <span data-ttu-id="9dc0d-113">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dc0d-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="9dc0d-114">Remarks</span></span>  
 <span data-ttu-id="9dc0d-115">Для логического сравнения `result` — `True`, только если в точности один из `expression1` и `expression2` равен `True`.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="9dc0d-116">То есть только в случае, если `expression1` и `expression2` имеют противоположные значения `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="9dc0d-117">В следующей таблице показано, как определяется `result`.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="9dc0d-118">Если `expression1` имеет значение</span><span class="sxs-lookup"><span data-stu-id="9dc0d-118">If `expression1` is</span></span>|<span data-ttu-id="9dc0d-119">И `expression2` является</span><span class="sxs-lookup"><span data-stu-id="9dc0d-119">And `expression2` is</span></span>|<span data-ttu-id="9dc0d-120">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="9dc0d-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="9dc0d-121">При логическом сравнении оператор `Xor` всегда вычисляет оба выражения, которые могут включать вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="9dc0d-122">Нет аналогового аналога для `Xor`, так как результат всегда зависит от обоих операндов.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="9dc0d-123">Дополнительные операторы для *сокращенного* вычисления логических операторов см. в разделе [оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) и [оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9dc0d-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="9dc0d-124">Для побитовых операций оператор `Xor` выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="9dc0d-125">Если бит в `expression1` равен</span><span class="sxs-lookup"><span data-stu-id="9dc0d-125">If bit in `expression1` is</span></span>|<span data-ttu-id="9dc0d-126">И бит в `expression2` —</span><span class="sxs-lookup"><span data-stu-id="9dc0d-126">And bit in `expression2` is</span></span>|<span data-ttu-id="9dc0d-127">Бит в `result` является</span><span class="sxs-lookup"><span data-stu-id="9dc0d-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="9dc0d-128">1</span><span class="sxs-lookup"><span data-stu-id="9dc0d-128">1</span></span>|<span data-ttu-id="9dc0d-129">1</span><span class="sxs-lookup"><span data-stu-id="9dc0d-129">1</span></span>|<span data-ttu-id="9dc0d-130">0</span><span class="sxs-lookup"><span data-stu-id="9dc0d-130">0</span></span>|  
|<span data-ttu-id="9dc0d-131">1</span><span class="sxs-lookup"><span data-stu-id="9dc0d-131">1</span></span>|<span data-ttu-id="9dc0d-132">0</span><span class="sxs-lookup"><span data-stu-id="9dc0d-132">0</span></span>|<span data-ttu-id="9dc0d-133">1</span><span class="sxs-lookup"><span data-stu-id="9dc0d-133">1</span></span>|  
|<span data-ttu-id="9dc0d-134">0</span><span class="sxs-lookup"><span data-stu-id="9dc0d-134">0</span></span>|<span data-ttu-id="9dc0d-135">1</span><span class="sxs-lookup"><span data-stu-id="9dc0d-135">1</span></span>|<span data-ttu-id="9dc0d-136">1</span><span class="sxs-lookup"><span data-stu-id="9dc0d-136">1</span></span>|  
|<span data-ttu-id="9dc0d-137">0</span><span class="sxs-lookup"><span data-stu-id="9dc0d-137">0</span></span>|<span data-ttu-id="9dc0d-138">0</span><span class="sxs-lookup"><span data-stu-id="9dc0d-138">0</span></span>|<span data-ttu-id="9dc0d-139">0</span><span class="sxs-lookup"><span data-stu-id="9dc0d-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="9dc0d-140">Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="9dc0d-141">Например, 5 `Xor` 3 — 6.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="9dc0d-142">Чтобы узнать, почему это так, преобразуйте значения 5 и 3 в двоичные представления, 101 и 011.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="9dc0d-143">Затем используйте предыдущую таблицу, чтобы определить, что 101 Xor 011 имеет значение 110, которое является двоичным представлением десятичного числа 6.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="9dc0d-144">Типы данных</span><span class="sxs-lookup"><span data-stu-id="9dc0d-144">Data Types</span></span>  
 <span data-ttu-id="9dc0d-145">Если операнды состоят из одного выражения `Boolean` и одного числового выражения, Visual Basic преобразует выражение `Boolean` в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="9dc0d-146">Для сравнения `Boolean` тип данных результата `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="9dc0d-147">Для побитового сравнения тип данных результата является числовым типом, подходящим для типов данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="9dc0d-148">См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="9dc0d-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9dc0d-149">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="9dc0d-149">Overloading</span></span>  
 <span data-ttu-id="9dc0d-150">Оператор `Xor` можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9dc0d-151">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="9dc0d-152">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9dc0d-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dc0d-153">Пример</span><span class="sxs-lookup"><span data-stu-id="9dc0d-153">Example</span></span>  
 <span data-ttu-id="9dc0d-154">В следующем примере оператор `Xor` используется для выполнения логического исключения (исключающее логическое сложение) в двух выражениях.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="9dc0d-155">Результатом является значение `Boolean`, которое показывает, является ли ровно одно из выражений `True`.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="9dc0d-156">В предыдущем примере получены результаты `False`, `True` и `False` соответственно.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dc0d-157">Пример</span><span class="sxs-lookup"><span data-stu-id="9dc0d-157">Example</span></span>  
 <span data-ttu-id="9dc0d-158">В следующем примере оператор `Xor` используется для выполнения логического исключения (исключающее логическое сложение) для отдельных битов двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="9dc0d-159">Бит в результирующем шаблоне устанавливается, если только один из соответствующих битов операндов имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="9dc0d-160">В предыдущем примере выдается результат 2, 12 и 14 соответственно.</span><span class="sxs-lookup"><span data-stu-id="9dc0d-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc0d-161">См. также</span><span class="sxs-lookup"><span data-stu-id="9dc0d-161">See also</span></span>

- [<span data-ttu-id="9dc0d-162">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9dc0d-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="9dc0d-163">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9dc0d-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9dc0d-164">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="9dc0d-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9dc0d-165">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9dc0d-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
