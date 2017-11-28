---
title: "Интерпретация выражений"
description: "Сведения о том, как написать код для проверки структуры дерева выражений."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: adf73dde-1e52-4df3-9929-2e0670e28e16
ms.openlocfilehash: e7c5f7404546c6f3812fc5cc3d0320c77816634d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="interpreting-expressions"></a><span data-ttu-id="7a9a7-104">Интерпретация выражений</span><span class="sxs-lookup"><span data-stu-id="7a9a7-104">Interpreting Expressions</span></span>

[<span data-ttu-id="7a9a7-105">Предыдущий раздел — "Выполнение выражений"</span><span class="sxs-lookup"><span data-stu-id="7a9a7-105">Previous -- Executing Expressions</span></span>](expression-trees-execution.md)

<span data-ttu-id="7a9a7-106">Теперь напишем код для проверки структуры *дерева выражения*.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-106">Now, let's write some code to examine the structure of an *expression tree*.</span></span> <span data-ttu-id="7a9a7-107">Каждый узел в дереве выражения будет объектом класса, производного от класса `Expression`.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-107">Every node in an expression tree will be an object of a class that is derived from `Expression`.</span></span>

<span data-ttu-id="7a9a7-108">Такая структура позволяет посещать все узлы в дереве выражения в виде относительно простой рекурсивной операции.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-108">That design makes visiting all the nodes in an expression tree a relatively straight forward recursive operation.</span></span> <span data-ttu-id="7a9a7-109">Общая стратегия заключается в том, что нужно начать с корневого узла и определить его тип.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-109">The general strategy is to start at the root node and determine what kind of node it is.</span></span>

<span data-ttu-id="7a9a7-110">Если тип узла имеет дочерние элементы, их нужно посетить в рекурсивном режиме.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-110">If the node type has children, recursively visit the children.</span></span> <span data-ttu-id="7a9a7-111">На каждом дочернем узле повторите процесс, используемый на корневом узле: определите тип и, если тип имеет дочерние элементы, пройдите по каждому из них.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-111">At each child node, repeat the process used at the root node: determine the type, and if the type has children, visit each of the children.</span></span>

## <a name="examining-an-expression-with-no-children"></a><span data-ttu-id="7a9a7-112">Проверка выражения без дочерних узлов</span><span class="sxs-lookup"><span data-stu-id="7a9a7-112">Examining an Expression with No Children</span></span>
<span data-ttu-id="7a9a7-113">Начнем с посещения каждого узла в очень простом дереве выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-113">Let's start by visiting each node in a very simple expression tree.</span></span>
<span data-ttu-id="7a9a7-114">Ниже приведен код, который создает константное выражение, а затем проверяет его свойства:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-114">Here's the code that creates a constant expression and then examines its properties:</span></span>

```csharp
var constant = Expression.Constant(24, typeof(int));

Console.WriteLine($"This is a/an {constant.NodeType} expression type");
Console.WriteLine($"The type of the constant value is {constant.Type}");
Console.WriteLine($"The value of the constant value is {constant.Value}");
```

<span data-ttu-id="7a9a7-115">Будут выведены следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-115">This will print the following:</span></span>

```
This is an Constant expression type
The type of the constant value is System.Int32
The value of the constant value is 24
```

<span data-ttu-id="7a9a7-116">Теперь напишем код, который будет проверять это выражение и записывать некоторые важные свойства.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-116">Now, let's write the code that would examine this expression and write out some important properties about it.</span></span> <span data-ttu-id="7a9a7-117">Вот этот код:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-117">Here's that code:</span></span>

## <a name="examining-a-simple-addition-expression"></a><span data-ttu-id="7a9a7-118">Проверка простого выражения сложения</span><span class="sxs-lookup"><span data-stu-id="7a9a7-118">Examining a simple Addition Expression</span></span>

<span data-ttu-id="7a9a7-119">Начнем с примера сложения из вводной части к этому разделу.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-119">Let's start with the addition sample from the introduction to this section.</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

> <span data-ttu-id="7a9a7-120">Здесь не используется `var` для объявления этого дерева выражения, так как это невозможно, поскольку правая часть назначения неявно типизирована.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-120">I'm not using `var` to declare this expression tree, as it is not possible because the right-hand side of the assignment is implicitly typed.</span></span> <span data-ttu-id="7a9a7-121">Более подробные сведения см. [здесь](implicitly-typed-lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7a9a7-121">To understand this more deeply, read [here](implicitly-typed-lambda-expressions.md).</span></span>

