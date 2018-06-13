---
title: Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)
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
ms.openlocfilehash: adc58c34150030eb0fc82050576bfecc453e21ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651081"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="bd5a9-102">Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd5a9-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="bd5a9-103">Объявление процедуры определяет механизм передачи.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="bd5a9-104">Если параметр объявляется [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic ожидает передачи соответствующего аргумента по ссылке.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="bd5a9-105">Это позволяет хранимой процедуре для изменения значения элемента программирования в аргументе в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="bd5a9-106">Если вы хотите защитить основные элементы от таких изменений, можно переопределить `ByRef` механизм передачи в процедуре вызовите, заключив имя аргумента в скобки.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="bd5a9-107">Эти скобки являются дополнением к круглым скобкам, содержащим список аргументов в вызове.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="bd5a9-108">Вызывающий код не может переопределить [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) механизм.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="bd5a9-109">Чтобы Принудительная передача аргумента по значению</span><span class="sxs-lookup"><span data-stu-id="bd5a9-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="bd5a9-110">Если соответствующий параметр объявлен `ByVal` в процедуре, не требуется предпринимать дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="bd5a9-111">Visual Basic уже ожидает передачи аргумента по значению.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="bd5a9-112">Если соответствующий параметр объявлен `ByRef` в процедуре, заключите аргумент в скобки в вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd5a9-113">Пример</span><span class="sxs-lookup"><span data-stu-id="bd5a9-113">Example</span></span>  
 <span data-ttu-id="bd5a9-114">В следующем примере переопределяется `ByRef` объявление параметра.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="bd5a9-115">В вызове, требующем `ByVal`, обратите внимание на два уровня скобок.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 <span data-ttu-id="bd5a9-116">Когда `str` заключается в дополнительные скобки в списке аргументов, `setNewString` процедура не может изменить его значение в вызывающем коде, и `MsgBox` отображает «Не может быть заменен при передаче ByVal».</span><span class="sxs-lookup"><span data-stu-id="bd5a9-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="bd5a9-117">При `str` не заключен в лишние круглые скобки, процедура может изменять его, и `MsgBox` отображает «Это новое значение для аргумента inString».</span><span class="sxs-lookup"><span data-stu-id="bd5a9-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bd5a9-118">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bd5a9-118">Compiling the Code</span></span>  
 <span data-ttu-id="bd5a9-119">Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово, чтобы указать этот механизм.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="bd5a9-120">По умолчанию в Visual Basic используется для передачи аргументов по значению.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="bd5a9-121">Тем не менее, это хороший стиль программирования способ включения либо [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="bd5a9-122">Это делает код более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bd5a9-123">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="bd5a9-123">Robust Programming</span></span>  
 <span data-ttu-id="bd5a9-124">Если процедура объявляет параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), правильное выполнение кода зависит от изменения базового элемента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="bd5a9-125">Если вызывающий код переопределяет механизм вызова путем заключения аргумента в круглые скобки или прохождении неизменяемого аргумента, процедура не может изменять базовый элемент.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="bd5a9-126">Это может привести к непредсказуемым результатам в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bd5a9-127">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bd5a9-127">.NET Framework Security</span></span>  
 <span data-ttu-id="bd5a9-128">Всегда есть потенциальный риск при разрешении процедуре изменять значение базового аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="bd5a9-129">Убедитесь, что предполагается, что это значение, чтобы изменить и будьте готовы к проверке его допустимости перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5a9-130">См. также</span><span class="sxs-lookup"><span data-stu-id="bd5a9-130">See Also</span></span>  
 [<span data-ttu-id="bd5a9-131">Процедуры</span><span class="sxs-lookup"><span data-stu-id="bd5a9-131">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="bd5a9-132">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="bd5a9-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="bd5a9-133">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="bd5a9-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="bd5a9-134">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="bd5a9-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="bd5a9-135">Различия между изменяемыми и неизменяемыми аргументами</span><span class="sxs-lookup"><span data-stu-id="bd5a9-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="bd5a9-136">Различия между передачей аргумента по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="bd5a9-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="bd5a9-137">Практическое руководство. Изменение значения аргумента процедуры</span><span class="sxs-lookup"><span data-stu-id="bd5a9-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="bd5a9-138">Практическое руководство. Защита аргумента процедуры от изменений значения</span><span class="sxs-lookup"><span data-stu-id="bd5a9-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="bd5a9-139">Передача аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="bd5a9-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="bd5a9-140">Типы значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="bd5a9-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
