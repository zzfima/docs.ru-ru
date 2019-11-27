---
title: Лямбда-выражения
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: f3f963167e1b3633cc5fe6e1f435e374cd272cce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345977"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="20079-102">Лямбда-выражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20079-102">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="20079-103">*Лямбда-выражение* — это функция или подпрограммы без имени, которую можно использовать везде, где действует делегат.</span><span class="sxs-lookup"><span data-stu-id="20079-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="20079-104">Лямбда-выражения могут быть функциями или подподпрограммами и могут быть однострочными или многострочными.</span><span class="sxs-lookup"><span data-stu-id="20079-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="20079-105">Можно передать значения из текущей области в лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="20079-105">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="20079-106">Оператор `RemoveHandler` является исключением.</span><span class="sxs-lookup"><span data-stu-id="20079-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="20079-107">Невозможно передать лямбда-выражение в для параметра делегата `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="20079-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="20079-108">Лямбда-выражения создаются с помощью ключевого слова `Function` или `Sub`, как при создании стандартной функции или подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="20079-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="20079-109">Однако лямбда-выражения включаются в оператор.</span><span class="sxs-lookup"><span data-stu-id="20079-109">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="20079-110">Следующий пример представляет собой лямбда-выражение, которое увеличивает свой аргумент и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="20079-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="20079-111">В примере показан синтаксис однострочного и многострочного лямбда-выражения для функции.</span><span class="sxs-lookup"><span data-stu-id="20079-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="20079-112">Следующий пример представляет собой лямбда-выражение, которое записывает значение в консоль.</span><span class="sxs-lookup"><span data-stu-id="20079-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="20079-113">В примере показан синтаксис однострочного и многострочного лямбда-выражения для подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="20079-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="20079-114">Обратите внимание, что в предыдущих примерах лямбда-выражения присваиваются имени переменной.</span><span class="sxs-lookup"><span data-stu-id="20079-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="20079-115">При каждом обращении к переменной вызывается лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="20079-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="20079-116">Можно также объявить и вызвать лямбда-выражение одновременно, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="20079-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="20079-117">Лямбда-выражение может быть возвращено как значение вызова функции (как показано в примере в разделе " [контекст](#context) " Далее в этом разделе) или передано в качестве аргумента в параметр, принимающий тип делегата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="20079-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="20079-118">Синтаксис лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="20079-118">Lambda Expression Syntax</span></span>

<span data-ttu-id="20079-119">Синтаксис лямбда-выражения напоминает стандартную функцию или подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="20079-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="20079-120">Различия заключаются в следующем.</span><span class="sxs-lookup"><span data-stu-id="20079-120">The differences are as follows:</span></span>

