---
title: Неявное преобразование делегата (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: 57e863d9781721a997ae49e1a5c9d8f3562a1bd0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842724"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="af5a6-102">Неявное преобразование делегата (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af5a6-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="af5a6-103">Неявное преобразование делегата позволяет присваивать делегатов обработчиков, подпрограмм и функций, даже в том случае, когда их подписи не совпадают.</span><span class="sxs-lookup"><span data-stu-id="af5a6-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="af5a6-104">Таким образом привязка к делегатам становится согласованной с привязкой уже разрешенной в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="af5a6-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="af5a6-105">Параметры и тип возвращаемого значения</span><span class="sxs-lookup"><span data-stu-id="af5a6-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="af5a6-106">Вместо сопоставления точной подписи неявного преобразования требуется соблюдение следующих условий при `Option Strict` присваивается `On`:</span><span class="sxs-lookup"><span data-stu-id="af5a6-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="af5a6-107">Должно существовать расширяющее преобразование из типа данных каждого параметра делегата к типу данных соответствующего параметра назначенной функции или `Sub`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="af5a6-108">В следующем примере делегат `Del1` имеет один параметр `Integer`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="af5a6-109">Параметр `m` в назначенный лямбда-выражения должны иметь тип данных, для которого имеется расширяющее преобразование из `Integer`, такие как `Long` или `Double`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="af5a6-110">Сужающие преобразования разрешены только тогда, когда `Option Strict` присваивается `Off`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
-   <span data-ttu-id="af5a6-111">Должен существовать расширяющее преобразование в обратном направлении из возвращаемого типа назначенной функции или `Sub` в возвращаемый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="af5a6-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="af5a6-112">В следующих примерах тело каждого назначенного лямбда-выражения должно иметь тип данных, который расширяется до `Integer` поскольку возвращаемого типа метода `del1` является `Integer`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="af5a6-113">Если `Option Strict` присваивается `Off`, расширяющие ограничение удаляется в обоих направлениях.</span><span class="sxs-lookup"><span data-stu-id="af5a6-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="af5a6-114">Пропуск параметра спецификации</span><span class="sxs-lookup"><span data-stu-id="af5a6-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="af5a6-115">Ослабленные делегаты также позволяют полностью опустить параметры спецификации в назначенном методе:</span><span class="sxs-lookup"><span data-stu-id="af5a6-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="af5a6-116">Обратите внимание, что не удается задать некоторые параметры и указать другие.</span><span class="sxs-lookup"><span data-stu-id="af5a6-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="af5a6-117">Возможность опускать параметры полезна в ситуации, например при определении обработчика событий, в которых участвуют несколько сложных параметров.</span><span class="sxs-lookup"><span data-stu-id="af5a6-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="af5a6-118">Аргументы для некоторых обработчиков событий не используются.</span><span class="sxs-lookup"><span data-stu-id="af5a6-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="af5a6-119">Вместо этого обработчик непосредственно получает состояние элемента управления, на котором регистрируется событие, а аргументы игнорируются.</span><span class="sxs-lookup"><span data-stu-id="af5a6-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="af5a6-120">Ослабленные делегаты позволяют опустить аргументы в таких объявлениях, когда результат неоднозначен.</span><span class="sxs-lookup"><span data-stu-id="af5a6-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="af5a6-121">В следующем примере, полностью указанный метод `OnClick` можно переписать в виде `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="af5a6-122">Примеры AddressOf</span><span class="sxs-lookup"><span data-stu-id="af5a6-122">AddressOf Examples</span></span>  
 <span data-ttu-id="af5a6-123">Лямбда-выражения используются в предыдущих примерах облегчает связи типов см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="af5a6-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="af5a6-124">Однако ослабление разрешено для назначений делегата, использующих `AddressOf`, `Handles`, или `AddHandler`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="af5a6-125">В следующем примере функции `f1`, `f2`, `f3`, и `f4` могут быть назначены `Del1`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="af5a6-126">Следующий пример доступен, только если `Option Strict` присваивается `Off`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="af5a6-127">Игнорирование возвращаемого значения функции</span><span class="sxs-lookup"><span data-stu-id="af5a6-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="af5a6-128">Неявное преобразование делегата позволяет назначить функцию `Sub` делегата, эффективно независимо от возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="af5a6-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="af5a6-129">Тем не менее, нельзя назначить `Sub` делегату функции.</span><span class="sxs-lookup"><span data-stu-id="af5a6-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="af5a6-130">В следующем примере адрес функции `doubler` назначается `Sub` делегировать `Del3`.</span><span class="sxs-lookup"><span data-stu-id="af5a6-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="af5a6-131">См. также</span><span class="sxs-lookup"><span data-stu-id="af5a6-131">See also</span></span>

- [<span data-ttu-id="af5a6-132">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="af5a6-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="af5a6-133">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="af5a6-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="af5a6-134">Делегаты</span><span class="sxs-lookup"><span data-stu-id="af5a6-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="af5a6-135">Практическое руководство. Передача процедур другой процедуре в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af5a6-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="af5a6-136">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="af5a6-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="af5a6-137">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="af5a6-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
