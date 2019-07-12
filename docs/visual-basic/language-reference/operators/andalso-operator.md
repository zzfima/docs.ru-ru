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
ms.openlocfilehash: 1cb4d372d3ac228f29c6fa45f124796e5dfb6709
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859885"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="c8cf8-102">Оператор AndAlso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8cf8-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="c8cf8-103">Выполняет сокращенное вычисление логического умножения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8cf8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8cf8-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c8cf8-105">Части</span><span class="sxs-lookup"><span data-stu-id="c8cf8-105">Parts</span></span>  
  
|<span data-ttu-id="c8cf8-106">Термин</span><span class="sxs-lookup"><span data-stu-id="c8cf8-106">Term</span></span>|<span data-ttu-id="c8cf8-107">Определение</span><span class="sxs-lookup"><span data-stu-id="c8cf8-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="c8cf8-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-108">Required.</span></span> <span data-ttu-id="c8cf8-109">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="c8cf8-109">Any `Boolean` expression.</span></span> <span data-ttu-id="c8cf8-110">В результате `Boolean` результат сравнения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="c8cf8-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-111">Required.</span></span> <span data-ttu-id="c8cf8-112">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="c8cf8-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="c8cf8-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-113">Required.</span></span> <span data-ttu-id="c8cf8-114">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="c8cf8-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8cf8-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8cf8-115">Remarks</span></span>  
 <span data-ttu-id="c8cf8-116">Логическая операция называется *сокращенного вычисления* Если скомпилированный код может пропустить вычисления одного выражения в зависимости от результата другого выражения.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="c8cf8-117">Если результат вычисления первого выражения определяет конечный результат операции, нет необходимости для вычисления второго выражения, так как он не может изменить результат.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="c8cf8-118">Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или содержит вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="c8cf8-119">Если оба выражения имеют значение `True`, `result` является `True`.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="c8cf8-120">В следующей таблице показано как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c8cf8-121">Если `expression1` —</span><span class="sxs-lookup"><span data-stu-id="c8cf8-121">If `expression1` is</span></span>|<span data-ttu-id="c8cf8-122">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="c8cf8-122">And `expression2` is</span></span>|<span data-ttu-id="c8cf8-123">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="c8cf8-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="c8cf8-124">(не вычисленное)</span><span class="sxs-lookup"><span data-stu-id="c8cf8-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="c8cf8-125">Типы данных</span><span class="sxs-lookup"><span data-stu-id="c8cf8-125">Data Types</span></span>  
 <span data-ttu-id="c8cf8-126">`AndAlso` Оператор определен только для [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="c8cf8-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="c8cf8-127">Visual Basic преобразует каждый операнд при необходимости `Boolean` перед вычислением выражения.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="c8cf8-128">Если результат назначается числовой тип, Visual Basic преобразует его из `Boolean` к этому типу таким образом, чтобы `False` становится `0` и `True` становится `-1`.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="c8cf8-129">Дополнительные сведения см. в разделе [логическое преобразования типов](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="c8cf8-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="c8cf8-130">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="c8cf8-130">Overloading</span></span>  
 <span data-ttu-id="c8cf8-131">[И оператором](../../../visual-basic/language-reference/operators/and-operator.md) и [оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип, класс или структура.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c8cf8-132">Перегрузка `And` и `IsFalse` операторы влияет на поведение `AndAlso` оператор.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="c8cf8-133">Если код использует `AndAlso` для класса или структуры, перегружающей `And` и `IsFalse`, убедитесь, что их переопределенное.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="c8cf8-134">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c8cf8-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8cf8-135">Пример</span><span class="sxs-lookup"><span data-stu-id="c8cf8-135">Example</span></span>  
 <span data-ttu-id="c8cf8-136">В следующем примере используется `AndAlso` оператору выполнять логическое умножение двух выражений.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="c8cf8-137">В результате `Boolean` значение, представляющее ли весь объединенных выражение имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="c8cf8-138">Если первое выражение является `False`, второй не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="c8cf8-139">В предыдущем примере получался результат `True`, `False`, и `False`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="c8cf8-140">В расчет `secondCheck`, второе выражение не вычисляется, так как первый уже `False`.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="c8cf8-141">Однако второе выражение оценивается в расчете `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8cf8-142">Пример</span><span class="sxs-lookup"><span data-stu-id="c8cf8-142">Example</span></span>  
 <span data-ttu-id="c8cf8-143">В следующем примере показан `Function` процедуру, которая выполняет поиск заданного значения среди элементов массива.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="c8cf8-144">Если массив пуст или если длина массива было превышено, `While` инструкции не проверяет элемент массива на значение поиска.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="c8cf8-145">См. также</span><span class="sxs-lookup"><span data-stu-id="c8cf8-145">See also</span></span>

- [<span data-ttu-id="c8cf8-146">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8cf8-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="c8cf8-147">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8cf8-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c8cf8-148">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="c8cf8-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c8cf8-149">Оператор And</span><span class="sxs-lookup"><span data-stu-id="c8cf8-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="c8cf8-150">Оператор IsFalse</span><span class="sxs-lookup"><span data-stu-id="c8cf8-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="c8cf8-151">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8cf8-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
