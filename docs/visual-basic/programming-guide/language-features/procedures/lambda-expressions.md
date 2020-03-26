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
ms.openlocfilehash: 1827eb5630ed217527de25fc9d9c2bb8994b9aff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249673"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="f8345-102">Лямбда-выражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8345-102">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="f8345-103">*Выражение lambda* — это функция или подпрограмма без имени, которое может быть использовано там, где делегат действителен.</span><span class="sxs-lookup"><span data-stu-id="f8345-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="f8345-104">Выражения Lambda могут быть функциями или подпрограммами и могут быть однолинейными или многолинейными.</span><span class="sxs-lookup"><span data-stu-id="f8345-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="f8345-105">Вы можете передать значения из текущего объема в выражение lambda.</span><span class="sxs-lookup"><span data-stu-id="f8345-105">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="f8345-106">Заявление `RemoveHandler` является исключением.</span><span class="sxs-lookup"><span data-stu-id="f8345-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="f8345-107">Вы не можете передать выражение лямбда `RemoveHandler`для делегата параметр .</span><span class="sxs-lookup"><span data-stu-id="f8345-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="f8345-108">Вы создаете выражения лямбда, используя `Function` или `Sub` ключевое слово, так же, как вы создаете стандартную функцию или подпрограмму.</span><span class="sxs-lookup"><span data-stu-id="f8345-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="f8345-109">Тем не менее, выражения лямбда включены в заявление.</span><span class="sxs-lookup"><span data-stu-id="f8345-109">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="f8345-110">Следующим примером является выражение лямбда, которое приращает свой аргумент и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="f8345-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="f8345-111">В примере показан синтаксис выражения одностроки, так и многолинейного выражения лямбда для функции.</span><span class="sxs-lookup"><span data-stu-id="f8345-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="f8345-112">Следующим примером является выражение лямбда, которое записывает значение для консоли.</span><span class="sxs-lookup"><span data-stu-id="f8345-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="f8345-113">На примере показан синтаксис выражения одностроки, так и многолинейного выражения лямбда для подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="f8345-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="f8345-114">Обратите внимание, что в предыдущих примерах выражения лямбда присваиваются переменному имени.</span><span class="sxs-lookup"><span data-stu-id="f8345-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="f8345-115">Всякий раз, когда вы ссылаетесь на переменную, вы ссылаетесь на выражение лямбда.</span><span class="sxs-lookup"><span data-stu-id="f8345-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="f8345-116">Вы также можете декларировать и вызывать выражение лямбда в то же время, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8345-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="f8345-117">Выражение лямбда может быть возвращено в качестве значения вызова функции (как показано в примере в разделе [Контекст](#context) позже в этой теме) или передано в качестве аргумента в параметр, который принимает тип делегата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8345-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="f8345-118">Синтаксис лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="f8345-118">Lambda Expression Syntax</span></span>

<span data-ttu-id="f8345-119">Синтаксис выражения лямбда напоминает выражение стандартной функции или подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="f8345-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="f8345-120">Различия заключаются в следующем.</span><span class="sxs-lookup"><span data-stu-id="f8345-120">The differences are as follows:</span></span>

