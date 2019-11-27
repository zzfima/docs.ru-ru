---
title: Оператор OrElse
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
ms.openlocfilehash: 361de44711c3b41411f2fa1dd81a3dd8db6b01e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348236"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="229da-102">Оператор OrElse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="229da-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="229da-103">Выполняет сокращенное вычисление инклюзивного логического сложения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="229da-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="229da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="229da-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="229da-105">Части</span><span class="sxs-lookup"><span data-stu-id="229da-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="229da-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="229da-106">Required.</span></span> <span data-ttu-id="229da-107">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="229da-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="229da-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="229da-108">Required.</span></span> <span data-ttu-id="229da-109">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="229da-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="229da-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="229da-110">Required.</span></span> <span data-ttu-id="229da-111">Произвольное выражение `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="229da-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="229da-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="229da-112">Remarks</span></span>  
 <span data-ttu-id="229da-113">Логическая операция называется *сокращенной* , если скомпилированный код может обходить вычисление одного выражения в зависимости от результата другого выражения.</span><span class="sxs-lookup"><span data-stu-id="229da-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="229da-114">Если результат вычисления первого выражения определяет окончательный результат операции, нет необходимости оценивать второе выражение, так как оно не может изменить окончательный результат.</span><span class="sxs-lookup"><span data-stu-id="229da-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="229da-115">Сокращенное вычисление может повысить производительность, если пропущенное выражение является сложным или если оно включает вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="229da-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="229da-116">Если одно или оба выражения оцениваются как `True`, `result` `True`.</span><span class="sxs-lookup"><span data-stu-id="229da-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="229da-117">В следующей таблице показано, как определяется `result`.</span><span class="sxs-lookup"><span data-stu-id="229da-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="229da-118">Если `expression1`</span><span class="sxs-lookup"><span data-stu-id="229da-118">If `expression1` is</span></span>|<span data-ttu-id="229da-119">И `expression2`</span><span class="sxs-lookup"><span data-stu-id="229da-119">And `expression2` is</span></span>|<span data-ttu-id="229da-120">Значение `result` равно</span><span class="sxs-lookup"><span data-stu-id="229da-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="229da-121">(не вычислено)</span><span class="sxs-lookup"><span data-stu-id="229da-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="229da-122">Типы данных</span><span class="sxs-lookup"><span data-stu-id="229da-122">Data Types</span></span>  
 <span data-ttu-id="229da-123">Оператор `OrElse` определен только для [типа данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="229da-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="229da-124">Visual Basic преобразует каждый операнд по мере необходимости для `Boolean` перед вычислением выражения.</span><span class="sxs-lookup"><span data-stu-id="229da-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="229da-125">Если результат присваивается числовому типу, Visual Basic преобразует его из `Boolean` в такой тип, чтобы `False` `0`, а `True` — `-1`.</span><span class="sxs-lookup"><span data-stu-id="229da-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="229da-126">Дополнительные сведения см. в разделе [преобразования логических типов](../data-types/boolean-data-type.md#type-conversions).</span><span class="sxs-lookup"><span data-stu-id="229da-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="229da-127">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="229da-127">Overloading</span></span>  
 <span data-ttu-id="229da-128">[Оператор OR](../../../visual-basic/language-reference/operators/or-operator.md) и [оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) могут быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="229da-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="229da-129">Перегрузка операторов `Or` и `IsTrue` влияет на поведение оператора `OrElse`.</span><span class="sxs-lookup"><span data-stu-id="229da-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="229da-130">Если в коде используется `OrElse` для класса или структуры, которая перегружает `Or` и `IsTrue`, убедитесь, что вы понимаете их переопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="229da-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="229da-131">Для получения дополнительной информации см. [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="229da-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="229da-132">Пример</span><span class="sxs-lookup"><span data-stu-id="229da-132">Example</span></span>  
 <span data-ttu-id="229da-133">В следующем примере оператор `OrElse` используется для выполнения логического сложения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="229da-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="229da-134">Результатом является `Boolean` значение, которое показывает, имеет ли одно из двух выражений значение true.</span><span class="sxs-lookup"><span data-stu-id="229da-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="229da-135">Если первое выражение является `True`, второе значение не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="229da-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="229da-136">В предыдущем примере создаются результаты `True`, `True`и `False` соответственно.</span><span class="sxs-lookup"><span data-stu-id="229da-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="229da-137">При вычислении `firstCheck`второе выражение не вычисляется, поскольку первый уже `True`.</span><span class="sxs-lookup"><span data-stu-id="229da-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="229da-138">Однако второе выражение вычисляется в вычислении `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="229da-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="229da-139">Пример</span><span class="sxs-lookup"><span data-stu-id="229da-139">Example</span></span>  
 <span data-ttu-id="229da-140">В следующем примере показана инструкция `If`...`Then`, содержащая два вызова процедур.</span><span class="sxs-lookup"><span data-stu-id="229da-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="229da-141">Если первый вызов возвращает `True`, вторая процедура не вызывается.</span><span class="sxs-lookup"><span data-stu-id="229da-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="229da-142">Это может привести к непредвиденным результатам, если вторая процедура выполняет важные задачи, которые всегда должны выполняться при выполнении этого раздела кода.</span><span class="sxs-lookup"><span data-stu-id="229da-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="229da-143">См. также</span><span class="sxs-lookup"><span data-stu-id="229da-143">See also</span></span>

- [<span data-ttu-id="229da-144">Логические и битовые операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="229da-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="229da-145">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="229da-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="229da-146">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="229da-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="229da-147">Оператор Or</span><span class="sxs-lookup"><span data-stu-id="229da-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="229da-148">Оператор IsTrue</span><span class="sxs-lookup"><span data-stu-id="229da-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="229da-149">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="229da-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
