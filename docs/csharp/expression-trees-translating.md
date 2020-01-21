---
title: Преобразование деревьев выражений
description: Сведения о том, как перейти к каждому узлу в дереве выражения при создании измененной копии этого дерева выражений.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: b453c591-acc6-4e08-8175-97e5bc65958e
ms.openlocfilehash: f60c447d5c89aa83f85073e642e621608131ed8d
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115779"
---
# <a name="translate-expression-trees"></a><span data-ttu-id="35846-103">Преобразование деревьев выражений</span><span class="sxs-lookup"><span data-stu-id="35846-103">Translate expression trees</span></span>

[<span data-ttu-id="35846-104">Предыдущий раздел — "Построение выражений"</span><span class="sxs-lookup"><span data-stu-id="35846-104">Previous -- Building Expressions</span></span>](expression-trees-building.md)

<span data-ttu-id="35846-105">В этом заключительном разделе вы узнаете, как перейти к каждому узлу в дереве выражения при создании измененной копии этого дерева выражений.</span><span class="sxs-lookup"><span data-stu-id="35846-105">In this final section, you'll learn how to visit each node in an expression tree while building a modified copy of that expression tree.</span></span> <span data-ttu-id="35846-106">В разделе представлены методы, которые будут использоваться в двух важных сценариях.</span><span class="sxs-lookup"><span data-stu-id="35846-106">These are the techniques that you will use in two important scenarios.</span></span> <span data-ttu-id="35846-107">Первый — понимание алгоритмов, выраженных деревом выражения, для преобразования в другую среду.</span><span class="sxs-lookup"><span data-stu-id="35846-107">The first is to understand the algorithms expressed by an expression tree so that it can be translated into another environment.</span></span> <span data-ttu-id="35846-108">Второй — необходимость изменить созданный алгоритм.</span><span class="sxs-lookup"><span data-stu-id="35846-108">The second is when you want to change the algorithm that has been created.</span></span> <span data-ttu-id="35846-109">Сюда можно отнести необходимость добавить ведение журнала и осуществлять перехват вызовов методов и отслеживать их, а также другие задачи.</span><span class="sxs-lookup"><span data-stu-id="35846-109">This might be to add logging, intercept method calls and track them, or other purposes.</span></span>

## <a name="translating-is-visiting"></a><span data-ttu-id="35846-110">Преобразование — это обход</span><span class="sxs-lookup"><span data-stu-id="35846-110">Translating is Visiting</span></span>

<span data-ttu-id="35846-111">Код, создаваемый для преобразования дерева выражения, является расширением кода, который используется для обхода всех узлов в дереве.</span><span class="sxs-lookup"><span data-stu-id="35846-111">The code you build to translate an expression tree is an extension of what you've already seen to visit all the nodes in a tree.</span></span> <span data-ttu-id="35846-112">Во время преобразования дерева выражения вы выполняете обход всех узлов и, таким образом, построение нового дерева.</span><span class="sxs-lookup"><span data-stu-id="35846-112">When you translate an expression tree, you visit all the nodes, and while visiting them, build the new tree.</span></span> <span data-ttu-id="35846-113">Новое дерево может содержать ссылки на исходные узлы или новые узлы, которые были помещены в дерево.</span><span class="sxs-lookup"><span data-stu-id="35846-113">The new tree may contain references to the original nodes, or new nodes that you have placed in the tree.</span></span>

