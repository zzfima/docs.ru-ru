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
ms.openlocfilehash: 0277b6f24e62ed5f0cad3dae225c86fffc4c09b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013521"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="16081-102">Оператор Or (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16081-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="16081-103">Выполняет логическое сложение двух `Boolean` выражений или побитовое сложение двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="16081-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16081-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16081-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="16081-105">Части</span><span class="sxs-lookup"><span data-stu-id="16081-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="16081-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="16081-106">Required.</span></span> <span data-ttu-id="16081-107">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="16081-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="16081-108">Для `Boolean` сравнения, `result` является логическое сложение двух `Boolean` значения.</span><span class="sxs-lookup"><span data-stu-id="16081-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="16081-109">Для битовых операций: `result` числовое значение, представляющее побитовое дизъюнкции двум битовым шаблонам чисел.</span><span class="sxs-lookup"><span data-stu-id="16081-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="16081-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="16081-110">Required.</span></span> <span data-ttu-id="16081-111">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="16081-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="16081-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="16081-112">Required.</span></span> <span data-ttu-id="16081-113">Любой `Boolean` или числовое выражение.</span><span class="sxs-lookup"><span data-stu-id="16081-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16081-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="16081-114">Remarks</span></span>  
 <span data-ttu-id="16081-115">Для `Boolean` сравнения, `result` — `False` Если и только если оба `expression1` и `expression2` иметь `False`.</span><span class="sxs-lookup"><span data-stu-id="16081-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="16081-116">В следующей таблице показано как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="16081-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="16081-117">Если `expression1` —</span><span class="sxs-lookup"><span data-stu-id="16081-117">If `expression1` is</span></span>|<span data-ttu-id="16081-118">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="16081-118">And `expression2` is</span></span>|<span data-ttu-id="16081-119">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="16081-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="16081-120">В `Boolean` сравнения, `Or` оператор всегда вычисляет оба выражения, которые могут включать вызовы процедуры.</span><span class="sxs-lookup"><span data-stu-id="16081-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="16081-121">[OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) выполняет *сокращенного вычисления*, т.е. Если `expression1` — `True`, затем `expression2` не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="16081-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="16081-122">Для битовых операций: `Or` оператор выполняет побитовое сравнение одинаково расположенных битов в двух числовых выражений и устанавливает значение соответствующего бита в `result` согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="16081-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="16081-123">Если бит в `expression1` —</span><span class="sxs-lookup"><span data-stu-id="16081-123">If bit in `expression1` is</span></span>|<span data-ttu-id="16081-124">И бит в `expression2` —</span><span class="sxs-lookup"><span data-stu-id="16081-124">And bit in `expression2` is</span></span>|<span data-ttu-id="16081-125">Бит в `result` —</span><span class="sxs-lookup"><span data-stu-id="16081-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="16081-126">1</span><span class="sxs-lookup"><span data-stu-id="16081-126">1</span></span>|<span data-ttu-id="16081-127">1</span><span class="sxs-lookup"><span data-stu-id="16081-127">1</span></span>|<span data-ttu-id="16081-128">1</span><span class="sxs-lookup"><span data-stu-id="16081-128">1</span></span>|  
|<span data-ttu-id="16081-129">1</span><span class="sxs-lookup"><span data-stu-id="16081-129">1</span></span>|<span data-ttu-id="16081-130">0</span><span class="sxs-lookup"><span data-stu-id="16081-130">0</span></span>|<span data-ttu-id="16081-131">1</span><span class="sxs-lookup"><span data-stu-id="16081-131">1</span></span>|  
|<span data-ttu-id="16081-132">0</span><span class="sxs-lookup"><span data-stu-id="16081-132">0</span></span>|<span data-ttu-id="16081-133">1</span><span class="sxs-lookup"><span data-stu-id="16081-133">1</span></span>|<span data-ttu-id="16081-134">1</span><span class="sxs-lookup"><span data-stu-id="16081-134">1</span></span>|  
|<span data-ttu-id="16081-135">0</span><span class="sxs-lookup"><span data-stu-id="16081-135">0</span></span>|<span data-ttu-id="16081-136">0</span><span class="sxs-lookup"><span data-stu-id="16081-136">0</span></span>|<span data-ttu-id="16081-137">0</span><span class="sxs-lookup"><span data-stu-id="16081-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="16081-138">Поскольку логические и побитовые операторы имеют более низкий приоритет, чем другие арифметические и реляционные операторы, битовые операции следует заключать в круглые скобки, чтобы обеспечить правильное выполнение.</span><span class="sxs-lookup"><span data-stu-id="16081-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="16081-139">Типы данных</span><span class="sxs-lookup"><span data-stu-id="16081-139">Data Types</span></span>  
 <span data-ttu-id="16081-140">Если операнды состоять из одного `Boolean` выражение и одного числового выражения, Visual Basic преобразуют `Boolean` выражение в числовое значение (-1 для `True` и 0 для `False`) и выполняет побитовую операцию.</span><span class="sxs-lookup"><span data-stu-id="16081-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="16081-141">Для `Boolean` имеет тип данных результата сравнения, `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="16081-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="16081-142">Побитовое сравнение, тип данных результата является числовым типом, соответствующим типам данных `expression1` и `expression2`.</span><span class="sxs-lookup"><span data-stu-id="16081-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="16081-143">См. в таблице «Реляционные и побитовое сравнение» в [типы данных из результатов оператора](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="16081-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="16081-144">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="16081-144">Overloading</span></span>  
 <span data-ttu-id="16081-145">`Or` Оператор может быть *перегружены*, что означает, что класс или структура может переопределить его поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="16081-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="16081-146">Если ваш код использует этот оператор для такого класса или структуры, убедитесь, что его переопределенное.</span><span class="sxs-lookup"><span data-stu-id="16081-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="16081-147">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="16081-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16081-148">Пример</span><span class="sxs-lookup"><span data-stu-id="16081-148">Example</span></span>  
 <span data-ttu-id="16081-149">В следующем примере используется `Or` оператору выполнять логическое сложение двух выражений.</span><span class="sxs-lookup"><span data-stu-id="16081-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="16081-150">В результате `Boolean` значение, представляющее одно из двух выражений ли `True`.</span><span class="sxs-lookup"><span data-stu-id="16081-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="16081-151">В предыдущем примере получался результат `True`, `True`, и `False`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="16081-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16081-152">Пример</span><span class="sxs-lookup"><span data-stu-id="16081-152">Example</span></span>  
 <span data-ttu-id="16081-153">В следующем примере используется `Or` оператор для выполнения логическое сложение с отдельными битами двух числовых выражений.</span><span class="sxs-lookup"><span data-stu-id="16081-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="16081-154">Бит в шаблоне результата устанавливается в том случае, если любой из соответствующих бита в операндов имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="16081-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="16081-155">В предыдущем примере получался результаты 10, 14 и 14, соответственно.</span><span class="sxs-lookup"><span data-stu-id="16081-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16081-156">См. также</span><span class="sxs-lookup"><span data-stu-id="16081-156">See also</span></span>

- [<span data-ttu-id="16081-157">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16081-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="16081-158">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16081-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="16081-159">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="16081-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="16081-160">Оператор OrElse</span><span class="sxs-lookup"><span data-stu-id="16081-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="16081-161">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16081-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
