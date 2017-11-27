---
title: "Подпрограммы (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e20e0dd5ff9e2b931e5792bebb3144930826f89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="8a9e0-102">Подпрограммы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a9e0-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="8a9e0-103">Объект `Sub` процедура представляет собой ряд [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] инструкций, заключенных в `Sub` и `End Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-103">A `Sub` procedure is a series of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="8a9e0-104">`Sub` Процедура выполняет задачу и возвращает управление вызывающему коду, но не возвращает значение вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="8a9e0-105">При каждом вызове процедуры ее инструкции выполняются, начиная с первого исполняемого оператора после `Sub` инструкции и заканчивая первым `End Sub`, `Exit Sub`, или `Return` обнаружен оператор.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="8a9e0-106">Можно определить `Sub` процедуру в модулях, классах и структурах.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="8a9e0-107">По умолчанию является `Public`, что означает можно вызывать из любого места в приложении, которое имеет доступ к модуля, класса или структуры, в котором она определена.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="8a9e0-108">Термин, *метод*, описывает `Sub` или `Function` процедуру, к которому осуществляется из вне модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="8a9e0-109">Дополнительные сведения см. в разделе [Procedures in Visual Basic](./index.md) (Процедуры в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="8a9e0-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="8a9e0-110">Объект `Sub` процедура может принимать аргументы, например константы, переменные или выражения, которые передаются вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="8a9e0-111">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="8a9e0-111">Declaration Syntax</span></span>  
 <span data-ttu-id="8a9e0-112">Синтаксис объявления `Sub` процедура является следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8a9e0-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="8a9e0-113">`[`*модификаторы* `] Sub` *дополнительное_имя* `[(` *список_параметров*  `)]`</span><span class="sxs-lookup"><span data-stu-id="8a9e0-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="8a9e0-114">`modifiers` Можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и затенение.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="8a9e0-115">Дополнительные сведения см. в разделе [оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8a9e0-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="8a9e0-116">Объявление параметра</span><span class="sxs-lookup"><span data-stu-id="8a9e0-116">Parameter Declaration</span></span>  
 <span data-ttu-id="8a9e0-117">Каждый параметр процедуры, аналогично как объявить переменную, указание параметра имя и тип данных объявляется.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="8a9e0-118">Можно также указать способ передачи и параметр является необязательным или массивом параметров.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="8a9e0-119">Синтаксис для каждого параметра в списке параметров выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8a9e0-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="8a9e0-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *имя_параметра*`As`*тип данных* </span><span class="sxs-lookup"><span data-stu-id="8a9e0-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="8a9e0-121">Если аргумент является необязательным, необходимо также указать значение по умолчанию как часть объявления.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="8a9e0-122">Ниже приведен синтаксис для указания значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="8a9e0-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="8a9e0-123">`Optional [ByVal | ByRef]`  *имя_параметра*`As`*datatype*`=`*defaultvalue* </span><span class="sxs-lookup"><span data-stu-id="8a9e0-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="8a9e0-124">Параметры как локальные переменные</span><span class="sxs-lookup"><span data-stu-id="8a9e0-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="8a9e0-125">Когда управление передается в процедуру, каждый параметр рассматривается как локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="8a9e0-126">Это означает, что время существования совпадает со значением, процедуры и ее область действия является вся процедура.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="8a9e0-127">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="8a9e0-127">Calling Syntax</span></span>  
 <span data-ttu-id="8a9e0-128">Вызвать `Sub` процедуру явным образом с помощью отдельного вызывающего оператора.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="8a9e0-129">Нельзя вызвать с помощью его имени в выражении.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="8a9e0-130">Необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргумент должен быть заключен в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="8a9e0-131">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="8a9e0-132">Использование `Call` ключевое слово необязательно, но не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="8a9e0-133">Синтаксис для вызова `Sub` процедура является следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8a9e0-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="8a9e0-134">`[Call]`  *дополнительное_имя* `[(` *argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="8a9e0-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="8a9e0-135">Можно вызвать `Sub` методу извне класса, определяющего его.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="8a9e0-136">Во-первых, необходимо использовать `New` ключевое слово, чтобы создать экземпляр класса, или вызвать метод, который возвращает экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="8a9e0-137">Дополнительные сведения см. в разделе [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="8a9e0-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="8a9e0-138">Затем можно использовать следующий синтаксис для вызова `Sub` метода для экземпляра объекта:</span><span class="sxs-lookup"><span data-stu-id="8a9e0-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="8a9e0-139">*Объект*. *имя_метода*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="8a9e0-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="8a9e0-140">Пример объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="8a9e0-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="8a9e0-141">Следующие `Sub` процедура показывает оператору компьютера, какое задание приложение собирается выполнить, а также отображает отметку времени.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="8a9e0-142">Вместо повторения этого кода в начале каждой задачи, приложение вызывает `tellOperator` из различных расположений.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="8a9e0-143">Каждый вызов передает строку в `task` , указывающий, запущенную задачу.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 <span data-ttu-id="8a9e0-144">В примере показан типичный вызов `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="8a9e0-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8a9e0-145">См. также</span><span class="sxs-lookup"><span data-stu-id="8a9e0-145">See Also</span></span>  
 [<span data-ttu-id="8a9e0-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="8a9e0-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="8a9e0-147">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="8a9e0-147">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="8a9e0-148">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="8a9e0-148">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="8a9e0-149">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="8a9e0-149">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="8a9e0-150">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="8a9e0-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="8a9e0-151">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="8a9e0-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="8a9e0-152">Практическое руководство. Вызов процедуры, которая не возвращает значение</span><span class="sxs-lookup"><span data-stu-id="8a9e0-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)  
 [<span data-ttu-id="8a9e0-153">Как: вызов обработчика событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a9e0-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