<span data-ttu-id="7a9a7-122">`LambdaExpression` — это корневой узел.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-122">The root node is a `LambdaExpression`.</span></span> <span data-ttu-id="7a9a7-123">Для получения нужного кода в правой части оператора `=>` нужно найти один из дочерних элементов `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-123">In order to get the interesting code on the right hand side of the `=>` operator, you need to find one of the children of the `LambdaExpression`.</span></span> <span data-ttu-id="7a9a7-124">Это необходимо сделать со всеми выражениями в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-124">We'll do that with all the expressions in this section.</span></span> <span data-ttu-id="7a9a7-125">Благодаря родительскому узлу можно найти возвращаемый тип `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-125">The parent node does help us find the return type of the `LambdaExpression`.</span></span>

<span data-ttu-id="7a9a7-126">Чтобы проверить каждый узел в этом выражении, необходимо рекурсивно пройти через несколько узлов.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-126">To examine each node in this expression, we'll need to recursively visit a number of nodes.</span></span> <span data-ttu-id="7a9a7-127">Вот простая первая реализация:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-127">Here's a simple first implementation:</span></span>

```csharp
Expression<Func<int, int, int>> addition = (a, b) => a + b;

Console.WriteLine($"This expression is a {addition.NodeType} expression type");
Console.WriteLine($"The name of the lambda is {((addition.Name == null) ? "<null>" : addition.Name)}");
Console.WriteLine($"The return type is {addition.ReturnType.ToString()}");
Console.WriteLine($"The expression has {addition.Parameters.Count} arguments. They are:");
foreach(var argumentExpression in addition.Parameters)
{
    Console.WriteLine($"\tParameter Type: {argumentExpression.Type.ToString()}, Name: {argumentExpression.Name}");
}

var additionBody = (BinaryExpression)addition.Body;
Console.WriteLine($"The body is a {additionBody.NodeType} expression");
Console.WriteLine($"The left side is a {additionBody.Left.NodeType} expression");
var left = (ParameterExpression)additionBody.Left;
Console.WriteLine($"\tParameter Type: {left.Type.ToString()}, Name: {left.Name}");
Console.WriteLine($"The right side is a {additionBody.Right.NodeType} expression");
var right= (ParameterExpression)additionBody.Right;
Console.WriteLine($"\tParameter Type: {right.Type.ToString()}, Name: {right.Name}");
```

<span data-ttu-id="7a9a7-128">Результатом является следующее:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-128">This sample prints the following output:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 arguments. They are:
        Parameter Type: System.Int32, Name: a
        Parameter Type: System.Int32, Name: b
The body is a/an Add expression
The left side is a Parameter expression
        Parameter Type: System.Int32, Name: a
The right side is a Parameter expression
        Parameter Type: System.Int32, Name: b
```

<span data-ttu-id="7a9a7-129">В примере кода выше можно заметить много повторений.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-129">You'll notice a lot of repetition in the code sample above.</span></span>
<span data-ttu-id="7a9a7-130">Очистим код и создадим посетитель узлов выражения более общего назначения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-130">Let's clean that up and build a more general purpose expression node visitor.</span></span> <span data-ttu-id="7a9a7-131">Для этого нужно написать рекурсивный алгоритм.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-131">That's going to require us to write a recursive algorithm.</span></span> <span data-ttu-id="7a9a7-132">Любой узел может иметь тип с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-132">Any node could be of a type that might have children.</span></span>
<span data-ttu-id="7a9a7-133">Любой узел, имеющий дочерние элементы, требует посетить эти дочерние элементы и определить тип узла.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-133">Any node that has children requires us to visit those children and determine what that node is.</span></span> <span data-ttu-id="7a9a7-134">Вот очищенная версия, где используется рекурсия для посещения операций сложения:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-134">Here's the cleaned up version that utilizes recursion to visit the addition operations:</span></span>

```csharp
// Base Visitor class:
public abstract class Visitor
{
    private readonly Expression node;

    protected Visitor(Expression node)
    {
        this.node = node;
    }

    public abstract void Visit(string prefix);

