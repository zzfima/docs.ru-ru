---
title: "Оператор OR (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Or
dev_langs:
- VB
helpviewer_keywords:
- Or operator
- operators [Visual Basic], bitwise
- inclusive Or operator
- bitwise operators, OR operator
- Or keyword
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison
- logical disjunction
- disjunction operator
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 01d51f50dd785f168ed850e3f1763b300d9d2011
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="59544-102">Оператор Or (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59544-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="59544-103">Выполняет логическое сложение двух `Boolean` выражений или побитового логического сложения двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="59544-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59544-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59544-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="59544-105">Части</span><span class="sxs-lookup"><span data-stu-id="59544-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="59544-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="59544-106">Required.</span></span> <span data-ttu-id="59544-107">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="59544-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="59544-108">Для `Boolean` сравнения, `result` является включающее логическое сложение двух `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="59544-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="59544-109">Для битовых операций `result` — это числовое значение, представляющее включающую побитовую дизъюнкцию двух числовых битовых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="59544-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="59544-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="59544-110">Required.</span></span> <span data-ttu-id="59544-111">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="59544-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="59544-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="59544-112">Required.</span></span> <span data-ttu-id="59544-113">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="59544-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59544-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="59544-114">Remarks</span></span>  
 <span data-ttu-id="59544-115">Для `Boolean` сравнения, `result` — `False` Если и только если оба `expression1` и `expression2` равен `False`.</span><span class="sxs-lookup"><span data-stu-id="59544-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="59544-116">В следующей таблице показано, как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="59544-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="59544-117">If `expression1` is</span><span class="sxs-lookup"><span data-stu-id="59544-117">If `expression1` is</span></span>|<span data-ttu-id="59544-118">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="59544-118">And `expression2` is</span></span>|<span data-ttu-id="59544-119">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="59544-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="59544-120">В `Boolean` сравнения, `Or` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="59544-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="59544-121">[Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет *сокращенного вычисления*, означает, что если `expression1` — `True`, то `expression2` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="59544-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="59544-122">Для битовых операций `Or` оператор выполняет поразрядное сравнение одинаково расположенных битов в двух числовых выражениях и задает соответствующий бит в `result` согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="59544-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="59544-123">Если бит в `expression1` —</span><span class="sxs-lookup"><span data-stu-id="59544-123">If bit in `expression1` is</span></span>|<span data-ttu-id="59544-124">И бита `expression2` —</span><span class="sxs-lookup"><span data-stu-id="59544-124">And bit in `expression2` is</span></span>|<span data-ttu-id="59544-125">Бит в `result` —</span><span class="sxs-lookup"><span data-stu-id="59544-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="59544-126">1</span><span class="sxs-lookup"><span data-stu-id="59544-126">1</span></span>|<span data-ttu-id="59544-127">1</span><span class="sxs-lookup"><span data-stu-id="59544-127">1</span></span>|<span data-ttu-id="59544-128">1</span><span class="sxs-lookup"><span data-stu-id="59544-128">1</span></span>|  
|<span data-ttu-id="59544-129">1</span><span class="sxs-lookup"><span data-stu-id="59544-129">1</span></span>|<span data-ttu-id="59544-130">0</span><span class="sxs-lookup"><span data-stu-id="59544-130">0</span></span>|<span data-ttu-id="59544-131">1</span><span class="sxs-lookup"><span data-stu-id="59544-131">1</span></span>|  
|<span data-ttu-id="59544-132">0</span><span class="sxs-lookup"><span data-stu-id="59544-132">0</span></span>|<span data-ttu-id="59544-133">1</span><span class="sxs-lookup"><span data-stu-id="59544-133">1</span></span>|<span data-ttu-id="59544-134">1</span><span class="sxs-lookup"><span data-stu-id="59544-134">1</span></span>|  
|<span data-ttu-id="59544-135">0</span><span class="sxs-lookup"><span data-stu-id="59544-135">0</span></span>|<span data-ttu-id="59544-136">0</span><span class="sxs-lookup"><span data-stu-id="59544-136">0</span></span>|<span data-ttu-id="59544-137">0</span><span class="sxs-lookup"><span data-stu-id="59544-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="59544-138">Поскольку логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические операторы и операторы отношения, побитовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.</span><span class="sxs-lookup"><span data-stu-id="59544-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="59544-139">Типы данных</span><span class="sxs-lookup"><span data-stu-id="59544-139">Data Types</span></span>  
 <span data-ttu-id="59544-140">Если операнды состоят из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразует `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет битовую операцию.</span><span class="sxs-lookup"><span data-stu-id="59544-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="59544-141">Для `Boolean` сравнения, тип данных результата является `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="59544-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="59544-142">Поразрядное сравнение, тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="59544-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="59544-143">В разделе «Реляционные и побитовое сравнение» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="59544-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="59544-144">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="59544-144">Overloading</span></span>  
 <span data-ttu-id="59544-145">`Or` Оператор может быть *перегружен*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="59544-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="59544-146">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="59544-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="59544-147">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="59544-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59544-148">Пример</span><span class="sxs-lookup"><span data-stu-id="59544-148">Example</span></span>  
 <span data-ttu-id="59544-149">В следующем примере используется `Or` оператора для выполнения логической дизъюнкции двух выражений.</span><span class="sxs-lookup"><span data-stu-id="59544-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="59544-150">В результате `Boolean` значение, представляющее ли два выражения являются `True`.</span><span class="sxs-lookup"><span data-stu-id="59544-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 <span data-ttu-id="59544-151">[!code-vb[VbVbalrOperators&#35;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="59544-151">[!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="59544-152">В предыдущем примере получаются результаты `True`, `True`, и `False`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="59544-152">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59544-153">Пример</span><span class="sxs-lookup"><span data-stu-id="59544-153">Example</span></span>  
 <span data-ttu-id="59544-154">В следующем примере используется `Or` оператора для выполнения логической дизъюнкции над отдельными битами двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="59544-154">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="59544-155">Бит в результирующем шаблоне устанавливается в том случае, если любой из соответствующих битов в операндах равен 1.</span><span class="sxs-lookup"><span data-stu-id="59544-155">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 <span data-ttu-id="59544-156">[!code-vb[VbVbalrOperators&#36;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="59544-156">[!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]</span></span>  
  
 <span data-ttu-id="59544-157">В предыдущем примере получаются результаты 10, 14 и 14 соответственно.</span><span class="sxs-lookup"><span data-stu-id="59544-157">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59544-158">См. также</span><span class="sxs-lookup"><span data-stu-id="59544-158">See Also</span></span>  
 <span data-ttu-id="59544-159">[Логические (побитовые) операторы (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md) </span><span class="sxs-lookup"><span data-stu-id="59544-159">[Logical/Bitwise Operators (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md) </span></span>  
<span data-ttu-id="59544-160"> [Приоритет операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="59544-160"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="59544-161"> [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="59544-161"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="59544-162"> [Оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) </span><span class="sxs-lookup"><span data-stu-id="59544-162"> [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) </span></span>  
<span data-ttu-id="59544-163"> [Логические и побитовые операторы в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="59544-163"> [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>