<span data-ttu-id="35846-114">Рассмотрим это на примере, выполнив обход дерева выражения и создав новое дерево, заменяя в нем несколько узлов.</span><span class="sxs-lookup"><span data-stu-id="35846-114">Let's see this in action by visiting an expression tree, and creating a new tree with some replacement nodes.</span></span> <span data-ttu-id="35846-115">В этом примере мы заменим любую константу константой, которая в десять раз больше.</span><span class="sxs-lookup"><span data-stu-id="35846-115">In this example, let's replace any constant with a constant that is ten times larger.</span></span>
<span data-ttu-id="35846-116">В противном случае мы оставим дерево выражения без изменений.</span><span class="sxs-lookup"><span data-stu-id="35846-116">Otherwise, we'll leave the expression tree intact.</span></span> <span data-ttu-id="35846-117">Вместо того чтобы считывать значение константы и заменять ее новой константой, мы осуществим такую подстановку, заменив узел константы новым узлом, который выполняет умножение.</span><span class="sxs-lookup"><span data-stu-id="35846-117">Rather than reading the value of the constant, and replacing it with a new constant, we'll make this replacement by replacing the constant node with a new node that performs the multiplication.</span></span>

<span data-ttu-id="35846-118">Итак, вы находите узел константы, создаете новый узел умножения, дочерний элемент которого является исходной константой, и константу `10`:</span><span class="sxs-lookup"><span data-stu-id="35846-118">Here, once you find a constant node, you create a new multiplication node whose children are the original constant, and the constant `10`:</span></span>

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

<span data-ttu-id="35846-119">При замене исходного узла новым узлом формируется новое дерево, содержащее наши изменения.</span><span class="sxs-lookup"><span data-stu-id="35846-119">By replacing the original node with the substitute, a new tree is formed that contains our modifications.</span></span> <span data-ttu-id="35846-120">Мы можем проверить это, скомпилировав и выполнив измененное дерево.</span><span class="sxs-lookup"><span data-stu-id="35846-120">We can verify that by compiling and executing the replaced tree.</span></span>

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

<span data-ttu-id="35846-121">Создание нового дерева представляет собой сочетание обхода узлов в существующем дереве и создания новых узлов и вставки их в дерево.</span><span class="sxs-lookup"><span data-stu-id="35846-121">Building a new tree is a combination of visiting the nodes in the existing tree, and creating new nodes and inserting them into the tree.</span></span>

<span data-ttu-id="35846-122">Этот пример демонстрирует значимость неизменяемых деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="35846-122">This example shows the importance of expression trees being immutable.</span></span> <span data-ttu-id="35846-123">Обратите внимание, что созданное нами новое дерево содержит сочетание вновь созданных узлов и узлов из существующего дерева.</span><span class="sxs-lookup"><span data-stu-id="35846-123">Notice that the new tree created above contains a mixture of newly created nodes, and nodes from the existing tree.</span></span> <span data-ttu-id="35846-124">Это безопасно, поскольку узлы в существующем дереве изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="35846-124">That's safe, because the nodes in the existing tree cannot be modified.</span></span> <span data-ttu-id="35846-125">Это позволяет существенно сократить потребление памяти.</span><span class="sxs-lookup"><span data-stu-id="35846-125">This can result in significant memory efficiencies.</span></span>
<span data-ttu-id="35846-126">Одни и те же узлы можно использовать в одном дереве или в нескольких деревьях выражений.</span><span class="sxs-lookup"><span data-stu-id="35846-126">The same nodes can be used throughout a tree, or in multiple expression trees.</span></span> <span data-ttu-id="35846-127">Поскольку узлы нельзя изменить, один узел можно при необходимости использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="35846-127">Since nodes can't be modified, the same node can be reused whenever it's needed.</span></span>

## <a name="traversing-and-executing-an-addition"></a><span data-ttu-id="35846-128">Обход и выполнение добавления</span><span class="sxs-lookup"><span data-stu-id="35846-128">Traversing and Executing an Addition</span></span>