- <span data-ttu-id="20079-121">Лямбда-выражение не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="20079-121">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="20079-122">Лямбда-выражения не могут иметь модификаторы, такие как `Overloads` или `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="20079-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="20079-123">Однострочные лямбда-функции не используют предложение `As` для обозначения возвращаемого типа.</span><span class="sxs-lookup"><span data-stu-id="20079-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="20079-124">Вместо этого тип выводится из значения, которое вычисляется телом лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="20079-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="20079-125">Например, если тело лямбда-выражения имеет `cust.City = "London"`, его возвращаемый тип — `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="20079-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="20079-126">В многострочных лямбда-функциях можно либо указать тип возвращаемого значения с помощью предложения `As`, либо опустить предложение `As`, чтобы тип возвращаемого значения был выведен.</span><span class="sxs-lookup"><span data-stu-id="20079-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="20079-127">Если в многострочной лямбда-функции пропущено предложение `As`, возвращаемый тип определяется как главный тип от всех инструкций `Return` в многострочной лямбда-функции.</span><span class="sxs-lookup"><span data-stu-id="20079-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="20079-128">*Главный тип* — это уникальный тип, к которому могут расширяться все другие типы.</span><span class="sxs-lookup"><span data-stu-id="20079-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="20079-129">Если невозможно определить этот уникальный тип, главным типом является уникальный тип, до которого могут быть ограничены все другие типы в массиве.</span><span class="sxs-lookup"><span data-stu-id="20079-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="20079-130">Если ни один из указанных уникальных типов нельзя определить, главным типом будет `Object`.</span><span class="sxs-lookup"><span data-stu-id="20079-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="20079-131">В этом случае, если `Option Strict` имеет значение `On`, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="20079-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="20079-132">Например, если выражения, передаваемые в оператор `Return`, содержат значения типа `Integer`, `Long`и `Double`, полученный массив имеет тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="20079-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="20079-133">Как `Integer`, так `Long` расширяются до `Double` и только `Double`.</span><span class="sxs-lookup"><span data-stu-id="20079-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="20079-134">Поэтому `Double` является главным типом.</span><span class="sxs-lookup"><span data-stu-id="20079-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="20079-135">Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="20079-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="20079-136">Тело однострочной функции должно быть выражением, возвращающим значение, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="20079-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="20079-137">Для однострочных функций отсутствует `Return`ная инструкция.</span><span class="sxs-lookup"><span data-stu-id="20079-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="20079-138">Значение, возвращаемое однострочной функцией, является значением выражения в теле функции.</span><span class="sxs-lookup"><span data-stu-id="20079-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="20079-139">Тело однострочной подпрограммы должно быть однострочным оператором.</span><span class="sxs-lookup"><span data-stu-id="20079-139">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="20079-140">Однострочные функции и подпрограммы не включают `End Function` или `End Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="20079-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="20079-141">Можно указать тип данных параметра лямбда-выражения с помощью ключевого слова `As`, или же тип данных параметра может быть определен.</span><span class="sxs-lookup"><span data-stu-id="20079-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="20079-142">Либо все параметры должны иметь указанные типы данных, либо все должны быть выведены.</span><span class="sxs-lookup"><span data-stu-id="20079-142">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="20079-143">Параметры `Optional` и `Paramarray` не разрешены.</span><span class="sxs-lookup"><span data-stu-id="20079-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="20079-144">Универсальные параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="20079-144">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="20079-145">Асинхронные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="20079-145">Async Lambdas</span></span>

<span data-ttu-id="20079-146">Можно легко создавать лямбда-выражения и инструкции, включающие асинхронную обработку с помощью ключевых слов оператора [Async](../../../../visual-basic/language-reference/modifiers/async.md) и [await](../../../../visual-basic/language-reference/operators/await-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="20079-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="20079-147">Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.</span><span class="sxs-lookup"><span data-stu-id="20079-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```vb
Public Class Form1

    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        ' ExampleMethodAsync returns a Task.
        Await ExampleMethodAsync()
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."
    End Sub

    Async Function ExampleMethodAsync() As Task
        ' The following line simulates a task-returning asynchronous process.
        Await Task.Delay(1000)
    End Function

End Class
```

<span data-ttu-id="20079-148">Вы можете добавить тот же обработчик событий с помощью асинхронного лямбда-выражения в [операторе AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="20079-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="20079-149">Чтобы добавить этот обработчик, поставьте модификатор `Async` перед списком параметров лямбда-выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="20079-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

```vb
Public Class Form1

    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        AddHandler Button1.Click,
            Async Sub(sender1, e1)
                ' ExampleMethodAsync returns a Task.
                Await ExampleMethodAsync()
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."
            End Sub
    End Sub

    Async Function ExampleMethodAsync() As Task
        ' The following line simulates a task-returning asynchronous process.
        Await Task.Delay(1000)
    End Function

