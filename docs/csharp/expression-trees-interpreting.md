---
title: Интерпретация выражений
description: Сведения о том, как написать код для проверки структуры дерева выражений.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: adf73dde-1e52-4df3-9929-2e0670e28e16
ms.openlocfilehash: 34434a633d866b82da3da713aaecc218c7d35124
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036900"
---
# <a name="interpreting-expressions"></a>Интерпретация выражений

[Предыдущий раздел — "Выполнение выражений"](expression-trees-execution.md)

Теперь напишем код для проверки структуры *дерева выражения*. Каждый узел в дереве выражения будет объектом класса, производного от класса `Expression`.

Такая структура позволяет посещать все узлы в дереве выражения в виде относительно простой рекурсивной операции. Общая стратегия заключается в том, что нужно начать с корневого узла и определить его тип.

Если тип узла имеет дочерние элементы, их нужно посетить в рекурсивном режиме. На каждом дочернем узле повторите процесс, используемый на корневом узле: определите тип и, если тип имеет дочерние элементы, пройдите по каждому из них.

## <a name="examining-an-expression-with-no-children"></a>Проверка выражения без дочерних узлов
Начнем с посещения каждого узла в очень простом дереве выражения.
Ниже приведен код, который создает константное выражение, а затем проверяет его свойства:

```csharp
var constant = Expression.Constant(24, typeof(int));

Console.WriteLine($"This is a/an {constant.NodeType} expression type");
Console.WriteLine($"The type of the constant value is {constant.Type}");
Console.WriteLine($"The value of the constant value is {constant.Value}");
```

Будут выведены следующие результаты:

```output
This is an Constant expression type
The type of the constant value is System.Int32
The value of the constant value is 24
```

Теперь напишем код, который будет проверять это выражение и записывать некоторые важные свойства. Вот этот код:

## <a name="examining-a-simple-addition-expression"></a>Проверка простого выражения сложения

Начнем с примера сложения из вводной части к этому разделу.

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

> Здесь не используется `var` для объявления этого дерева выражения, так как это невозможно, поскольку правая часть назначения неявно типизирована. Более подробные сведения см. [здесь](implicitly-typed-lambda-expressions.md).

`LambdaExpression` — это корневой узел. Для получения нужного кода в правой части оператора `=>` нужно найти один из дочерних элементов `LambdaExpression`. Это необходимо сделать со всеми выражениями в этом разделе. Благодаря родительскому узлу можно найти возвращаемый тип `LambdaExpression`.

Чтобы проверить каждый узел в этом выражении, необходимо рекурсивно пройти через несколько узлов. Вот простая первая реализация:

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

Результатом является следующее:

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

В примере кода выше можно заметить много повторений.
Очистим код и создадим посетитель узлов выражения более общего назначения. Для этого нужно написать рекурсивный алгоритм. Любой узел может иметь тип с дочерними элементами.
Любой узел, имеющий дочерние элементы, требует посетить эти дочерние элементы и определить тип узла. Вот очищенная версия, где используется рекурсия для посещения операций сложения:

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

Этот алгоритм является основой для алгоритма, который может посещать любой произвольный `LambdaExpression`. Существует множество брешей, а именно: созданный код выполняет поиск совсем небольшого примера возможных наборов узлов дерева выражения, который он может найти. Однако в результатах вы по-прежнему сможете находить полезные данные. (По умолчанию при обнаружении нового типа узла метод `Visitor.CreateFromExpression` выводит сообщение на консоль ошибок. Таким образом, вы знаете, что нужно добавить новый тип выражения.)

При запуске этого посетителя в выражении сложения, показанном выше, вы получите следующие выходные данные:

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

Теперь, когда вы создали более общую реализацию посетителя, можно посещать и обрабатывать гораздо больше разных типов выражений.

## <a name="examining-an-addition-expression-with-many-levels"></a>Проверка выражения сложения с несколькими уровнями

Рассмотрим более сложный пример, но по-прежнему ограничим типы узлов только сложением:

```csharp
Expression<Func<int>> sum = () => 1 + 2 + 3 + 4;
```

Перед запуском примера в алгоритме посетителя попробуйте представить, какие выходные данные могут быть получены. Помните, что оператор `+` является *бинарным*: он должна иметь два дочерних элемента, представляющих левый и правый операнды. Существует несколько правильных возможных способов построения дерева:

```csharp
Expression<Func<int>> sum1 = () => 1 + (2 + (3 + 4));
Expression<Func<int>> sum2 = () => ((1 + 2) + 3) + 4;

Expression<Func<int>> sum3 = () => (1 + 2) + (3 + 4);
Expression<Func<int>> sum4 = () => 1 + ((2 + 3) + 4);
Expression<Func<int>> sum5 = () => (1 + (2 + 3)) + 4;
```

