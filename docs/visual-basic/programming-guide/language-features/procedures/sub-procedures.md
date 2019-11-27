---
title: Подпрограммы
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
ms.openlocfilehash: 7848dc07d6462622685cdbea92202585f4d5d2c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352527"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="28214-102">Подпрограммы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28214-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="28214-103">`Sub` процедура — это последовательность Visual Basic инструкций, заключенных в операторы `Sub` и `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="28214-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="28214-104">`Sub` процедура выполняет задачу, а затем возвращает управление вызывающему коду, но не возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="28214-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="28214-105">При каждом вызове процедуры выполняются ее операторы, начиная с первого исполняемого оператора после оператора `Sub` и заканчивая первой инструкцией `End Sub`, `Exit Sub`или `Return`.</span><span class="sxs-lookup"><span data-stu-id="28214-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="28214-106">Процедуру `Sub` можно определить в модулях, классах и структурах.</span><span class="sxs-lookup"><span data-stu-id="28214-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="28214-107">По умолчанию это `Public`, что означает, что вы можете вызывать его из любого места в приложении, которое имеет доступ к модулю, классу или структуре, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="28214-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="28214-108">Термин « *метод*» описывает `Sub` или `Function` процедуру, доступ к которой осуществляется извне его определяющего модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="28214-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="28214-109">Дополнительные сведения см. в разделе [Procedures in Visual Basic](./index.md) (Процедуры в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="28214-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="28214-110">`Sub` процедура может принимать аргументы, такие как константы, переменные или выражения, которые передаются в него вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="28214-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="28214-111">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="28214-111">Declaration Syntax</span></span>  
 <span data-ttu-id="28214-112">Синтаксис для объявления `Sub` процедуры выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="28214-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="28214-113">`[` *модификаторы* `] Sub`*подимени* `[(` *parameterlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="28214-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="28214-114">`modifiers` может указывать уровень доступа и сведения о перегрузке, переопределении, совместном использовании и затенении.</span><span class="sxs-lookup"><span data-stu-id="28214-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="28214-115">Дополнительные сведения см. в разделе [оператор подраздела](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="28214-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="28214-116">Объявление параметра</span><span class="sxs-lookup"><span data-stu-id="28214-116">Parameter Declaration</span></span>  
 <span data-ttu-id="28214-117">Каждый параметр процедуры объявляется аналогично объявлению переменной, указывая имя параметра и тип данных.</span><span class="sxs-lookup"><span data-stu-id="28214-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="28214-118">Кроме того, можно указать механизм передачи, а также определить, является ли параметр необязательным или массивом параметров.</span><span class="sxs-lookup"><span data-stu-id="28214-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="28214-119">Для каждого параметра в списке параметров используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28214-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="28214-120">`[Optional] [ByVal | ByRef] [ParamArray]`*parametername*`As`*DataType*</span><span class="sxs-lookup"><span data-stu-id="28214-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="28214-121">Если параметр является необязательным, необходимо также указать значение по умолчанию в составе объявления.</span><span class="sxs-lookup"><span data-stu-id="28214-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="28214-122">Для указания значения по умолчанию используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="28214-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="28214-123">`Optional [ByVal | ByRef]`*parametername*`As`*DataType*`=`*DefaultValue*</span><span class="sxs-lookup"><span data-stu-id="28214-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="28214-124">Параметры как локальные переменные</span><span class="sxs-lookup"><span data-stu-id="28214-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="28214-125">Когда управление передается в процедуру, каждый параметр рассматривается как локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="28214-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="28214-126">Это означает, что его время существования совпадает с жизненным циклом процедуры, а ее областью является вся процедура.</span><span class="sxs-lookup"><span data-stu-id="28214-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="28214-127">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="28214-127">Calling Syntax</span></span>  
 <span data-ttu-id="28214-128">Процедура `Sub` явно вызывается с помощью изолированного вызывающего оператора.</span><span class="sxs-lookup"><span data-stu-id="28214-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="28214-129">Его нельзя вызвать, используя его имя в выражении.</span><span class="sxs-lookup"><span data-stu-id="28214-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="28214-130">Необходимо указать значения для всех аргументов, которые не являются необязательными, и необходимо заключить список аргументов в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="28214-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="28214-131">Если аргументы не указаны, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="28214-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="28214-132">Использование ключевого слова `Call` является необязательным, но не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="28214-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="28214-133">Синтаксис вызова `Sub` процедуры выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="28214-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="28214-134">*имя* `[Call]``[(` *ArgumentList* `)]`</span><span class="sxs-lookup"><span data-stu-id="28214-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="28214-135">Метод `Sub` можно вызвать извне класса, который его определяет.</span><span class="sxs-lookup"><span data-stu-id="28214-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="28214-136">Во-первых, необходимо использовать ключевое слово `New` для создания экземпляра класса или вызвать метод, возвращающий экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="28214-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="28214-137">Дополнительные сведения см. в разделе [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="28214-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="28214-138">Затем можно использовать следующий синтаксис, чтобы вызвать метод `Sub` для объекта экземпляра:</span><span class="sxs-lookup"><span data-stu-id="28214-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="28214-139">*Объект*. *имя_метода*`[(`*ArgumentList*`)]`</span><span class="sxs-lookup"><span data-stu-id="28214-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="28214-140">Иллюстрация объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="28214-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="28214-141">Следующая процедура `Sub` указывает оператору компьютера, какую задачу собирается выполнить приложение, а также отображает метку времени.</span><span class="sxs-lookup"><span data-stu-id="28214-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="28214-142">Вместо дублирования этого кода в начале каждой задачи приложение просто вызывает `tellOperator` из различных расположений.</span><span class="sxs-lookup"><span data-stu-id="28214-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="28214-143">Каждый вызов передает строку в аргументе `task`, который определяет запускаемую задачу.</span><span class="sxs-lookup"><span data-stu-id="28214-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="28214-144">В следующем примере показан типичный вызов `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="28214-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="28214-145">См. также</span><span class="sxs-lookup"><span data-stu-id="28214-145">See also</span></span>

- [<span data-ttu-id="28214-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="28214-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="28214-147">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="28214-147">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="28214-148">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="28214-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="28214-149">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="28214-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="28214-150">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="28214-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="28214-151">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="28214-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="28214-152">Практическое руководство. Вызов процедуры, которая не возвращает значение</span><span class="sxs-lookup"><span data-stu-id="28214-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="28214-153">Как вызвать обработчик событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="28214-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