End Class
```

<span data-ttu-id="20079-150">Дополнительные сведения о создании и использовании асинхронных методов см. в разделе [Асинхронное программирование с использованием Async и await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="20079-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="20079-151">Контекст</span><span class="sxs-lookup"><span data-stu-id="20079-151">Context</span></span>

<span data-ttu-id="20079-152">Лямбда-выражение использует свой контекст с областью, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="20079-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="20079-153">Он имеет те же права доступа, что и любой код, написанный в содержащей его области.</span><span class="sxs-lookup"><span data-stu-id="20079-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="20079-154">Это включает доступ к переменным элементов, функциям и процедурам, `Me`, а также параметрам и локальным переменным в содержащей их области.</span><span class="sxs-lookup"><span data-stu-id="20079-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="20079-155">Доступ к локальным переменным и параметрам в содержащей области может дополняться за время существования этой области.</span><span class="sxs-lookup"><span data-stu-id="20079-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="20079-156">Пока делегат, ссылающийся на лямбда-выражение, недоступен для сборки мусора, доступ к переменным в исходной среде сохраняется.</span><span class="sxs-lookup"><span data-stu-id="20079-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="20079-157">В следующем примере переменная `target` локальная для `makeTheGame`, метод, в котором определяется лямбда-выражение `playTheGame`.</span><span class="sxs-lookup"><span data-stu-id="20079-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="20079-158">Обратите внимание, что возвращенное лямбда-выражение, назначенное `takeAGuess` в `Main`, по-прежнему имеет доступ к локальной переменной `target`.</span><span class="sxs-lookup"><span data-stu-id="20079-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="20079-159">В следующем примере показан широкий спектр прав доступа вложенного лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="20079-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="20079-160">Когда возвращаемое лямбда-выражение выполняется из `Main` как `aDel`, оно обращается к следующим элементам:</span><span class="sxs-lookup"><span data-stu-id="20079-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="20079-161">Поле класса, в котором оно определено: `aField`</span><span class="sxs-lookup"><span data-stu-id="20079-161">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="20079-162">Свойство класса, в котором оно определено: `aProp`</span><span class="sxs-lookup"><span data-stu-id="20079-162">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="20079-163">Параметр метода `functionWithNestedLambda`, в котором он определен: `level1`</span><span class="sxs-lookup"><span data-stu-id="20079-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="20079-164">Локальная переменная `functionWithNestedLambda`: `localVar`</span><span class="sxs-lookup"><span data-stu-id="20079-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="20079-165">Параметр лямбда-выражения, в котором он вложен: `level2`</span><span class="sxs-lookup"><span data-stu-id="20079-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="20079-166">Преобразование в тип делегата</span><span class="sxs-lookup"><span data-stu-id="20079-166">Converting to a Delegate Type</span></span>

<span data-ttu-id="20079-167">Лямбда-выражение может быть неявно преобразовано в совместимый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="20079-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="20079-168">Сведения о общих требованиях к совместимости см. в разделе [неявное преобразование делегатов](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="20079-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="20079-169">Например, в следующем примере кода показано лямбда-выражение, которое неявно преобразуется в `Func(Of Integer, Boolean)` или соответствующую сигнатуру делегата.</span><span class="sxs-lookup"><span data-stu-id="20079-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="20079-170">В следующем примере кода показано лямбда-выражение, которое неявно преобразуется в `Sub(Of Double, String, Double)` или соответствующую сигнатуру делегата.</span><span class="sxs-lookup"><span data-stu-id="20079-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="20079-171">При назначении лямбда-выражений делегатам или передаче их в качестве аргументов в процедуры можно указать имена параметров, но не указывать их типы данных, позволяя принимать типы из делегата.</span><span class="sxs-lookup"><span data-stu-id="20079-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="20079-172">Примеры</span><span class="sxs-lookup"><span data-stu-id="20079-172">Examples</span></span>

- <span data-ttu-id="20079-173">В следующем примере определяется лямбда-выражение, которое возвращает `True`, если аргументу, допускающему значение null, присвоено значение, и `False`, если его значение равно `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="20079-173">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="20079-174">В следующем примере определяется лямбда-выражение, возвращающее индекс последнего элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="20079-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="20079-175">См. также</span><span class="sxs-lookup"><span data-stu-id="20079-175">See also</span></span>

- [<span data-ttu-id="20079-176">Процедуры</span><span class="sxs-lookup"><span data-stu-id="20079-176">Procedures</span></span>](./index.md)
- <span data-ttu-id="20079-177">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20079-177">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="20079-178">Делегаты</span><span class="sxs-lookup"><span data-stu-id="20079-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="20079-179">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="20079-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="20079-180">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="20079-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="20079-181">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="20079-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- <span data-ttu-id="20079-182">[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) (Практическое руководство. Передача процедур другой процедуре в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20079-182">[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)</span></span>
- [<span data-ttu-id="20079-183">Практическое руководство. Создание лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="20079-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="20079-184">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="20079-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
