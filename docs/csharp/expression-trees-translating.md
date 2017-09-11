---
title: "Преобразование деревьев выражений"
description: "Сведения о том, как перейти к каждому узлу в дереве выражения при создании измененной копии этого дерева выражений."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: b453c591-acc6-4e08-8175-97e5bc65958e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 602a17591d27ebfd098516453b9028bca37ad5e3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="translating-expression-trees"></a><span data-ttu-id="bbbec-104">Преобразование деревьев выражений</span><span class="sxs-lookup"><span data-stu-id="bbbec-104">Translating Expression Trees</span></span>

[<span data-ttu-id="bbbec-105">Предыдущий раздел — "Построение выражений"</span><span class="sxs-lookup"><span data-stu-id="bbbec-105">Previous -- Building Expressions</span></span>](expression-trees-building.md)

<span data-ttu-id="bbbec-106">В этом заключительном разделе вы узнаете, как перейти к каждому узлу в дереве выражения при создании измененной копии этого дерева выражений.</span><span class="sxs-lookup"><span data-stu-id="bbbec-106">In this final section, you'll learn how to visit each node in an expression tree while building a modified copy of that expression tree.</span></span> <span data-ttu-id="bbbec-107">В разделе представлены методы, которые будут использоваться в двух важных сценариях.</span><span class="sxs-lookup"><span data-stu-id="bbbec-107">These are the techniques that you will use in two important scenarios.</span></span> <span data-ttu-id="bbbec-108">Первый — понимание алгоритмов, выраженных деревом выражения, для преобразования в другую среду.</span><span class="sxs-lookup"><span data-stu-id="bbbec-108">The first is to understand the algorithms expressed by an expression tree so that it can be translated into another environment.</span></span> <span data-ttu-id="bbbec-109">Второй — необходимость изменить созданный алгоритм.</span><span class="sxs-lookup"><span data-stu-id="bbbec-109">The second is when you want to change the algorithm that has been created.</span></span> <span data-ttu-id="bbbec-110">Сюда можно отнести необходимость добавить ведение журнала и осуществлять перехват вызовов методов и отслеживать их, а также другие задачи.</span><span class="sxs-lookup"><span data-stu-id="bbbec-110">This might be to add logging, intercept method calls and track them, or other purposes.</span></span>

## <a name="translating-is-visiting"></a><span data-ttu-id="bbbec-111">Преобразование — это обход</span><span class="sxs-lookup"><span data-stu-id="bbbec-111">Translating is Visiting</span></span>

<span data-ttu-id="bbbec-112">Код, создаваемый для преобразования дерева выражения, является расширением кода, который используется для обхода всех узлов в дереве.</span><span class="sxs-lookup"><span data-stu-id="bbbec-112">The code you build to translate an expression tree is an extension of what you've already seen to visit all the nodes in a tree.</span></span> <span data-ttu-id="bbbec-113">Во время преобразования дерева выражения вы выполняете обход всех узлов и, таким образом, построение нового дерева.</span><span class="sxs-lookup"><span data-stu-id="bbbec-113">When you translate an expression tree, you visit all the nodes, and while visiting them, build the new tree.</span></span> <span data-ttu-id="bbbec-114">Новое дерево может содержать ссылки на исходные узлы или новые узлы, которые были помещены в дерево.</span><span class="sxs-lookup"><span data-stu-id="bbbec-114">The new tree may contain references to the original nodes, or new nodes that you have placed in the tree.</span></span>

<span data-ttu-id="bbbec-115">Рассмотрим это на примере, выполнив обход дерева выражения и создав новое дерево, заменяя в нем несколько узлов.</span><span class="sxs-lookup"><span data-stu-id="bbbec-115">Let's see this in action by visiting an expression tree, and creating a new tree with some replacement nodes.</span></span> <span data-ttu-id="bbbec-116">В этом примере мы заменим любую константу константой, которая в десять раз больше.</span><span class="sxs-lookup"><span data-stu-id="bbbec-116">In this example, let's replace any constant with a constant that is ten times larger.</span></span>
<span data-ttu-id="bbbec-117">В противном случае мы оставим дерево выражения без изменений.</span><span class="sxs-lookup"><span data-stu-id="bbbec-117">Otherwise, we'll leave the expression tree intact.</span></span> <span data-ttu-id="bbbec-118">Вместо того чтобы считывать значение константы и заменять ее новой константой, мы осуществим такую подстановку, заменив узел константы новым узлом, который выполняет умножение.</span><span class="sxs-lookup"><span data-stu-id="bbbec-118">Rather than reading the value of the constant, and replacing it with a new constant, we'll make this replacement by replacing the constant node with a new node that performs the multiplication.</span></span>