    public ExpressionType NodeType => this.node.NodeType;
    public static Visitor CreateFromExpression(Expression node)
    {
        switch(node.NodeType)
        {
            case ExpressionType.Constant:
                return new ConstantVisitor((ConstantExpression)node);
            case ExpressionType.Lambda:
                return new LambdaVisitor((LambdaExpression)node);
            case ExpressionType.Parameter:
                return new ParameterVisitor((ParameterExpression)node);
            case ExpressionType.Add:
                return new BinaryVisitor((BinaryExpression)node);
            default:
                Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
                return default(Visitor);
        }
    }
}

// Lambda Visitor
public class LambdaVisitor : Visitor
{
    private readonly LambdaExpression node;
    public LambdaVisitor(LambdaExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression type");
        Console.WriteLine($"{prefix}The name of the lambda is {((node.Name == null) ? "<null>" : node.Name)}");
        Console.WriteLine($"{prefix}The return type is {node.ReturnType.ToString()}");
        Console.WriteLine($"{prefix}The expression has {node.Parameters.Count} argument(s). They are:");
        // Visit each parameter:
        foreach (var argumentExpression in node.Parameters)
        {
            var argumentVisitor = Visitor.CreateFromExpression(argumentExpression);
            argumentVisitor.Visit(prefix + "\t");
        }
        Console.WriteLine($"{prefix}The expression body is:");
        // Visit the body:
        var bodyVisitor = Visitor.CreateFromExpression(node.Body);
        bodyVisitor.Visit(prefix + "\t");
    }
}

// Binary Expression Visitor:
public class BinaryVisitor : Visitor
{
    private readonly BinaryExpression node;
    public BinaryVisitor(BinaryExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This binary expression is a {NodeType} expression");
        var left = Visitor.CreateFromExpression(node.Left);
        Console.WriteLine($"{prefix}The Left argument is:");
        left.Visit(prefix + "\t");
        var right = Visitor.CreateFromExpression(node.Right);
        Console.WriteLine($"{prefix}The Right argument is:");
        right.Visit(prefix + "\t");
    }
}

// Parameter visitor:
public class ParameterVisitor : Visitor
{
    private readonly ParameterExpression node;
    public ParameterVisitor(ParameterExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}Type: {node.Type.ToString()}, Name: {node.Name}, ByRef: {node.IsByRef}");
    }
}

// Constant visitor:
public class ConstantVisitor : Visitor
{
    private readonly ConstantExpression node;
    public ConstantVisitor(ConstantExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}The type of the constant value is {node.Type}");
        Console.WriteLine($"{prefix}The value of the constant value is {node.Value}");
    }
}
```

<span data-ttu-id="7a9a7-135">Этот алгоритм является основой для алгоритма, который может посещать любой произвольный `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-135">This algorithm is the basis of an algorithm that can visit any arbitrary `LambdaExpression`.</span></span> <span data-ttu-id="7a9a7-136">Существует множество брешей, а именно: созданный код выполняет поиск совсем небольшого примера возможных наборов узлов дерева выражения, который он может найти.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-136">There are a lot of holes, namely that the code I created only looks for a very small sample of the possible sets of expression tree nodes that it may encounter.</span></span> <span data-ttu-id="7a9a7-137">Однако в результатах вы по-прежнему сможете находить полезные данные.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-137">However, you can still learn quite a bit from what it produces.</span></span> <span data-ttu-id="7a9a7-138">(По умолчанию при обнаружении нового типа узла метод `Visitor.CreateFromExpression` выводит сообщение на консоль ошибок.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-138">(The default case in the `Visitor.CreateFromExpression` method prints a message to the error console when a new node type is encountered.</span></span> <span data-ttu-id="7a9a7-139">Таким образом, вы знаете, что нужно добавить новый тип выражения.)</span><span class="sxs-lookup"><span data-stu-id="7a9a7-139">That way, you know to add a new expression type.)</span></span>

<span data-ttu-id="7a9a7-140">При запуске этого посетителя в выражении сложения, показанном выше, вы получите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-140">When you run this visitor on the addition expression shown above, you get the following output:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: b, ByRef: False
```

<span data-ttu-id="7a9a7-141">Теперь, когда вы создали более общую реализацию посетителя, можно посещать и обрабатывать гораздо больше разных типов выражений.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-141">Now that you've built a more general visitor implementation, you can visit and process many more different types of expressions.</span></span>

## <a name="examining-an-addition-expression-with-many-levels"></a><span data-ttu-id="7a9a7-142">Проверка выражения сложения с несколькими уровнями</span><span class="sxs-lookup"><span data-stu-id="7a9a7-142">Examining an Addition Expression with Many Levels</span></span>

<span data-ttu-id="7a9a7-143">Рассмотрим более сложный пример, но по-прежнему ограничим типы узлов только сложением:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-143">Let's try a more complicated example, yet still limit the node types to addition only:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2 + 3 + 4;
```

