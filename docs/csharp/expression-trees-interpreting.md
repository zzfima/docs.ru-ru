---
title: Интерпретация выражений
description: Сведения о том, как написать код для проверки структуры дерева выражений.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: adf73dde-1e52-4df3-9929-2e0670e28e16
ms.openlocfilehash: 1283d7d957c72558652b96cb428efd0f071f0184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146012"
---
# <a name="interpreting-expressions"></a><span data-ttu-id="df4c6-103">Интерпретация выражений</span><span class="sxs-lookup"><span data-stu-id="df4c6-103">Interpreting Expressions</span></span>

[<span data-ttu-id="df4c6-104">Предыдущий раздел — "Выполнение выражений"</span><span class="sxs-lookup"><span data-stu-id="df4c6-104">Previous -- Executing Expressions</span></span>](expression-trees-execution.md)

<span data-ttu-id="df4c6-105">Теперь напишем код для проверки структуры *дерева выражения*.</span><span class="sxs-lookup"><span data-stu-id="df4c6-105">Now, let's write some code to examine the structure of an *expression tree*.</span></span> <span data-ttu-id="df4c6-106">Каждый узел в дереве выражения будет объектом класса, производного от класса `Expression`.</span><span class="sxs-lookup"><span data-stu-id="df4c6-106">Every node in an expression tree will be an object of a class that is derived from `Expression`.</span></span>

<span data-ttu-id="df4c6-107">Такая структура позволяет посещать все узлы в дереве выражения в виде относительно простой рекурсивной операции.</span><span class="sxs-lookup"><span data-stu-id="df4c6-107">That design makes visiting all the nodes in an expression tree a relatively straight forward recursive operation.</span></span> <span data-ttu-id="df4c6-108">Общая стратегия заключается в том, что нужно начать с корневого узла и определить его тип.</span><span class="sxs-lookup"><span data-stu-id="df4c6-108">The general strategy is to start at the root node and determine what kind of node it is.</span></span>

<span data-ttu-id="df4c6-109">Если тип узла имеет дочерние элементы, их нужно посетить в рекурсивном режиме.</span><span class="sxs-lookup"><span data-stu-id="df4c6-109">If the node type has children, recursively visit the children.</span></span> <span data-ttu-id="df4c6-110">На каждом дочернем узле повторите процесс, используемый на корневом узле: определите тип и, если тип имеет дочерние элементы, пройдите по каждому из них.</span><span class="sxs-lookup"><span data-stu-id="df4c6-110">At each child node, repeat the process used at the root node: determine the type, and if the type has children, visit each of the children.</span></span>

## <a name="examining-an-expression-with-no-children"></a><span data-ttu-id="df4c6-111">Проверка выражения без дочерних узлов</span><span class="sxs-lookup"><span data-stu-id="df4c6-111">Examining an Expression with No Children</span></span>
<span data-ttu-id="df4c6-112">Начнем с посещения каждого узла в очень простом дереве выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-112">Let's start by visiting each node in a very simple expression tree.</span></span>
<span data-ttu-id="df4c6-113">Ниже приведен код, который создает константное выражение, а затем проверяет его свойства:</span><span class="sxs-lookup"><span data-stu-id="df4c6-113">Here's the code that creates a constant expression and then examines its properties:</span></span>

```csharp
var constant = Expression.Constant(24, typeof(int));

Console.WriteLine($"This is a/an {constant.NodeType} expression type");
Console.WriteLine($"The type of the constant value is {constant.Type}");
Console.WriteLine($"The value of the constant value is {constant.Value}");
```

<span data-ttu-id="df4c6-114">Будут выведены следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="df4c6-114">This will print the following:</span></span>

```output
This is an Constant expression type
The type of the constant value is System.Int32
The value of the constant value is 24
```

<span data-ttu-id="df4c6-115">Теперь напишем код, который будет проверять это выражение и записывать некоторые важные свойства.</span><span class="sxs-lookup"><span data-stu-id="df4c6-115">Now, let's write the code that would examine this expression and write out some important properties about it.</span></span> <span data-ttu-id="df4c6-116">Вот этот код:</span><span class="sxs-lookup"><span data-stu-id="df4c6-116">Here's that code:</span></span>

## <a name="examining-a-simple-addition-expression"></a><span data-ttu-id="df4c6-117">Проверка простого выражения сложения</span><span class="sxs-lookup"><span data-stu-id="df4c6-117">Examining a simple Addition Expression</span></span>