<span data-ttu-id="bbbec-119">Итак, вы находите узел константы, создаете новый узел умножения, дочерний элемент которого является исходной константой, и константу `10`:</span><span class="sxs-lookup"><span data-stu-id="bbbec-119">Here, once you find a constant node, you create a new multiplication node whose children are the original constant, and the constant `10`:</span></span>

```csharp
private static Expression ReplaceNodes(Expression original)
{
    if (original.NodeType == ExpressionType.Constant)
    {
        return Expression.Multiply(original, Expression.Constant(10));
    }
    else if (original.NodeType == ExpressionType.Add)
    {
        var binaryExpression = (BinaryExpression)original;
        return Expression.Add(
            ReplaceNodes(binaryExpression.Left),
            ReplaceNodes(binaryExpression.Right));
    }
    return original;
}
```

<span data-ttu-id="bbbec-120">При замене исходного узла новым узлом формируется новое дерево, содержащее наши изменения.</span><span class="sxs-lookup"><span data-stu-id="bbbec-120">By replacing the original node with the substitute, a new tree is formed that contains our modifications.</span></span> <span data-ttu-id="bbbec-121">Мы можем проверить это, скомпилировав и выполнив измененное дерево.</span><span class="sxs-lookup"><span data-stu-id="bbbec-121">We can verify that by compiling and executing the replaced tree.</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
var sum = ReplaceNodes(addition);
var executableFunc = Expression.Lambda(sum);

var func = (Func<int>)executableFunc.Compile();
var answer = func();
Console.WriteLine(answer);
```

<span data-ttu-id="bbbec-122">Создание нового дерева представляет собой сочетание обхода узлов в существующем дереве и создания новых узлов и вставки их в дерево.</span><span class="sxs-lookup"><span data-stu-id="bbbec-122">Building a new tree is a combination of visiting the nodes in the existing tree, and creating new nodes and inserting them into the tree.</span></span>

<span data-ttu-id="bbbec-123">Этот пример демонстрирует значимость неизменяемых деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="bbbec-123">This example shows the importance of expression trees being immutable.</span></span> <span data-ttu-id="bbbec-124">Обратите внимание, что созданное нами новое дерево содержит сочетание вновь созданных узлов и узлов из существующего дерева.</span><span class="sxs-lookup"><span data-stu-id="bbbec-124">Notice that the new tree created above contains a mixture of newly created nodes, and nodes from the existing tree.</span></span> <span data-ttu-id="bbbec-125">Это безопасно, поскольку узлы в существующем дереве изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="bbbec-125">That's safe, because the nodes in the existing tree cannot be modified.</span></span> <span data-ttu-id="bbbec-126">Это позволяет существенно сократить потребление памяти.</span><span class="sxs-lookup"><span data-stu-id="bbbec-126">This can result in significant memory efficiencies.</span></span>
<span data-ttu-id="bbbec-127">Одни и те же узлы можно использовать в одном дереве или в нескольких деревьях выражений.</span><span class="sxs-lookup"><span data-stu-id="bbbec-127">The same nodes can be used throughout a tree, or in multiple expression trees.</span></span> <span data-ttu-id="bbbec-128">Поскольку узлы нельзя изменить, один узел можно при необходимости использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="bbbec-128">Since nodes can't be modified, the same node can be reused whenever its needed.</span></span>

## <a name="traversing-and-executing-an-addition"></a><span data-ttu-id="bbbec-129">Обход и выполнение добавления</span><span class="sxs-lookup"><span data-stu-id="bbbec-129">Traversing and Executing an Addition</span></span>

<span data-ttu-id="bbbec-130">Давайте проверим это, создав второй посетитель, который обходит дерево дополнительных узлов и вычисляет результат.</span><span class="sxs-lookup"><span data-stu-id="bbbec-130">Let's verify this by building a second visitor that walks the tree of addition nodes and computes the result.</span></span> <span data-ttu-id="bbbec-131">Для этого вы можете просто внести пару изменений в уже готовый посетитель.</span><span class="sxs-lookup"><span data-stu-id="bbbec-131">You can do this by making a couple modifications to the vistor that you've seen so far.</span></span> <span data-ttu-id="bbbec-132">В этой новой версии посетитель вернет частичную сумму операции сложения до этой точки.</span><span class="sxs-lookup"><span data-stu-id="bbbec-132">In this new version, the visitor will return the partial sum of the addition operation up to this point.</span></span> <span data-ttu-id="bbbec-133">Для константного выражения это будет просто значением константного выражения.</span><span class="sxs-lookup"><span data-stu-id="bbbec-133">For a constant expression, that is simply the value of the constant expression.</span></span> <span data-ttu-id="bbbec-134">Для выражения добавления результатом будет сумма левого и правого операндов, поскольку выполняется обход этих деревьев.</span><span class="sxs-lookup"><span data-stu-id="bbbec-134">For an addition expression, the result is the sum of the left and right operands, once those trees have been traversed.</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var three= Expression.Constant(3, typeof(int));
var four = Expression.Constant(4, typeof(int));
var addition = Expression.Add(one, two);
var add2 = Expression.Add(three, four);
var sum = Expression.Add(addition, add2);

// Declare the delegate, so we can call it 
// from itself recursively:
Func<Expression, int> aggregate = null;
// Aggregate, return constants, or the sum of the left and right operand.
// Major simplification: Assume every binary expression is an addition.
aggregate = (exp) =>
    exp.NodeType == ExpressionType.Constant ?
    (int)((ConstantExpression)exp).Value :
    aggregate(((BinaryExpression)exp).Left) + aggregate(((BinaryExpression)exp).Right);

var theSum = aggregate(sum);
Console.WriteLine(theSum);
```

