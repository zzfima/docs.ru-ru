---
title: Практическое руководство. Принудительная аргумента передаваться по значению (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 497ae11b858b7d164ba3b5607ff2109254a154de
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842050"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="67c28-102">Практическое руководство. Принудительная аргумента передаваться по значению (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67c28-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="67c28-103">Объявление процедуры определяет механизм передачи.</span><span class="sxs-lookup"><span data-stu-id="67c28-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="67c28-104">Если параметр объявлен [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic и ожидает передачи соответствующего аргумента по ссылке.</span><span class="sxs-lookup"><span data-stu-id="67c28-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="67c28-105">Это позволяет процедуре для изменения значения элемента программирования, в аргументе в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="67c28-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="67c28-106">Если вы хотите защитить основные элементы от таких изменений, можно переопределить `ByRef` механизм передачи в процедуре вызовите, заключив имя аргумента в скобки.</span><span class="sxs-lookup"><span data-stu-id="67c28-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="67c28-107">Эти скобки являются дополнением к круглым скобкам, содержащим список аргументов в вызове.</span><span class="sxs-lookup"><span data-stu-id="67c28-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="67c28-108">Вызывающий код не может переопределить [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) механизм.</span><span class="sxs-lookup"><span data-stu-id="67c28-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="67c28-109">Чтобы принудительно аргумент, передаваемый по значению</span><span class="sxs-lookup"><span data-stu-id="67c28-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="67c28-110">Если соответствующий параметр объявлен `ByVal` в процедуре, не нужно предпринимать дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="67c28-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="67c28-111">Visual Basic уже ожидает передачи аргумента по значению.</span><span class="sxs-lookup"><span data-stu-id="67c28-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="67c28-112">Если соответствующий параметр объявлен `ByRef` в процедуре, заключите аргумент в круглые скобки в вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="67c28-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67c28-113">Пример</span><span class="sxs-lookup"><span data-stu-id="67c28-113">Example</span></span>  
 <span data-ttu-id="67c28-114">В следующем примере переопределяется `ByRef` объявление параметра.</span><span class="sxs-lookup"><span data-stu-id="67c28-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="67c28-115">В вызове, требующем `ByVal`, обратите внимание на два уровня скобок.</span><span class="sxs-lookup"><span data-stu-id="67c28-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="67c28-116">Когда `str` заключен в дополнительные скобки в списке аргументов, `setNewString` процедура не может изменить его значение в вызывающий код, и `MsgBox` отображает «Не может быть заменен при передаче ByVal».</span><span class="sxs-lookup"><span data-stu-id="67c28-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="67c28-117">При `str` не заключен в дополнительные скобки процедуру можно изменить его, и `MsgBox` отображает «Это новое значение для аргумента inString».</span><span class="sxs-lookup"><span data-stu-id="67c28-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="67c28-118">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="67c28-118">Compiling the Code</span></span>  
 <span data-ttu-id="67c28-119">Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово, чтобы указать этот механизм.</span><span class="sxs-lookup"><span data-stu-id="67c28-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="67c28-120">По умолчанию в Visual Basic используется для передачи аргументов по значению.</span><span class="sxs-lookup"><span data-stu-id="67c28-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="67c28-121">Тем не менее, рекомендуется использовать одну [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром.</span><span class="sxs-lookup"><span data-stu-id="67c28-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="67c28-122">Это делает код более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="67c28-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="67c28-123">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="67c28-123">Robust Programming</span></span>  
 <span data-ttu-id="67c28-124">Если процедура объявляет параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), правильное выполнение кода зависит от изменения базового элемента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="67c28-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="67c28-125">Если вызывающий код переопределяет механизм вызова путем заключения аргумента в круглые скобки, или он передает неизменяемого аргумента, процедура не может изменять элемент.</span><span class="sxs-lookup"><span data-stu-id="67c28-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="67c28-126">Это может привести к непредвиденным результатам в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="67c28-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="67c28-127">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="67c28-127">.NET Framework Security</span></span>  
 <span data-ttu-id="67c28-128">Всегда найдется потенциальную угрозу в разрешении процедуре измените значение базового аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="67c28-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="67c28-129">Убедитесь, что предполагается, что это значение, чтобы изменить и будьте готовы, проверяемый на допустимость перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="67c28-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c28-130">См. также</span><span class="sxs-lookup"><span data-stu-id="67c28-130">See also</span></span>

- [<span data-ttu-id="67c28-131">Процедуры</span><span class="sxs-lookup"><span data-stu-id="67c28-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="67c28-132">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="67c28-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="67c28-133">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="67c28-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="67c28-134">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="67c28-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="67c28-135">Различия между изменяемыми и неизменяемыми аргументами</span><span class="sxs-lookup"><span data-stu-id="67c28-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="67c28-136">Различия между передачей аргумента по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="67c28-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="67c28-137">Практическое руководство. Изменение значения аргумента процедуры</span><span class="sxs-lookup"><span data-stu-id="67c28-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="67c28-138">Практическое руководство. Защита аргумента процедуры от изменения значения</span><span class="sxs-lookup"><span data-stu-id="67c28-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="67c28-139">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="67c28-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="67c28-140">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="67c28-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
