---
title: "Оператор OrElse (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47239a1d2b5b20f2b8cacc9b9185a0f95f63dc84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="8a05e-102">Оператор OrElse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a05e-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="8a05e-103">Выполняет сокращенное вычисление логического сложения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="8a05e-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a05e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a05e-104">Syntax</span></span>  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="8a05e-105">Части</span><span class="sxs-lookup"><span data-stu-id="8a05e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="8a05e-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8a05e-106">Required.</span></span> <span data-ttu-id="8a05e-107">Произвольное выражение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8a05e-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="8a05e-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8a05e-108">Required.</span></span> <span data-ttu-id="8a05e-109">Произвольное выражение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8a05e-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="8a05e-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8a05e-110">Required.</span></span> <span data-ttu-id="8a05e-111">Произвольное выражение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8a05e-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a05e-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a05e-112">Remarks</span></span>  
 <span data-ttu-id="8a05e-113">Логическая операция называется *сокращенного вычисления* Если скомпилированный код может пропустить оценку одного выражения в зависимости от результата другого выражения.</span><span class="sxs-lookup"><span data-stu-id="8a05e-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="8a05e-114">Если результат вычисления первого выражения определяет конечный результат операции, нет необходимости для вычисления второго выражения, так как он не может изменить результат.</span><span class="sxs-lookup"><span data-stu-id="8a05e-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="8a05e-115">Сокращенные вычисления могут повысить производительность, если пропущенное выражение является сложным или содержит вызовы процедур.</span><span class="sxs-lookup"><span data-stu-id="8a05e-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="8a05e-116">Если один или оба выражения `True`, `result` — `True`.</span><span class="sxs-lookup"><span data-stu-id="8a05e-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="8a05e-117">В следующей таблице показано, как `result` определяется.</span><span class="sxs-lookup"><span data-stu-id="8a05e-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8a05e-118">Если `expression1` является</span><span class="sxs-lookup"><span data-stu-id="8a05e-118">If `expression1` is</span></span>|<span data-ttu-id="8a05e-119">И `expression2` —</span><span class="sxs-lookup"><span data-stu-id="8a05e-119">And `expression2` is</span></span>|<span data-ttu-id="8a05e-120">Значение `result` —</span><span class="sxs-lookup"><span data-stu-id="8a05e-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="8a05e-121">(не вычисленное)</span><span class="sxs-lookup"><span data-stu-id="8a05e-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="8a05e-122">Типы данных</span><span class="sxs-lookup"><span data-stu-id="8a05e-122">Data Types</span></span>  
 <span data-ttu-id="8a05e-123">`OrElse` Оператор определен только для [тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="8a05e-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="8a05e-124">Visual Basic каждый операнд при необходимости преобразуется к `Boolean` и выполняет операцию полностью в `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8a05e-124">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="8a05e-125">Если назначить результат в числовой тип, Visual Basic преобразует его из `Boolean` к этому типу.</span><span class="sxs-lookup"><span data-stu-id="8a05e-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="8a05e-126">Это может привести к непредвиденному поведению.</span><span class="sxs-lookup"><span data-stu-id="8a05e-126">This could produce unexpected behavior.</span></span> <span data-ttu-id="8a05e-127">Например `5 OrElse 12` приводит к `–1` при преобразовании `Integer`.</span><span class="sxs-lookup"><span data-stu-id="8a05e-127">For example, `5 OrElse 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8a05e-128">Перегрузка</span><span class="sxs-lookup"><span data-stu-id="8a05e-128">Overloading</span></span>  
 <span data-ttu-id="8a05e-129">[Или оператор](../../../visual-basic/language-reference/operators/or-operator.md) и [Оператор IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) может быть *перегружены*, что означает, что класс или структура может переопределить их поведение, если операнд имеет тип этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="8a05e-129">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8a05e-130">Перегрузка `Or` и `IsTrue` операторы влияет на поведение `OrElse` оператор.</span><span class="sxs-lookup"><span data-stu-id="8a05e-130">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="8a05e-131">Если ваш код использует `OrElse` для класса или структуры, перегружающей `Or` и `IsTrue`, убедитесь, что их переопределенное.</span><span class="sxs-lookup"><span data-stu-id="8a05e-131">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="8a05e-132">Дополнительные сведения см. в разделе [процедуры оператора](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8a05e-132">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a05e-133">Пример</span><span class="sxs-lookup"><span data-stu-id="8a05e-133">Example</span></span>  
 <span data-ttu-id="8a05e-134">В следующем примере используется `OrElse` оператор для выполнения логического сложения двух выражений.</span><span class="sxs-lookup"><span data-stu-id="8a05e-134">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="8a05e-135">В результате `Boolean` значение, представляющее ли одно из выражений имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="8a05e-135">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="8a05e-136">Если первое выражение является `True`, второй не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="8a05e-136">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 <span data-ttu-id="8a05e-137">В предыдущем примере получаются результаты `True`, `True`, и `False` соответственно.</span><span class="sxs-lookup"><span data-stu-id="8a05e-137">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="8a05e-138">При расчете `firstCheck`, второе выражение не вычисляется, поскольку первый уже `True`.</span><span class="sxs-lookup"><span data-stu-id="8a05e-138">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="8a05e-139">Однако второе выражение вычисляется при расчете `secondCheck`.</span><span class="sxs-lookup"><span data-stu-id="8a05e-139">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a05e-140">Пример</span><span class="sxs-lookup"><span data-stu-id="8a05e-140">Example</span></span>  
 <span data-ttu-id="8a05e-141">В следующем примере показан `If`... `Then` оператор, содержащий два вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="8a05e-141">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="8a05e-142">Если первый вызов возвращает `True`, вторая процедура не вызывается.</span><span class="sxs-lookup"><span data-stu-id="8a05e-142">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="8a05e-143">Это может привести к непредвиденным результатам, если вторая процедура выполняет важные задачи, которые всегда должны быть выполнены при запуске этот раздел кода.</span><span class="sxs-lookup"><span data-stu-id="8a05e-143">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8a05e-144">См. также</span><span class="sxs-lookup"><span data-stu-id="8a05e-144">See Also</span></span>  
 [<span data-ttu-id="8a05e-145">Логические (побитовые) операторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a05e-145">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="8a05e-146">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a05e-146">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="8a05e-147">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="8a05e-147">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="8a05e-148">Оператор Or</span><span class="sxs-lookup"><span data-stu-id="8a05e-148">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)  
 [<span data-ttu-id="8a05e-149">Оператор IsTrue</span><span class="sxs-lookup"><span data-stu-id="8a05e-149">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="8a05e-150">Логические и побитовые операторы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a05e-150">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
