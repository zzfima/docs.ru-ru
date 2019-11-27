---
title: Неявное преобразование делегата
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: ffb242842553382ba26121333c38fc65eaa168a9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345221"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="e57f5-102">Неявное преобразование делегата (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e57f5-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="e57f5-103">Неявное преобразование делегатов позволяет назначать процедуры и функции делегатам или обработчикам, даже если их сигнатуры не идентичны.</span><span class="sxs-lookup"><span data-stu-id="e57f5-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="e57f5-104">Таким образом, привязка к делегатам будет соответствовать привязке, уже разрешенной для вызовов методов.</span><span class="sxs-lookup"><span data-stu-id="e57f5-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="e57f5-105">Параметры и возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="e57f5-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="e57f5-106">Вместо точного соответствия сигнатуры для ослабленного преобразования требуется выполнение следующих условий, если `Option Strict` имеет значение `On`.</span><span class="sxs-lookup"><span data-stu-id="e57f5-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="e57f5-107">Должно существовать расширяющее преобразование из типа данных каждого параметра делегата в тип данных соответствующего параметра назначенной функции или `Sub`.</span><span class="sxs-lookup"><span data-stu-id="e57f5-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="e57f5-108">В следующем примере делегат `Del1` имеет один параметр — `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e57f5-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="e57f5-109">Параметр `m` в назначенных лямбда-выражениях должен иметь тип данных, для которого существует расширяющее преобразование из `Integer`, например `Long` или `Double`.</span><span class="sxs-lookup"><span data-stu-id="e57f5-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="e57f5-110">Сужающие преобразования разрешены, только если `Option Strict` имеет значение `Off`.</span><span class="sxs-lookup"><span data-stu-id="e57f5-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="e57f5-111">Расширяющее преобразование должно существовать в обратном направлении от возвращаемого типа назначенной функции или `Sub` типу возвращаемого значения делегата.</span><span class="sxs-lookup"><span data-stu-id="e57f5-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="e57f5-112">В следующих примерах текст каждого назначенного лямбда-выражения должен иметь тип данных, который расширяется на `Integer`, поскольку тип возвращаемого значения `del1` — `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e57f5-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="e57f5-113">Если `Option Strict` имеет значение `Off`, расширяющееся ограничение удаляется в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="e57f5-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="e57f5-114">Пропуск спецификаций параметров</span><span class="sxs-lookup"><span data-stu-id="e57f5-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="e57f5-115">Ослабленные делегаты также позволяют полностью опускать спецификации параметров в назначенном методе:</span><span class="sxs-lookup"><span data-stu-id="e57f5-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="e57f5-116">Обратите внимание, что нельзя указать некоторые параметры и опустить другие.</span><span class="sxs-lookup"><span data-stu-id="e57f5-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="e57f5-117">Возможность опускать параметры полезна в таких ситуациях, как определение обработчика событий, в котором участвуют несколько сложных параметров.</span><span class="sxs-lookup"><span data-stu-id="e57f5-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="e57f5-118">Аргументы некоторых обработчиков событий не используются.</span><span class="sxs-lookup"><span data-stu-id="e57f5-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="e57f5-119">Вместо этого обработчик напрямую обращается к состоянию элемента управления, в котором регистрируется событие, и игнорирует аргументы.</span><span class="sxs-lookup"><span data-stu-id="e57f5-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="e57f5-120">Ослабленные делегаты позволяют опускать аргументы в таких объявлениях, если результат неоднозначности.</span><span class="sxs-lookup"><span data-stu-id="e57f5-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="e57f5-121">В следующем примере полностью указанный метод `OnClick` может быть перезаписан как `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="e57f5-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="e57f5-122">Примеры AddressOf</span><span class="sxs-lookup"><span data-stu-id="e57f5-122">AddressOf Examples</span></span>  
 <span data-ttu-id="e57f5-123">Лямбда-выражения используются в предыдущих примерах для упрощения просмотра связей типов.</span><span class="sxs-lookup"><span data-stu-id="e57f5-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="e57f5-124">Тем не менее, для назначений делегатов, использующих `AddressOf`, `Handles`или `AddHandler`, разрешены одни и те же ограничения.</span><span class="sxs-lookup"><span data-stu-id="e57f5-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="e57f5-125">В следующем примере функции `f1`, `f2`, `f3`и `f4` могут быть назначены `Del1`.</span><span class="sxs-lookup"><span data-stu-id="e57f5-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="e57f5-126">Следующий пример допустим только в том случае, если `Option Strict` имеет значение `Off`.</span><span class="sxs-lookup"><span data-stu-id="e57f5-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="e57f5-127">Удаление возвращаемых функций</span><span class="sxs-lookup"><span data-stu-id="e57f5-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="e57f5-128">Неявное преобразование делегата позволяет присвоить функцию делегату `Sub`, фактически игнорируя возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="e57f5-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="e57f5-129">Однако нельзя присвоить `Sub` делегату функции.</span><span class="sxs-lookup"><span data-stu-id="e57f5-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="e57f5-130">В следующем примере адрес функции `doubler` назначается `Sub` `Del3`делегата.</span><span class="sxs-lookup"><span data-stu-id="e57f5-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="e57f5-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e57f5-131">See also</span></span>

- [<span data-ttu-id="e57f5-132">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="e57f5-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="e57f5-133">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="e57f5-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="e57f5-134">Делегаты</span><span class="sxs-lookup"><span data-stu-id="e57f5-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- <span data-ttu-id="e57f5-135">[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e57f5-135">[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)</span></span>
- [<span data-ttu-id="e57f5-136">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="e57f5-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="e57f5-137">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="e57f5-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