<span data-ttu-id="7a9a7-144">Перед запуском примера в алгоритме посетителя попробуйте представить, какие выходные данные могут быть получены.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-144">Before you run this on the visitor algorithm, try a thought exercise to work out what the output might be.</span></span> <span data-ttu-id="7a9a7-145">Помните, что оператор `+` является *бинарным*: он должна иметь два дочерних элемента, представляющих левый и правый операнды.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-145">Remember that the `+` operator is a *binary operator*: it must have two children, representing the left and right operands.</span></span> <span data-ttu-id="7a9a7-146">Существует несколько правильных возможных способов построения дерева:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-146">There are several possible ways to construct a tree that could be correct:</span></span>

```csharp
Expression<Func<int>> sum1 = () => 1 + (2 + (3 + 4));
Expression<Func<int>> sum2 = () => ((1 + 2) + 3) + 4;

Expression<Func<int>> sum3 = () => (1 + 2) + (3 + 4);
Expression<Func<int>> sum4 = () => 1 + ((2 + 3) + 4);
Expression<Func<int>> sum5 = () => (1 + (2 + 3)) + 4;
```

<span data-ttu-id="7a9a7-147">Здесь выполнено разделение на два возможных ответа для выделения наиболее перспективного из них.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-147">You can see the separation into two possible answers to highlight the most promising.</span></span> <span data-ttu-id="7a9a7-148">Первый представляет *правоассоциативные* выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-148">The first represents *right associative* expressions.</span></span> <span data-ttu-id="7a9a7-149">Второй представляет *левоассоциативные* выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-149">The second represent *left associative* expressions.</span></span>
<span data-ttu-id="7a9a7-150">Преимущества этих двух форматов в том, что формат масштабируется до любого произвольного числа в выражениях сложения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-150">The advantage of both of those two formats is that the format scales to any arbitrary number of addition expressions.</span></span> 

<span data-ttu-id="7a9a7-151">При запуске этого выражения через посетитель вы увидите эти выходные данные, проверяющие, что выражение простого сложения является *левоассоциативным*.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-151">If you do run this expression through the visitor, you will see this this output, verifying that the simple addition expression is *left associative*.</span></span> 

<span data-ttu-id="7a9a7-152">Чтобы выполнить этот пример и увидеть полное дерево выражения, пришлось внести одно изменение в исходное дерево выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-152">In order to run this sample, and see the full expression tree, I had to make one change to the source expression tree.</span></span> <span data-ttu-id="7a9a7-153">Если дерево выражения содержит все константы, результирующее дерево просто содержит константное значение, равное `10`.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-153">When the expression tree contains all constants, the resulting tree simply contains the constant value of `10`.</span></span> <span data-ttu-id="7a9a7-154">Компилятор выполняет все операции сложения и сокращает выражение до его простейшей формы.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-154">The compiler performs all the addition and reduces the expression to its simplest form.</span></span> <span data-ttu-id="7a9a7-155">Для просмотра исходного дерева достаточно добавить одну переменную в выражение:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-155">Simply adding one variable in the expression is sufficient to see the original tree:</span></span>

```csharp
Expression<Func<int, int>> sum = (a) => 1 + a + 3 + 4;
```

<span data-ttu-id="7a9a7-156">Создайте посетитель для этой суммы и запустите его. После этого вы увидите эти выходные данные:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-156">Create a visitor for this sum and run the visitor you'll see this output:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This binary expression is a Add expression
                        The Left argument is:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                        The Right argument is:
                                This is an Parameter expression type
                                Type: System.Int32, Name: a, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
        The Right argument is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 4
```

<span data-ttu-id="7a9a7-157">С помощью кода посетителя можно также выполнить другие примеры и просмотреть, какое дерево он представляет.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-157">You can also run any of the other samples through the visitor code and see what tree it represents.</span></span> <span data-ttu-id="7a9a7-158">Ниже приведен пример выражения `sum3` выше (с дополнительным параметром, чтобы компилятор не смог вычислить константу):</span><span class="sxs-lookup"><span data-stu-id="7a9a7-158">Here's an example of the `sum3` expression above (with an additional parameter to prevent the compiler from computing the constant):</span></span>

```csharp
Expression<Func<int, int, int>> sum3 = (a, b) => (1 + a) + (3 + b);
```

<span data-ttu-id="7a9a7-159">Вот результат посетителя:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-159">Here's the output from the visitor:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 1
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: b, ByRef: False
```

