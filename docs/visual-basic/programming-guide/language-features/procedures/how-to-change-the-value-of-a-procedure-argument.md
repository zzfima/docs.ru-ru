---
title: Как выполнить Изменение значения аргумента процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: 096bc6adfa7a8c95674d235f0112d23f7a45caf9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672296"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="956b4-102">Как выполнить Изменение значения аргумента процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="956b4-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="956b4-103">При вызове процедуры, каждый аргумент соответствует одному из параметров, определенных в процедуре.</span><span class="sxs-lookup"><span data-stu-id="956b4-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="956b4-104">В некоторых случаях код процедуры можно изменить значение базового аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="956b4-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="956b4-105">В других случаях процедуру можно изменить только свою локальную копию аргумента.</span><span class="sxs-lookup"><span data-stu-id="956b4-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="956b4-106">При вызове процедуры, Visual Basic производит локальную копию каждый аргумент, передаваемый [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="956b4-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="956b4-107">Для каждого передаваемого аргумента [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic предоставляет код процедуры прямую ссылку на элемент программирования, в аргументе в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="956b4-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="956b4-108">Если элемент в вызывающем коде является изменяемым и аргумент, передаваемый `ByRef`, код процедуры можно использовать прямую ссылку, чтобы изменить значение этого элемента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="956b4-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="956b4-109">Изменение базового значения</span><span class="sxs-lookup"><span data-stu-id="956b4-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="956b4-110">Чтобы изменить базовое значение аргумента в вызывающем коде процедуры</span><span class="sxs-lookup"><span data-stu-id="956b4-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="956b4-111">В объявлении процедуры, указывать [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для параметра, соответствующего аргументу.</span><span class="sxs-lookup"><span data-stu-id="956b4-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="956b4-112">В вызывающем коде передайте изменяемый элемент программирования в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="956b4-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="956b4-113">В вызывающем коде не заключайте аргумент в списке аргументов в скобках.</span><span class="sxs-lookup"><span data-stu-id="956b4-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="956b4-114">В коде процедуры используйте имя параметра для присвоения значения базового элемента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="956b4-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="956b4-115">См. в примере ниже для демонстрации.</span><span class="sxs-lookup"><span data-stu-id="956b4-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="956b4-116">Изменение локальных копий</span><span class="sxs-lookup"><span data-stu-id="956b4-116">Changing Local Copies</span></span>  
 <span data-ttu-id="956b4-117">Если элемент в вызывающем коде является неизменяемым или если аргумент, передаваемый `ByVal`, процедура не может изменить его значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="956b4-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="956b4-118">Тем не менее процедура может изменять свою локальную копию такого аргумента.</span><span class="sxs-lookup"><span data-stu-id="956b4-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="956b4-119">Чтобы изменить копию аргумента процедуры в коде процедуры</span><span class="sxs-lookup"><span data-stu-id="956b4-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="956b4-120">В объявлении процедуры, указывать [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) для параметра, соответствующего аргументу.</span><span class="sxs-lookup"><span data-stu-id="956b4-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="956b4-121">- или -</span><span class="sxs-lookup"><span data-stu-id="956b4-121">-or-</span></span>  
  
     <span data-ttu-id="956b4-122">В вызывающем коде заключите аргумент в списке аргументов в скобках.</span><span class="sxs-lookup"><span data-stu-id="956b4-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="956b4-123">Это заставляет Visual Basic для передачи аргумента по значению, даже если соответствующий параметр указывает `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="956b4-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="956b4-124">В коде процедуры используйте имя параметра для присвоения значения аргумента в локальной копии.</span><span class="sxs-lookup"><span data-stu-id="956b4-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="956b4-125">Базовое значение в вызывающий код не изменяется.</span><span class="sxs-lookup"><span data-stu-id="956b4-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="956b4-126">Пример</span><span class="sxs-lookup"><span data-stu-id="956b4-126">Example</span></span>  
 <span data-ttu-id="956b4-127">Следующий пример показывает две процедуры, которые принимают переменную массива и работают на его элементы.</span><span class="sxs-lookup"><span data-stu-id="956b4-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="956b4-128">`increase` Процедура добавляет единицу к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="956b4-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="956b4-129">`replace` Процедура присваивает новый массив в параметре `a()` и добавляет единицу к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="956b4-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 <span data-ttu-id="956b4-130">Первый `MsgBox` вызове отображается «после увеличения (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="956b4-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="956b4-131">Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на то, что механизм передачи `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="956b4-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="956b4-132">Второй `MsgBox` вызове отображается «после замены(n): 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="956b4-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="956b4-133">Так как `n` передается `ByRef`, `replace` можно изменить переменную `n` в вызывающий код и присвоить ей новый массив, к нему.</span><span class="sxs-lookup"><span data-stu-id="956b4-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="956b4-134">Так как `n` является ссылочным типом, `replace` также можно менять ее членов.</span><span class="sxs-lookup"><span data-stu-id="956b4-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="956b4-135">Можно запретить процедуре изменять переменную в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="956b4-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="956b4-136">См. практическое руководство по [ Защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="956b4-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="956b4-137">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="956b4-137">Compiling the Code</span></span>  
 <span data-ttu-id="956b4-138">Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово, чтобы указать этот механизм.</span><span class="sxs-lookup"><span data-stu-id="956b4-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="956b4-139">По умолчанию в Visual Basic используется для передачи аргументов по значению.</span><span class="sxs-lookup"><span data-stu-id="956b4-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="956b4-140">Тем не менее, рекомендуется использовать одну [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром.</span><span class="sxs-lookup"><span data-stu-id="956b4-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="956b4-141">Это делает код более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="956b4-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="956b4-142">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="956b4-142">.NET Framework Security</span></span>  
 <span data-ttu-id="956b4-143">Всегда найдется потенциальную угрозу в разрешении процедуре измените значение базового аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="956b4-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="956b4-144">Убедитесь, что предполагается, что это значение, чтобы изменить и будьте готовы, проверяемый на допустимость перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="956b4-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956b4-145">См. также</span><span class="sxs-lookup"><span data-stu-id="956b4-145">See also</span></span>
- [<span data-ttu-id="956b4-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="956b4-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="956b4-147">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="956b4-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="956b4-148">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="956b4-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="956b4-149">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="956b4-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="956b4-150">Различия между изменяемыми и неизменяемыми аргументами</span><span class="sxs-lookup"><span data-stu-id="956b4-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="956b4-151">Различия между передачей аргумента по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="956b4-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="956b4-152">Практическое руководство. Защита аргумента процедуры от изменения значения</span><span class="sxs-lookup"><span data-stu-id="956b4-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="956b4-153">Практическое руководство. Принудительная передаваться по значению аргумента</span><span class="sxs-lookup"><span data-stu-id="956b4-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="956b4-154">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="956b4-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="956b4-155">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="956b4-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
