---
title: Подпрограммы (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 646d7d217891dc8ea5b78f7ce30fce19fab08316
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977582"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="d4ea8-102">Подпрограммы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4ea8-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="d4ea8-103">Объект `Sub` процедура — это последовательность операторов Visual Basic, заключенным `Sub` и `End Sub` инструкций.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="d4ea8-104">`Sub` Процедура выполняет задачи и возвращает управление вызывающему коду, но не возвращает значение вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="d4ea8-105">Каждый раз при вызове процедуры, его операторы выполняются, начиная с первого выполняемого оператора после `Sub` инструкции и заканчивая первым `End Sub`, `Exit Sub`, или `Return` обнаружен оператор.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="d4ea8-106">Вы можете определить `Sub` процедуры в модули, классы и структуры.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="d4ea8-107">По умолчанию это `Public`, который означает, что можно вызывать из любого места в приложении, которое имеет доступ к модуля, класса или структуры, в котором она определена.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="d4ea8-108">Термин, *метод*, описывает `Sub` или `Function` процедуры, к которому осуществляется из вне модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="d4ea8-109">Дополнительные сведения см. в разделе [Procedures in Visual Basic](./index.md) (Процедуры в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d4ea8-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="d4ea8-110">Объект `Sub` процедура может принимать аргументы, такие как константы, переменные или выражения, которые передаются в него в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="d4ea8-111">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="d4ea8-111">Declaration Syntax</span></span>  
 <span data-ttu-id="d4ea8-112">Синтаксис объявления `Sub` процедура выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4ea8-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="d4ea8-113">`[` *модификаторы* `] Sub` *subname* `[(` *список_параметров* `)]`</span><span class="sxs-lookup"><span data-stu-id="d4ea8-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="d4ea8-114">`modifiers` Можно указать уровень доступа и сведения о перегрузка, переопределение, совместного использования и затенении.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="d4ea8-115">Дополнительные сведения см. в разделе [оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d4ea8-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="d4ea8-116">Объявление параметра</span><span class="sxs-lookup"><span data-stu-id="d4ea8-116">Parameter Declaration</span></span>  
 <span data-ttu-id="d4ea8-117">Каждый параметр процедуры, как объявить переменную, указав параметр имя и тип данных точно так же объявляется.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="d4ea8-118">Можно также указать способ передачи и параметр является необязательным, или массив параметров.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="d4ea8-119">Синтаксис для каждого параметра в списке параметров выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4ea8-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="d4ea8-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *имя_параметра*`As`*тип данных*</span><span class="sxs-lookup"><span data-stu-id="d4ea8-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="d4ea8-121">Если параметр является необязательным, необходимо также указать значение по умолчанию как часть объявления.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="d4ea8-122">Синтаксис для указания значения по умолчанию выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4ea8-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="d4ea8-123">`Optional [ByVal | ByRef]`  *имя_параметра*`As`*datatype*`=`*defaultvalue*</span><span class="sxs-lookup"><span data-stu-id="d4ea8-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="d4ea8-124">Параметры в качестве локальных переменных</span><span class="sxs-lookup"><span data-stu-id="d4ea8-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="d4ea8-125">Когда управление передается в процедуру, каждый параметр рассматривается как локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="d4ea8-126">Это означает, что его времени существования совпадает со значением, процедуры и ее область действия является вся процедура.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="d4ea8-127">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="d4ea8-127">Calling Syntax</span></span>  
 <span data-ttu-id="d4ea8-128">Вы вызываете `Sub` процедуру явным образом с помощью отдельного вызывающего оператора.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="d4ea8-129">Его нельзя вызвать с помощью его имени в выражении.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="d4ea8-130">Необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргументов необходимо заключить в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="d4ea8-131">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="d4ea8-132">Использование `Call` ключевое слово является необязательным, но не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="d4ea8-133">Синтаксис для вызова `Sub` процедура выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4ea8-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="d4ea8-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="d4ea8-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="d4ea8-135">Вы можете вызвать `Sub` метода из за пределами класса, определяющего его.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="d4ea8-136">Во-первых, необходимо использовать `New` ключевое слово для создания экземпляра класса, или вызвать метод, который возвращает экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="d4ea8-137">Дополнительные сведения см. в разделе [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="d4ea8-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="d4ea8-138">Затем можно использовать следующий синтаксис для вызова `Sub` метода для экземпляра объекта:</span><span class="sxs-lookup"><span data-stu-id="d4ea8-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="d4ea8-139">*Объект*. *имя_метода*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="d4ea8-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="d4ea8-140">Пример объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="d4ea8-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="d4ea8-141">Следующие `Sub` процедура показывает оператору компьютера, какую задачу, приложение собирается выполнить, а также указана метка времени.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="d4ea8-142">Вместо повторения этого кода в начале каждой задачи, приложение вызывает `tellOperator` из различных расположений.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="d4ea8-143">Каждый вызов передает строку в `task` , указывающий, запущенную задачу.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="d4ea8-144">В следующем примере показано типичный вызов `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="d4ea8-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d4ea8-145">См. также</span><span class="sxs-lookup"><span data-stu-id="d4ea8-145">See also</span></span>
- [<span data-ttu-id="d4ea8-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d4ea8-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d4ea8-147">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="d4ea8-147">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="d4ea8-148">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="d4ea8-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d4ea8-149">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="d4ea8-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="d4ea8-150">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="d4ea8-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d4ea8-151">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="d4ea8-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d4ea8-152">Практическое руководство. Вызов процедуры, которая не возвращает значение</span><span class="sxs-lookup"><span data-stu-id="d4ea8-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="d4ea8-153">Практическое руководство. Вызов обработчика событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4ea8-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