<span data-ttu-id="df4c6-118">Начнем с примера сложения из вводной части к этому разделу.</span><span class="sxs-lookup"><span data-stu-id="df4c6-118">Let's start with the addition sample from the introduction to this section.</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

> <span data-ttu-id="df4c6-119">Здесь не используется `var` для объявления этого дерева выражения, так как это невозможно, поскольку правая часть назначения неявно типизирована.</span><span class="sxs-lookup"><span data-stu-id="df4c6-119">I'm not using `var` to declare this expression tree, as it is not possible because the right-hand side of the assignment is implicitly typed.</span></span> <span data-ttu-id="df4c6-120">Более подробные сведения см. [здесь](implicitly-typed-lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="df4c6-120">To understand this more deeply, read [here](implicitly-typed-lambda-expressions.md).</span></span>

<span data-ttu-id="df4c6-121">`LambdaExpression` — это корневой узел.</span><span class="sxs-lookup"><span data-stu-id="df4c6-121">The root node is a `LambdaExpression`.</span></span> <span data-ttu-id="df4c6-122">Для получения нужного кода в правой части оператора `=>` нужно найти один из дочерних элементов `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="df4c6-122">In order to get the interesting code on the right hand side of the `=>` operator, you need to find one of the children of the `LambdaExpression`.</span></span> <span data-ttu-id="df4c6-123">Это необходимо сделать со всеми выражениями в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="df4c6-123">We'll do that with all the expressions in this section.</span></span> <span data-ttu-id="df4c6-124">Благодаря родительскому узлу можно найти возвращаемый тип `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="df4c6-124">The parent node does help us find the return type of the `LambdaExpression`.</span></span>

<span data-ttu-id="df4c6-125">Чтобы проверить каждый узел в этом выражении, необходимо рекурсивно пройти через несколько узлов.</span><span class="sxs-lookup"><span data-stu-id="df4c6-125">To examine each node in this expression, we'll need to recursively visit a number of nodes.</span></span> <span data-ttu-id="df4c6-126">Вот простая первая реализация:</span><span class="sxs-lookup"><span data-stu-id="df4c6-126">Here's a simple first implementation:</span></span>

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

<span data-ttu-id="df4c6-127">Результатом является следующее:</span><span class="sxs-lookup"><span data-stu-id="df4c6-127">This sample prints the following output:</span></span>

```output
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

<span data-ttu-id="df4c6-128">В примере кода выше можно заметить много повторений.</span><span class="sxs-lookup"><span data-stu-id="df4c6-128">You'll notice a lot of repetition in the code sample above.</span></span>
<span data-ttu-id="df4c6-129">Очистим код и создадим посетитель узлов выражения более общего назначения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-129">Let's clean that up and build a more general purpose expression node visitor.</span></span> <span data-ttu-id="df4c6-130">Для этого нужно написать рекурсивный алгоритм.</span><span class="sxs-lookup"><span data-stu-id="df4c6-130">That's going to require us to write a recursive algorithm.</span></span> <span data-ttu-id="df4c6-131">Любой узел может иметь тип с дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="df4c6-131">Any node could be of a type that might have children.</span></span>
<span data-ttu-id="df4c6-132">Любой узел, имеющий дочерние элементы, требует посетить эти дочерние элементы и определить тип узла.</span><span class="sxs-lookup"><span data-stu-id="df4c6-132">Any node that has children requires us to visit those children and determine what that node is.</span></span> <span data-ttu-id="df4c6-133">Вот очищенная версия, где используется рекурсия для посещения операций сложения:</span><span class="sxs-lookup"><span data-stu-id="df4c6-133">Here's the cleaned up version that utilizes recursion to visit the addition operations:</span></span>

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

<span data-ttu-id="df4c6-134">Этот алгоритм является основой для алгоритма, который может посещать любой произвольный `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="df4c6-134">This algorithm is the basis of an algorithm that can visit any arbitrary `LambdaExpression`.</span></span> <span data-ttu-id="df4c6-135">Существует множество брешей, а именно: созданный код выполняет поиск совсем небольшого примера возможных наборов узлов дерева выражения, который он может найти.</span><span class="sxs-lookup"><span data-stu-id="df4c6-135">There are a lot of holes, namely that the code I created only looks for a very small sample of the possible sets of expression tree nodes that it may encounter.</span></span> <span data-ttu-id="df4c6-136">Однако в результатах вы по-прежнему сможете находить полезные данные.</span><span class="sxs-lookup"><span data-stu-id="df4c6-136">However, you can still learn quite a bit from what it produces.</span></span> <span data-ttu-id="df4c6-137">(По умолчанию при обнаружении нового типа узла метод `Visitor.CreateFromExpression` выводит сообщение на консоль ошибок.</span><span class="sxs-lookup"><span data-stu-id="df4c6-137">(The default case in the `Visitor.CreateFromExpression` method prints a message to the error console when a new node type is encountered.</span></span> <span data-ttu-id="df4c6-138">Таким образом, вы знаете, что нужно добавить новый тип выражения.)</span><span class="sxs-lookup"><span data-stu-id="df4c6-138">That way, you know to add a new expression type.)</span></span>

