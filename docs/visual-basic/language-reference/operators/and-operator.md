---
title: Оператор And (Visual Basic)
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
ms.openlocfilehash: 7e25f25677fa684427bdaf00cea73916ffbad655
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818622"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="82b50-102">Оператор And (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82b50-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="82b50-103">Выполняет логическое умножение двух `Boolean` выражений или побитовое логическое умножение двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="82b50-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82b50-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82b50-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="82b50-105">Части</span><span class="sxs-lookup"><span data-stu-id="82b50-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="82b50-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="82b50-106">Required.</span></span> <span data-ttu-id="82b50-107">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="82b50-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="82b50-108">Для логического сравнения `result` — логическое умножение двух `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="82b50-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="82b50-109">Для битовых операций: `result` числовое значение, представляющее побитовое логическое умножение двум битовым шаблонам чисел.</span><span class="sxs-lookup"><span data-stu-id="82b50-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="82b50-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="82b50-110">Required.</span></span> <span data-ttu-id="82b50-111">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="82b50-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="82b50-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="82b50-112">Required.</span></span> <span data-ttu-id="82b50-113">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="82b50-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82b50-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="82b50-114">Remarks</span></span>  
 <span data-ttu-id="82b50-115">Для логического сравнения `result` — `True` Если и только если оба `expression1` и `expression2` иметь `True`.</span><span class="sxs-lookup"><span data-stu-id="82b50-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="82b50-116">В следующей таблице показано как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="82b50-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="82b50-117">Если `expression1` —</span><span class="sxs-lookup"><span data-stu-id="82b50-117">If `expression1` is</span></span>|<span data-ttu-id="82b50-118">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="82b50-118">And `expression2` is</span></span>|<span data-ttu-id="82b50-119">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="82b50-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="82b50-120">В логическое сравнение `And` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедуры.</span><span class="sxs-lookup"><span data-stu-id="82b50-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="82b50-121">[AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) выполняет *сокращенного вычисления*, т.е. Если `expression1` — `False`, затем `expression2` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="82b50-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="82b50-122">При применении в числовые значения `And` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="82b50-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="82b50-123">Если бит в `expression1` —</span><span class="sxs-lookup"><span data-stu-id="82b50-123">If bit in `expression1` is</span></span>|<span data-ttu-id="82b50-124">И бит в `expression2` —</span><span class="sxs-lookup"><span data-stu-id="82b50-124">And bit in `expression2` is</span></span>|<span data-ttu-id="82b50-125">Бит в `result` —</span><span class="sxs-lookup"><span data-stu-id="82b50-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="82b50-126">1</span><span class="sxs-lookup"><span data-stu-id="82b50-126">1</span></span>|<span data-ttu-id="82b50-127">1</span><span class="sxs-lookup"><span data-stu-id="82b50-127">1</span></span>|<span data-ttu-id="82b50-128">1</span><span class="sxs-lookup"><span data-stu-id="82b50-128">1</span></span>|  
|<span data-ttu-id="82b50-129">1</span><span class="sxs-lookup"><span data-stu-id="82b50-129">1</span></span>|<span data-ttu-id="82b50-130">0</span><span class="sxs-lookup"><span data-stu-id="82b50-130">0</span></span>|<span data-ttu-id="82b50-131">0</span><span class="sxs-lookup"><span data-stu-id="82b50-131">0</span></span>|  
|<span data-ttu-id="82b50-132">0</span><span class="sxs-lookup"><span data-stu-id="82b50-132">0</span></span>|<span data-ttu-id="82b50-133">1</span><span class="sxs-lookup"><span data-stu-id="82b50-133">1</span></span>|<span data-ttu-id="82b50-134">0</span><span class="sxs-lookup"><span data-stu-id="82b50-134">0</span></span>|  
|<span data-ttu-id="82b50-135">0</span><span class="sxs-lookup"><span data-stu-id="82b50-135">0</span></span>|<span data-ttu-id="82b50-136">0</span><span class="sxs-lookup"><span data-stu-id="82b50-136">0</span></span>|<span data-ttu-id="82b50-137">0</span><span class="sxs-lookup"><span data-stu-id="82b50-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="82b50-138">Поскольку логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, битовые операции следует заключать в круглые скобки, чтобы обеспечить точные результаты.</span><span class="sxs-lookup"><span data-stu-id="82b50-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="82b50-139">Типы данных</span><span class="sxs-lookup"><span data-stu-id="82b50-139">Data Types</span></span>  
 <span data-ttu-id="82b50-140">Если операнды состоять из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразуют `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="82b50-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="82b50-141">Для логического сравнения, тип данных результата — `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="82b50-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="82b50-142">Побитовое сравнение, тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="82b50-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="82b50-143">См. в таблице «Реляционные и побитовое сравнение» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="82b50-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82b50-144">`And` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="82b50-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="82b50-145">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="82b50-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="82b50-146">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="82b50-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82b50-147">Пример</span><span class="sxs-lookup"><span data-stu-id="82b50-147">Example</span></span>  
 <span data-ttu-id="82b50-148">В следующем примере используется `And` оператору выполнять логическое умножение двух выражений.</span><span class="sxs-lookup"><span data-stu-id="82b50-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="82b50-149">В результате `Boolean` значение, которое показывает, что оба выражения являются `True`.</span><span class="sxs-lookup"><span data-stu-id="82b50-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="82b50-150">В предыдущем примере получался результат `True` и `False`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="82b50-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82b50-151">Пример</span><span class="sxs-lookup"><span data-stu-id="82b50-151">Example</span></span>  
 <span data-ttu-id="82b50-152">В следующем примере используется `And` оператор для выполнения логического умножения отдельных битов двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="82b50-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="82b50-153">Бит в шаблоне результата устанавливается в том случае, если соответствующие биты в операндах являются равными 1.</span><span class="sxs-lookup"><span data-stu-id="82b50-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="82b50-154">В предыдущем примере получался результаты 8, 2 и 0, соответственно.</span><span class="sxs-lookup"><span data-stu-id="82b50-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b50-155">См. также</span><span class="sxs-lookup"><span data-stu-id="82b50-155">See also</span></span>

- [<span data-ttu-id="82b50-156">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82b50-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="82b50-157">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82b50-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="82b50-158">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="82b50-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="82b50-159">Оператор AndAlso</span><span class="sxs-lookup"><span data-stu-id="82b50-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="82b50-160">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82b50-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
