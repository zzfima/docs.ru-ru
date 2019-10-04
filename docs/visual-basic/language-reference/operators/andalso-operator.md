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
ms.openlocfilehash: a52f598c8a7c7a79b0f2436f1add7b3eb5d5261b
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835231"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="81ed4-102">Оператор AndAlso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81ed4-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="81ed4-103">Выполняет сокращенное вычисление логического умножения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="81ed4-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81ed4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81ed4-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="81ed4-105">Части</span><span class="sxs-lookup"><span data-stu-id="81ed4-105">Parts</span></span>  
  
|<span data-ttu-id="81ed4-106">Термин</span><span class="sxs-lookup"><span data-stu-id="81ed4-106">Term</span></span>|<span data-ttu-id="81ed4-107">Определение</span><span class="sxs-lookup"><span data-stu-id="81ed4-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="81ed4-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="81ed4-108">Required.</span></span> <span data-ttu-id="81ed4-109">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="81ed4-109">Any `Boolean` expression.</span></span> <span data-ttu-id="81ed4-110">Результатом является `Boolean` при сравнении двух выражений.</span><span class="sxs-lookup"><span data-stu-id="81ed4-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="81ed4-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="81ed4-111">Required.</span></span> <span data-ttu-id="81ed4-112">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="81ed4-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="81ed4-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="81ed4-113">Required.</span></span> <span data-ttu-id="81ed4-114">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="81ed4-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81ed4-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="81ed4-115">Remarks</span></span>  
 <span data-ttu-id="81ed4-116">Логическая операция называется *сокращенной* , если скомпилированный код может обходить вычисление одного выражения в зависимости от результата другого выражения.</span><span class="sxs-lookup"><span data-stu-id="81ed4-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="81ed4-117">Если результат вычисления первого выражения определяет окончательный результат операции, нет необходимости оценивать второе выражение, так как оно не может изменить окончательный результат.</span><span class="sxs-lookup"><span data-stu-id="81ed4-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="81ed4-118">Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или если оно включает вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="81ed4-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="81ed4-119">Если оба выражения имеют значение `True`, `result` — `True`.</span><span class="sxs-lookup"><span data-stu-id="81ed4-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="81ed4-120">В следующей таблице показано, как определяется `result`.</span><span class="sxs-lookup"><span data-stu-id="81ed4-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="81ed4-121">Если `expression1` имеет значение</span><span class="sxs-lookup"><span data-stu-id="81ed4-121">If `expression1` is</span></span>|<span data-ttu-id="81ed4-122">И `expression2` является</span><span class="sxs-lookup"><span data-stu-id="81ed4-122">And `expression2` is</span></span>|<span data-ttu-id="81ed4-123">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="81ed4-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="81ed4-124">(не вычислено)</span><span class="sxs-lookup"><span data-stu-id="81ed4-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="81ed4-125">Типы данных</span><span class="sxs-lookup"><span data-stu-id="81ed4-125">Data Types</span></span>  
 <span data-ttu-id="81ed4-126">Оператор `AndAlso` определен только для [типа данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="81ed4-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="81ed4-127">При необходимости Visual Basic преобразует каждый операнд в `Boolean` перед вычислением выражения.</span><span class="sxs-lookup"><span data-stu-id="81ed4-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="81ed4-128">Если результат присваивается числовому типу, Visual Basic преобразует его из `Boolean` в этот тип, чтобы `False` стало `0`, а `True` преобразуется в `-1`.</span><span class="sxs-lookup"><span data-stu-id="81ed4-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="81ed4-129">Дополнительные сведения см. в разделе [преобразования логических типов](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="81ed4-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="81ed4-130">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="81ed4-130">Overloading</span></span>  
 <span data-ttu-id="81ed4-131">[Операторы and](../../../visual-basic/language-reference/operators/and-operator.md) и [IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) можно *перегружать*, что означает, что класс или структура могут переопределять их поведение, когда операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="81ed4-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="81ed4-132">Перегрузка операторов `And` и `IsFalse` влияет на поведение оператора `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="81ed4-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="81ed4-133">Если в коде используется `AndAlso` для класса или структуры, которая перегружает `And` и `IsFalse`, убедитесь, что вы понимаете их переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="81ed4-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="81ed4-134">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="81ed4-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81ed4-135">Пример</span><span class="sxs-lookup"><span data-stu-id="81ed4-135">Example</span></span>  
 <span data-ttu-id="81ed4-136">В следующем примере оператор `AndAlso` используется для выполнения логического умножения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="81ed4-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="81ed4-137">Результатом является значение `Boolean`, которое показывает, является ли все соединение истинным.</span><span class="sxs-lookup"><span data-stu-id="81ed4-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="81ed4-138">Если первое выражение — `False`, второе значение не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="81ed4-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="81ed4-139">В предыдущем примере создаются результаты `True`, `False` и `False` соответственно.</span><span class="sxs-lookup"><span data-stu-id="81ed4-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="81ed4-140">При вычислении `secondCheck` второе выражение не вычисляется, поскольку первый уже `False`.</span><span class="sxs-lookup"><span data-stu-id="81ed4-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="81ed4-141">Однако второе выражение вычисляется в вычислении `thirdCheck`.</span><span class="sxs-lookup"><span data-stu-id="81ed4-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81ed4-142">Пример</span><span class="sxs-lookup"><span data-stu-id="81ed4-142">Example</span></span>  
 <span data-ttu-id="81ed4-143">В следующем примере показана процедура `Function`, которая осуществляет поиск заданного значения в элементах массива.</span><span class="sxs-lookup"><span data-stu-id="81ed4-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="81ed4-144">Если массив пуст или превышена длина массива, то оператор `While` не проверяет элемент массива на соответствие значению поиска.</span><span class="sxs-lookup"><span data-stu-id="81ed4-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="81ed4-145">См. также</span><span class="sxs-lookup"><span data-stu-id="81ed4-145">See also</span></span>

- [<span data-ttu-id="81ed4-146">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81ed4-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="81ed4-147">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81ed4-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="81ed4-148">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="81ed4-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="81ed4-149">Оператор And</span><span class="sxs-lookup"><span data-stu-id="81ed4-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="81ed4-150">Оператор IsFalse</span><span class="sxs-lookup"><span data-stu-id="81ed4-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="81ed4-151">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81ed4-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
