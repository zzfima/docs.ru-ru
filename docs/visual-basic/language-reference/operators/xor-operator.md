---
title: Оператор Xor
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
ms.openlocfilehash: c5c7ec87bc173f724f8c670395bc3b0458444df6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335404"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="fb3c7-102">Оператор Xor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb3c7-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="fb3c7-103">Выполняет логическое исключение в двух выражениях `Boolean` или побитовое исключение для двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb3c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb3c7-104">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="fb3c7-105">Части</span><span class="sxs-lookup"><span data-stu-id="fb3c7-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="fb3c7-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-106">Required.</span></span> <span data-ttu-id="fb3c7-107">Любая `Boolean` или числовая переменная.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="fb3c7-108">Для логического сравнения `result` является логическим исключением (исключающее логическое сложение) двух `Boolean`ных значений.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="fb3c7-109">Для побитовых операций `result` — это числовое значение, представляющее побитовое исключающее исключение (с истечением побитового сложения) двух числовых битов.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="fb3c7-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-110">Required.</span></span> <span data-ttu-id="fb3c7-111">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="fb3c7-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-112">Required.</span></span> <span data-ttu-id="fb3c7-113">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb3c7-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb3c7-114">Remarks</span></span>  
 <span data-ttu-id="fb3c7-115">Для логического сравнения `result` `True` только в том случае, если только один из `expression1` и `expression2` равен `True`.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="fb3c7-116">То есть только если `expression1` и `expression2` имеют противоположные `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="fb3c7-117">В следующей таблице показано, как определяется `result`.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="fb3c7-118">Если `expression1`</span><span class="sxs-lookup"><span data-stu-id="fb3c7-118">If `expression1` is</span></span>|<span data-ttu-id="fb3c7-119">И `expression2`</span><span class="sxs-lookup"><span data-stu-id="fb3c7-119">And `expression2` is</span></span>|<span data-ttu-id="fb3c7-120">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="fb3c7-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="fb3c7-121">При логическом сравнении оператор `Xor` всегда вычисляет оба выражения, которые могут включать вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="fb3c7-122">Нет сокращенного результата для `Xor`, так как результат всегда зависит от обоих операндов.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="fb3c7-123">Дополнительные операторы для *сокращенного* вычисления логических операторов см. в разделе [оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) и [оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="fb3c7-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="fb3c7-124">Для побитовых операций оператор `Xor` выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="fb3c7-125">Если бит в `expression1` имеет значение</span><span class="sxs-lookup"><span data-stu-id="fb3c7-125">If bit in `expression1` is</span></span>|<span data-ttu-id="fb3c7-126">И бит в `expression2` —</span><span class="sxs-lookup"><span data-stu-id="fb3c7-126">And bit in `expression2` is</span></span>|<span data-ttu-id="fb3c7-127">Бит в `result`</span><span class="sxs-lookup"><span data-stu-id="fb3c7-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="fb3c7-128">1</span><span class="sxs-lookup"><span data-stu-id="fb3c7-128">1</span></span>|<span data-ttu-id="fb3c7-129">1</span><span class="sxs-lookup"><span data-stu-id="fb3c7-129">1</span></span>|<span data-ttu-id="fb3c7-130">0</span><span class="sxs-lookup"><span data-stu-id="fb3c7-130">0</span></span>|  
|<span data-ttu-id="fb3c7-131">1</span><span class="sxs-lookup"><span data-stu-id="fb3c7-131">1</span></span>|<span data-ttu-id="fb3c7-132">0</span><span class="sxs-lookup"><span data-stu-id="fb3c7-132">0</span></span>|<span data-ttu-id="fb3c7-133">1</span><span class="sxs-lookup"><span data-stu-id="fb3c7-133">1</span></span>|  
|<span data-ttu-id="fb3c7-134">0</span><span class="sxs-lookup"><span data-stu-id="fb3c7-134">0</span></span>|<span data-ttu-id="fb3c7-135">1</span><span class="sxs-lookup"><span data-stu-id="fb3c7-135">1</span></span>|<span data-ttu-id="fb3c7-136">1</span><span class="sxs-lookup"><span data-stu-id="fb3c7-136">1</span></span>|  
|<span data-ttu-id="fb3c7-137">0</span><span class="sxs-lookup"><span data-stu-id="fb3c7-137">0</span></span>|<span data-ttu-id="fb3c7-138">0</span><span class="sxs-lookup"><span data-stu-id="fb3c7-138">0</span></span>|<span data-ttu-id="fb3c7-139">0</span><span class="sxs-lookup"><span data-stu-id="fb3c7-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="fb3c7-140">Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки, чтобы обеспечить точное выполнение.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="fb3c7-141">Например, 5 `Xor` 3 — 6.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="fb3c7-142">Чтобы узнать, почему это так, преобразуйте значения 5 и 3 в двоичные представления, 101 и 011.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="fb3c7-143">Затем используйте предыдущую таблицу, чтобы определить, что 101 Xor 011 имеет значение 110, которое является двоичным представлением десятичного числа 6.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="fb3c7-144">Типы данных</span><span class="sxs-lookup"><span data-stu-id="fb3c7-144">Data Types</span></span>  
 <span data-ttu-id="fb3c7-145">Если операнды состоят из одного `Boolean` выражения и одного числового выражения, Visual Basic преобразует выражение `Boolean` в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="fb3c7-146">Для сравнения `Boolean` тип данных результата `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="fb3c7-147">Для побитового сравнения тип данных результата является числовым типом, подходящим для типов данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="fb3c7-148">См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="fb3c7-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="fb3c7-149">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="fb3c7-149">Overloading</span></span>  
 <span data-ttu-id="fb3c7-150">Оператор `Xor` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fb3c7-151">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="fb3c7-152">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fb3c7-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb3c7-153">Пример</span><span class="sxs-lookup"><span data-stu-id="fb3c7-153">Example</span></span>  
 <span data-ttu-id="fb3c7-154">В следующем примере оператор `Xor` используется для выполнения логического исключения (исключающее логическое сложение) в двух выражениях.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="fb3c7-155">Результатом является `Boolean` значение, которое показывает, `True`ли ровно одно из выражений.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="fb3c7-156">В предыдущем примере создаются результаты `False`, `True`и `False`соответственно.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb3c7-157">Пример</span><span class="sxs-lookup"><span data-stu-id="fb3c7-157">Example</span></span>  
 <span data-ttu-id="fb3c7-158">В следующем примере оператор `Xor` используется для выполнения логического исключения (исключающее логическое сложение) для отдельных битов двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="fb3c7-159">Бит в результирующем шаблоне устанавливается, если только один из соответствующих битов операндов имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="fb3c7-160">В предыдущем примере выдается результат 2, 12 и 14 соответственно.</span><span class="sxs-lookup"><span data-stu-id="fb3c7-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3c7-161">См. также</span><span class="sxs-lookup"><span data-stu-id="fb3c7-161">See also</span></span>

- [<span data-ttu-id="fb3c7-162">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb3c7-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="fb3c7-163">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb3c7-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fb3c7-164">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="fb3c7-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fb3c7-165">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb3c7-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
