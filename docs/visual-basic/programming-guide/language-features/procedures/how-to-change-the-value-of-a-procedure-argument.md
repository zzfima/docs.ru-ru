---
title: Практическое руководство. Изменение значения аргумента процедуры
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
ms.openlocfilehash: e562c0f5ec01380c792b4dc064554171cfb007e7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74339959"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="32865-102">Практическое руководство. Изменение значения аргумента процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32865-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="32865-103">При вызове процедуры каждый указываемый аргумент соответствует одному из параметров, определенных в процедуре.</span><span class="sxs-lookup"><span data-stu-id="32865-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="32865-104">В некоторых случаях код процедуры может изменить значение, которое является базовым для аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="32865-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="32865-105">В других случаях процедура может изменить только локальную копию аргумента.</span><span class="sxs-lookup"><span data-stu-id="32865-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="32865-106">При вызове процедуры Visual Basic создает локальную копию каждого аргумента, который передается по [значению ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="32865-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="32865-107">Для каждого аргумента, переданного по [ссылке ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic предоставляет коду процедуры прямую ссылку на программный элемент, лежащий в основе аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="32865-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="32865-108">Если базовый элемент в вызывающем коде является изменяемым, а аргумент передается `ByRef`, то код процедуры может использовать прямую ссылку для изменения значения элемента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="32865-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="32865-109">Изменение базового значения</span><span class="sxs-lookup"><span data-stu-id="32865-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="32865-110">Изменение базового значения аргумента процедуры в вызывающем коде</span><span class="sxs-lookup"><span data-stu-id="32865-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="32865-111">В объявлении процедуры укажите [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) для параметра, соответствующего аргументу.</span><span class="sxs-lookup"><span data-stu-id="32865-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="32865-112">В вызывающем коде передайте изменяемый программный элемент в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="32865-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="32865-113">В вызывающем коде не заключайте аргумент в круглые скобки в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="32865-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="32865-114">В коде процедуры используйте имя параметра, чтобы присвоить значение базовому элементу в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="32865-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="32865-115">Для демонстрации см. пример ниже.</span><span class="sxs-lookup"><span data-stu-id="32865-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="32865-116">Изменение локальных копий</span><span class="sxs-lookup"><span data-stu-id="32865-116">Changing Local Copies</span></span>  
 <span data-ttu-id="32865-117">Если базовый элемент в вызывающем коде является неизменяемым, или если аргумент передается `ByVal`, процедура не может изменить его значение в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="32865-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="32865-118">Однако процедура может изменить локальную копию такого аргумента.</span><span class="sxs-lookup"><span data-stu-id="32865-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="32865-119">Изменение копии аргумента процедуры в коде процедуры</span><span class="sxs-lookup"><span data-stu-id="32865-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="32865-120">В объявлении процедуры укажите [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) для параметра, соответствующего аргументу.</span><span class="sxs-lookup"><span data-stu-id="32865-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="32865-121">\- или -</span><span class="sxs-lookup"><span data-stu-id="32865-121">-or-</span></span>  
  
     <span data-ttu-id="32865-122">В вызывающем коде заключите аргумент в круглые скобки в список аргументов.</span><span class="sxs-lookup"><span data-stu-id="32865-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="32865-123">Это заставляет Visual Basic передавать аргумент по значению, даже если соответствующий параметр указывает `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="32865-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="32865-124">В коде процедуры используйте имя параметра, чтобы присвоить значение локальной копии аргумента.</span><span class="sxs-lookup"><span data-stu-id="32865-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="32865-125">Базовое значение в вызывающем коде не изменяется.</span><span class="sxs-lookup"><span data-stu-id="32865-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32865-126">Пример</span><span class="sxs-lookup"><span data-stu-id="32865-126">Example</span></span>  
 <span data-ttu-id="32865-127">В следующем примере показаны две процедуры, которые принимают переменную массива и работают с ее элементами.</span><span class="sxs-lookup"><span data-stu-id="32865-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="32865-128">`increase` процедура просто добавляет по одной к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="32865-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="32865-129">`replace` процедура присваивает новый массив параметру `a()` а затем добавляет его к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="32865-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="32865-130">Первый вызов `MsgBox` выводит "после увеличения (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="32865-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="32865-131">Поскольку массив `n` является ссылочным типом, `replace` может изменять его члены, даже если механизм передачи `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="32865-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="32865-132">Во втором вызове `MsgBox` отображается "After Replace (n): 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="32865-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="32865-133">Поскольку `n` передается `ByRef`, `replace` может изменить переменную `n` в вызывающем коде и присвоить ей новый массив.</span><span class="sxs-lookup"><span data-stu-id="32865-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="32865-134">Поскольку `n` является ссылочным типом, `replace` также может изменять его члены.</span><span class="sxs-lookup"><span data-stu-id="32865-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="32865-135">Можно запретить процедуре изменять саму переменную в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="32865-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="32865-136">См. раздел [как защитить аргумент процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="32865-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32865-137">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="32865-137">Compiling the Code</span></span>  
 <span data-ttu-id="32865-138">При передаче переменной по ссылке необходимо использовать ключевое слово `ByRef` для указания этого механизма.</span><span class="sxs-lookup"><span data-stu-id="32865-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="32865-139">По умолчанию в Visual Basic передаются аргументы по значению.</span><span class="sxs-lookup"><span data-stu-id="32865-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="32865-140">Однако рекомендуется включать ключевое слово [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) с каждым объявленным параметром.</span><span class="sxs-lookup"><span data-stu-id="32865-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="32865-141">Это упрощает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="32865-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="32865-142">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="32865-142">.NET Framework Security</span></span>  
 <span data-ttu-id="32865-143">Всегда существует потенциальный риск, позволяющий процедуре изменять значение, которое является базовым для аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="32865-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="32865-144">Убедитесь, что это значение было изменено, и будьте готовы проверить его на допустимость перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="32865-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32865-145">См. также</span><span class="sxs-lookup"><span data-stu-id="32865-145">See also</span></span>

- [<span data-ttu-id="32865-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="32865-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="32865-147">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="32865-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="32865-148">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="32865-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="32865-149">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="32865-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="32865-150">Различия между изменяемыми и неизменяемыми аргументами</span><span class="sxs-lookup"><span data-stu-id="32865-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="32865-151">Различия между передачей аргумента по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="32865-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="32865-152">Практическое руководство. Защита аргумента процедуры от изменений значения</span><span class="sxs-lookup"><span data-stu-id="32865-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="32865-153">Практическое руководство. Принудительная передача аргумента по значению</span><span class="sxs-lookup"><span data-stu-id="32865-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="32865-154">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="32865-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="32865-155">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="32865-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