<span data-ttu-id="df4c6-139">При запуске этого посетителя в выражении сложения, показанном выше, вы получите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="df4c6-139">When you run this visitor on the addition expression shown above, you get the following output:</span></span>

```output
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

<span data-ttu-id="df4c6-140">Теперь, когда вы создали более общую реализацию посетителя, можно посещать и обрабатывать гораздо больше разных типов выражений.</span><span class="sxs-lookup"><span data-stu-id="df4c6-140">Now that you've built a more general visitor implementation, you can visit and process many more different types of expressions.</span></span>

## <a name="examining-an-addition-expression-with-many-levels"></a><span data-ttu-id="df4c6-141">Проверка выражения сложения с несколькими уровнями</span><span class="sxs-lookup"><span data-stu-id="df4c6-141">Examining an Addition Expression with Many Levels</span></span>

<span data-ttu-id="df4c6-142">Рассмотрим более сложный пример, но по-прежнему ограничим типы узлов только сложением:</span><span class="sxs-lookup"><span data-stu-id="df4c6-142">Let's try a more complicated example, yet still limit the node types to addition only:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2 + 3 + 4;
```

<span data-ttu-id="df4c6-143">Перед запуском примера в алгоритме посетителя попробуйте представить, какие выходные данные могут быть получены.</span><span class="sxs-lookup"><span data-stu-id="df4c6-143">Before you run this on the visitor algorithm, try a thought exercise to work out what the output might be.</span></span> <span data-ttu-id="df4c6-144">Помните, что оператор `+` является *бинарным*: он должна иметь два дочерних элемента, представляющих левый и правый операнды.</span><span class="sxs-lookup"><span data-stu-id="df4c6-144">Remember that the `+` operator is a *binary operator*: it must have two children, representing the left and right operands.</span></span> <span data-ttu-id="df4c6-145">Существует несколько правильных возможных способов построения дерева:</span><span class="sxs-lookup"><span data-stu-id="df4c6-145">There are several possible ways to construct a tree that could be correct:</span></span>

```csharp
Expression<Func<int>> sum1 = () => 1 + (2 + (3 + 4));
Expression<Func<int>> sum2 = () => ((1 + 2) + 3) + 4;

Expression<Func<int>> sum3 = () => (1 + 2) + (3 + 4);
Expression<Func<int>> sum4 = () => 1 + ((2 + 3) + 4);
Expression<Func<int>> sum5 = () => (1 + (2 + 3)) + 4;
```

<span data-ttu-id="df4c6-146">Здесь выполнено разделение на два возможных ответа для выделения наиболее перспективного из них.</span><span class="sxs-lookup"><span data-stu-id="df4c6-146">You can see the separation into two possible answers to highlight the most promising.</span></span> <span data-ttu-id="df4c6-147">Первый представляет *правоассоциативные* выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-147">The first represents *right associative* expressions.</span></span> <span data-ttu-id="df4c6-148">Второй представляет *левоассоциативные* выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-148">The second represent *left associative* expressions.</span></span>
<span data-ttu-id="df4c6-149">Преимущества этих двух форматов в том, что формат масштабируется до любого произвольного числа в выражениях сложения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-149">The advantage of both of those two formats is that the format scales to any arbitrary number of addition expressions.</span></span>

<span data-ttu-id="df4c6-150">При запуске этого выражения через посетитель вы увидите эти выходные данные, проверяющие, что выражение простого сложения является *левоассоциативным*.</span><span class="sxs-lookup"><span data-stu-id="df4c6-150">If you do run this expression through the visitor, you will see this this output, verifying that the simple addition expression is *left associative*.</span></span>

