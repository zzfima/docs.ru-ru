---
title: "Практическое руководство: защита аргумента процедуры от изменения значения (Visual Basic) | Документы Microsoft"
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
- procedures, calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
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
ms.openlocfilehash: db40b3426256e7789a5273ab4d0afc8d5b47c8a7
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="d55cf-102">Практическое руководство. Защита аргумента процедуры от изменения значения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d55cf-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="d55cf-103">Если процедура объявляет параметр как [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет код процедуры прямую ссылку на программный элемент, лежащий в основе аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="d55cf-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="d55cf-104">Это позволяет процедуре изменять значение базового аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="d55cf-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="d55cf-105">В некоторых случаях вызывающему коду может потребоваться защита от таких изменений.</span><span class="sxs-lookup"><span data-stu-id="d55cf-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="d55cf-106">Всегда можно защитить аргумент от изменений, объявив соответствующий параметр [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) в процедуре.</span><span class="sxs-lookup"><span data-stu-id="d55cf-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="d55cf-107">Если вы хотите иметь возможность изменять данный аргумент, в некоторых случаях, но не другие, его можно объявить `ByRef` и позволить вызывающему коду определять механизм передачи в каждом вызове.</span><span class="sxs-lookup"><span data-stu-id="d55cf-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="d55cf-108">Это делается путем заключения соответствующего аргумента в круглые скобки, чтобы передать его по значению или не заключать в круглые скобки, чтобы передать его по ссылке.</span><span class="sxs-lookup"><span data-stu-id="d55cf-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="d55cf-109">Дополнительные сведения см. в разделе [как: Принудительная передача аргумента передается значение](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="d55cf-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d55cf-110">Пример</span><span class="sxs-lookup"><span data-stu-id="d55cf-110">Example</span></span>  
 <span data-ttu-id="d55cf-111">Следующий пример показывает две процедуры, которые принимают переменную массива и производят на его элементы.</span><span class="sxs-lookup"><span data-stu-id="d55cf-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="d55cf-112">`increase` Процедура просто добавляет единицу к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="d55cf-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="d55cf-113">`replace` Процедура присваивает новый массив параметру `a()` и затем добавляет единицу к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="d55cf-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="d55cf-114">Однако переназначение не влияет на базовую переменную массива в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="d55cf-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 <span data-ttu-id="d55cf-115">[!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d55cf-115">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span></span>  
  
 <span data-ttu-id="d55cf-116">[!code-vb[VbVbcnProcedures&#38;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d55cf-116">[!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span></span>  
  
 <span data-ttu-id="d55cf-117">[!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="d55cf-117">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span></span>  
  
 <span data-ttu-id="d55cf-118">Первый `MsgBox` вызове отображается «после увеличения (n): 11, 21, 31, 41».</span><span class="sxs-lookup"><span data-stu-id="d55cf-118">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="d55cf-119">Так как массив `n` является ссылочным типом, `replace` может изменить его элементы, несмотря на то, что механизм передачи `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="d55cf-119">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="d55cf-120">Второй `MsgBox` вызове отображается «после замены(n): 11, 21, 31, 41».</span><span class="sxs-lookup"><span data-stu-id="d55cf-120">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="d55cf-121">Поскольку `n` передается `ByVal`, `replace` не может изменить переменную `n` в вызывающем коде, присвоив ей новый массив.</span><span class="sxs-lookup"><span data-stu-id="d55cf-121">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="d55cf-122">Когда `replace` создает новый экземпляр массива `k` и назначает его локальной переменной `a`, он теряет ссылку на `n` передается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="d55cf-122">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="d55cf-123">Когда он изменяет элементы `a`, только локальный массив `k` изменяется.</span><span class="sxs-lookup"><span data-stu-id="d55cf-123">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="d55cf-124">Таким образом `replace` не увеличивает значения из массива `n` в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="d55cf-124">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d55cf-125">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d55cf-125">Compiling the Code</span></span>  
 <span data-ttu-id="d55cf-126">По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] аргументы передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="d55cf-126">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="d55cf-127">Тем не менее, хорошим стилем программирования считается включают в себя [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром.</span><span class="sxs-lookup"><span data-stu-id="d55cf-127">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="d55cf-128">Это облегчает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="d55cf-128">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d55cf-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d55cf-129">See Also</span></span>  
 <span data-ttu-id="d55cf-130">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="d55cf-130">[Procedures](./index.md) </span></span>  
<span data-ttu-id="d55cf-131"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="d55cf-131"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="d55cf-132"> [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d55cf-132"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="d55cf-133"> [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d55cf-133"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="d55cf-134"> [Различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="d55cf-134"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="d55cf-135"> [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d55cf-135"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="d55cf-136"> [Практическое руководство: изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="d55cf-136"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="d55cf-137"> [Практическое руководство: Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="d55cf-137"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="d55cf-138"> [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="d55cf-138"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="d55cf-139"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="d55cf-139"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
