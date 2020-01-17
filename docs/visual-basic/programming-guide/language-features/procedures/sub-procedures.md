---
title: Sub - процедуры
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
ms.openlocfilehash: 9ca1d302a0bc8e989e0b2dddf8cce68e89211d57
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163817"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="4d7f7-102">Процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d7f7-102">Sub procedures (Visual Basic)</span></span>

<span data-ttu-id="4d7f7-103">`Sub` процедура — это последовательность Visual Basic инструкций, заключенных в операторы `Sub` и `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="4d7f7-104">`Sub` процедура выполняет задачу, а затем возвращает управление вызывающему коду, но не возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>

<span data-ttu-id="4d7f7-105">При каждом вызове процедуры выполняются ее операторы, начиная с первого исполняемого оператора после оператора `Sub` и заканчивая первой инструкцией `End Sub`, `Exit Sub`или `Return`.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>

<span data-ttu-id="4d7f7-106">Процедуру `Sub` можно определить в модулях, классах и структурах.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="4d7f7-107">По умолчанию это `Public`, что означает, что вы можете вызывать его из любого места в приложении, которое имеет доступ к модулю, классу или структуре, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="4d7f7-108">*Метод* term описывает `Sub` или `Function` процедуру, доступ к которой осуществляется извне его определяющего модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-108">The term *method* describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="4d7f7-109">Дополнительные сведения см. в разделе [Procedures in Visual Basic](./index.md) (Процедуры в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4d7f7-109">For more information, see [Procedures](./index.md).</span></span>

<span data-ttu-id="4d7f7-110">`Sub` процедура может принимать аргументы, такие как константы, переменные или выражения, которые передаются в него вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="4d7f7-111">Синтаксис объявления</span><span class="sxs-lookup"><span data-stu-id="4d7f7-111">Declaration syntax</span></span>

<span data-ttu-id="4d7f7-112">Синтаксис для объявления `Sub` процедуры выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4d7f7-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

<span data-ttu-id="4d7f7-113">`modifiers` может указывать уровень доступа и сведения о перегрузке, переопределении, совместном использовании и затенении.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-113">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="4d7f7-114">Дополнительные сведения см. в разделе [оператор подраздела](../../../language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4d7f7-114">For more information, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="4d7f7-115">Объявление параметра</span><span class="sxs-lookup"><span data-stu-id="4d7f7-115">Parameter declaration</span></span>

<span data-ttu-id="4d7f7-116">Каждый параметр процедуры объявляется аналогично объявлению переменной, указывая имя параметра и тип данных.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-116">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="4d7f7-117">Кроме того, можно указать механизм передачи, а также определить, является ли параметр необязательным или массивом параметров.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-117">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>

<span data-ttu-id="4d7f7-118">Для каждого параметра в списке параметров используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4d7f7-118">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

<span data-ttu-id="4d7f7-119">Если параметр является необязательным, необходимо также указать значение по умолчанию в составе объявления.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-119">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="4d7f7-120">Для указания значения по умолчанию используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4d7f7-120">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a><span data-ttu-id="4d7f7-121">Параметры как локальные переменные</span><span class="sxs-lookup"><span data-stu-id="4d7f7-121">Parameters as local variables</span></span>

<span data-ttu-id="4d7f7-122">Когда управление передается в процедуру, каждый параметр рассматривается как локальная переменная.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-122">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="4d7f7-123">Это означает, что его время существования совпадает с жизненным циклом процедуры, а ее областью является вся процедура.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-123">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="4d7f7-124">Синтаксис вызова</span><span class="sxs-lookup"><span data-stu-id="4d7f7-124">Calling syntax</span></span>

<span data-ttu-id="4d7f7-125">Процедура `Sub` явно вызывается с помощью изолированного вызывающего оператора.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-125">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="4d7f7-126">Его нельзя вызвать, используя его имя в выражении.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-126">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="4d7f7-127">Необходимо указать значения для всех аргументов, которые не являются необязательными, и необходимо заключить список аргументов в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-127">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="4d7f7-128">Если аргументы не указаны, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-128">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="4d7f7-129">Использование ключевого слова `Call` является необязательным, но не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-129">The use of the `Call` keyword is optional but not recommended.</span></span>

<span data-ttu-id="4d7f7-130">Синтаксис вызова `Sub` процедуры выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4d7f7-130">The syntax for a call to a `Sub` procedure is as follows:</span></span>

```vb
[Call] SubName[(argumentlist)]
```

<span data-ttu-id="4d7f7-131">Метод `Sub` можно вызвать извне класса, который его определяет.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-131">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="4d7f7-132">Во-первых, необходимо использовать ключевое слово `New` для создания экземпляра класса или вызвать метод, возвращающий экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-132">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="4d7f7-133">Дополнительные сведения см. в разделе [оператор New](../../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4d7f7-133">For more information, see [New Operator](../../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="4d7f7-134">Затем можно использовать следующий синтаксис, чтобы вызвать метод `Sub` для объекта экземпляра:</span><span class="sxs-lookup"><span data-stu-id="4d7f7-134">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="4d7f7-135">Иллюстрация объявления и вызова</span><span class="sxs-lookup"><span data-stu-id="4d7f7-135">Illustration of declaration and call</span></span>

<span data-ttu-id="4d7f7-136">Следующая процедура `Sub` указывает оператору компьютера, какую задачу собирается выполнить приложение, а также отображает метку времени.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-136">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="4d7f7-137">Вместо дублирования этого кода в начале каждой задачи приложение просто вызывает `tellOperator` из различных расположений.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-137">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="4d7f7-138">Каждый вызов передает строку в аргументе `task`, который определяет запускаемую задачу.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-138">Each call passes a string in the `task` argument that identifies the task being started.</span></span>

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

<span data-ttu-id="4d7f7-139">В следующем примере показан типичный вызов `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="4d7f7-139">The following example shows a typical call to `tellOperator`.</span></span>

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a><span data-ttu-id="4d7f7-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d7f7-140">See also</span></span>

- [<span data-ttu-id="4d7f7-141">Процедуры</span><span class="sxs-lookup"><span data-stu-id="4d7f7-141">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4d7f7-142">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="4d7f7-142">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="4d7f7-143">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="4d7f7-143">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="4d7f7-144">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="4d7f7-144">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="4d7f7-145">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="4d7f7-145">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4d7f7-146">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="4d7f7-146">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="4d7f7-147">Практическое руководство. Вызов процедуры, которая не возвращает значение</span><span class="sxs-lookup"><span data-stu-id="4d7f7-147">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="4d7f7-148">Как вызвать обработчик событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d7f7-148">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