Здесь выполнено разделение на два возможных ответа для выделения наиболее перспективного из них. Первый представляет *правоассоциативные* выражения. Второй представляет *левоассоциативные* выражения.
Преимущества этих двух форматов в том, что формат масштабируется до любого произвольного числа в выражениях сложения. 

При запуске этого выражения через посетитель вы увидите эти выходные данные, проверяющие, что выражение простого сложения является *левоассоциативным*. 

Чтобы выполнить этот пример и увидеть полное дерево выражения, пришлось внести одно изменение в исходное дерево выражения. Если дерево выражения содержит все константы, результирующее дерево просто содержит константное значение, равное `10`. Компилятор выполняет все операции сложения и сокращает выражение до его простейшей формы. Для просмотра исходного дерева достаточно добавить одну переменную в выражение:

```csharp
Expression<Func<int, int>> sum = (a) => 1 + a + 3 + 4;
```

Создайте посетитель для этой суммы и запустите его. После этого вы увидите эти выходные данные:

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

С помощью кода посетителя можно также выполнить другие примеры и просмотреть, какое дерево он представляет. Ниже приведен пример выражения `sum3` выше (с дополнительным параметром, чтобы компилятор не смог вычислить константу):

```csharp
Expression<Func<int, int, int>> sum3 = (a, b) => (1 + a) + (3 + b);
```

Вот результат посетителя:

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

Обратите внимание, что скобки не являются частью выходных данных. В дереве выражения нет узлов, представляющих круглые скобки во входном выражении. Структура дерева выражения содержит всю информацию, необходимую для сообщения о приоритете.

## <a name="extending-from-this-sample"></a>Расширение примера

В этом примере используются только самые элементарные деревья выражений. Код, который вы видели в этом разделе, обрабатывает только целочисленные константы и двоичный оператор `+`. Обратимся к последнему примеру и изменим посетитель для обработки более сложного выражения. Сделаем так, чтобы он работал следующим образом:

```csharp
Expression<Func<int, int>> factorial = (n) =>
    n == 0 ? 
    1 : 
    Enumerable.Range(1, n).Aggregate((product, factor) => product * factor);
```

Этот код представляет одну из возможных реализаций для математической функции — *факториала*. В способе написания кода выделяется два ограничения для создания деревьев выражений путем присваивания лямбда-выражений выражениям. Во-первых, лямбды операторов не допускаются. Это означает, что нельзя использовать циклы, блоки, операторы if/else и другие структуры управления, распространенные в C#. Можно использовать только выражения. Во-вторых, нельзя выполнить рекурсивный вызов того же выражения.
Это можно было бы сделать, если бы уже имелся делегат, но его нельзя вызвать в форме дерева выражения. В разделе о [построении деревьев выражений](expression-trees-building.md) вы узнаете о том, как преодолеть эти ограничения.

В этом выражении вы встретите узлы всех указанных далее типов:

1. Equal (двоичное выражение)
2. Multiply (двоичное выражение)
3. Conditional (выражение ? :)
4. Выражение вызова метода (вызов `Range()` и `Aggregate()`)

Одним из способов изменения алгоритма посетителя является поддержка его выполнения и запись типа узла при каждом достижении предложения `default`. После нескольких повторений вы просмотрите все возможные узлы. Итак, у вас есть все, что нужно. Результат будет выглядеть примерно следующим образом:

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

ConditionalVisitor и MethodCallVisitor обрабатывают эти два узла:

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

Будет получен следующий результат для дерева выражения:

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

## <a name="extending-the-sample-library"></a>Расширение примера библиотеки

В примерах в этом разделе демонстрируются основные способы посещения и изучения узлов в дереве выражения. Вы узнали о целом ряде действий, которые может потребоваться выполнить для реализации основных задач, связанных с посещением узлов в дереве выражения. 

Во-первых, посетители могут обрабатывать только константы, которые являются целыми числами. Константные значения могут иметь любой другой числовой тип, и язык C# поддерживает преобразования и повышения уровней этих типов. Все эти возможности будут отражены в более надежной версии этого кода.

Даже последний пример распознает подмножество возможных типов узлов.
В него можно по-прежнему вводить множество выражений, которые приведут к его сбою.
Полная реализация включена в стандартную библиотеку .NET с именем <xref:System.Linq.Expressions.ExpressionVisitor> и может обрабатывать все возможные типы узлов.

И, наконец библиотека, которая использовалась в этой статье, была создана для демонстрации и обучения. Она не оптимизирована. Она была написана для более четкого представления структур и для выделения методов, использовавшихся для посещения узлов и анализа их содержимого. В рабочей реализации производительности будет уделено гораздо больше внимания.

Даже с этими ограничениями вы будете обладать достаточными знаниями для написания алгоритмов по чтению и анализу деревьев выражений.

[Следующий раздел — "Построение выражений"](expression-trees-building.md)