<span data-ttu-id="7a9a7-160">Обратите внимание, что скобки не являются частью выходных данных.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-160">Notice that the parentheses are not part of the output.</span></span> <span data-ttu-id="7a9a7-161">В дереве выражения нет узлов, представляющих круглые скобки во входном выражении.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-161">There are no nodes in the expression tree that represent the parentheses in the input expression.</span></span> <span data-ttu-id="7a9a7-162">Структура дерева выражения содержит всю информацию, необходимую для сообщения о приоритете.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-162">The structure of the expression tree contains all the information necessary to communicate the precedence.</span></span>

## <a name="extending-from-this-sample"></a><span data-ttu-id="7a9a7-163">Расширение примера</span><span class="sxs-lookup"><span data-stu-id="7a9a7-163">Extending from this sample</span></span>

<span data-ttu-id="7a9a7-164">В этом примере используются только самые элементарные деревья выражений.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-164">The sample deals with only the most rudimentary expression trees.</span></span> <span data-ttu-id="7a9a7-165">Код, который вы видели в этом разделе, обрабатывает только целочисленные константы и двоичный оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-165">The code you've seen in this section only handles constant integers and the binary `+` operator.</span></span> <span data-ttu-id="7a9a7-166">Обратимся к последнему примеру и изменим посетитель для обработки более сложного выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-166">As a final sample, let's update the visitor to handle a more complicated expression.</span></span> <span data-ttu-id="7a9a7-167">Сделаем так, чтобы он работал следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-167">Let's make it work for this:</span></span>

```csharp
Expression<Func<int, int>> factorial = (n) =>
    n == 0 ? 
    1 : 
    Enumerable.Range(1, n).Aggregate((product, factor) => product * factor);
```

<span data-ttu-id="7a9a7-168">Этот код представляет одну из возможных реализаций для математической функции — *факториала*.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-168">This code represents one possible implementation for the mathematical *factorial* function.</span></span> <span data-ttu-id="7a9a7-169">В способе написания кода выделяется два ограничения для создания деревьев выражений путем присваивания лямбда-выражений выражениям.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-169">The way I've written this code highlights two limitiations of building expression trees by assigning lambda expressions to Expressions.</span></span> <span data-ttu-id="7a9a7-170">Во-первых, лямбды операторов не допускаются.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-170">First, statement lambdas are not allowed.</span></span> <span data-ttu-id="7a9a7-171">Это означает, что нельзя использовать циклы, блоки, операторы if/else и другие структуры управления, распространенные в C#.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-171">That means I can't use loops, blocks, if / else statements, and other control structures common in C#.</span></span> <span data-ttu-id="7a9a7-172">Можно использовать только выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-172">I'm limited to using expressions.</span></span> <span data-ttu-id="7a9a7-173">Во-вторых, нельзя выполнить рекурсивный вызов того же выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-173">Second, I can't recursively call the same expression.</span></span>
<span data-ttu-id="7a9a7-174">Это можно было бы сделать, если бы уже имелся делегат, но его нельзя вызвать в форме дерева выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-174">I could if it were already a delegate, but I can't call it in its expression tree form.</span></span> <span data-ttu-id="7a9a7-175">В разделе о [построении деревьев выражений](expression-trees-building.md) вы узнаете о том, как преодолеть эти ограничения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-175">In the section on [building expression trees](expression-trees-building.md) you'll learn techniques to overcome these limitations.</span></span>


<span data-ttu-id="7a9a7-176">В этом выражении вы встретите узлы всех указанных далее типов:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-176">In this expression, you'll encounter nodes of all these types:</span></span>
1. <span data-ttu-id="7a9a7-177">Equal (двоичное выражение)</span><span class="sxs-lookup"><span data-stu-id="7a9a7-177">Equal (binary expression)</span></span>
2. <span data-ttu-id="7a9a7-178">Multiply (двоичное выражение)</span><span class="sxs-lookup"><span data-stu-id="7a9a7-178">Multiply (binary expression)</span></span>
3. <span data-ttu-id="7a9a7-179">Conditional (выражение ?</span><span class="sxs-lookup"><span data-stu-id="7a9a7-179">Conditional (the ?</span></span> <span data-ttu-id="7a9a7-180">:)</span><span class="sxs-lookup"><span data-stu-id="7a9a7-180">: expression)</span></span>
4. <span data-ttu-id="7a9a7-181">Выражение вызова метода (вызов `Range()` и `Aggregate()`)</span><span class="sxs-lookup"><span data-stu-id="7a9a7-181">Method Call Expression (calling `Range()` and `Aggregate()`)</span></span>