<span data-ttu-id="bbbec-135">Нам потребуется написать небольшой фрагмент кода, однако основные принципы очень просты.</span><span class="sxs-lookup"><span data-stu-id="bbbec-135">There's quite a bit of code here, but the concepts are very approachable.</span></span>
<span data-ttu-id="bbbec-136">Этот код обходит дочерние элементы при поиске в глубину.</span><span class="sxs-lookup"><span data-stu-id="bbbec-136">This code visits children in a depth first search.</span></span> <span data-ttu-id="bbbec-137">При обнаружении узла константы посетитель возвращает значение этой константы.</span><span class="sxs-lookup"><span data-stu-id="bbbec-137">When it encounters a constant node, the visitor returns the value of the constant.</span></span> <span data-ttu-id="bbbec-138">После обхода обоих дочерних элементов для них вычисляется сумма, вычисляемая для этого поддерева.</span><span class="sxs-lookup"><span data-stu-id="bbbec-138">After the visitor has visited both children, those children will have computed the sum computed for that sub-tree.</span></span> <span data-ttu-id="bbbec-139">Теперь добавленный узел может вычислить свою сумму.</span><span class="sxs-lookup"><span data-stu-id="bbbec-139">The addition node can now compute its sum.</span></span>
<span data-ttu-id="bbbec-140">После обхода всех узлов в дереве выражений будут вычислена сумма.</span><span class="sxs-lookup"><span data-stu-id="bbbec-140">Once all the nodes in the expression tree have been visited, the sum will have been computed.</span></span> <span data-ttu-id="bbbec-141">Вы можете отслеживать выполнение, запустив пример в отладчике с трассировкой выполнения.</span><span class="sxs-lookup"><span data-stu-id="bbbec-141">You can trace the execution by running the sample in the debugger and tracing the execution.</span></span>

<span data-ttu-id="bbbec-142">Мы можем упростить трассировку анализа узлов и вычисления суммы путем обхода дерева.</span><span class="sxs-lookup"><span data-stu-id="bbbec-142">Let's make it easier to trace how the nodes are analyzed and how the sum is computed by travsersing the tree.</span></span> <span data-ttu-id="bbbec-143">Вот обновленная версия метода агрегирования, который включает совсем немного данных трассировки:</span><span class="sxs-lookup"><span data-stu-id="bbbec-143">Here's an updated version of the Aggregate method that includes quite a bit of tracing information:</span></span>

```csharp
private static int Aggregate(Expression exp)
{
    if (exp.NodeType == ExpressionType.Constant)
    {
        var constantExp = (ConstantExpression)exp;
        Console.Error.WriteLine($"Found Constant: {constantExp.Value}");
        return (int)constantExp.Value;
    }
    else if (exp.NodeType == ExpressionType.Add)
    {
        var addExp = (BinaryExpression)exp;
        Console.Error.WriteLine("Found Addition Expression");
        Console.Error.WriteLine("Computing Left node");
        var leftOperand = Aggregate(addExp.Left);
        Console.Error.WriteLine($"Left is: {leftOperand}");
        Console.Error.WriteLine("Computing Right node");
        var rightOperand = Aggregate(addExp.Right);
        Console.Error.WriteLine($"Right is: {rightOperand}");
        var sum = leftOperand + rightOperand;
        Console.Error.WriteLine($"Computed sum: {sum}");
        return sum;
    }
    else throw new NotSupportedException("Haven't written this yet");
}
```

<span data-ttu-id="bbbec-144">Если выполнить его в том же выражении, получаются следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="bbbec-144">Running it on the same expression yields the following output:</span></span>

