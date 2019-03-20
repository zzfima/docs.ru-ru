---
title: Лямбда-выражения (руководство по программированию на C#)
ms.custom: seodec18
ms.date: 03/14/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: dd9b77a90030a96d17104c8c0e48964b6a85d165
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2019
ms.locfileid: "58125737"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="473ad-102">Лямбда-выражения (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="473ad-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="473ad-103">*Лямбда-выражение* представляет собой блок кода (выражение или блок оператора), который рассматривается как объект.</span><span class="sxs-lookup"><span data-stu-id="473ad-103">A *lambda expression* is a block of code (an expression or a statement block) that is treated as an object.</span></span> <span data-ttu-id="473ad-104">Оно может передаваться в качестве аргумента в методы, а также возвращаться вызовами метода.</span><span class="sxs-lookup"><span data-stu-id="473ad-104">It can be passed as an argument to methods, and it can also be returned by method calls.</span></span> <span data-ttu-id="473ad-105">Лямбда-выражения широко используются для:</span><span class="sxs-lookup"><span data-stu-id="473ad-105">Lambda expressions are used extensively for:</span></span>

- <span data-ttu-id="473ad-106">передачи выполняемого кода в асинхронные методы, такие как <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>;</span><span class="sxs-lookup"><span data-stu-id="473ad-106">Passing the code that is to be executed to asynchronous methods, such as <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="473ad-107">написания [выражений запросов LINQ](../../linq/index.md);</span><span class="sxs-lookup"><span data-stu-id="473ad-107">Writing [LINQ query expressions](../../linq/index.md).</span></span>

- <span data-ttu-id="473ad-108">создания [деревьев выражений](../concepts/expression-trees/index.md).</span><span class="sxs-lookup"><span data-stu-id="473ad-108">Creating [expression trees](../concepts/expression-trees/index.md).</span></span>

<span data-ttu-id="473ad-109">Лямбда-выражения — это код, который может быть представлен как делегат или дерево выражений, которое компилируется в делегат.</span><span class="sxs-lookup"><span data-stu-id="473ad-109">Lambda expressions are code that can be represented either as a delegate, or as an expression tree that compiles to a delegate.</span></span> <span data-ttu-id="473ad-110">Конкретный тип делегата лямбда-выражения зависит от его параметров и возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="473ad-110">The specific delegate type of a lambda expression depends on its parameters and return value.</span></span> <span data-ttu-id="473ad-111">Лямбда-выражения, которые не возвращают значение, соответствуют конкретному делегату `Action` в зависимости от числа параметров.</span><span class="sxs-lookup"><span data-stu-id="473ad-111">Lambda expressions that don't return a value correspond to a specific `Action` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="473ad-112">Лямбда-выражения, которые возвращают значение, соответствуют конкретному делегату `Func` в зависимости от числа параметров.</span><span class="sxs-lookup"><span data-stu-id="473ad-112">Lambda expressions that return a value correspond to a specific `Func` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="473ad-113">Например, лямбда-выражение, которое имеет два параметра, но не возвращает значение, соответствует делегату <xref:System.Action%602>.</span><span class="sxs-lookup"><span data-stu-id="473ad-113">For example, a lambda expression that has two parameters but returns no value corresponds to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="473ad-114">Лямбда-выражение, которое имеет один параметр и возвращает значение, соответствует делегату <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="473ad-114">A lambda expression that has one parameter and returns a value corresponds to <xref:System.Func%602> delegate.</span></span>

<span data-ttu-id="473ad-115">Лямбда-выражение использует `=>`, [оператор объявления лямбда-выражения](../../language-reference/operators/lambda-operator.md), для отделения списка параметров лямбда-выражения от исполняемого кода.</span><span class="sxs-lookup"><span data-stu-id="473ad-115">A lambda expression uses `=>`, the [lambda declaration operator](../../language-reference/operators/lambda-operator.md), to separate the lambda's parameter list from its executable code.</span></span> <span data-ttu-id="473ad-116">Чтобы создать лямбда-выражение, необходимо указать входные параметры (если они есть) с левой стороны лямбда-оператора, и поместить блок выражений или операторов с другой стороны.</span><span class="sxs-lookup"><span data-stu-id="473ad-116">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator, and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="473ad-117">Например, однострочное лямбда-выражение `x => x * x` задает параметр с именем `x` и возвращает значение `x` в квадрате.</span><span class="sxs-lookup"><span data-stu-id="473ad-117">For example, the single-line lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="473ad-118">Можно назначить это выражение типу делегата, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="473ad-118">You can assign this expression to a delegate type, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="473ad-119">Кроме того, вы можете назначить лямбда-выражение в качестве типа дерева выражения:</span><span class="sxs-lookup"><span data-stu-id="473ad-119">You also can assign a lambda expression to an expression tree type:</span></span>

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="473ad-120">Можно также передать его непосредственно в качестве аргумента метода:</span><span class="sxs-lookup"><span data-stu-id="473ad-120">Or you can pass it directly as a method argument:</span></span>

[!code-csharp-interactive[lambda is argument](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="473ad-121">При использовании синтаксиса на основе методов для вызова метода <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> в классе <xref:System.Linq.Enumerable?displayProperty=nameWithType> (как это делается в LINQ to Objects и LINQ to XML) параметром является тип делегата <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="473ad-121">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class (as you do in LINQ to Objects and LINQ to XML) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="473ad-122">Лямбда-выражение — это наиболее удобный способ создания делегата.</span><span class="sxs-lookup"><span data-stu-id="473ad-122">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="473ad-123">При вызове метода <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> в классе <xref:System.Linq.Queryable?displayProperty=nameWithType> (как это делается в LINQ to SQL) типом параметра является тип дерева выражения [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span><span class="sxs-lookup"><span data-stu-id="473ad-123">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in LINQ to SQL) the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="473ad-124">Опять же, лямбда-выражения представляют собой самый быстрый способ построения дерева выражений.</span><span class="sxs-lookup"><span data-stu-id="473ad-124">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="473ad-125">Лямбда-выражения позволяют вызовам `Select` выглядеть одинаково, хотя на самом деле объект, созданный из лямбда-выражения, имеет другой тип.</span><span class="sxs-lookup"><span data-stu-id="473ad-125">The lambdas allow the `Select` calls to look similar although in fact the type of object created from the lambda is different.</span></span>

<span data-ttu-id="473ad-126">Все ограничения, применяемые к [анонимным методам](anonymous-methods.md), применяются также к лямбда-выражениям.</span><span class="sxs-lookup"><span data-stu-id="473ad-126">All restrictions that apply to [anonymous methods](anonymous-methods.md) also apply to lambda expressions.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="473ad-127">Выражения-лямбды</span><span class="sxs-lookup"><span data-stu-id="473ad-127">Expression lambdas</span></span>

<span data-ttu-id="473ad-128">Лямбда-выражение с выражением с правой стороны оператора `=>` называется *выражением лямбда*.</span><span class="sxs-lookup"><span data-stu-id="473ad-128">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="473ad-129">Выражения-лямбды широко используются при конструировании [деревьев выражений](../concepts/expression-trees/index.md).</span><span class="sxs-lookup"><span data-stu-id="473ad-129">Expression lambdas are used extensively in the construction of [expression trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="473ad-130">Выражения-лямбды возвращают результат выражения и принимают следующую основную форму.</span><span class="sxs-lookup"><span data-stu-id="473ad-130">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="473ad-131">Если лямбда-выражение имеет только один входной параметр, скобки можно не ставить; во всех остальных случаях они обязательны.</span><span class="sxs-lookup"><span data-stu-id="473ad-131">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span>

<span data-ttu-id="473ad-132">Нулевое количество входных параметры задается пустыми скобками:</span><span class="sxs-lookup"><span data-stu-id="473ad-132">Specify zero input parameters with empty parentheses:</span></span>  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

<span data-ttu-id="473ad-133">Два и более входных параметра разделяются запятыми и заключаются в скобки:</span><span class="sxs-lookup"><span data-stu-id="473ad-133">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

<span data-ttu-id="473ad-134">Иногда компилятору не удается определить входные типы.</span><span class="sxs-lookup"><span data-stu-id="473ad-134">Sometimes it's impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="473ad-135">Вы можете указать типы данных в явном виде, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="473ad-135">You can specify the types explicitly as shown in the following example:</span></span>

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

<span data-ttu-id="473ad-136">Для входных параметров все типы нужно задать либо в явном, либо в неявном виде. В противном случае компилятор выдает ошибку [CS0748](../../misc/cs0748.md).</span><span class="sxs-lookup"><span data-stu-id="473ad-136">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="473ad-137">Текст выражения лямбды может состоять из вызова метода.</span><span class="sxs-lookup"><span data-stu-id="473ad-137">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="473ad-138">Но при создании деревьев выражений, которые вычисляются вне контекста поддержки общеязыковой среды выполнения .NET, например в SQL Server, вызовы методов не следует использовать в лямбда-выражениях.</span><span class="sxs-lookup"><span data-stu-id="473ad-138">However, if you are creating expression trees that are evaluated outside the context of the .NET common language runtime, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="473ad-139">Эти методы не имеют смысла вне контекста среды CLR .NET.</span><span class="sxs-lookup"><span data-stu-id="473ad-139">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="473ad-140">Лямбды операторов</span><span class="sxs-lookup"><span data-stu-id="473ad-140">Statement lambdas</span></span>

<span data-ttu-id="473ad-141">Лямбда оператора напоминает выражение-лямбду, за исключением того, что оператор (или операторы) заключается в фигурные скобки:</span><span class="sxs-lookup"><span data-stu-id="473ad-141">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp  
(input-parameters) => { statement; }
```

<span data-ttu-id="473ad-142">Тело лямбды оператора может состоять из любого количества операторов; однако на практике обычно используется не более двух-трех.</span><span class="sxs-lookup"><span data-stu-id="473ad-142">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

<span data-ttu-id="473ad-143">Лямбды операторов, как и анонимные методы, не могут использоваться для создания деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="473ad-143">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>
  
## <a name="async-lambdas"></a><span data-ttu-id="473ad-144">Асинхронные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="473ad-144">Async lambdas</span></span>

<span data-ttu-id="473ad-145">С помощью ключевых слов [async](../../language-reference/keywords/async.md) и [await](../../language-reference/keywords/await.md) можно легко создавать лямбда-выражения и операторы, включающие асинхронную обработку.</span><span class="sxs-lookup"><span data-stu-id="473ad-145">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../language-reference/keywords/async.md) and [await](../../language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="473ad-146">Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.</span><span class="sxs-lookup"><span data-stu-id="473ad-146">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="473ad-147">Такой же обработчик событий можно добавить с помощью асинхронного лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="473ad-147">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="473ad-148">Чтобы добавить этот обработчик, поставьте модификатор `async` перед списком параметров лямбда-выражения, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="473ad-148">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="473ad-149">Дополнительные сведения о создании и использовании асинхронных методов см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="473ad-149">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="473ad-150">Лямбда-выражения и кортежи</span><span class="sxs-lookup"><span data-stu-id="473ad-150">Lambda expressions and tuples</span></span>

<span data-ttu-id="473ad-151">В C# 7.0 представлена встроенная поддержка [кортежей](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="473ad-151">Starting with C# 7.0, the C# language provides built-in support for [tuples](../../tuples.md).</span></span> <span data-ttu-id="473ad-152">Кортеж можно ввести в качестве аргумента лямбда-выражения, и лямбда-выражение также может возвращать кортеж.</span><span class="sxs-lookup"><span data-stu-id="473ad-152">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="473ad-153">В некоторых случаях компилятор C# использует определение типа для определения типов компонентов кортежа.</span><span class="sxs-lookup"><span data-stu-id="473ad-153">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="473ad-154">Кортеж определяется путем заключения в скобки списка его компонентов с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="473ad-154">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="473ad-155">В следующем примере кортеж с тремя компонентами используется для передачи последовательности чисел в лямбда-выражение. Оно удваивает каждое значение и возвращает кортеж с тремя компонентами, содержащий результат операций умножения.</span><span class="sxs-lookup"><span data-stu-id="473ad-155">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="473ad-156">Как правило, поля кортежи именуются как `Item1`, `Item2` и т. д. Тем не менее кортеж с именованными компонентами можно определить, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="473ad-156">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="473ad-157">См. дополнительные сведения о [типах кортежей в C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="473ad-157">For more information about C# tuples, see [C# tuple types](../../tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="473ad-158">Лямбда-выражения со стандартными операторами запросов</span><span class="sxs-lookup"><span data-stu-id="473ad-158">Lambdas with the standard query operators</span></span>

<span data-ttu-id="473ad-159">В LINQ to Objects, наряду с другими реализациями, есть входной параметр, тип которого принадлежит к семейству универсальных делегатов <xref:System.Func%601>.</span><span class="sxs-lookup"><span data-stu-id="473ad-159">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="473ad-160">Эти делегаты используют параметры типа для определения количества и типов входных параметров, а также тип возвращаемого значения делегата.</span><span class="sxs-lookup"><span data-stu-id="473ad-160">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="473ad-161">Делегаты`Func` очень полезны для инкапсуляции пользовательских выражений, которые применяются к каждому элементу в наборе исходных данных.</span><span class="sxs-lookup"><span data-stu-id="473ad-161">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="473ad-162">В качестве примера рассмотрим следующий тип делегата <xref:System.Func%602>:</span><span class="sxs-lookup"><span data-stu-id="473ad-162">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="473ad-163">Экземпляр этого делегата можно создать как `Func<int, bool>`, где `int` — входной параметр, а `bool` — возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="473ad-163">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="473ad-164">Возвращаемое значение всегда указывается в последнем параметре типа.</span><span class="sxs-lookup"><span data-stu-id="473ad-164">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="473ad-165">Например, `Func<int, string, bool>` определяет делегат с двумя входными параметрами, `int` и `string`, и типом возвращаемого значения `bool`.</span><span class="sxs-lookup"><span data-stu-id="473ad-165">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="473ad-166">Следующий делегат `Func` при вызове возвращает логическое значение, которое показывает, равен ли входной параметр 5:</span><span class="sxs-lookup"><span data-stu-id="473ad-166">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="473ad-167">Лямбда-выражения также можно использовать, когда аргумент имеет тип <xref:System.Linq.Expressions.Expression%601>, например в стандартных операторах запросов, которые определены в типе <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="473ad-167">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="473ad-168">При указании аргумента <xref:System.Linq.Expressions.Expression%601> лямбда-выражение компилируется в дерево выражения.</span><span class="sxs-lookup"><span data-stu-id="473ad-168">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="473ad-169">В этом примере используется стандартный оператор запроса <xref:System.Linq.Enumerable.Count%2A>:</span><span class="sxs-lookup"><span data-stu-id="473ad-169">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="473ad-170">Компилятор может вывести тип входного параметра ввода; но его также можно определить явным образом.</span><span class="sxs-lookup"><span data-stu-id="473ad-170">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="473ad-171">Данное лямбда-выражение подсчитывает указанные целые значения (`n`), которые при делении на два дают остаток 1.</span><span class="sxs-lookup"><span data-stu-id="473ad-171">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="473ad-172">В следующем примере кода показано, как создать последовательность, которая содержит все элементы массива `numbers`, предшествующие 9, так как это первое число последовательности, не удовлетворяющее условию:</span><span class="sxs-lookup"><span data-stu-id="473ad-172">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="473ad-173">В следующем примере показано, как указать несколько входных параметров путем их заключения в скобки.</span><span class="sxs-lookup"><span data-stu-id="473ad-173">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="473ad-174">Этот метод возвращает все элементы в массиве `numbers` до того числа, значение которого меньше его порядкового номера в массиве:</span><span class="sxs-lookup"><span data-stu-id="473ad-174">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="473ad-175">Определение типа в лямбда-выражениях</span><span class="sxs-lookup"><span data-stu-id="473ad-175">Type inference in lambda expressions</span></span>

<span data-ttu-id="473ad-176">При написании лямбда-выражений обычно не требуется указывать тип входных параметров, так как компилятор может выводить этот тип на основе тела лямбда-выражения, типов параметров и других факторов, как описано в спецификации языка C#.</span><span class="sxs-lookup"><span data-stu-id="473ad-176">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="473ad-177">Для большинства стандартных операторов запросов первой входное значение имеет тип элементов в исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="473ad-177">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="473ad-178">При запросе `IEnumerable<Customer>` входная переменная считается объектом `Customer`, а это означает, что у вас есть доступ к его методам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="473ad-178">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="473ad-179">Общие правила определения типа для лямбда-выражений формулируются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="473ad-179">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="473ad-180">лямбда-выражение должно содержать то же число параметров, что и тип делегата;</span><span class="sxs-lookup"><span data-stu-id="473ad-180">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="473ad-181">каждый входной параметр в лямбда-выражении должен быть неявно преобразуемым в соответствующий параметр делегата;</span><span class="sxs-lookup"><span data-stu-id="473ad-181">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="473ad-182">возвращаемое значение лямбда-выражения (если таковое имеется) должно быть неявно преобразуемым в возвращаемый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="473ad-182">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="473ad-183">Обратите внимание, что у лямбда-выражений нет типа, так как в системе общих типов изначально отсутствует такое понятие, как лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="473ad-183">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="473ad-184">Но применительно к лямбда-выражениям иногда бывает удобно оперировать понятием типа.</span><span class="sxs-lookup"><span data-stu-id="473ad-184">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="473ad-185">При этом под типом понимается тип делегата или тип <xref:System.Linq.Expressions.Expression> , в который преобразуется лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="473ad-185">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="473ad-186">Область действия переменной в лямбда-выражениях</span><span class="sxs-lookup"><span data-stu-id="473ad-186">Variable scope in lambda expressions</span></span>

<span data-ttu-id="473ad-187">Лямбда-выражения могут ссылаться на *внешние переменные* (см. раздел [Анонимные методы](anonymous-methods.md)), находящиеся в области метода, в котором определено лямбда-выражение, или области типа, который содержит лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="473ad-187">Lambdas can refer to *outer variables* (see [Anonymous methods](anonymous-methods.md)) that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="473ad-188">Переменные, полученные таким способом, сохраняются для использования в лямбда-выражениях, даже если бы в ином случае они оказались за границами области действия и уничтожились сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="473ad-188">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="473ad-189">Внешняя переменная должна быть определенным образом присвоена, прежде чем она сможет использоваться в лямбда-выражениях.</span><span class="sxs-lookup"><span data-stu-id="473ad-189">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="473ad-190">В следующем примере демонстрируются эти правила.</span><span class="sxs-lookup"><span data-stu-id="473ad-190">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="473ad-191">Следующие правила применимы к области действия переменной в лямбда-выражениях.</span><span class="sxs-lookup"><span data-stu-id="473ad-191">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="473ad-192">Захваченная переменная не будет уничтожена сборщиком мусора до тех пор, пока делегат, который на нее ссылается, не перейдет в статус подлежащего уничтожению при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="473ad-192">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="473ad-193">Переменные, представленные в лямбда-выражении, невидимы в заключающем методе.</span><span class="sxs-lookup"><span data-stu-id="473ad-193">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="473ad-194">Лямбда-выражение не может непосредственно захватывать параметры [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) или [out](../../language-reference/keywords/out-parameter-modifier.md) из заключающего метода.</span><span class="sxs-lookup"><span data-stu-id="473ad-194">A lambda expression cannot directly capture an [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="473ad-195">Оператор [return](../../language-reference/keywords/return.md) в лямбда-выражении не вызывает возврат значения заключающим методом.</span><span class="sxs-lookup"><span data-stu-id="473ad-195">A [return](../../language-reference/keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="473ad-196">Лямбда-выражение не может содержать операторы [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md) или [continue](../../language-reference/keywords/continue.md), если целевой объект этого оператора перехода находится за пределами блока лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="473ad-196">A lambda expression cannot contain a [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md), or [continue](../../language-reference/keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="473ad-197">Если целевой объект находится внутри блока, использование оператора перехода за пределами лямбда-выражения также будет ошибкой.</span><span class="sxs-lookup"><span data-stu-id="473ad-197">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="473ad-198">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="473ad-198">C# language specification</span></span>

<span data-ttu-id="473ad-199">Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="473ad-199">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="featured-book-chapter"></a><span data-ttu-id="473ad-200">Важная глава книги</span><span class="sxs-lookup"><span data-stu-id="473ad-200">Featured book chapter</span></span>

<span data-ttu-id="473ad-201">[Делегаты, события и лямбда-выражения](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) в [справочном руководстве по C# 3.0, третье издание. Более 250 решений для программистов на C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="473ad-201">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="473ad-202">См. также</span><span class="sxs-lookup"><span data-stu-id="473ad-202">See also</span></span>

- [<span data-ttu-id="473ad-203">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="473ad-203">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="473ad-204">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="473ad-204">LINQ (Language-Integrated Query)</span></span>](../concepts/linq/index.md)
- [<span data-ttu-id="473ad-205">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="473ad-205">Anonymous Methods</span></span>](anonymous-methods.md)
- [<span data-ttu-id="473ad-206">Деревья выражений</span><span class="sxs-lookup"><span data-stu-id="473ad-206">Expression Trees</span></span>](../concepts/expression-trees/index.md)
- [<span data-ttu-id="473ad-207">Локальные функции в сравнении с лямбда-выражениями</span><span class="sxs-lookup"><span data-stu-id="473ad-207">Local functions compared to lambda expressions</span></span>](../../local-functions-vs-lambdas.md)
- [<span data-ttu-id="473ad-208">Неявно типизированные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="473ad-208">Implicitly typed lambda expressions</span></span>](../../implicitly-typed-lambda-expressions.md)
- [<span data-ttu-id="473ad-209">Примеры C# в Visual Studio 2008 (см. файлы примеров запросов LINQ и программу XQuery)</span><span class="sxs-lookup"><span data-stu-id="473ad-209">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="473ad-210">Рекурсивные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="473ad-210">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
