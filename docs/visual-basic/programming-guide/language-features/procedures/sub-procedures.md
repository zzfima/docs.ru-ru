---
title: "Процедуры (Visual Basic) Sub | Документы Microsoft"
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
- Sub procedures, about Sub procedures
- statement blocks
- Sub procedures, calling
- procedures, calling
- Sub procedures, syntax
- Sub procedures
- procedures, Sub
- syntax, Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
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
ms.openlocfilehash: 83f0a16498accf383da96d702c4e3a4b7de1c861
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="caa0b-102">Подпрограммы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="caa0b-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="caa0b-103">Объект `Sub` процедура представляет собой ряд [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] операторы заключены в `Sub` и `End Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="caa0b-103">A `Sub` procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="caa0b-104">`Sub` Процедура выполняет задачу и возвращает управление вызывающему коду, но не возвращает значения в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="caa0b-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="caa0b-105">При каждом вызове процедуры ее инструкции выполняются, начиная с первого исполняемого оператора после `Sub` инструкции и заканчивая первым `End Sub`, `Exit Sub`, или `Return` обнаружен оператор.</span><span class="sxs-lookup"><span data-stu-id="caa0b-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="caa0b-106">Можно определить `Sub` процедуру в модули, классы и структуры.</span><span class="sxs-lookup"><span data-stu-id="caa0b-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="caa0b-107">По умолчанию является `Public`, означает, что можно вызывать из любого места в приложении, которое имеет доступ к модуля, класса или структуры, в котором она определена.</span><span class="sxs-lookup"><span data-stu-id="caa0b-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="caa0b-108">Термин, *метод*, описание `Sub` или `Function` процедуры, к которому осуществляется из вне модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="caa0b-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="caa0b-109">Дополнительные сведения см. в разделе [процедуры](./index.md).</span><span class="sxs-lookup"><span data-stu-id="caa0b-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="caa0b-110">A `Sub` процедура может принимать аргументы, например константы, переменные или выражения, которые передаются ей вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="caa0b-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="caa0b-111">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="caa0b-111">Declaration Syntax</span></span>  
 <span data-ttu-id="caa0b-112">Синтаксис объявления `Sub` используется следующая процедура:</span><span class="sxs-lookup"><span data-stu-id="caa0b-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="caa0b-113">`[`*modifiers* `] Sub`*subname* `[(` *parameterlist*  `)]`</span><span class="sxs-lookup"><span data-stu-id="caa0b-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="caa0b-114">`modifiers` Можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и затенение.</span><span class="sxs-lookup"><span data-stu-id="caa0b-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="caa0b-115">Дополнительные сведения см. в разделе [оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="caa0b-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="caa0b-116">Объявление параметра</span><span class="sxs-lookup"><span data-stu-id="caa0b-116">Parameter Declaration</span></span>  
 <span data-ttu-id="caa0b-117">Объявите каждый параметр процедуры аналогично как объявить переменную, указав параметр имя и тип данных.</span><span class="sxs-lookup"><span data-stu-id="caa0b-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="caa0b-118">Можно также указать механизм передачи и параметр является необязательным или массивом параметров.</span><span class="sxs-lookup"><span data-stu-id="caa0b-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="caa0b-119">Синтаксис для каждого параметра в списке параметров выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="caa0b-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="caa0b-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *имя_параметра*`As`*тип данных    *</span><span class="sxs-lookup"><span data-stu-id="caa0b-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="caa0b-121">Если аргумент является необязательным, необходимо также указать значение по умолчанию как часть его объявления.</span><span class="sxs-lookup"><span data-stu-id="caa0b-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="caa0b-122">Синтаксис для указания значения по умолчанию выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="caa0b-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="caa0b-123">`Optional [ByVal | ByRef]`  *имя_параметра*`As`*datatype*`=`*defaultvalue        *</span><span class="sxs-lookup"><span data-stu-id="caa0b-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="caa0b-124">Параметры как локальные переменные</span><span class="sxs-lookup"><span data-stu-id="caa0b-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="caa0b-125">Когда управление передается в процедуру, каждый параметр рассматривается как локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="caa0b-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="caa0b-126">Это означает, что время существования совпадает, процедуры и ее область действия является вся процедура.</span><span class="sxs-lookup"><span data-stu-id="caa0b-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="caa0b-127">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="caa0b-127">Calling Syntax</span></span>  
 <span data-ttu-id="caa0b-128">Вызвать `Sub` процедуру явным образом с помощью отдельного вызывающего оператора.</span><span class="sxs-lookup"><span data-stu-id="caa0b-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="caa0b-129">Нельзя вызвать, указав ее имя в выражении.</span><span class="sxs-lookup"><span data-stu-id="caa0b-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="caa0b-130">Необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргументов должен быть заключен в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="caa0b-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="caa0b-131">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="caa0b-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="caa0b-132">Использование `Call` ключевое слово, но это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="caa0b-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="caa0b-133">Синтаксис для вызова `Sub` используется следующая процедура:</span><span class="sxs-lookup"><span data-stu-id="caa0b-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="caa0b-134">`[Call]`  *дополнительное_имя* `[(` *argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="caa0b-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="caa0b-135">Можно вызвать `Sub` методу извне определяющего его класса.</span><span class="sxs-lookup"><span data-stu-id="caa0b-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="caa0b-136">Во-первых, необходимо использовать `New` ключевое слово для создания экземпляра класса, или вызвать метод, который возвращает экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="caa0b-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="caa0b-137">Дополнительные сведения см. в разделе [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="caa0b-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="caa0b-138">Затем можно использовать следующий синтаксис для вызова `Sub` метода для экземпляра объекта:</span><span class="sxs-lookup"><span data-stu-id="caa0b-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="caa0b-139">*Object*.* methodName*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="caa0b-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="caa0b-140">Пример объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="caa0b-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="caa0b-141">Следующие `Sub` процедура показывает оператору компьютера, какое задание приложение собирается выполнить, а также отображает отметку времени.</span><span class="sxs-lookup"><span data-stu-id="caa0b-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="caa0b-142">Вместо дублирования этого кода в начале каждой задачи, приложение вызывает `tellOperator` из различных расположений.</span><span class="sxs-lookup"><span data-stu-id="caa0b-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="caa0b-143">Каждый вызов передает строку в `task` , указывающий, запущенную задачу.</span><span class="sxs-lookup"><span data-stu-id="caa0b-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 <span data-ttu-id="caa0b-144">[!code-vb[VbVbcnProcedures&#2;](./codesnippet/VisualBasic/sub-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="caa0b-144">[!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="caa0b-145">В следующем примере показано типичный вызов `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="caa0b-145">The following example shows a typical call to `tellOperator`.</span></span>  
  
 <span data-ttu-id="caa0b-146">[!code-vb[VbVbcnProcedures&#3;](./codesnippet/VisualBasic/sub-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="caa0b-146">[!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa0b-147">См. также</span><span class="sxs-lookup"><span data-stu-id="caa0b-147">See Also</span></span>  
 <span data-ttu-id="caa0b-148">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="caa0b-148">[Procedures](./index.md) </span></span>  
<span data-ttu-id="caa0b-149"> [Процедуры функций](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="caa0b-149"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="caa0b-150"> [Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="caa0b-150"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="caa0b-151"> [Процедуры операторов](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="caa0b-151"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="caa0b-152"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="caa0b-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="caa0b-153"> [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="caa0b-153"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="caa0b-154"> [Практическое руководство: вызов процедуры, которая не возвращает значение](./how-to-call-a-procedure-that-does-not-return-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="caa0b-154"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md) </span></span>  
<span data-ttu-id="caa0b-155"> [Практическое руководство: вызов обработчика событий в Visual Basic](./how-to-call-an-event-handler.md)</span><span class="sxs-lookup"><span data-stu-id="caa0b-155"> [How to: Call an Event Handler in Visual Basic](./how-to-call-an-event-handler.md)</span></span>