<span data-ttu-id="35846-129">Давайте проверим это, создав второй посетитель, который обходит дерево дополнительных узлов и вычисляет результат.</span><span class="sxs-lookup"><span data-stu-id="35846-129">Let's verify this by building a second visitor that walks the tree of addition nodes and computes the result.</span></span> <span data-ttu-id="35846-130">Для этого вы можете просто внести пару изменений в уже готовый посетитель.</span><span class="sxs-lookup"><span data-stu-id="35846-130">You can do this by making a couple modifications to the visitor that you've seen so far.</span></span> <span data-ttu-id="35846-131">В этой новой версии посетитель вернет частичную сумму операции сложения до этой точки.</span><span class="sxs-lookup"><span data-stu-id="35846-131">In this new version, the visitor will return the partial sum of the addition operation up to this point.</span></span> <span data-ttu-id="35846-132">Для константного выражения это будет просто значением константного выражения.</span><span class="sxs-lookup"><span data-stu-id="35846-132">For a constant expression, that is simply the value of the constant expression.</span></span> <span data-ttu-id="35846-133">Для выражения добавления результатом будет сумма левого и правого операндов, поскольку выполняется обход этих деревьев.</span><span class="sxs-lookup"><span data-stu-id="35846-133">For an addition expression, the result is the sum of the left and right operands, once those trees have been traversed.</span></span>

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

<span data-ttu-id="35846-134">Нам потребуется написать небольшой фрагмент кода, однако основные принципы очень просты.</span><span class="sxs-lookup"><span data-stu-id="35846-134">There's quite a bit of code here, but the concepts are very approachable.</span></span>
<span data-ttu-id="35846-135">Этот код обходит дочерние элементы при поиске в глубину.</span><span class="sxs-lookup"><span data-stu-id="35846-135">This code visits children in a depth first search.</span></span> <span data-ttu-id="35846-136">При обнаружении узла константы посетитель возвращает значение этой константы.</span><span class="sxs-lookup"><span data-stu-id="35846-136">When it encounters a constant node, the visitor returns the value of the constant.</span></span> <span data-ttu-id="35846-137">После обхода обоих дочерних элементов для них вычисляется сумма для этого поддерева.</span><span class="sxs-lookup"><span data-stu-id="35846-137">After the visitor has visited both children, those children will have computed the sum computed for that subtree.</span></span> <span data-ttu-id="35846-138">Теперь добавленный узел может вычислить свою сумму.</span><span class="sxs-lookup"><span data-stu-id="35846-138">The addition node can now compute its sum.</span></span>
<span data-ttu-id="35846-139">После обхода всех узлов в дереве выражений будут вычислена сумма.</span><span class="sxs-lookup"><span data-stu-id="35846-139">Once all the nodes in the expression tree have been visited, the sum will have been computed.</span></span> <span data-ttu-id="35846-140">Вы можете отслеживать выполнение, запустив пример в отладчике с трассировкой выполнения.</span><span class="sxs-lookup"><span data-stu-id="35846-140">You can trace the execution by running the sample in the debugger and tracing the execution.</span></span>

<span data-ttu-id="35846-141">Мы можем упростить трассировку анализа узлов и вычисления суммы путем обхода дерева.</span><span class="sxs-lookup"><span data-stu-id="35846-141">Let's make it easier to trace how the nodes are analyzed and how the sum is computed by traversing the tree.</span></span> <span data-ttu-id="35846-142">Вот обновленная версия метода агрегирования, который включает совсем немного данных трассировки:</span><span class="sxs-lookup"><span data-stu-id="35846-142">Here's an updated version of the Aggregate method that includes quite a bit of tracing information:</span></span>

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

<span data-ttu-id="35846-143">Если выполнить его в том же выражении, получаются следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="35846-143">Running it on the same expression yields the following output:</span></span>

