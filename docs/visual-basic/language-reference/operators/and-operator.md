---
title: Оператор And
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: 78a65843a449bd15d5615710e1685f40d94c37f7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350256"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="149c1-102">Оператор And (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="149c1-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="149c1-103">Выполняет логическое умножение двух выражений `Boolean` или побитовое умножение двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="149c1-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="149c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="149c1-104">Syntax</span></span>  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="149c1-105">Части</span><span class="sxs-lookup"><span data-stu-id="149c1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="149c1-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="149c1-106">Required.</span></span> <span data-ttu-id="149c1-107">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="149c1-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="149c1-108">Для логического сравнения `result` — это логическое умножение двух `Boolean` значений.</span><span class="sxs-lookup"><span data-stu-id="149c1-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="149c1-109">Для побитовых операций `result` является числовым значением, представляющим побитовое умножение двух числовых битов.</span><span class="sxs-lookup"><span data-stu-id="149c1-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="149c1-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="149c1-110">Required.</span></span> <span data-ttu-id="149c1-111">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="149c1-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="149c1-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="149c1-112">Required.</span></span> <span data-ttu-id="149c1-113">Любое `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="149c1-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="149c1-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="149c1-114">Remarks</span></span>  
 <span data-ttu-id="149c1-115">Для логического сравнения `result` `True` только в том случае, если оба `expression1` и `expression2` имеют значение `True`.</span><span class="sxs-lookup"><span data-stu-id="149c1-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="149c1-116">В следующей таблице показано, как определяется `result`.</span><span class="sxs-lookup"><span data-stu-id="149c1-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="149c1-117">Если `expression1`</span><span class="sxs-lookup"><span data-stu-id="149c1-117">If `expression1` is</span></span>|<span data-ttu-id="149c1-118">И `expression2`</span><span class="sxs-lookup"><span data-stu-id="149c1-118">And `expression2` is</span></span>|<span data-ttu-id="149c1-119">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="149c1-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="149c1-120">При логическом сравнении оператор `And` всегда вычисляет оба выражения, которые могут включать вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="149c1-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="149c1-121">[Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) выполняет *сокращенное вычисление*, что означает, что если `expression1` `False`, то `expression2` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="149c1-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="149c1-122">При применении к числовым значениям оператор `And` выполняет побитовое сравнение одинаково позиционированных битов в двух числовых выражениях и устанавливает соответствующий бит в `result` в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="149c1-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="149c1-123">Если бит в `expression1` имеет значение</span><span class="sxs-lookup"><span data-stu-id="149c1-123">If bit in `expression1` is</span></span>|<span data-ttu-id="149c1-124">И бит в `expression2` —</span><span class="sxs-lookup"><span data-stu-id="149c1-124">And bit in `expression2` is</span></span>|<span data-ttu-id="149c1-125">Бит в `result`</span><span class="sxs-lookup"><span data-stu-id="149c1-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="149c1-126">1</span><span class="sxs-lookup"><span data-stu-id="149c1-126">1</span></span>|<span data-ttu-id="149c1-127">1</span><span class="sxs-lookup"><span data-stu-id="149c1-127">1</span></span>|<span data-ttu-id="149c1-128">1</span><span class="sxs-lookup"><span data-stu-id="149c1-128">1</span></span>|  
|<span data-ttu-id="149c1-129">1</span><span class="sxs-lookup"><span data-stu-id="149c1-129">1</span></span>|<span data-ttu-id="149c1-130">0</span><span class="sxs-lookup"><span data-stu-id="149c1-130">0</span></span>|<span data-ttu-id="149c1-131">0</span><span class="sxs-lookup"><span data-stu-id="149c1-131">0</span></span>|  
|<span data-ttu-id="149c1-132">0</span><span class="sxs-lookup"><span data-stu-id="149c1-132">0</span></span>|<span data-ttu-id="149c1-133">1</span><span class="sxs-lookup"><span data-stu-id="149c1-133">1</span></span>|<span data-ttu-id="149c1-134">0</span><span class="sxs-lookup"><span data-stu-id="149c1-134">0</span></span>|  
|<span data-ttu-id="149c1-135">0</span><span class="sxs-lookup"><span data-stu-id="149c1-135">0</span></span>|<span data-ttu-id="149c1-136">0</span><span class="sxs-lookup"><span data-stu-id="149c1-136">0</span></span>|<span data-ttu-id="149c1-137">0</span><span class="sxs-lookup"><span data-stu-id="149c1-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="149c1-138">Так как логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, все битовые операции должны быть заключены в круглые скобки для обеспечения точных результатов.</span><span class="sxs-lookup"><span data-stu-id="149c1-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="149c1-139">Типы данных</span><span class="sxs-lookup"><span data-stu-id="149c1-139">Data Types</span></span>  
 <span data-ttu-id="149c1-140">Если операнды состоят из одного `Boolean` выражения и одного числового выражения, Visual Basic преобразует выражение `Boolean` в числовое значение (– 1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="149c1-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="149c1-141">Для логического сравнения тип данных результата `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="149c1-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="149c1-142">Для побитового сравнения тип данных результата является числовым типом, подходящим для типов данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="149c1-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="149c1-143">См. таблицу "реляционные и побитовые сравнения" в разделе [типы данных результатов операторов](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="149c1-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="149c1-144">Оператор `And` может быть *перегружен*, что означает, что класс или структура может переопределить свое поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="149c1-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="149c1-145">Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="149c1-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="149c1-146">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="149c1-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="149c1-147">Пример</span><span class="sxs-lookup"><span data-stu-id="149c1-147">Example</span></span>  
 <span data-ttu-id="149c1-148">В следующем примере оператор `And` используется для выполнения логического умножения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="149c1-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="149c1-149">Результатом является `Boolean` значение, которое показывает, `True`ли оба выражения.</span><span class="sxs-lookup"><span data-stu-id="149c1-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="149c1-150">В предыдущем примере создаются результаты `True` и `False`соответственно.</span><span class="sxs-lookup"><span data-stu-id="149c1-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="149c1-151">Пример</span><span class="sxs-lookup"><span data-stu-id="149c1-151">Example</span></span>  
 <span data-ttu-id="149c1-152">В следующем примере оператор `And` используется для выполнения логического умножения отдельных битов двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="149c1-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="149c1-153">Бит в результирующем шаблоне задается, если для соответствующих битов в операндах задано значение 1.</span><span class="sxs-lookup"><span data-stu-id="149c1-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="149c1-154">В предыдущем примере выдается результат 8, 2 и 0 соответственно.</span><span class="sxs-lookup"><span data-stu-id="149c1-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="149c1-155">См. также</span><span class="sxs-lookup"><span data-stu-id="149c1-155">See also</span></span>

- [<span data-ttu-id="149c1-156">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="149c1-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="149c1-157">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="149c1-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="149c1-158">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="149c1-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="149c1-159">Оператор AndAlso</span><span class="sxs-lookup"><span data-stu-id="149c1-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="149c1-160">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="149c1-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