<span data-ttu-id="7a9a7-182">Одним из способов изменения алгоритма посетителя является поддержка его выполнения и запись типа узла при каждом достижении предложения `default`.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-182">One way to modify the visitor algorithm is to keep executing it, and write the node type every time you reach your `default` clause.</span></span> <span data-ttu-id="7a9a7-183">После нескольких повторений вы просмотрите все возможные узлы.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-183">After a few iterations, you'll have seen each of the potential nodes.</span></span> <span data-ttu-id="7a9a7-184">Итак, у вас есть все, что нужно.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-184">Then, you have all you need.</span></span> <span data-ttu-id="7a9a7-185">Результат будет выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-185">The result would be something like this:</span></span>

```csharp
public static Visitor CreateFromExpression(Expression node)
{
    switch(node.NodeType)
    {
        case ExpressionType.Constant:
            return new ConstantVisitor((ConstantExpression)node);
        case ExpressionType.Lambda:
            return new LambdaVisitor((LambdaExpression)node);
        case ExpressionType.Parameter:
            return new ParameterVisitor((ParameterExpression)node);
        case ExpressionType.Add:
        case ExpressionType.Equal:
        case ExpressionType.Multiply:
            return new BinaryVisitor((BinaryExpression)node);
        case ExpressionType.Conditional:
            return new ConditionalVisitor((ConditionalExpression)node);
        case ExpressionType.Call:
            return new MethodCallVisitor((MethodCallExpression)node);
        default:
            Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
            return default(Visitor);
    }
}
```

<span data-ttu-id="7a9a7-186">ConditionalVisitor и MethodCallVisitor обрабатывают эти два узла:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-186">The ConditionalVisitor and MethodCallVisitor process those two nodes:</span></span>

```csharp
public class ConditionalVisitor : Visitor
{
    private readonly ConditionalExpression node;
    public ConditionalVisitor(ConditionalExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        var testVisitor = Visitor.CreateFromExpression(node.Test);
        Console.WriteLine($"{prefix}The Test for this expression is:");
        testVisitor.Visit(prefix + "\t");
        var trueVisitor = Visitor.CreateFromExpression(node.IfTrue);
        Console.WriteLine($"{prefix}The True clause for this expression is:");
        trueVisitor.Visit(prefix + "\t");
        var falseVisitor = Visitor.CreateFromExpression(node.IfFalse);
        Console.WriteLine($"{prefix}The False clause for this expression is:");
        falseVisitor.Visit(prefix + "\t");
    }
}

public class MethodCallVisitor : Visitor
{
    private readonly MethodCallExpression node;
    public MethodCallVisitor(MethodCallExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        if (node.Object == null)
            Console.WriteLine($"{prefix}This is a static method call");
        else
        {
            Console.WriteLine($"{prefix}The receiver (this) is:");
            var receiverVisitor = Visitor.CreateFromExpression(node.Object);
            receiverVisitor.Visit(prefix + "\t");
        }

        var methodInfo = node.Method;
        Console.WriteLine($"{prefix}The method name is {methodInfo.DeclaringType}.{methodInfo.Name}");
        // There is more here, like generic arguments, and so on.
        Console.WriteLine($"{prefix}The Arguments are:");
        foreach(var arg in node.Arguments)
        {
            var argVisitor = Visitor.CreateFromExpression(arg);
            argVisitor.Visit(prefix + "\t");
        }
    }
}
```

