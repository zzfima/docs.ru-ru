---
title: "Смягчается преобразование делегата (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions, relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 016c808145f7faba26a288cd5075f10d7f5279d5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="bf38a-102">Неявное преобразование делегата (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf38a-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="bf38a-103">Неявное преобразование делегата позволяет присваивать делегатам обработчики, подпрограммы и функции, даже в том случае, когда их подписи не идентичны.</span><span class="sxs-lookup"><span data-stu-id="bf38a-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="bf38a-104">Таким образом привязка к делегату становится согласованной с привязкой уже разрешенной в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="bf38a-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="bf38a-105">Параметры и тип возвращаемого значения</span><span class="sxs-lookup"><span data-stu-id="bf38a-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="bf38a-106">Вместо сопоставления точной подписи ослабленное преобразование требует соблюдение следующих условий при `Option Strict` задано значение `On`:</span><span class="sxs-lookup"><span data-stu-id="bf38a-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="bf38a-107">Должно существовать расширяющее преобразование типа данных каждого параметра делегата к типу данных соответствующего параметра назначенной функции или `Sub`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="bf38a-108">В следующем примере делегат `Del1` имеет один параметр `Integer`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="bf38a-109">Параметр `m` в назначенный лямбда-выражения должны иметь тип данных, для которых имеется расширяющее преобразование из `Integer`, такие как `Long` или `Double`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     <span data-ttu-id="bf38a-110">[!code-vb[VbVbalrRelaxedDelegates&#1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-110">[!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span></span>  
  
     <span data-ttu-id="bf38a-111">[!code-vb[VbVbalrRelaxedDelegates&#2;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-111">[!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]</span></span>  
  
     <span data-ttu-id="bf38a-112">Сужающие преобразования разрешены только тогда, когда `Option Strict` равен `Off`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-112">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     <span data-ttu-id="bf38a-113">[!code-vb[VbVbalrRelaxedDelegates №&8;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-113">[!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]</span></span>  
  
-   <span data-ttu-id="bf38a-114">Должно существовать расширяющее преобразование в обратном направлении из возвращаемого типа назначенной функции или `Sub` в возвращаемый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="bf38a-114">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="bf38a-115">В следующих примерах тело каждого назначенного лямбда-выражения должно иметь тип данных, который может быть расширен до `Integer` , так как возвращаемый тип `del1` — `Integer`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-115">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     <span data-ttu-id="bf38a-116">[!code-vb[VbVbalrRelaxedDelegates&#3;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-116">[!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]</span></span>  
  
 <span data-ttu-id="bf38a-117">Если `Option Strict` равен `Off`, расширяющее ограничение удаляется в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="bf38a-117">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 <span data-ttu-id="bf38a-118">[!code-vb[VbVbalrRelaxedDelegates&#4;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-118">[!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]</span></span>  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="bf38a-119">Пропуск параметра спецификации</span><span class="sxs-lookup"><span data-stu-id="bf38a-119">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="bf38a-120">Ослабленные делегаты также позволяют полностью опустить параметры спецификации в назначенном методе:</span><span class="sxs-lookup"><span data-stu-id="bf38a-120">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 <span data-ttu-id="bf38a-121">[!code-vb[VbVbalrRelaxedDelegates&#5;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-121">[!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]</span></span>  
  
 <span data-ttu-id="bf38a-122">[!code-vb[VbVbalrRelaxedDelegates №&6;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-122">[!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]</span></span>  
  
 <span data-ttu-id="bf38a-123">Обратите внимание, что нельзя задать некоторые параметры и указать другие.</span><span class="sxs-lookup"><span data-stu-id="bf38a-123">Note that you cannot specify some parameters and omit others.</span></span>  
  
 <span data-ttu-id="bf38a-124">[!code-vb[VbVbalrRelaxedDelegates&#15;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-124">[!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]</span></span>  
  
 <span data-ttu-id="bf38a-125">Возможность опустить параметры является полезным в ситуации, например при определении обработчика событий, в которых участвуют несколько сложных параметров.</span><span class="sxs-lookup"><span data-stu-id="bf38a-125">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="bf38a-126">Аргументы для некоторых обработчиков событий не используются.</span><span class="sxs-lookup"><span data-stu-id="bf38a-126">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="bf38a-127">Вместо этого обработчик непосредственно получает состояние элемента управления, на котором регистрируется событие, а аргументы игнорируются.</span><span class="sxs-lookup"><span data-stu-id="bf38a-127">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="bf38a-128">Ослабленные делегаты позволяют опустить аргументы в таких объявлениях, когда результат неоднозначен.</span><span class="sxs-lookup"><span data-stu-id="bf38a-128">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="bf38a-129">В следующем примере полностью заданный метод `OnClick` можно переписать в виде `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-129">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="bf38a-130">Примеры AddressOf</span><span class="sxs-lookup"><span data-stu-id="bf38a-130">AddressOf Examples</span></span>  
 <span data-ttu-id="bf38a-131">Лямбда-выражения используются в предыдущих примерах облегчает связи типа см.</span><span class="sxs-lookup"><span data-stu-id="bf38a-131">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="bf38a-132">Однако ослабление разрешено для назначений делегата, использующих `AddressOf`, `Handles`, или `AddHandler`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-132">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="bf38a-133">В следующем примере функции `f1`, `f2`, `f3`, и `f4` могут быть назначены `Del1`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-133">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 <span data-ttu-id="bf38a-134">[!code-vb[VbVbalrRelaxedDelegates&#1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-134">[!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span></span>  
  
 <span data-ttu-id="bf38a-135">[!code-vb[VbVbalrRelaxedDelegates&#7;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-135">[!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]</span></span>  
  
 <span data-ttu-id="bf38a-136">[!code-vb[VbVbalrRelaxedDelegates №&9;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-136">[!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]</span></span>  
  
 <span data-ttu-id="bf38a-137">Следующий пример доступен, только если `Option Strict` равен `Off`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-137">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 <span data-ttu-id="bf38a-138">[!code-vb[VbVbalrRelaxedDelegates&#14;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-138">[!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]</span></span>  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="bf38a-139">Игнорирование возвращаемого значения функции</span><span class="sxs-lookup"><span data-stu-id="bf38a-139">Dropping Function Returns</span></span>  
 <span data-ttu-id="bf38a-140">Неявное преобразование делегата позволяет назначить функцию `Sub` делегатом, фактически независимо от возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="bf38a-140">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="bf38a-141">Тем не менее, нельзя назначить `Sub` делегату функции.</span><span class="sxs-lookup"><span data-stu-id="bf38a-141">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="bf38a-142">В следующем примере адрес функции `doubler` назначается `Sub` делегат `Del3`.</span><span class="sxs-lookup"><span data-stu-id="bf38a-142">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 <span data-ttu-id="bf38a-143">[!code-vb[VbVbalrRelaxedDelegates&#10;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-143">[!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]</span></span>  
  
 <span data-ttu-id="bf38a-144">[!code-vb[VbVbalrRelaxedDelegates&11;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf38a-144">[!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf38a-145">См. также</span><span class="sxs-lookup"><span data-stu-id="bf38a-145">See Also</span></span>  
 <span data-ttu-id="bf38a-146">[Лямбда-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="bf38a-146">[Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="bf38a-147"> [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="bf38a-147"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="bf38a-148"> [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="bf38a-148"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="bf38a-149"> [Практическое руководство: передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="bf38a-149"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="bf38a-150"> [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="bf38a-150"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="bf38a-151"> [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="bf38a-151"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
