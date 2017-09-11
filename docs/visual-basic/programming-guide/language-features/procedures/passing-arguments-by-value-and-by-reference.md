---
title: "Передача аргументов по значению и по ссылке (Visual Basic) | Документы Microsoft"
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
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- passing arguments, by value or by reference
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing, by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
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
ms.openlocfilehash: 44107171d6f24e22614788470c65cf7ad8d28640
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="c617c-102">Передача аргументов по значению и по ссылке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c617c-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="c617c-103">В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], можно передать аргумент в процедуру *по значению* или *по ссылке*.</span><span class="sxs-lookup"><span data-stu-id="c617c-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="c617c-104">Это называется *механизм передачи*, и определяет, является ли процедура может изменять программный элемент, лежащий в основе аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="c617c-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="c617c-105">Объявление процедуры определяет механизм передачи для каждого параметра, указав [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="c617c-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="c617c-106">Различия между устройствами</span><span class="sxs-lookup"><span data-stu-id="c617c-106">Distinctions</span></span>  
 <span data-ttu-id="c617c-107">При передаче аргумента в процедуру, следует учитывать несколько отличительных особенностей, которые взаимодействуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="c617c-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
-   <span data-ttu-id="c617c-108">Является ли базовый элемент программирования изменяемым или неизменяемым</span><span class="sxs-lookup"><span data-stu-id="c617c-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="c617c-109">Является ли сам аргумент изменяемым или неизменяемым</span><span class="sxs-lookup"><span data-stu-id="c617c-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="c617c-110">Является ли аргумент передается по значению или по ссылке</span><span class="sxs-lookup"><span data-stu-id="c617c-110">Whether the argument is being passed by value or by reference</span></span>  
  
-   <span data-ttu-id="c617c-111">Является ли тип данных аргумента типом значения или ссылочным типом</span><span class="sxs-lookup"><span data-stu-id="c617c-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="c617c-112">Дополнительные сведения см. в разделе [различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md) и [различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c617c-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="c617c-113">Выбор механизма передачи</span><span class="sxs-lookup"><span data-stu-id="c617c-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="c617c-114">Необходимо выбрать механизм передачи тщательно для каждого аргумента.</span><span class="sxs-lookup"><span data-stu-id="c617c-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
-   <span data-ttu-id="c617c-115">**Защита**.</span><span class="sxs-lookup"><span data-stu-id="c617c-115">**Protection**.</span></span> <span data-ttu-id="c617c-116">При выборе между двумя механизмами передачи, наиболее важный критерий является раскрытие вызова переменных для изменения.</span><span class="sxs-lookup"><span data-stu-id="c617c-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="c617c-117">Преимущество передачи аргумента `ByRef` является, что процедура может возвратить значение в вызывающий код через этот аргумент.</span><span class="sxs-lookup"><span data-stu-id="c617c-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="c617c-118">Преимущество передачи аргумента `ByVal` является, что в этом случае переменная защищена от изменений, вносимых в процедуре.</span><span class="sxs-lookup"><span data-stu-id="c617c-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
-   <span data-ttu-id="c617c-119">**Производительность**.</span><span class="sxs-lookup"><span data-stu-id="c617c-119">**Performance**.</span></span> <span data-ttu-id="c617c-120">Несмотря на то, что механизм передачи может повлиять на производительность кода, разница не заметна.</span><span class="sxs-lookup"><span data-stu-id="c617c-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="c617c-121">Единственным исключением является передача типа значения `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="c617c-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="c617c-122">В этом случае [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] копирует все содержимое аргумента.</span><span class="sxs-lookup"><span data-stu-id="c617c-122">In this case, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copies the entire data contents of the argument.</span></span> <span data-ttu-id="c617c-123">Таким образом, для типа больших значений, например структуры, он может быть более эффективным для ее передачи `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="c617c-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="c617c-124">Указатель на данные работает для ссылочных типов, скопированные (4 байта на 32-разрядных платформах, восемь байтов на 64-разрядных платформах).</span><span class="sxs-lookup"><span data-stu-id="c617c-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="c617c-125">Таким образом, можно передавать аргументы типа `String` или `Object` по значению без потери производительности.</span><span class="sxs-lookup"><span data-stu-id="c617c-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="c617c-126">Определение алгоритма передачи</span><span class="sxs-lookup"><span data-stu-id="c617c-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="c617c-127">Объявление процедуры определяет механизм передачи для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="c617c-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="c617c-128">Вызывающий код не может изменить `ByVal` механизм.</span><span class="sxs-lookup"><span data-stu-id="c617c-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="c617c-129">Если параметр объявлен с `ByRef`, вызывающий код может заставить механизм `ByVal` , заключив имя аргумента в скобки в вызове.</span><span class="sxs-lookup"><span data-stu-id="c617c-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="c617c-130">Дополнительные сведения см. в разделе [как: Принудительная передача аргумента передается значение](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="c617c-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="c617c-131">По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] аргументы передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="c617c-131">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="c617c-132">Когда передавать аргумент по значению</span><span class="sxs-lookup"><span data-stu-id="c617c-132">When to Pass an Argument by Value</span></span>  
  
-   <span data-ttu-id="c617c-133">Если элемент кода вызова, содержащийся в аргументе, является неизменяемым, объявите соответствующий параметр [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="c617c-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="c617c-134">Код не может изменить значение неизменяемого элемента.</span><span class="sxs-lookup"><span data-stu-id="c617c-134">No code can change the value of a nonmodifiable element.</span></span>  
  
-   <span data-ttu-id="c617c-135">Если элемент является изменяемым, но нежелательно процедуру, чтобы иметь возможность изменить его значение, объявите параметр `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="c617c-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="c617c-136">Только вызывающий код может изменить значение изменяемого элемента, передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="c617c-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="c617c-137">Когда передавать аргумент по ссылке</span><span class="sxs-lookup"><span data-stu-id="c617c-137">When to Pass an Argument by Reference</span></span>  
  
-   <span data-ttu-id="c617c-138">Если процедуре необходимо изменить базовый элемент в коде вызова, объявите соответствующий параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span><span class="sxs-lookup"><span data-stu-id="c617c-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
-   <span data-ttu-id="c617c-139">Если правильное выполнение кода зависит от изменения базового элемента в вызывающем коде процедуры, объявите параметр `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="c617c-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="c617c-140">Если при передаче по значению или код вызова переопределяет `ByRef` механизма передачи, заключив аргумент в круглые скобки, вызов процедуры может привести к непредсказуемым результатам.</span><span class="sxs-lookup"><span data-stu-id="c617c-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c617c-141">Пример</span><span class="sxs-lookup"><span data-stu-id="c617c-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c617c-142">Описание</span><span class="sxs-lookup"><span data-stu-id="c617c-142">Description</span></span>  
 <span data-ttu-id="c617c-143">В следующем примере показано, когда передача аргументов по значению, а когда передавать их по ссылке.</span><span class="sxs-lookup"><span data-stu-id="c617c-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="c617c-144">Процедура `Calculate` имеет оба `ByVal` и `ByRef` параметр.</span><span class="sxs-lookup"><span data-stu-id="c617c-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="c617c-145">Дана процентная ставка, `rate`и суммы денег, `debt`, задачей процедуры является вычисление нового значения для `debt` , являющееся результатом применения процентной ставки к исходному значению `debt`.</span><span class="sxs-lookup"><span data-stu-id="c617c-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="c617c-146">Поскольку `debt` — `ByRef` параметр, новая сумма отражается в значении аргумента в вызывающем коде, который соответствует `debt`.</span><span class="sxs-lookup"><span data-stu-id="c617c-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="c617c-147">Параметр `rate` — `ByVal` параметр поскольку `Calculate` не следует менять его значение.</span><span class="sxs-lookup"><span data-stu-id="c617c-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c617c-148">Код</span><span class="sxs-lookup"><span data-stu-id="c617c-148">Code</span></span>  
 <span data-ttu-id="c617c-149">[!code-vb[VbVbcnProcedures&#74;](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c617c-149">[!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c617c-150">См. также</span><span class="sxs-lookup"><span data-stu-id="c617c-150">See Also</span></span>  
 <span data-ttu-id="c617c-151">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="c617c-151">[Procedures](./index.md) </span></span>  
<span data-ttu-id="c617c-152"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="c617c-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="c617c-153"> [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c617c-153"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="c617c-154"> [Практическое руководство: изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="c617c-154"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="c617c-155"> [Практическое руководство: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="c617c-155"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="c617c-156"> [Практическое руководство: Принудительная передача аргумента по значению](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="c617c-156"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="c617c-157"> [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="c617c-157"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="c617c-158"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="c617c-158"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
