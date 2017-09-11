---
title: "Практическое руководство: Принудительная передача аргумента по значению (Visual Basic) | Документы Microsoft"
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
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], in parentheses
- procedure arguments, in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
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
ms.openlocfilehash: b151c319489ccda357faa082ce0b3c1addad0458
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="bd8b5-102">Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd8b5-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="bd8b5-103">Объявление процедуры определяет механизм передачи.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="bd8b5-104">Если параметр объявляется [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ожидает передачи соответствующего аргумента по ссылке.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="bd8b5-105">Это позволяет процедуре изменять значение элемента программирования, содержащегося в аргументе в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="bd8b5-106">Если вы хотите защитить основные элементы от таких изменений, можно переопределить `ByRef` вызова механизм передачи в процедуре, заключив имя аргумента в скобки.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="bd8b5-107">Эти скобки являются дополнением к круглым скобкам, содержащим список аргументов в вызове.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="bd8b5-108">Вызывающий код не может изменить [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) механизм.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="bd8b5-109">Чтобы принудительно аргумент, передаваемый по значению</span><span class="sxs-lookup"><span data-stu-id="bd8b5-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="bd8b5-110">Если соответствующий параметр объявлен `ByVal` в процедуре, не нужно предпринимать никаких дополнительных действий.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="bd8b5-111">уже ожидает передачи аргумента по значению.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="bd8b5-112">Если соответствующий параметр объявлен `ByRef` в процедуре, заключите аргумент в скобки в вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd8b5-113">Пример</span><span class="sxs-lookup"><span data-stu-id="bd8b5-113">Example</span></span>  
 <span data-ttu-id="bd8b5-114">В следующем примере переопределяется `ByRef` объявление параметра.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="bd8b5-115">В вызове, требующем `ByVal`, обратите внимание на два уровня скобок.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 <span data-ttu-id="bd8b5-116">[!code-vb[VbVbcnProcedures&#39;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd8b5-116">[!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span></span>  
  
 <span data-ttu-id="bd8b5-117">[!code-vb[VbVbcnProcedures&#40;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="bd8b5-117">[!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span></span>  
  
 <span data-ttu-id="bd8b5-118">При `str` заключено в дополнительные скобки в списке аргументов, `setNewString` процедура не может изменять его значение в вызывающем коде и `MsgBox` отображает «Не может быть заменен при передаче ByVal».</span><span class="sxs-lookup"><span data-stu-id="bd8b5-118">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="bd8b5-119">Когда `str` не заключен в дополнительные скобки процедуры можно изменить его, и `MsgBox` отображает «Это новое значение для аргумента inString».</span><span class="sxs-lookup"><span data-stu-id="bd8b5-119">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bd8b5-120">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bd8b5-120">Compiling the Code</span></span>  
 <span data-ttu-id="bd8b5-121">Если переменная передается по ссылке, необходимо использовать `ByRef` ключевое слово для выбора этого способа.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-121">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="bd8b5-122">По умолчанию в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] аргументы передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-122">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="bd8b5-123">Тем не менее, хорошим стилем программирования считается включают в себя [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) ключевое слово с каждым объявленным параметром.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-123">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="bd8b5-124">Это облегчает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-124">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bd8b5-125">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="bd8b5-125">Robust Programming</span></span>  
 <span data-ttu-id="bd8b5-126">Если процедура объявляет параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), правильное выполнение кода зависит от изменения базового элемента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-126">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="bd8b5-127">Если код вызова переопределяет механизм вызова путем заключения аргумента в круглые скобки, или если он передает неизменяемого аргумента, процедура не может изменять базовый элемент.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-127">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="bd8b5-128">Это может привести к непредсказуемым результатам в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-128">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bd8b5-129">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bd8b5-129">.NET Framework Security</span></span>  
 <span data-ttu-id="bd8b5-130">Всегда есть потенциальный риск при разрешении процедуре изменять значение базового аргумента в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-130">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="bd8b5-131">Убедитесь, что предполагается, что значение изменено и будьте готовы к проверке его допустимости перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="bd8b5-131">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd8b5-132">См. также</span><span class="sxs-lookup"><span data-stu-id="bd8b5-132">See Also</span></span>  
 <span data-ttu-id="bd8b5-133">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="bd8b5-133">[Procedures](./index.md) </span></span>  
<span data-ttu-id="bd8b5-134"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="bd8b5-134"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="bd8b5-135"> [Практическое руководство: передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="bd8b5-135"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="bd8b5-136"> [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bd8b5-136"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="bd8b5-137"> [Различия между изменяемые и неизменяемые аргументы](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="bd8b5-137"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="bd8b5-138"> [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bd8b5-138"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="bd8b5-139"> [Практическое руководство: изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="bd8b5-139"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="bd8b5-140"> [Практическое руководство: защита аргумента процедуры от изменения значения](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="bd8b5-140"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="bd8b5-141"> [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="bd8b5-141"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="bd8b5-142"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="bd8b5-142"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