<span data-ttu-id="df4c6-151">Чтобы выполнить этот пример и увидеть полное дерево выражения, пришлось внести одно изменение в исходное дерево выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-151">In order to run this sample, and see the full expression tree, I had to make one change to the source expression tree.</span></span> <span data-ttu-id="df4c6-152">Если дерево выражения содержит все константы, результирующее дерево просто содержит константное значение, равное `10`.</span><span class="sxs-lookup"><span data-stu-id="df4c6-152">When the expression tree contains all constants, the resulting tree simply contains the constant value of `10`.</span></span> <span data-ttu-id="df4c6-153">Компилятор выполняет все операции сложения и сокращает выражение до его простейшей формы.</span><span class="sxs-lookup"><span data-stu-id="df4c6-153">The compiler performs all the addition and reduces the expression to its simplest form.</span></span> <span data-ttu-id="df4c6-154">Для просмотра исходного дерева достаточно добавить одну переменную в выражение:</span><span class="sxs-lookup"><span data-stu-id="df4c6-154">Simply adding one variable in the expression is sufficient to see the original tree:</span></span>

```csharp
Expression<Func<int, int>> sum = (a) => 1 + a + 3 + 4;
```

<span data-ttu-id="df4c6-155">Создайте посетитель для этой суммы и запустите его. После этого вы увидите эти выходные данные:</span><span class="sxs-lookup"><span data-stu-id="df4c6-155">Create a visitor for this sum and run the visitor you'll see this output:</span></span>

```output
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

<span data-ttu-id="df4c6-156">С помощью кода посетителя можно также выполнить другие примеры и просмотреть, какое дерево он представляет.</span><span class="sxs-lookup"><span data-stu-id="df4c6-156">You can also run any of the other samples through the visitor code and see what tree it represents.</span></span> <span data-ttu-id="df4c6-157">Ниже приведен пример выражения `sum3` выше (с дополнительным параметром, чтобы компилятор не смог вычислить константу):</span><span class="sxs-lookup"><span data-stu-id="df4c6-157">Here's an example of the `sum3` expression above (with an additional parameter to prevent the compiler from computing the constant):</span></span>

```csharp
Expression<Func<int, int, int>> sum3 = (a, b) => (1 + a) + (3 + b);
```

<span data-ttu-id="df4c6-158">Вот результат посетителя:</span><span class="sxs-lookup"><span data-stu-id="df4c6-158">Here's the output from the visitor:</span></span>

```output
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

<span data-ttu-id="df4c6-159">Обратите внимание, что скобки не являются частью выходных данных.</span><span class="sxs-lookup"><span data-stu-id="df4c6-159">Notice that the parentheses are not part of the output.</span></span> <span data-ttu-id="df4c6-160">В дереве выражения нет узлов, представляющих круглые скобки во входном выражении.</span><span class="sxs-lookup"><span data-stu-id="df4c6-160">There are no nodes in the expression tree that represent the parentheses in the input expression.</span></span> <span data-ttu-id="df4c6-161">Структура дерева выражения содержит всю информацию, необходимую для сообщения о приоритете.</span><span class="sxs-lookup"><span data-stu-id="df4c6-161">The structure of the expression tree contains all the information necessary to communicate the precedence.</span></span>

## <a name="extending-from-this-sample"></a><span data-ttu-id="df4c6-162">Расширение примера</span><span class="sxs-lookup"><span data-stu-id="df4c6-162">Extending from this sample</span></span>

<span data-ttu-id="df4c6-163">В этом примере используются только самые элементарные деревья выражений.</span><span class="sxs-lookup"><span data-stu-id="df4c6-163">The sample deals with only the most rudimentary expression trees.</span></span> <span data-ttu-id="df4c6-164">Код, который вы видели в этом разделе, обрабатывает только целочисленные константы и двоичный оператор `+`.</span><span class="sxs-lookup"><span data-stu-id="df4c6-164">The code you've seen in this section only handles constant integers and the binary `+` operator.</span></span> <span data-ttu-id="df4c6-165">Обратимся к последнему примеру и изменим посетитель для обработки более сложного выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-165">As a final sample, let's update the visitor to handle a more complicated expression.</span></span> <span data-ttu-id="df4c6-166">Сделаем так, чтобы он работал следующим образом:</span><span class="sxs-lookup"><span data-stu-id="df4c6-166">Let's make it work for this:</span></span>

