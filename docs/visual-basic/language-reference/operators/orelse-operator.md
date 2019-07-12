---
title: Оператор OrElse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 02be78c8f2b7529f1fb0e46e9fe610a3c66b0652
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860147"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="810bb-102">Оператор OrElse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="810bb-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="810bb-103">Выполняет сокращенное вычисление логического сложения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="810bb-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="810bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="810bb-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="810bb-105">Части</span><span class="sxs-lookup"><span data-stu-id="810bb-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="810bb-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="810bb-106">Required.</span></span> <span data-ttu-id="810bb-107">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="810bb-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="810bb-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="810bb-108">Required.</span></span> <span data-ttu-id="810bb-109">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="810bb-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="810bb-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="810bb-110">Required.</span></span> <span data-ttu-id="810bb-111">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="810bb-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="810bb-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="810bb-112">Remarks</span></span>  
 <span data-ttu-id="810bb-113">Логическая операция называется *сокращенного вычисления* Если скомпилированный код может пропустить вычисления одного выражения в зависимости от результата другого выражения.</span><span class="sxs-lookup"><span data-stu-id="810bb-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="810bb-114">Если результат вычисления первого выражения определяет конечный результат операции, нет необходимости для вычисления второго выражения, так как он не может изменить результат.</span><span class="sxs-lookup"><span data-stu-id="810bb-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="810bb-115">Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или содержит вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="810bb-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="810bb-116">Если один или оба выражения `True`, `result` является `True`.</span><span class="sxs-lookup"><span data-stu-id="810bb-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="810bb-117">В следующей таблице показано как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="810bb-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="810bb-118">Если `expression1` —</span><span class="sxs-lookup"><span data-stu-id="810bb-118">If `expression1` is</span></span>|<span data-ttu-id="810bb-119">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="810bb-119">And `expression2` is</span></span>|<span data-ttu-id="810bb-120">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="810bb-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="810bb-121">(не вычисленное)</span><span class="sxs-lookup"><span data-stu-id="810bb-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="810bb-122">Типы данных</span><span class="sxs-lookup"><span data-stu-id="810bb-122">Data Types</span></span>  
 <span data-ttu-id="810bb-123">`OrElse` Оператор определен только для [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="810bb-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="810bb-124">Visual Basic преобразует каждый операнд при необходимости `Boolean` перед вычислением выражения.</span><span class="sxs-lookup"><span data-stu-id="810bb-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="810bb-125">Если результат назначается числовой тип, Visual Basic преобразует его из `Boolean` к этому типу таким образом, чтобы `False` становится `0` и `True` становится `-1`.</span><span class="sxs-lookup"><span data-stu-id="810bb-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="810bb-126">Дополнительные сведения см. в разделе [логическое преобразования типов](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="810bb-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="810bb-127">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="810bb-127">Overloading</span></span>  
 <span data-ttu-id="810bb-128">[Или оператор](../../../visual-basic/language-reference/operators/or-operator.md) и [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="810bb-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="810bb-129">Перегрузка `Or` и `IsTrue` операторы влияет на поведение `OrElse` оператор.</span><span class="sxs-lookup"><span data-stu-id="810bb-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="810bb-130">Если код использует `OrElse` для класса или структуры, перегружающей `Or` и `IsTrue`, убедитесь, что их переопределенное.</span><span class="sxs-lookup"><span data-stu-id="810bb-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="810bb-131">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="810bb-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="810bb-132">Пример</span><span class="sxs-lookup"><span data-stu-id="810bb-132">Example</span></span>  
 <span data-ttu-id="810bb-133">В следующем примере используется `OrElse` оператор для выполнения логического сложения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="810bb-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="810bb-134">В результате `Boolean` значение, представляющее ли одно из выражений имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="810bb-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="810bb-135">Если первое выражение является `True`, второй не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="810bb-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="810bb-136">В предыдущем примере получался результат `True`, `True`, и `False` соответственно.</span><span class="sxs-lookup"><span data-stu-id="810bb-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="810bb-137">В расчет `firstCheck`, второе выражение не вычисляется, так как первый уже `True`.</span><span class="sxs-lookup"><span data-stu-id="810bb-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="810bb-138">Однако второе выражение оценивается в расчете `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="810bb-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="810bb-139">Пример</span><span class="sxs-lookup"><span data-stu-id="810bb-139">Example</span></span>  
 <span data-ttu-id="810bb-140">В следующем примере показан `If`... `Then` инструкции, содержащей два вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="810bb-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="810bb-141">Если первый вызов возвращает `True`, вторая процедура не вызывается.</span><span class="sxs-lookup"><span data-stu-id="810bb-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="810bb-142">Это может привести к непредвиденным результатам, если вторая процедура выполняет важные задачи, которые всегда должны выполняться при запуске этот раздел кода.</span><span class="sxs-lookup"><span data-stu-id="810bb-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="810bb-143">См. также</span><span class="sxs-lookup"><span data-stu-id="810bb-143">See also</span></span>

- [<span data-ttu-id="810bb-144">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="810bb-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="810bb-145">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="810bb-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="810bb-146">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="810bb-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="810bb-147">Оператор Or</span><span class="sxs-lookup"><span data-stu-id="810bb-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="810bb-148">Оператор IsTrue</span><span class="sxs-lookup"><span data-stu-id="810bb-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="810bb-149">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="810bb-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
