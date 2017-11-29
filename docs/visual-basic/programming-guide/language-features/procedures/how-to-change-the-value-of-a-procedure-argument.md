---
title: "Практическое руководство. Изменение значения аргумента процедуры (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba23c8f0b4b0b6e751546019af902a6305b9ef53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="31baf-102">Практическое руководство. Изменение значения аргумента процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31baf-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="31baf-103">При вызове процедуры каждый аргумент соответствует одному из параметров, определенных в процедуре.</span><span class="sxs-lookup"><span data-stu-id="31baf-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="31baf-104">В некоторых случаях код процедуры можно изменить значение базового аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="31baf-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="31baf-105">В других случаях процедура может изменять только его локальную копию аргумента.</span><span class="sxs-lookup"><span data-stu-id="31baf-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="31baf-106">При вызове процедуры, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] делает локальную копию каждого аргумента, который передается [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="31baf-106">When you call the procedure, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="31baf-107">Для каждого передаваемого аргумента [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] предоставляет код процедуры прямую ссылку на элемент программирования в аргументе в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="31baf-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="31baf-108">Если базовый элемент в вызывающем коде является изменяемым и передается аргумент `ByRef`, код процедуры можно использовать прямую ссылку, чтобы изменить значение элемента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="31baf-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="31baf-109">Изменение базового значения</span><span class="sxs-lookup"><span data-stu-id="31baf-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="31baf-110">Чтобы изменить базовое значение аргумента в вызывающем коде процедуры</span><span class="sxs-lookup"><span data-stu-id="31baf-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="31baf-111">В объявлении процедуры укажите [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для параметра, соответствующего аргументу.</span><span class="sxs-lookup"><span data-stu-id="31baf-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="31baf-112">В вызывающем коде передайте изменяемый элемент программирования в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="31baf-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="31baf-113">В вызывающем коде не заключайте аргумент в списке аргументов в скобках.</span><span class="sxs-lookup"><span data-stu-id="31baf-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="31baf-114">В коде процедуры используйте имя параметра для присвоения значения основной элемент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="31baf-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="31baf-115">См. в примере ниже для демонстрации.</span><span class="sxs-lookup"><span data-stu-id="31baf-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="31baf-116">Изменение локальных копий</span><span class="sxs-lookup"><span data-stu-id="31baf-116">Changing Local Copies</span></span>  
 <span data-ttu-id="31baf-117">Если базовый элемент в вызывающем коде является неизменяемым или если передается аргумент `ByVal`, процедура не может изменить его значение в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="31baf-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="31baf-118">Однако процедура может изменить свою локальную копию такого аргумента.</span><span class="sxs-lookup"><span data-stu-id="31baf-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="31baf-119">Чтобы изменить копию аргумента процедуры в коде процедуры</span><span class="sxs-lookup"><span data-stu-id="31baf-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="31baf-120">В объявлении процедуры укажите [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) для параметра, соответствующего аргументу.</span><span class="sxs-lookup"><span data-stu-id="31baf-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="31baf-121">-или-</span><span class="sxs-lookup"><span data-stu-id="31baf-121">-or-</span></span>  
  
     <span data-ttu-id="31baf-122">В вызывающем коде заключите аргумент в скобки в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="31baf-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="31baf-123">Это заставляет [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] передача аргумента по значению, даже если соответствующий параметр указывает `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="31baf-123">This forces [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="31baf-124">В коде процедуры используйте имя параметра для присвоения значения локальной копии аргумента.</span><span class="sxs-lookup"><span data-stu-id="31baf-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="31baf-125">Базовое значение в вызывающий код не изменяется.</span><span class="sxs-lookup"><span data-stu-id="31baf-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31baf-126">Пример</span><span class="sxs-lookup"><span data-stu-id="31baf-126">Example</span></span>  
 <span data-ttu-id="31baf-127">Следующий пример показывает две процедуры, которые принимают переменную массива и работать над его элементами.</span><span class="sxs-lookup"><span data-stu-id="31baf-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="31baf-128">`increase` Процедура добавляет единицу к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="31baf-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="31baf-129">`replace` Процедура присваивает новый массив параметру `a()` и добавляет единицу к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="31baf-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 <span data-ttu-id="31baf-130">Первый `MsgBox` вызове отображается «после увеличения (n): 11, 21, 31, 41».</span><span class="sxs-lookup"><span data-stu-id="31baf-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="31baf-131">Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на то, что механизм передачи `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="31baf-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="31baf-132">Второй `MsgBox` вызове отображается «после замены(n): 101, 201, 301».</span><span class="sxs-lookup"><span data-stu-id="31baf-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="31baf-133">Поскольку `n` передается `ByRef`, `replace` можно изменить переменную `n` в вызывающем коде и присвоить ей новый массив.</span><span class="sxs-lookup"><span data-stu-id="31baf-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="31baf-134">Поскольку `n` является ссылочным типом, `replace` может изменять его члены.</span><span class="sxs-lookup"><span data-stu-id="31baf-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="31baf-135">Можно запретить процедуре изменять переменную в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="31baf-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="31baf-136">В разделе [как: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="31baf-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31baf-137">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="31baf-137">Compiling the Code</span></span>  
 <span data-ttu-id="31baf-138">Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово, чтобы указать этот механизм.</span><span class="sxs-lookup"><span data-stu-id="31baf-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="31baf-139">Значение по умолчанию в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] аргументы передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="31baf-139">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="31baf-140">Тем не менее, это хороший стиль программирования способ включения либо [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром.</span><span class="sxs-lookup"><span data-stu-id="31baf-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="31baf-141">Это делает код более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="31baf-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="31baf-142">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="31baf-142">.NET Framework Security</span></span>  
 <span data-ttu-id="31baf-143">Всегда есть потенциальный риск при разрешении процедуре изменять значение базового аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="31baf-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="31baf-144">Убедитесь, что предполагается, что это значение, чтобы изменить и будьте готовы к проверке его допустимости перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="31baf-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31baf-145">См. также</span><span class="sxs-lookup"><span data-stu-id="31baf-145">See Also</span></span>  
 [<span data-ttu-id="31baf-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="31baf-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="31baf-147">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="31baf-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="31baf-148">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="31baf-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="31baf-149">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="31baf-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="31baf-150">Различия между изменяемыми и неизменяемыми аргументами</span><span class="sxs-lookup"><span data-stu-id="31baf-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="31baf-151">Различия между передачей аргумента по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="31baf-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="31baf-152">Практическое руководство. Защита аргумента процедуры от изменений значения</span><span class="sxs-lookup"><span data-stu-id="31baf-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="31baf-153">Практическое руководство. Принудительная передача аргумента по значению</span><span class="sxs-lookup"><span data-stu-id="31baf-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="31baf-154">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="31baf-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="31baf-155">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="31baf-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
