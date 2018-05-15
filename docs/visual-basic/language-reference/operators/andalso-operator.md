---
title: Оператор AndAlso (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 549d14cc35d285ac2e4a02a37dd201cc669c5627
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="37ba8-102">Оператор AndAlso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37ba8-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="37ba8-103">Выполняет сокращенное вычисление логического умножения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="37ba8-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ba8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37ba8-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="37ba8-105">Части</span><span class="sxs-lookup"><span data-stu-id="37ba8-105">Parts</span></span>  
  
|<span data-ttu-id="37ba8-106">Термин</span><span class="sxs-lookup"><span data-stu-id="37ba8-106">Term</span></span>|<span data-ttu-id="37ba8-107">Определение</span><span class="sxs-lookup"><span data-stu-id="37ba8-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="37ba8-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="37ba8-108">Required.</span></span> <span data-ttu-id="37ba8-109">Произвольное выражение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="37ba8-109">Any `Boolean` expression.</span></span> <span data-ttu-id="37ba8-110">В результате `Boolean` результат сравнения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="37ba8-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="37ba8-111">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="37ba8-111">Required.</span></span> <span data-ttu-id="37ba8-112">Произвольное выражение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="37ba8-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="37ba8-113">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="37ba8-113">Required.</span></span> <span data-ttu-id="37ba8-114">Произвольное выражение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="37ba8-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37ba8-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="37ba8-115">Remarks</span></span>  
 <span data-ttu-id="37ba8-116">Логическая операция называется *сокращенного вычисления* Если скомпилированный код может пропустить оценку одного выражения в зависимости от результата другого выражения.</span><span class="sxs-lookup"><span data-stu-id="37ba8-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="37ba8-117">Если результат вычисления первого выражения определяет конечный результат операции, нет необходимости для вычисления второго выражения, так как он не может изменить результат.</span><span class="sxs-lookup"><span data-stu-id="37ba8-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="37ba8-118">Сокращенные вычисления могут повысить производительность, если пропущенное выражение является сложным или содержит вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="37ba8-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="37ba8-119">Если оба выражения `True`, `result` — `True`.</span><span class="sxs-lookup"><span data-stu-id="37ba8-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="37ba8-120">В следующей таблице показано, как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="37ba8-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="37ba8-121">Если `expression1` является</span><span class="sxs-lookup"><span data-stu-id="37ba8-121">If `expression1` is</span></span>|<span data-ttu-id="37ba8-122">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="37ba8-122">And `expression2` is</span></span>|<span data-ttu-id="37ba8-123">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="37ba8-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="37ba8-124">(не вычисленное)</span><span class="sxs-lookup"><span data-stu-id="37ba8-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="37ba8-125">Типы данных</span><span class="sxs-lookup"><span data-stu-id="37ba8-125">Data Types</span></span>  
 <span data-ttu-id="37ba8-126">`AndAlso` Оператор определен только для [тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="37ba8-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="37ba8-127">Visual Basic каждый операнд при необходимости преобразуется к `Boolean` и выполняет операцию полностью в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="37ba8-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="37ba8-128">Если назначить результат в числовой тип, Visual Basic преобразует его из `Boolean` к этому типу.</span><span class="sxs-lookup"><span data-stu-id="37ba8-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="37ba8-129">Это может привести к непредвиденному поведению.</span><span class="sxs-lookup"><span data-stu-id="37ba8-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="37ba8-130">Например `5 AndAlso 12` приводит к `–1` при преобразовании `Integer`.</span><span class="sxs-lookup"><span data-stu-id="37ba8-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="37ba8-131">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="37ba8-131">Overloading</span></span>  
 <span data-ttu-id="37ba8-132">[И оператор](../../../visual-basic/language-reference/operators/and-operator.md) и [оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип, класс или структура.</span><span class="sxs-lookup"><span data-stu-id="37ba8-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="37ba8-133">Перегрузка `And` и `IsFalse` операторы влияет на поведение `AndAlso` оператор.</span><span class="sxs-lookup"><span data-stu-id="37ba8-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="37ba8-134">Если ваш код использует `AndAlso` для класса или структуры, перегружающей `And` и `IsFalse`, убедитесь, что их переопределенное.</span><span class="sxs-lookup"><span data-stu-id="37ba8-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="37ba8-135">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="37ba8-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37ba8-136">Пример</span><span class="sxs-lookup"><span data-stu-id="37ba8-136">Example</span></span>  
 <span data-ttu-id="37ba8-137">В следующем примере используется `AndAlso` оператор для выполнения логического умножения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="37ba8-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="37ba8-138">В результате `Boolean` значение, которое показывает, что объединенное всего выражения имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="37ba8-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="37ba8-139">Если первое выражение является `False`, второй не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="37ba8-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 <span data-ttu-id="37ba8-140">В предыдущем примере получаются результаты `True`, `False`, и `False`соответственно.</span><span class="sxs-lookup"><span data-stu-id="37ba8-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="37ba8-141">При расчете `secondCheck`, второе выражение не вычисляется, поскольку первый уже `False`.</span><span class="sxs-lookup"><span data-stu-id="37ba8-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="37ba8-142">Однако второе выражение вычисляется при расчете `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="37ba8-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37ba8-143">Пример</span><span class="sxs-lookup"><span data-stu-id="37ba8-143">Example</span></span>  
 <span data-ttu-id="37ba8-144">В следующем примере показан `Function` процедуру, которая выполняет поиск заданного значения среди элементов массива.</span><span class="sxs-lookup"><span data-stu-id="37ba8-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="37ba8-145">Если массив пуст или превышает длину массива `While` инструкции не проверяет элементы массива на значение поиска.</span><span class="sxs-lookup"><span data-stu-id="37ba8-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="37ba8-146">См. также</span><span class="sxs-lookup"><span data-stu-id="37ba8-146">See Also</span></span>  
 [<span data-ttu-id="37ba8-147">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37ba8-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="37ba8-148">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37ba8-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="37ba8-149">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="37ba8-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="37ba8-150">Оператор And</span><span class="sxs-lookup"><span data-stu-id="37ba8-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)  
 [<span data-ttu-id="37ba8-151">Оператор IsFalse</span><span class="sxs-lookup"><span data-stu-id="37ba8-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="37ba8-152">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37ba8-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
