---
title: Оператор Xor (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b14f11f2df2df9c29e88e9188390cfe245d2cb58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="4258d-102">Оператор Xor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4258d-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="4258d-103">Выполняет логическое исключение над двумя `Boolean` выражений или побитовое Вычитание двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="4258d-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4258d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4258d-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="4258d-105">Части</span><span class="sxs-lookup"><span data-stu-id="4258d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="4258d-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4258d-106">Required.</span></span> <span data-ttu-id="4258d-107">Любой `Boolean` или числовой переменной.</span><span class="sxs-lookup"><span data-stu-id="4258d-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="4258d-108">Для логического сравнения `result` является логическим исключением (исключающая логическая дизъюнкция) из двух `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="4258d-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="4258d-109">Для битовых операций `result` является числовым значением, представляющим побитовое исключение (исключающая Побитовая дизъюнкция) из двух числовых битовых шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4258d-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="4258d-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4258d-110">Required.</span></span> <span data-ttu-id="4258d-111">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="4258d-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4258d-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="4258d-112">Required.</span></span> <span data-ttu-id="4258d-113">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="4258d-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4258d-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="4258d-114">Remarks</span></span>  
 <span data-ttu-id="4258d-115">Логическое сравнение `result` — `True` , только если один из `expression1` и `expression2` равен `True`.</span><span class="sxs-lookup"><span data-stu-id="4258d-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="4258d-116">То есть, только если `expression1` и `expression2` оценки в обратном `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="4258d-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="4258d-117">В следующей таблице показано, как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="4258d-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="4258d-118">Если `expression1` является</span><span class="sxs-lookup"><span data-stu-id="4258d-118">If `expression1` is</span></span>|<span data-ttu-id="4258d-119">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="4258d-119">And `expression2` is</span></span>|<span data-ttu-id="4258d-120">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="4258d-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="4258d-121">В логическом сравнении `Xor` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="4258d-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="4258d-122">Нет не сокращенной обработки аналогом `Xor`, поскольку результат всегда зависит от обоих операндов.</span><span class="sxs-lookup"><span data-stu-id="4258d-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="4258d-123">Для *сокращенного вычисления* логические операторы в разделе [оператор AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) и [оператор OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4258d-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="4258d-124">Для битовых операций `Xor` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4258d-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="4258d-125">Если бит в `expression1` —</span><span class="sxs-lookup"><span data-stu-id="4258d-125">If bit in `expression1` is</span></span>|<span data-ttu-id="4258d-126">И бита `expression2` —</span><span class="sxs-lookup"><span data-stu-id="4258d-126">And bit in `expression2` is</span></span>|<span data-ttu-id="4258d-127">Бит в `result` —</span><span class="sxs-lookup"><span data-stu-id="4258d-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="4258d-128">1</span><span class="sxs-lookup"><span data-stu-id="4258d-128">1</span></span>|<span data-ttu-id="4258d-129">1</span><span class="sxs-lookup"><span data-stu-id="4258d-129">1</span></span>|<span data-ttu-id="4258d-130">0</span><span class="sxs-lookup"><span data-stu-id="4258d-130">0</span></span>|  
|<span data-ttu-id="4258d-131">1</span><span class="sxs-lookup"><span data-stu-id="4258d-131">1</span></span>|<span data-ttu-id="4258d-132">0</span><span class="sxs-lookup"><span data-stu-id="4258d-132">0</span></span>|<span data-ttu-id="4258d-133">1</span><span class="sxs-lookup"><span data-stu-id="4258d-133">1</span></span>|  
|<span data-ttu-id="4258d-134">0</span><span class="sxs-lookup"><span data-stu-id="4258d-134">0</span></span>|<span data-ttu-id="4258d-135">1</span><span class="sxs-lookup"><span data-stu-id="4258d-135">1</span></span>|<span data-ttu-id="4258d-136">1</span><span class="sxs-lookup"><span data-stu-id="4258d-136">1</span></span>|  
|<span data-ttu-id="4258d-137">0</span><span class="sxs-lookup"><span data-stu-id="4258d-137">0</span></span>|<span data-ttu-id="4258d-138">0</span><span class="sxs-lookup"><span data-stu-id="4258d-138">0</span></span>|<span data-ttu-id="4258d-139">0</span><span class="sxs-lookup"><span data-stu-id="4258d-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4258d-140">Поскольку логические и битовые операторы имеют более низкий приоритет, чем другие арифметических операторов и операторов отношения, побитовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.</span><span class="sxs-lookup"><span data-stu-id="4258d-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="4258d-141">Например, 5 `Xor` 3-6.</span><span class="sxs-lookup"><span data-stu-id="4258d-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="4258d-142">Чтобы убедиться в этом, преобразуйте 5 и 3 в двоичное представление, 101 и 011.</span><span class="sxs-lookup"><span data-stu-id="4258d-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="4258d-143">Чтобы определить, что 101 Xor 011 110, который является двоичным представлением десятичного числа 6, воспользуйтесь приведенной выше таблице.</span><span class="sxs-lookup"><span data-stu-id="4258d-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="4258d-144">Типы данных</span><span class="sxs-lookup"><span data-stu-id="4258d-144">Data Types</span></span>  
 <span data-ttu-id="4258d-145">Если операнды состоят из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразует `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="4258d-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="4258d-146">Для `Boolean` сравнения, тип данных результата является `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4258d-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="4258d-147">Поразрядное сравнение, тип данных результата является числовым типом, соответствующим для типов данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="4258d-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="4258d-148">См. в таблице «Реляционных и Побитовый оператор сравнения» [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="4258d-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4258d-149">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="4258d-149">Overloading</span></span>  
 <span data-ttu-id="4258d-150">`Xor` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4258d-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4258d-151">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="4258d-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="4258d-152">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4258d-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4258d-153">Пример</span><span class="sxs-lookup"><span data-stu-id="4258d-153">Example</span></span>  
 <span data-ttu-id="4258d-154">В следующем примере используется `Xor` оператор для выполнения логического исключения (исключающая логическая дизъюнкция) для двух выражений.</span><span class="sxs-lookup"><span data-stu-id="4258d-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="4258d-155">В результате `Boolean` значение, которое указывает, находится ли ровно одно из выражений `True`.</span><span class="sxs-lookup"><span data-stu-id="4258d-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 <span data-ttu-id="4258d-156">В предыдущем примере получаются результаты `False`, `True`, и `False`соответственно.</span><span class="sxs-lookup"><span data-stu-id="4258d-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4258d-157">Пример</span><span class="sxs-lookup"><span data-stu-id="4258d-157">Example</span></span>  
 <span data-ttu-id="4258d-158">В следующем примере используется `Xor` оператор для выполнения логического исключения (исключающая логическая дизъюнкция) для отдельных битов двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="4258d-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="4258d-159">Бит в шаблоне результата устанавливается в том случае, если только один из соответствующих битов в операндах равен 1.</span><span class="sxs-lookup"><span data-stu-id="4258d-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 <span data-ttu-id="4258d-160">В предыдущем примере получаются результаты 2, 12 и 14 соответственно.</span><span class="sxs-lookup"><span data-stu-id="4258d-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4258d-161">См. также</span><span class="sxs-lookup"><span data-stu-id="4258d-161">See Also</span></span>  
 [<span data-ttu-id="4258d-162">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4258d-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="4258d-163">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4258d-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="4258d-164">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="4258d-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="4258d-165">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4258d-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