```csharp
Expression<Func<int, int>> factorial = (n) =>
    n == 0 ?
    1 :
    Enumerable.Range(1, n).Aggregate((product, factor) => product * factor);
```

<span data-ttu-id="df4c6-167">Этот код представляет одну из возможных реализаций для математической функции — *факториала*.</span><span class="sxs-lookup"><span data-stu-id="df4c6-167">This code represents one possible implementation for the mathematical *factorial* function.</span></span> <span data-ttu-id="df4c6-168">В способе написания кода выделяется два ограничения для создания деревьев выражений путем присваивания лямбда-выражений выражениям.</span><span class="sxs-lookup"><span data-stu-id="df4c6-168">The way I've written this code highlights two limitations of building expression trees by assigning lambda expressions to Expressions.</span></span> <span data-ttu-id="df4c6-169">Во-первых, лямбды операторов не допускаются.</span><span class="sxs-lookup"><span data-stu-id="df4c6-169">First, statement lambdas are not allowed.</span></span> <span data-ttu-id="df4c6-170">Это означает, что нельзя использовать циклы, блоки, операторы if/else и другие структуры управления, распространенные в C#.</span><span class="sxs-lookup"><span data-stu-id="df4c6-170">That means I can't use loops, blocks, if / else statements, and other control structures common in C#.</span></span> <span data-ttu-id="df4c6-171">Можно использовать только выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-171">I'm limited to using expressions.</span></span> <span data-ttu-id="df4c6-172">Во-вторых, нельзя выполнить рекурсивный вызов того же выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-172">Second, I can't recursively call the same expression.</span></span>
<span data-ttu-id="df4c6-173">Это можно было бы сделать, если бы уже имелся делегат, но его нельзя вызвать в форме дерева выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-173">I could if it were already a delegate, but I can't call it in its expression tree form.</span></span> <span data-ttu-id="df4c6-174">В разделе о [построении деревьев выражений](expression-trees-building.md) вы узнаете о том, как преодолеть эти ограничения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-174">In the section on [building expression trees](expression-trees-building.md) you'll learn techniques to overcome these limitations.</span></span>

<span data-ttu-id="df4c6-175">В этом выражении вы встретите узлы всех указанных далее типов:</span><span class="sxs-lookup"><span data-stu-id="df4c6-175">In this expression, you'll encounter nodes of all these types:</span></span>

1. <span data-ttu-id="df4c6-176">Equal (двоичное выражение)</span><span class="sxs-lookup"><span data-stu-id="df4c6-176">Equal (binary expression)</span></span>
2. <span data-ttu-id="df4c6-177">Multiply (двоичное выражение)</span><span class="sxs-lookup"><span data-stu-id="df4c6-177">Multiply (binary expression)</span></span>
3. <span data-ttu-id="df4c6-178">Conditional (выражение ?</span><span class="sxs-lookup"><span data-stu-id="df4c6-178">Conditional (the ?</span></span> <span data-ttu-id="df4c6-179">:)</span><span class="sxs-lookup"><span data-stu-id="df4c6-179">: expression)</span></span>
4. <span data-ttu-id="df4c6-180">Выражение вызова метода (вызов `Range()` и `Aggregate()`)</span><span class="sxs-lookup"><span data-stu-id="df4c6-180">Method Call Expression (calling `Range()` and `Aggregate()`)</span></span>

<span data-ttu-id="df4c6-181">Одним из способов изменения алгоритма посетителя является поддержка его выполнения и запись типа узла при каждом достижении предложения `default`.</span><span class="sxs-lookup"><span data-stu-id="df4c6-181">One way to modify the visitor algorithm is to keep executing it, and write the node type every time you reach your `default` clause.</span></span> <span data-ttu-id="df4c6-182">После нескольких повторений вы просмотрите все возможные узлы.</span><span class="sxs-lookup"><span data-stu-id="df4c6-182">After a few iterations, you'll have seen each of the potential nodes.</span></span> <span data-ttu-id="df4c6-183">Итак, у вас есть все, что нужно.</span><span class="sxs-lookup"><span data-stu-id="df4c6-183">Then, you have all you need.</span></span> <span data-ttu-id="df4c6-184">Результат будет выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="df4c6-184">The result would be something like this:</span></span>

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

<span data-ttu-id="df4c6-185">ConditionalVisitor и MethodCallVisitor обрабатывают эти два узла:</span><span class="sxs-lookup"><span data-stu-id="df4c6-185">The ConditionalVisitor and MethodCallVisitor process those two nodes:</span></span>

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

