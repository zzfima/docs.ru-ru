---
title: "Лямбда-выражения (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.LambdaFunction
dev_langs:
- VB
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e4624e5f20beeebf85656c893043030566200557
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="04b57-102">Лямбда-выражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04b57-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="04b57-103">Объект *лямбда-выражение* является функцией или подпрограммой без имени, которую можно использовать везде, где допустим делегат.</span><span class="sxs-lookup"><span data-stu-id="04b57-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="04b57-104">Лямбда-выражения могут быть функциями или подпрограммами и может быть одной или нескольких строк.</span><span class="sxs-lookup"><span data-stu-id="04b57-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="04b57-105">Лямбда-выражение можно передавать значения из текущей области.</span><span class="sxs-lookup"><span data-stu-id="04b57-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04b57-106">`RemoveHandler` Инструкция является исключением.</span><span class="sxs-lookup"><span data-stu-id="04b57-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="04b57-107">Невозможно передать лямбда-выражение в параметра делегата для `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="04b57-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="04b57-108">Лямбда-выражения создаются с помощью `Function` или `Sub` ключевое слово, так же как стандартные функции или подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="04b57-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="04b57-109">Однако лямбда-выражения включаются в оператор.</span><span class="sxs-lookup"><span data-stu-id="04b57-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="04b57-110">Следующий пример является лямбда-выражение, которое увеличивает значение своего аргумента и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="04b57-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="04b57-111">В этом примере синтаксис однострочные и многострочные лямбда-выражения для функции.</span><span class="sxs-lookup"><span data-stu-id="04b57-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 <span data-ttu-id="04b57-112">[!code-vb[VbVbalrLambdas&#14;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-112">[!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span></span>  
  
 <span data-ttu-id="04b57-113">Следующий пример является лямбда-выражения, записывающего значение на консоль.</span><span class="sxs-lookup"><span data-stu-id="04b57-113">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="04b57-114">В этом примере синтаксис однострочные и многострочные лямбда-выражения для подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="04b57-114">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 <span data-ttu-id="04b57-115">[!code-vb[VbVbalrLambdas&#15;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-115">[!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span></span>  
  
 <span data-ttu-id="04b57-116">Обратите внимание, что в предыдущих примерах лямбда-выражения назначены имя переменной.</span><span class="sxs-lookup"><span data-stu-id="04b57-116">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="04b57-117">При каждом обращении к переменной вызывается лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="04b57-117">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="04b57-118">Можно также объявить и вызвать лямбда-выражение, в то же время, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="04b57-118">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 <span data-ttu-id="04b57-119">[!code-vb[VbVbalrLambdas&#3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-119">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span></span>  
  
 <span data-ttu-id="04b57-120">Лямбда-выражения могут возвращаться как значение вызванной функции (как показано в примере в [контекста](#context) позже в этой статье), либо передано в качестве аргумента параметр, который принимает тип делегата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="04b57-120">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 <span data-ttu-id="04b57-121">[!code-vb[VbVbalrLambdas №&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-121">[!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="04b57-122">Синтаксис лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="04b57-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="04b57-123">Синтаксис лямбда-выражения похож стандартные функции или подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="04b57-123">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="04b57-124">Ниже приведены различия.</span><span class="sxs-lookup"><span data-stu-id="04b57-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="04b57-125">Лямбда-выражение не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="04b57-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="04b57-126">Лямбда-выражения не могут иметь модификаторы, такие как `Overloads` или `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="04b57-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="04b57-127">Однострочные лямбда-функции не используют `As` предложения, чтобы указать тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="04b57-127">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="04b57-128">Вместо этого тип выводится из значения, результатом которого является тело лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="04b57-128">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="04b57-129">Например, если тело лямбда-выражения — `cust.City = "London"`, возвращается тип `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="04b57-129">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="04b57-130">В многострочных лямбда-функции, можно указать тип возвращаемого значения с помощью `As` предложение, или пропускать `As` предложение, чтобы вывести тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="04b57-130">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="04b57-131">Когда `As` опущен для многострочных лямбда-функции, возвращаемый тип определяется как главный тип из всех `Return` инструкций в многострочных лямбда-функции.</span><span class="sxs-lookup"><span data-stu-id="04b57-131">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="04b57-132">*Главный тип* — это уникальный тип, могут быть расширены все другие типы.</span><span class="sxs-lookup"><span data-stu-id="04b57-132">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="04b57-133">Если такой уникальный тип нельзя определить, главным типом будет тип, до которого можно сузить все другие типы массива.</span><span class="sxs-lookup"><span data-stu-id="04b57-133">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="04b57-134">Если ни один из указанных уникальных типов нельзя определить, главным типом будет `Object`.</span><span class="sxs-lookup"><span data-stu-id="04b57-134">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="04b57-135">В этом случае если `Option Strict` равен `On`, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="04b57-135">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="04b57-136">Например, если передан выражения `Return` инструкции содержат значения типа `Integer`, `Long`, и `Double`, полученный массив имеет тип `Double`.</span><span class="sxs-lookup"><span data-stu-id="04b57-136">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="04b57-137">Оба `Integer` и `Long` расширяются до `Double` и только `Double`.</span><span class="sxs-lookup"><span data-stu-id="04b57-137">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="04b57-138">Поэтому `Double` является главным типом.</span><span class="sxs-lookup"><span data-stu-id="04b57-138">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="04b57-139">Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="04b57-139">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
-   <span data-ttu-id="04b57-140">Тело функции однострочный должно быть выражение, возвращающее значение, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="04b57-140">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="04b57-141">Существует не `Return` инструкции для однострочных функций.</span><span class="sxs-lookup"><span data-stu-id="04b57-141">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="04b57-142">Значение, возвращаемое функцией однострочный значение выражения в теле функции.</span><span class="sxs-lookup"><span data-stu-id="04b57-142">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
-   <span data-ttu-id="04b57-143">Тело подпрограммы однострочный должно быть одностроковый оператор.</span><span class="sxs-lookup"><span data-stu-id="04b57-143">The body of a single-line subroutine must be single-line statement.</span></span>  
  
-   <span data-ttu-id="04b57-144">Не включайте однострочных функций и подпрограмм `End Function` или `End Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="04b57-144">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="04b57-145">Тип данных параметра лямбда-выражения можно указать с помощью `As` ключевое слово или тип данных параметра может быть выведен.</span><span class="sxs-lookup"><span data-stu-id="04b57-145">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="04b57-146">Все параметры должно было быть задано, что необходимо определить типы данных или все.</span><span class="sxs-lookup"><span data-stu-id="04b57-146">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="04b57-147">`Optional`и `Paramarray` параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="04b57-147">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="04b57-148">Универсальные параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="04b57-148">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="04b57-149">Асинхронные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="04b57-149">Async Lambdas</span></span>  
 <span data-ttu-id="04b57-150">Можно легко создавать лямбда-выражения и операторы, включающие асинхронную обработку с помощью [Async](../../../../visual-basic/language-reference/modifiers/async.md) и [оператор Await](../../../../visual-basic/language-reference/operators/await-operator.md) ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="04b57-150">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="04b57-151">Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.</span><span class="sxs-lookup"><span data-stu-id="04b57-151">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
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
  
 <span data-ttu-id="04b57-152">Можно добавить тот же обработчик событий с помощью асинхронного лямбда-выражения в [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="04b57-152">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="04b57-153">Чтобы добавить этот обработчик, поставьте модификатор `Async` перед списком параметров лямбда-выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="04b57-153">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
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
  
 <span data-ttu-id="04b57-154">Дополнительные сведения о том, как создавать и использовать асинхронные методы см. в разделе [асинхронное программирование с использованием Async и Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="04b57-154">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
##  <span data-ttu-id="04b57-155"><a name="context"></a>Контекст</span><span class="sxs-lookup"><span data-stu-id="04b57-155"><a name="context"></a> Context</span></span>  
 <span data-ttu-id="04b57-156">Лямбда-выражение использует общий контекст с областью, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="04b57-156">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="04b57-157">Он имеет те же права доступа, что любой код, написанный в содержащей области.</span><span class="sxs-lookup"><span data-stu-id="04b57-157">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="04b57-158">Это включает доступ к переменным-членам, функции и подпрограммы, `Me`и параметры, так и локальные переменные в содержащей области.</span><span class="sxs-lookup"><span data-stu-id="04b57-158">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="04b57-159">Доступ к локальным переменным и параметрам в содержащей области можно продлить сверх времени существования этой области.</span><span class="sxs-lookup"><span data-stu-id="04b57-159">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="04b57-160">При условии, что делегат, относящийся к лямбда-выражение не доступен для сборки мусора, доступ к переменным среды исходного кода сохраняется.</span><span class="sxs-lookup"><span data-stu-id="04b57-160">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="04b57-161">В следующем примере переменная `target` является локальным для `makeTheGame`, метод которого лямбда-выражение `playTheGame` определен.</span><span class="sxs-lookup"><span data-stu-id="04b57-161">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="04b57-162">Обратите внимание, что возвращаемое лямбда-выражения, назначенные `takeAGuess` в `Main`, по-прежнему есть доступ к локальной переменной `target`.</span><span class="sxs-lookup"><span data-stu-id="04b57-162">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 <span data-ttu-id="04b57-163">[!code-vb[VbVbalrLambdas&#12;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-163">[!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span></span>  
  
 <span data-ttu-id="04b57-164">В следующем примере показано широкий спектр прав доступа вложенных лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="04b57-164">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="04b57-165">При выполнении возвращаемого лямбда-выражения из `Main` как `aDel`, он обращается к следующим элементам:</span><span class="sxs-lookup"><span data-stu-id="04b57-165">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
-   <span data-ttu-id="04b57-166">Поле класса, в котором он определен:`aField`</span><span class="sxs-lookup"><span data-stu-id="04b57-166">A field of the class in which it is defined: `aField`</span></span>  
  
-   <span data-ttu-id="04b57-167">Свойство класса, в котором он определен:`aProp`</span><span class="sxs-lookup"><span data-stu-id="04b57-167">A property of the class in which it is defined: `aProp`</span></span>  
  
-   <span data-ttu-id="04b57-168">Параметр метода `functionWithNestedLambda`, в котором он определен:`level1`</span><span class="sxs-lookup"><span data-stu-id="04b57-168">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
-   <span data-ttu-id="04b57-169">Локальная переменная `functionWithNestedLambda`:`localVar`</span><span class="sxs-lookup"><span data-stu-id="04b57-169">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
-   <span data-ttu-id="04b57-170">Параметр лямбда-выражения, в котором он является вложенным:`level2`</span><span class="sxs-lookup"><span data-stu-id="04b57-170">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 <span data-ttu-id="04b57-171">[!code-vb[VbVbalrLambdas №&9;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-171">[!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span></span>  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="04b57-172">Преобразование к типу делегата</span><span class="sxs-lookup"><span data-stu-id="04b57-172">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="04b57-173">Лямбда-выражения могут быть неявно преобразованы к совместимому типу делегата.</span><span class="sxs-lookup"><span data-stu-id="04b57-173">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="04b57-174">Сведения об общих требованиях для совместимости см. в разделе [неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="04b57-174">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="04b57-175">Например, в следующем примере кода показано лямбда-выражение, которое неявно преобразуется к `Func(Of Integer, Boolean)` или соответствующей сигнатуре делегата.</span><span class="sxs-lookup"><span data-stu-id="04b57-175">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="04b57-176">[!code-vb[VbVbalrLambdas №&16;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-176">[!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span></span>  
  
 <span data-ttu-id="04b57-177">В следующем примере кода показано лямбда-выражение, которое неявно преобразуется к `Sub(Of Double, String, Double)` или соответствующей сигнатуре делегата.</span><span class="sxs-lookup"><span data-stu-id="04b57-177">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="04b57-178">[!code-vb[VbVbalrLambdas&#23;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-178">[!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span></span>  
  
 <span data-ttu-id="04b57-179">При присваивании лямбда-выражений делегатам или передавать их в качестве аргументов для процедуры, можно указать имена параметров, но опустить их типы, позволяя принимать типы из делегата.</span><span class="sxs-lookup"><span data-stu-id="04b57-179">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="04b57-180">Примеры</span><span class="sxs-lookup"><span data-stu-id="04b57-180">Examples</span></span>  
  
-   <span data-ttu-id="04b57-181">В следующем примере определяется лямбда-выражение, возвращающее `True` Если аргументу типа nullable было присвоено значение, и `False` имеет значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="04b57-181">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     <span data-ttu-id="04b57-182">[!code-vb[VbVbalrLambdas&#4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-182">[!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span></span>  
  
-   <span data-ttu-id="04b57-183">В следующем примере определяется лямбда-выражение, возвращающее индекс последнего элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="04b57-183">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     <span data-ttu-id="04b57-184">[!code-vb[VbVbalrLambdas&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="04b57-184">[!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b57-185">См. также</span><span class="sxs-lookup"><span data-stu-id="04b57-185">See Also</span></span>  
 <span data-ttu-id="04b57-186">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="04b57-186">[Procedures](./index.md) </span></span>  
<span data-ttu-id="04b57-187"> [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="04b57-187"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="04b57-188"> [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="04b57-188"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="04b57-189"> [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="04b57-189"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="04b57-190"> [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="04b57-190"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="04b57-191"> [Обнуляемые типы значений](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span><span class="sxs-lookup"><span data-stu-id="04b57-191"> [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span></span>  
<span data-ttu-id="04b57-192"> [Практическое руководство: передача процедур другой процедуре в Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="04b57-192"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="04b57-193"> [Практическое руководство: создание лямбда-выражения](./how-to-create-a-lambda-expression.md) </span><span class="sxs-lookup"><span data-stu-id="04b57-193"> [How to: Create a Lambda Expression](./how-to-create-a-lambda-expression.md) </span></span>  
<span data-ttu-id="04b57-194"> [Неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="04b57-194"> [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span></span>