```output
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

<span data-ttu-id="35846-144">Проследите выходные данные по приведенному выше коду.</span><span class="sxs-lookup"><span data-stu-id="35846-144">Trace the output and follow along in the code above.</span></span> <span data-ttu-id="35846-145">Вы наверняка поймете, каким образом код обходит каждый узел и вычисляет сумму по мере обхода дерева и нахождения суммы.</span><span class="sxs-lookup"><span data-stu-id="35846-145">You should be able to work out how the code visits each node and computes the sum as it goes through the tree and finds the sum.</span></span>

<span data-ttu-id="35846-146">Теперь рассмотрим другое выполнение, где выражение задается объектом `sum1`:</span><span class="sxs-lookup"><span data-stu-id="35846-146">Now, let's look at a different run, with the expression given by `sum1`:</span></span>

```csharp
Expression<Func<int> sum1 = () => 1 + (2 + (3 + 4));
```

<span data-ttu-id="35846-147">Ниже вы видите выходные данные проверки этого выражения:</span><span class="sxs-lookup"><span data-stu-id="35846-147">Here's the output from examining this expression:</span></span>

```output
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

<span data-ttu-id="35846-148">Хотя окончательный ответ совпадает, способ обхода дерева совершенно другой.</span><span class="sxs-lookup"><span data-stu-id="35846-148">While the final answer is the same, the tree traversal is completely different.</span></span> <span data-ttu-id="35846-149">Узлы обходятся в другом порядке, так как дерево было создано с помощью других начальных операций.</span><span class="sxs-lookup"><span data-stu-id="35846-149">The nodes are traveled in a different order, because the tree was constructed with different operations occurring first.</span></span>

## <a name="learning-more"></a><span data-ttu-id="35846-150">Получение дополнительных сведений</span><span class="sxs-lookup"><span data-stu-id="35846-150">Learning More</span></span>

<span data-ttu-id="35846-151">В этом примере показана малая часть кода, который необходимо создать для обхода и интерпретации алгоритмов, представляемых деревом выражения.</span><span class="sxs-lookup"><span data-stu-id="35846-151">This sample shows a small subset of the code you would build to traverse and interpret the algorithms represented by an expression tree.</span></span> <span data-ttu-id="35846-152">Более полное рассмотрение всех действий, необходимых для создания библиотеки общего назначения, которая преобразует деревья выражений в другой язык, см. в [этой серии публикаций](https://docs.microsoft.com/archive/blogs/mattwar/linq-building-an-iqueryable-provider-series) Мэтта Уоррена (Matt Warren).</span><span class="sxs-lookup"><span data-stu-id="35846-152">For a complete discussion of all the work necessary to build a general purpose library that translates expression trees into another language, please read [this series](https://docs.microsoft.com/archive/blogs/mattwar/linq-building-an-iqueryable-provider-series) by Matt Warren.</span></span> <span data-ttu-id="35846-153">Здесь преобразование кода, который можно найти в дереве выражения, рассматривается гораздо подробнее.</span><span class="sxs-lookup"><span data-stu-id="35846-153">It goes into great detail on how to translate any of the code you might find in an expression tree.</span></span>

<span data-ttu-id="35846-154">Надеюсь, теперь вы оценили эффективность и удобство деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="35846-154">I hope you've now seen the true power of expression trees.</span></span>
<span data-ttu-id="35846-155">Вы можете проверить фрагмент кода, внести в него необходимые изменения и выполнить измененную версию.</span><span class="sxs-lookup"><span data-stu-id="35846-155">You can examine a set of code, make any changes you'd like to that code, and execute the changed version.</span></span> <span data-ttu-id="35846-156">Поскольку деревья выражений являются неизменяемыми, вы можете создавать новые деревья на основе компонентов существующих деревьев.</span><span class="sxs-lookup"><span data-stu-id="35846-156">Because the expression trees are immutable, you can create new trees by using the components of existing trees.</span></span> <span data-ttu-id="35846-157">Это позволяет свести к минимуму потребление памяти для создания измененных деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="35846-157">This minimizes the amount of memory needed to create modified expression trees.</span></span>

[<span data-ttu-id="35846-158">Далее — "Заключение"</span><span class="sxs-lookup"><span data-stu-id="35846-158">Next -- Summing up</span></span>](expression-trees-summary.md)