<span data-ttu-id="df4c6-186">Будет получен следующий результат для дерева выражения:</span><span class="sxs-lookup"><span data-stu-id="df4c6-186">And the output for the expression tree would be:</span></span>

```output
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

## <a name="extending-the-sample-library"></a><span data-ttu-id="df4c6-187">Расширение примера библиотеки</span><span class="sxs-lookup"><span data-stu-id="df4c6-187">Extending the Sample Library</span></span>

<span data-ttu-id="df4c6-188">В примерах в этом разделе демонстрируются основные способы посещения и изучения узлов в дереве выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-188">The samples in this section show the core techniques to visit and examine nodes in an expression tree.</span></span> <span data-ttu-id="df4c6-189">Вы узнали о целом ряде действий, которые может потребоваться выполнить для реализации основных задач, связанных с посещением узлов в дереве выражения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-189">I glossed over many actions you might need in order to concentrate on the core tasks of visiting and accessing nodes in an expression tree.</span></span>

<span data-ttu-id="df4c6-190">Во-первых, посетители могут обрабатывать только константы, которые являются целыми числами.</span><span class="sxs-lookup"><span data-stu-id="df4c6-190">First, the visitors only handle constants that are integers.</span></span> <span data-ttu-id="df4c6-191">Константные значения могут иметь любой другой числовой тип, и язык C# поддерживает преобразования и повышения уровней этих типов.</span><span class="sxs-lookup"><span data-stu-id="df4c6-191">Constant values could be any other numeric type, and the C# language supports conversions and promotions between those types.</span></span> <span data-ttu-id="df4c6-192">Все эти возможности будут отражены в более надежной версии этого кода.</span><span class="sxs-lookup"><span data-stu-id="df4c6-192">A more robust version of this code would mirror all those capabilities.</span></span>

<span data-ttu-id="df4c6-193">Даже последний пример распознает подмножество возможных типов узлов.</span><span class="sxs-lookup"><span data-stu-id="df4c6-193">Even the last example recognizes a subset of the possible node types.</span></span>
<span data-ttu-id="df4c6-194">В него можно по-прежнему вводить множество выражений, которые приведут к его сбою.</span><span class="sxs-lookup"><span data-stu-id="df4c6-194">You can still feed it many expressions that will cause it to fail.</span></span>
<span data-ttu-id="df4c6-195">Полная реализация включена в стандартную библиотеку .NET с именем <xref:System.Linq.Expressions.ExpressionVisitor> и может обрабатывать все возможные типы узлов.</span><span class="sxs-lookup"><span data-stu-id="df4c6-195">A full implementation is included in the .NET Standard under the name <xref:System.Linq.Expressions.ExpressionVisitor> and can handle all the possible node types.</span></span>

<span data-ttu-id="df4c6-196">И, наконец библиотека, которая использовалась в этой статье, была создана для демонстрации и обучения.</span><span class="sxs-lookup"><span data-stu-id="df4c6-196">Finally, the library I used in this article was built for demonstration and learning.</span></span> <span data-ttu-id="df4c6-197">Она не оптимизирована.</span><span class="sxs-lookup"><span data-stu-id="df4c6-197">It's not optimized.</span></span> <span data-ttu-id="df4c6-198">Она была написана для более четкого представления структур и для выделения методов, использовавшихся для посещения узлов и анализа их содержимого.</span><span class="sxs-lookup"><span data-stu-id="df4c6-198">I wrote it to make the structures used very clear, and to highlight the techniques used to visit the nodes and analyze what's there.</span></span> <span data-ttu-id="df4c6-199">В рабочей реализации производительности будет уделено гораздо больше внимания.</span><span class="sxs-lookup"><span data-stu-id="df4c6-199">A production implementation would pay more attention to performance than I have.</span></span>

<span data-ttu-id="df4c6-200">Даже с этими ограничениями вы будете обладать достаточными знаниями для написания алгоритмов по чтению и анализу деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="df4c6-200">Even with those limitations, you should be well on your way to writing algorithms that read and understand expression trees.</span></span>

[<span data-ttu-id="df4c6-201">Следующий раздел — "Построение выражений"</span><span class="sxs-lookup"><span data-stu-id="df4c6-201">Next -- Building Expressions</span></span>](expression-trees-building.md)