- <span data-ttu-id="f8345-121">Выражение лямбда не имеет названия.</span><span class="sxs-lookup"><span data-stu-id="f8345-121">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="f8345-122">Выражения Lambda не могут иметь `Overloads` модификаторы, такие как или `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="f8345-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="f8345-123">Функции однолинейной лямбды не используют `As` положение для обозначения типа возврата.</span><span class="sxs-lookup"><span data-stu-id="f8345-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="f8345-124">Вместо этого, тип выведен из значения, что тело выражения лямбда оценивает.</span><span class="sxs-lookup"><span data-stu-id="f8345-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="f8345-125">Например, если тело выражения лямбды, `cust.City = "London"`его `Boolean`тип возврата .</span><span class="sxs-lookup"><span data-stu-id="f8345-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="f8345-126">В многолинейных функциях lambda можно либо указать `As` тип возврата, `As` используя оговорку, либо пропустить оговорку, чтобы вывод типа возврата.</span><span class="sxs-lookup"><span data-stu-id="f8345-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="f8345-127">Когда `As` оговорка опущена для многолинейной функции лямбды, тип возврата выводится как доминирующий тип из всех `Return` утверждений в многолинейной функции лямбды.</span><span class="sxs-lookup"><span data-stu-id="f8345-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="f8345-128">*Доминирующим типом* является уникальный тип, который все другие типы могут расширитьдок.</span><span class="sxs-lookup"><span data-stu-id="f8345-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="f8345-129">Если этот уникальный тип не может быть определен, доминирующим типом является уникальный тип, который все другие типы в массиве могут сузиться до.</span><span class="sxs-lookup"><span data-stu-id="f8345-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="f8345-130">Если ни один из указанных уникальных типов нельзя определить, главным типом будет `Object`.</span><span class="sxs-lookup"><span data-stu-id="f8345-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="f8345-131">В этом случае, `Option Strict` если `On`установлен, происходит ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="f8345-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="f8345-132">Например, если выражения, поставляемые `Return` в оператора, `Long`содержат `Double`значения типа `Integer`и, `Double`то результирующая массивная часть типа.</span><span class="sxs-lookup"><span data-stu-id="f8345-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="f8345-133">И `Integer` `Long` расширить `Double` и `Double`только .</span><span class="sxs-lookup"><span data-stu-id="f8345-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="f8345-134">Поэтому `Double` является главным типом.</span><span class="sxs-lookup"><span data-stu-id="f8345-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="f8345-135">Для получения дополнительной информации см. [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="f8345-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="f8345-136">Тело функции одной строки должно быть выражением, которое возвращает значение, а не заявление.</span><span class="sxs-lookup"><span data-stu-id="f8345-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="f8345-137">Для однолинейных функций не `Return` существует оператора.</span><span class="sxs-lookup"><span data-stu-id="f8345-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="f8345-138">Значение, возвращаемые однолинейной функцией, является значением выражения в теле функции.</span><span class="sxs-lookup"><span data-stu-id="f8345-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="f8345-139">Тело однолинейного подпрограммы должно быть однолинейным заявлением.</span><span class="sxs-lookup"><span data-stu-id="f8345-139">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="f8345-140">Функции и подпрограммы одной строки `End Function` `End Sub` не включают в себя или заявление.</span><span class="sxs-lookup"><span data-stu-id="f8345-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="f8345-141">Можно указать тип параметра выражения лямбда `As` с помощью ключевого слова или сделать вывод о типе параметра.</span><span class="sxs-lookup"><span data-stu-id="f8345-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="f8345-142">Либо все параметры должны иметь указанные типы данных, либо все должны быть выведены.</span><span class="sxs-lookup"><span data-stu-id="f8345-142">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="f8345-143">`Optional`и `Paramarray` параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="f8345-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="f8345-144">Общие параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="f8345-144">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="f8345-145">Асинхронные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="f8345-145">Async Lambdas</span></span>

<span data-ttu-id="f8345-146">Вы можете легко создавать выражения и заявления lambda, которые включают асинхронную обработку с помощью ключевых слов [Async](../../../../visual-basic/language-reference/modifiers/async.md) и [Await Operator.](../../../../visual-basic/language-reference/operators/await-operator.md)</span><span class="sxs-lookup"><span data-stu-id="f8345-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="f8345-147">Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.</span><span class="sxs-lookup"><span data-stu-id="f8345-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="f8345-148">Вы можете добавить тот же обработчик событий с помощью async lambda в [отчете AddHandler.](../../../../visual-basic/language-reference/statements/addhandler-statement.md)</span><span class="sxs-lookup"><span data-stu-id="f8345-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="f8345-149">Чтобы добавить этот обработчик, поставьте модификатор `Async` перед списком параметров лямбда-выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8345-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

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

<span data-ttu-id="f8345-150">Для получения дополнительной информации о том, как создавать и использовать методы async, [см.](../../../../visual-basic/programming-guide/concepts/async/index.md)</span><span class="sxs-lookup"><span data-stu-id="f8345-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="f8345-151">Контекст</span><span class="sxs-lookup"><span data-stu-id="f8345-151">Context</span></span>

<span data-ttu-id="f8345-152">Выражение лямбда разделяет его контекст с областью, в которой оно определено.</span><span class="sxs-lookup"><span data-stu-id="f8345-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="f8345-153">Он имеет те же права доступа, что и любой код, написанный в содержащем области.</span><span class="sxs-lookup"><span data-stu-id="f8345-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="f8345-154">Это включает в себя доступ к переменным членов, функциям и подлодкам, `Me`а также параметрам и локальным переменным в области, содержащему область.</span><span class="sxs-lookup"><span data-stu-id="f8345-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="f8345-155">Доступ к локальным переменным и параметрам в содержащейся области может выходить за рамки срока службы этой сферы.</span><span class="sxs-lookup"><span data-stu-id="f8345-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="f8345-156">До тех пор, пока делегат, ссылаясь на выражение лямбды, не доступен для сбора мусора, доступ к переменным в исходной среде сохраняется.</span><span class="sxs-lookup"><span data-stu-id="f8345-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="f8345-157">В следующем примере `target` переменная `makeTheGame`является локальной для метода, в котором определяется выражение `playTheGame` лямбда.</span><span class="sxs-lookup"><span data-stu-id="f8345-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="f8345-158">Обратите внимание, что возвращенное выражение `takeAGuess` `Main`lambda, назначенное `target`в, по-прежнему имеет доступ к локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="f8345-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="f8345-159">Следующий пример демонстрирует широкий спектр прав доступа вложенного выражения лямбда.</span><span class="sxs-lookup"><span data-stu-id="f8345-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="f8345-160">Когда возвращенное выражение lambda `Main` `aDel`выполняется от как, оно получает доступ к этим элементам:</span><span class="sxs-lookup"><span data-stu-id="f8345-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="f8345-161">Поле класса, в котором он определяется:`aField`</span><span class="sxs-lookup"><span data-stu-id="f8345-161">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="f8345-162">Свойство класса, в котором он определяется:`aProp`</span><span class="sxs-lookup"><span data-stu-id="f8345-162">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="f8345-163">Параметр метода, `functionWithNestedLambda`в котором он определен:`level1`</span><span class="sxs-lookup"><span data-stu-id="f8345-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="f8345-164">Локальная `functionWithNestedLambda`переменная:`localVar`</span><span class="sxs-lookup"><span data-stu-id="f8345-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="f8345-165">Параметр выражения лямбда, в котором она вложена:`level2`</span><span class="sxs-lookup"><span data-stu-id="f8345-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="f8345-166">Преобразование в тип делегата</span><span class="sxs-lookup"><span data-stu-id="f8345-166">Converting to a Delegate Type</span></span>

<span data-ttu-id="f8345-167">Выражение лямбда может быть неявно преобразовано в совместимый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="f8345-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="f8345-168">Для получения информации об общих требованиях к совместимости [см.](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="f8345-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="f8345-169">Например, в следующем примере кода показано выражение лямбда, которое неявно преобразуется `Func(Of Integer, Boolean)` в подпись делегата или соответствующую подпись делегата.</span><span class="sxs-lookup"><span data-stu-id="f8345-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="f8345-170">Следующий пример кода показывает выражение лямбда, `Sub(Of Double, String, Double)` которое неявно преобразуется в или соответствующую подпись делегата.</span><span class="sxs-lookup"><span data-stu-id="f8345-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="f8345-171">При присвоении выражения мягца делегатам или в качестве аргументов в процедуры можно указать имена параметров, но пропустить их типы данных, позволяя отнять типы данных у делегата.</span><span class="sxs-lookup"><span data-stu-id="f8345-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="f8345-172">Примеры</span><span class="sxs-lookup"><span data-stu-id="f8345-172">Examples</span></span>

- <span data-ttu-id="f8345-173">Следующий пример определяет выражение lambda, которое возвращается, `True` если аргумент типа `False` нулевой `Nothing`значения имеет присвоенное значение, и если его значение находится в .</span><span class="sxs-lookup"><span data-stu-id="f8345-173">The following example defines a lambda expression that returns `True` if the nullable value type argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="f8345-174">Следующий пример определяет выражение лямбда, которое возвращает индекс последнего элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="f8345-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="f8345-175">См. также</span><span class="sxs-lookup"><span data-stu-id="f8345-175">See also</span></span>

- [<span data-ttu-id="f8345-176">Процедуры</span><span class="sxs-lookup"><span data-stu-id="f8345-176">Procedures</span></span>](./index.md)
- <span data-ttu-id="f8345-177">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8345-177">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="f8345-178">Делегаты</span><span class="sxs-lookup"><span data-stu-id="f8345-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="f8345-179">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="f8345-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="f8345-180">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="f8345-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f8345-181">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="f8345-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="f8345-182">Практическое руководство. Передача процедур другой процедуре в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8345-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="f8345-183">Практическое руководство. Создание лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="f8345-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="f8345-184">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="f8345-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