```
10
Found Addition Expression
Computing Left node
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Constant: 2
Right is: 2
Computed sum: 3
Left is: 3
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 10
10
```

<span data-ttu-id="bbbec-145">Проследите выходные данные по приведенному выше коду.</span><span class="sxs-lookup"><span data-stu-id="bbbec-145">Trace the output and follow along in the code above.</span></span> <span data-ttu-id="bbbec-146">Вы наверняка поймете, каким образом код обходит каждый узел и вычисляет сумму по мере обхода дерева и нахождения суммы.</span><span class="sxs-lookup"><span data-stu-id="bbbec-146">You should be able to work out how the code visits each node and computes the sum as it goes through the tree and finds the sum.</span></span>

<span data-ttu-id="bbbec-147">Теперь рассмотрим другое выполнение, где выражение задается объектом `sum1`:</span><span class="sxs-lookup"><span data-stu-id="bbbec-147">Now, let's look at a different run, with the expression given by `sum1`:</span></span>

```csharp
Expression<Func<int> sum1 = () => 1 + (2 + (3 + 4));
```

<span data-ttu-id="bbbec-148">Ниже вы видите выходные данные проверки этого выражения:</span><span class="sxs-lookup"><span data-stu-id="bbbec-148">Here's the output from examining this expression:</span></span>

```
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 2
Left is: 2
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 9
Right is: 9
Computed sum: 10
10
```

<span data-ttu-id="bbbec-149">Хотя окончательный ответ совпадает, способ обхода дерева совершенно другой.</span><span class="sxs-lookup"><span data-stu-id="bbbec-149">While the final answer is the same, the tree traversal is completely different.</span></span> <span data-ttu-id="bbbec-150">Узлы обходятся в другом порядке, так как дерево было создано с помощью других начальных операций.</span><span class="sxs-lookup"><span data-stu-id="bbbec-150">The nodes are traveled in a different order, because the tree was constructed with different operations occurring first.</span></span>

## <a name="learning-more"></a><span data-ttu-id="bbbec-151">Получение дополнительных сведений</span><span class="sxs-lookup"><span data-stu-id="bbbec-151">Learning More</span></span>

<span data-ttu-id="bbbec-152">В этом примере показана малая часть кода, который необходимо создать для обхода и интерпретации алгоритмов, представляемых деревом выражения.</span><span class="sxs-lookup"><span data-stu-id="bbbec-152">This sample shows a small subset of the code you would build to traverse and interpret the algorithms represented by an expression tree.</span></span> <span data-ttu-id="bbbec-153">Более полное рассмотрение всех действий, необходимых для создания библиотеки общего назначения, которая преобразует деревья выражений в другой язык, см. в [этой серии публикаций](http://blogs.msdn.com/b/mattwar/archive/2008/11/18/linq-links.aspx) Мэтта Уоррена (Matt Warren).</span><span class="sxs-lookup"><span data-stu-id="bbbec-153">For a complete discussion of all the work necessary to build a general purpose library that translates expression trees into another language, please read [this series](http://blogs.msdn.com/b/mattwar/archive/2008/11/18/linq-links.aspx) by Matt Warren.</span></span> <span data-ttu-id="bbbec-154">Здесь преобразование кода, который можно найти в дереве выражения, рассматривается гораздо подробнее.</span><span class="sxs-lookup"><span data-stu-id="bbbec-154">It goes into great detail on how to translate any of the code you might find in an expression tree.</span></span>

<span data-ttu-id="bbbec-155">Надеюсь, теперь вы оценили эффективность и удобство деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="bbbec-155">I hope you've now seen the true power of expression trees.</span></span>
<span data-ttu-id="bbbec-156">Вы можете проверить фрагмент кода, внести в него необходимые изменения и выполнить измененную версию.</span><span class="sxs-lookup"><span data-stu-id="bbbec-156">You can examine a set of code, make any changes you'd like to that code, and execute the changed version.</span></span> <span data-ttu-id="bbbec-157">Поскольку деревья выражений являются неизменяемыми, вы можете создавать новые деревья на основе компонентов существующих деревьев.</span><span class="sxs-lookup"><span data-stu-id="bbbec-157">Because the expression trees are immutable, you can create new trees by using the components of existing trees.</span></span> <span data-ttu-id="bbbec-158">Это позволяет свести к минимуму потребление памяти для создания измененных деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="bbbec-158">This minimizes the amount of memory needed to create modified expression trees.</span></span>

[<span data-ttu-id="bbbec-159">Далее — "Заключение"</span><span class="sxs-lookup"><span data-stu-id="bbbec-159">Next -- Summing up</span></span>](expression-trees-summary.md)