<span data-ttu-id="7a9a7-187">Будет получен следующий результат для дерева выражения:</span><span class="sxs-lookup"><span data-stu-id="7a9a7-187">And the output for the expression tree would be:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: n, ByRef: False
The expression body is:
        This expression is a Conditional expression
        The Test for this expression is:
                This binary expression is a Equal expression
                The Left argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: n, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 0
        The True clause for this expression is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 1
        The False clause for this expression is:
                This expression is a Call expression
                This is a static method call
                The method name is System.Linq.Enumerable.Aggregate
                The Arguments are:
                        This expression is a Call expression
                        This is a static method call
                        The method name is System.Linq.Enumerable.Range
                        The Arguments are:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                                This is an Parameter expression type
                                Type: System.Int32, Name: n, ByRef: False
                        This expression is a Lambda expression type
                        The name of the lambda is <null>
                        The return type is System.Int32
                        The expression has 2 arguments. They are:
                                This is an Parameter expression type
                                Type: System.Int32, Name: product, ByRef: False
                                This is an Parameter expression type
                                Type: System.Int32, Name: factor, ByRef: False
                        The expression body is:
                                This binary expression is a Multiply expression
                                The Left argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: product, ByRef: False
                                The Right argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: factor, ByRef: False
```

## <a name="extending-the-sample-library"></a><span data-ttu-id="7a9a7-188">Расширение примера библиотеки</span><span class="sxs-lookup"><span data-stu-id="7a9a7-188">Extending the Sample Library</span></span>

<span data-ttu-id="7a9a7-189">В примерах в этом разделе демонстрируются основные способы посещения и изучения узлов в дереве выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-189">The samples in this section show the core techniques to visit and examine nodes in an expression tree.</span></span> <span data-ttu-id="7a9a7-190">Вы узнали о целом ряде действий, которые может потребоваться выполнить для реализации основных задач, связанных с посещением узлов в дереве выражения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-190">I glossed over many actions you might need in order to concentrate on the core tasks of visiting and accessing nodes in an expression tree.</span></span> 

<span data-ttu-id="7a9a7-191">Во-первых, посетители могут обрабатывать только константы, которые являются целыми числами.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-191">First, the visitors only handle constants that are integers.</span></span> <span data-ttu-id="7a9a7-192">Константные значения могут иметь любой другой числовой тип, и язык C# поддерживает преобразования и повышения уровней этих типов.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-192">Constant values could be any other numeric type, and the C# language supports conversions and promotions between those types.</span></span> <span data-ttu-id="7a9a7-193">Все эти возможности будут отражены в более надежной версии этого кода.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-193">A more robust version of this code would mirror all those capabilities.</span></span>

<span data-ttu-id="7a9a7-194">Даже последний пример распознает подмножество возможных типов узлов.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-194">Even the last example recognizes a subset of the possible node types.</span></span>
<span data-ttu-id="7a9a7-195">В него можно по-прежнему вводить множество выражений, которые приведут к его сбою.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-195">You can still feed it many expressions that will cause it to fail.</span></span>
<span data-ttu-id="7a9a7-196">Полная реализация включена в стандартную библиотеку .NET с именем [ExpressionVisitor](/dotnet/core/api/System.Linq.Expressions.ExpressionVisitor) и может обрабатывать все возможные типы узлов.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-196">A full implementation is included in the .NET Standard under the name [ExpressionVisitor](/dotnet/core/api/System.Linq.Expressions.ExpressionVisitor) and can handle all the possible node types.</span></span>

<span data-ttu-id="7a9a7-197">И, наконец библиотека, которая использовалась в этой статье, была создана для демонстрации и обучения.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-197">Finally, the library I used in this article was built for demonstration and learning.</span></span> <span data-ttu-id="7a9a7-198">Она не оптимизирована.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-198">It's not optimized.</span></span> <span data-ttu-id="7a9a7-199">Она была написана для более четкого представления структур и для выделения методов, использовавшихся для посещения узлов и анализа их содержимого.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-199">I wrote it to make the structures used very clear, and to highlight the techniques used to visit the nodes and analyze what's there.</span></span> <span data-ttu-id="7a9a7-200">В рабочей реализации производительности будет уделено гораздо больше внимания.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-200">A production implementation would pay more attention to performance than I have.</span></span>

<span data-ttu-id="7a9a7-201">Даже с этими ограничениями вы будете обладать достаточными знаниями для написания алгоритмов по чтению и анализу деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="7a9a7-201">Even with those limitations, you should be well on your way to writing algorithms that read and understand expression trees.</span></span>

[<span data-ttu-id="7a9a7-202">Следующий раздел — "Построение выражений"</span><span class="sxs-lookup"><span data-stu-id="7a9a7-202">Next -- Building Expressions</span></span>](expression-trees-building.md)
