---
title: "Практическое руководство: изменение значения аргумента процедуры (Visual Basic) | Документы Microsoft"
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
- procedures, arguments
- procedures, parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
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
ms.openlocfilehash: 3f192d738ca2753cd12b6fffca1f4f94a606a42c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="54a0b-102">Практическое руководство. Изменение значения аргумента процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54a0b-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="54a0b-103">При вызове процедуры каждый аргумент соответствует одному из параметров, определенных в процедуре.</span><span class="sxs-lookup"><span data-stu-id="54a0b-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="54a0b-104">В некоторых случаях код процедуры можно изменить значение, лежащий в основе аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="54a0b-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="54a0b-105">В других случаях процедура может изменять только его локальную копию аргумента.</span><span class="sxs-lookup"><span data-stu-id="54a0b-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="54a0b-106">При вызове процедуры, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] делает локальную копию каждого аргумента, который передается [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="54a0b-106">When you call the procedure, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="54a0b-107">Для каждого передаваемого аргумента [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет код процедуры прямую ссылку на программный элемент, лежащий в основе аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="54a0b-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="54a0b-108">Если базовый элемент вызывающего кода является изменяемым, и аргумент передается `ByRef`, код процедуры позволяет изменить значение элемента в вызывающем коде прямых ссылок.</span><span class="sxs-lookup"><span data-stu-id="54a0b-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="54a0b-109">Изменение базового значения</span><span class="sxs-lookup"><span data-stu-id="54a0b-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="54a0b-110">Чтобы изменить основное значение аргумента в вызывающем коде процедуры</span><span class="sxs-lookup"><span data-stu-id="54a0b-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="54a0b-111">В объявлении процедуры укажите [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для параметра, соответствующего аргументу.</span><span class="sxs-lookup"><span data-stu-id="54a0b-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="54a0b-112">В вызывающем коде передайте изменяемый элемент программирования в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="54a0b-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="54a0b-113">В вызывающем коде не заключайте аргумент в список аргументов в скобках.</span><span class="sxs-lookup"><span data-stu-id="54a0b-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="54a0b-114">В коде процедуры используйте имя параметра для присвоения значения для базового элемента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="54a0b-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="54a0b-115">См. пример ниже, для демонстрации.</span><span class="sxs-lookup"><span data-stu-id="54a0b-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="54a0b-116">Изменение локальных копий</span><span class="sxs-lookup"><span data-stu-id="54a0b-116">Changing Local Copies</span></span>  
 <span data-ttu-id="54a0b-117">Если базовый элемент в вызывающем коде является неизменяемым или аргумент передается `ByVal`, процедура не может изменять его значение в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="54a0b-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="54a0b-118">Однако процедура может изменить локальную копию такого аргумента.</span><span class="sxs-lookup"><span data-stu-id="54a0b-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="54a0b-119">Чтобы изменить копию аргумента процедуры в коде процедуры</span><span class="sxs-lookup"><span data-stu-id="54a0b-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="54a0b-120">В объявлении процедуры укажите [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) для параметра, соответствующего аргументу.</span><span class="sxs-lookup"><span data-stu-id="54a0b-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="54a0b-121">-или-</span><span class="sxs-lookup"><span data-stu-id="54a0b-121">-or-</span></span>  
  
     <span data-ttu-id="54a0b-122">В вызывающем коде заключите аргумент в списке аргументов в скобках.</span><span class="sxs-lookup"><span data-stu-id="54a0b-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="54a0b-123">Это заставляет [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] передача аргумента по значению, даже если соответствующий параметр указывает `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="54a0b-123">This forces [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="54a0b-124">В коде процедуры используйте имя параметра для присвоения значения локальной копии аргумента.</span><span class="sxs-lookup"><span data-stu-id="54a0b-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="54a0b-125">Базовое значение в вызывающем коде не изменяется.</span><span class="sxs-lookup"><span data-stu-id="54a0b-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54a0b-126">Пример</span><span class="sxs-lookup"><span data-stu-id="54a0b-126">Example</span></span>  
 <span data-ttu-id="54a0b-127">Следующий пример показывает две процедуры, которые принимают переменную массива и производят на его элементы.</span><span class="sxs-lookup"><span data-stu-id="54a0b-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="54a0b-128">`increase` Процедура просто добавляет единицу к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="54a0b-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="54a0b-129">`replace` Процедура присваивает новый массив параметру `a()` и затем добавляет единицу к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="54a0b-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 <span data-ttu-id="54a0b-130">[!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="54a0b-130">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]</span></span>  
  
 <span data-ttu-id="54a0b-131">[!code-vb[VbVbcnProcedures&#36;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="54a0b-131">[!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]</span></span>  
  
 <span data-ttu-id="54a0b-132">[!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="54a0b-132">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]</span></span>  
  
 <span data-ttu-id="54a0b-133">Первый `MsgBox` вызове отображается «после увеличения (n): 11, 21, 31, 41».</span><span class="sxs-lookup"><span data-stu-id="54a0b-133">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="54a0b-134">Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на то, что механизм передачи `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="54a0b-134">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="54a0b-135">Второй `MsgBox` вызове отображается «после замены(n): 101, 201, 301».</span><span class="sxs-lookup"><span data-stu-id="54a0b-135">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="54a0b-136">Поскольку `n` передается `ByRef`, `replace` можно изменить переменную `n` в вызывающем коде и присвоить ей новый массив.</span><span class="sxs-lookup"><span data-stu-id="54a0b-136">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="54a0b-137">Поскольку `n` является ссылочным типом, `replace` может изменять его члены.</span><span class="sxs-lookup"><span data-stu-id="54a0b-137">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="54a0b-138">Можно запретить процедуре изменять переменную в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="54a0b-138">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="54a0b-139">В разделе [как: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="54a0b-139">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="54a0b-140">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="54a0b-140">Compiling the Code</span></span>  
 <span data-ttu-id="54a0b-141">Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово для выбора этого способа.</span><span class="sxs-lookup"><span data-stu-id="54a0b-141">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="54a0b-142">По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] аргументы передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="54a0b-142">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="54a0b-143">Тем не менее, хорошим стилем программирования считается включают в себя [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром.</span><span class="sxs-lookup"><span data-stu-id="54a0b-143">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="54a0b-144">Это облегчает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="54a0b-144">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="54a0b-145">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="54a0b-145">.NET Framework Security</span></span>  
 <span data-ttu-id="54a0b-146">Всегда есть потенциальный риск при разрешении процедуре изменять значение базового аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="54a0b-146">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="54a0b-147">Убедитесь, что предполагается, что значение изменено и будьте готовы к проверке его допустимости перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="54a0b-147">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54a0b-148">См. также</span><span class="sxs-lookup"><span data-stu-id="54a0b-148">See Also</span></span>  
 <span data-ttu-id="54a0b-149">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="54a0b-149">[Procedures](./index.md) </span></span>  
<span data-ttu-id="54a0b-150"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="54a0b-150"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="54a0b-151"> [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="54a0b-151"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="54a0b-152"> [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="54a0b-152"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="54a0b-153"> [Различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="54a0b-153"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="54a0b-154"> [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="54a0b-154"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="54a0b-155"> [Практическое руководство: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="54a0b-155"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="54a0b-156"> [Практическое руководство: Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="54a0b-156"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="54a0b-157"> [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="54a0b-157"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="54a0b-158"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="54a0b-158"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
