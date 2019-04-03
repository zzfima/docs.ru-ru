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
ms.openlocfilehash: 3876fd9c32d486b8ebecc9ee2428486a687a1624
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817127"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="5471a-102">Оператор AndAlso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5471a-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="5471a-103">Выполняет сокращенное вычисление логического умножения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="5471a-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5471a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5471a-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="5471a-105">Части</span><span class="sxs-lookup"><span data-stu-id="5471a-105">Parts</span></span>  
  
|<span data-ttu-id="5471a-106">Термин</span><span class="sxs-lookup"><span data-stu-id="5471a-106">Term</span></span>|<span data-ttu-id="5471a-107">Определение</span><span class="sxs-lookup"><span data-stu-id="5471a-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="5471a-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5471a-108">Required.</span></span> <span data-ttu-id="5471a-109">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5471a-109">Any `Boolean` expression.</span></span> <span data-ttu-id="5471a-110">В результате `Boolean` результат сравнения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="5471a-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="5471a-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5471a-111">Required.</span></span> <span data-ttu-id="5471a-112">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5471a-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="5471a-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5471a-113">Required.</span></span> <span data-ttu-id="5471a-114">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="5471a-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5471a-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="5471a-115">Remarks</span></span>  
 <span data-ttu-id="5471a-116">Логическая операция называется *сокращенного вычисления* Если скомпилированный код может пропустить вычисления одного выражения в зависимости от результата другого выражения.</span><span class="sxs-lookup"><span data-stu-id="5471a-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="5471a-117">Если результат вычисления первого выражения определяет конечный результат операции, нет необходимости для вычисления второго выражения, так как он не может изменить результат.</span><span class="sxs-lookup"><span data-stu-id="5471a-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="5471a-118">Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или содержит вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="5471a-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="5471a-119">Если оба выражения имеют значение `True`, `result` является `True`.</span><span class="sxs-lookup"><span data-stu-id="5471a-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="5471a-120">В следующей таблице показано как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="5471a-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="5471a-121">Если `expression1` —</span><span class="sxs-lookup"><span data-stu-id="5471a-121">If `expression1` is</span></span>|<span data-ttu-id="5471a-122">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="5471a-122">And `expression2` is</span></span>|<span data-ttu-id="5471a-123">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="5471a-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="5471a-124">(не вычисленное)</span><span class="sxs-lookup"><span data-stu-id="5471a-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="5471a-125">Типы данных</span><span class="sxs-lookup"><span data-stu-id="5471a-125">Data Types</span></span>  
 <span data-ttu-id="5471a-126">`AndAlso` Оператор определен только для [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="5471a-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="5471a-127">Visual Basic преобразует каждый операнд при необходимости `Boolean` и выполняет операцию полностью в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5471a-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="5471a-128">Если результат назначается числовой тип, Visual Basic преобразует его из `Boolean` к этому типу.</span><span class="sxs-lookup"><span data-stu-id="5471a-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="5471a-129">Это может привести к непредвиденному поведению.</span><span class="sxs-lookup"><span data-stu-id="5471a-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="5471a-130">Например `5 AndAlso 12` приводит `–1` при преобразовании `Integer`.</span><span class="sxs-lookup"><span data-stu-id="5471a-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5471a-131">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="5471a-131">Overloading</span></span>  
 <span data-ttu-id="5471a-132">[И оператором](../../../visual-basic/language-reference/operators/and-operator.md) и [оператор IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип, класс или структура.</span><span class="sxs-lookup"><span data-stu-id="5471a-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5471a-133">Перегрузка `And` и `IsFalse` операторы влияет на поведение `AndAlso` оператор.</span><span class="sxs-lookup"><span data-stu-id="5471a-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="5471a-134">Если код использует `AndAlso` для класса или структуры, перегружающей `And` и `IsFalse`, убедитесь, что их переопределенное.</span><span class="sxs-lookup"><span data-stu-id="5471a-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="5471a-135">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5471a-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5471a-136">Пример</span><span class="sxs-lookup"><span data-stu-id="5471a-136">Example</span></span>  
 <span data-ttu-id="5471a-137">В следующем примере используется `AndAlso` оператору выполнять логическое умножение двух выражений.</span><span class="sxs-lookup"><span data-stu-id="5471a-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="5471a-138">В результате `Boolean` значение, представляющее ли весь объединенных выражение имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="5471a-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="5471a-139">Если первое выражение является `False`, второй не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="5471a-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="5471a-140">В предыдущем примере получался результат `True`, `False`, и `False`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="5471a-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="5471a-141">В расчет `secondCheck`, второе выражение не вычисляется, так как первый уже `False`.</span><span class="sxs-lookup"><span data-stu-id="5471a-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="5471a-142">Однако второе выражение оценивается в расчете `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="5471a-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5471a-143">Пример</span><span class="sxs-lookup"><span data-stu-id="5471a-143">Example</span></span>  
 <span data-ttu-id="5471a-144">В следующем примере показан `Function` процедуру, которая выполняет поиск заданного значения среди элементов массива.</span><span class="sxs-lookup"><span data-stu-id="5471a-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="5471a-145">Если массив пуст или если длина массива было превышено, `While` инструкции не проверяет элемент массива на значение поиска.</span><span class="sxs-lookup"><span data-stu-id="5471a-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="5471a-146">См. также</span><span class="sxs-lookup"><span data-stu-id="5471a-146">See also</span></span>

- [<span data-ttu-id="5471a-147">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5471a-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="5471a-148">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5471a-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5471a-149">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="5471a-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="5471a-150">Оператор And</span><span class="sxs-lookup"><span data-stu-id="5471a-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="5471a-151">Оператор IsFalse</span><span class="sxs-lookup"><span data-stu-id="5471a-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="5471a-152">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5471a-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
