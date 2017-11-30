---
title: "Оператор And (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.And
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e1f9df11152f88ef0db24a794026d6f5888a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="cf205-102">Оператор And (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf205-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="cf205-103">Выполняет логическое умножение двух `Boolean` выражений или побитовое логическое умножение двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="cf205-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf205-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf205-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="cf205-105">Части</span><span class="sxs-lookup"><span data-stu-id="cf205-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="cf205-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cf205-106">Required.</span></span> <span data-ttu-id="cf205-107">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="cf205-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="cf205-108">Для логического сравнения `result` — логическое умножение двух `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="cf205-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="cf205-109">Для битовых операций `result` — это числовое значение, представляющее побитовое логическое умножение двух числовых битовых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="cf205-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="cf205-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cf205-110">Required.</span></span> <span data-ttu-id="cf205-111">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="cf205-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="cf205-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cf205-112">Required.</span></span> <span data-ttu-id="cf205-113">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="cf205-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf205-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf205-114">Remarks</span></span>  
 <span data-ttu-id="cf205-115">Логическое сравнение `result` — `True` Если и только если оба `expression1` и `expression2` равен `True`.</span><span class="sxs-lookup"><span data-stu-id="cf205-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="cf205-116">В следующей таблице показано, как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="cf205-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="cf205-117">Если `expression1` является</span><span class="sxs-lookup"><span data-stu-id="cf205-117">If `expression1` is</span></span>|<span data-ttu-id="cf205-118">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="cf205-118">And `expression2` is</span></span>|<span data-ttu-id="cf205-119">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="cf205-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="cf205-120">В логическом сравнении `And` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="cf205-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="cf205-121">[Оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) выполняет *сокращенного вычисления*, т.е. Если `expression1` — `False`, затем `expression2` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="cf205-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="cf205-122">При применении к числовым значениям, `And` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cf205-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="cf205-123">Если бит в `expression1` —</span><span class="sxs-lookup"><span data-stu-id="cf205-123">If bit in `expression1` is</span></span>|<span data-ttu-id="cf205-124">И бита `expression2` —</span><span class="sxs-lookup"><span data-stu-id="cf205-124">And bit in `expression2` is</span></span>|<span data-ttu-id="cf205-125">Бит в `result` —</span><span class="sxs-lookup"><span data-stu-id="cf205-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="cf205-126">1</span><span class="sxs-lookup"><span data-stu-id="cf205-126">1</span></span>|<span data-ttu-id="cf205-127">1</span><span class="sxs-lookup"><span data-stu-id="cf205-127">1</span></span>|<span data-ttu-id="cf205-128">1</span><span class="sxs-lookup"><span data-stu-id="cf205-128">1</span></span>|  
|<span data-ttu-id="cf205-129">1</span><span class="sxs-lookup"><span data-stu-id="cf205-129">1</span></span>|<span data-ttu-id="cf205-130">0</span><span class="sxs-lookup"><span data-stu-id="cf205-130">0</span></span>|<span data-ttu-id="cf205-131">0</span><span class="sxs-lookup"><span data-stu-id="cf205-131">0</span></span>|  
|<span data-ttu-id="cf205-132">0</span><span class="sxs-lookup"><span data-stu-id="cf205-132">0</span></span>|<span data-ttu-id="cf205-133">1</span><span class="sxs-lookup"><span data-stu-id="cf205-133">1</span></span>|<span data-ttu-id="cf205-134">0</span><span class="sxs-lookup"><span data-stu-id="cf205-134">0</span></span>|  
|<span data-ttu-id="cf205-135">0</span><span class="sxs-lookup"><span data-stu-id="cf205-135">0</span></span>|<span data-ttu-id="cf205-136">0</span><span class="sxs-lookup"><span data-stu-id="cf205-136">0</span></span>|<span data-ttu-id="cf205-137">0</span><span class="sxs-lookup"><span data-stu-id="cf205-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="cf205-138">Поскольку логические и битовые операторы имеют более низкий приоритет, чем другие арифметических операторов и операторов отношения, побитовые операции следует заключать в круглые скобки, чтобы обеспечить точность результатов.</span><span class="sxs-lookup"><span data-stu-id="cf205-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="cf205-139">Типы данных</span><span class="sxs-lookup"><span data-stu-id="cf205-139">Data Types</span></span>  
 <span data-ttu-id="cf205-140">Если операнды состоят из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразует `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="cf205-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="cf205-141">Для логического сравнения, тип данных результата является `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="cf205-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="cf205-142">Поразрядное сравнение, тип данных результата является числовым типом, соответствующим для типов данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="cf205-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="cf205-143">См. в таблице «Реляционных и Побитовый оператор сравнения» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="cf205-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf205-144">`And` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="cf205-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="cf205-145">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="cf205-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="cf205-146">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="cf205-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf205-147">Пример</span><span class="sxs-lookup"><span data-stu-id="cf205-147">Example</span></span>  
 <span data-ttu-id="cf205-148">В следующем примере используется `And` оператор для выполнения логического умножения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="cf205-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="cf205-149">В результате `Boolean` значение, которое показывает, что оба выражения являются `True`.</span><span class="sxs-lookup"><span data-stu-id="cf205-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 <span data-ttu-id="cf205-150">В предыдущем примере получаются результаты `True` и `False`соответственно.</span><span class="sxs-lookup"><span data-stu-id="cf205-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf205-151">Пример</span><span class="sxs-lookup"><span data-stu-id="cf205-151">Example</span></span>  
 <span data-ttu-id="cf205-152">В следующем примере используется `And` оператор для выполнения логического умножения отдельных битов двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="cf205-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="cf205-153">Бит в шаблоне результата устанавливается в том случае, если соответствующие биты в операндах устанавливаются в 1.</span><span class="sxs-lookup"><span data-stu-id="cf205-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 <span data-ttu-id="cf205-154">В предыдущем примере получаются результаты 8, 2 и 0, соответственно.</span><span class="sxs-lookup"><span data-stu-id="cf205-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf205-155">См. также</span><span class="sxs-lookup"><span data-stu-id="cf205-155">See Also</span></span>  
 [<span data-ttu-id="cf205-156">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf205-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="cf205-157">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf205-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="cf205-158">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="cf205-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="cf205-159">Оператор AndAlso</span><span class="sxs-lookup"><span data-stu-id="cf205-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [<span data-ttu-id="cf205-160">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf205-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
