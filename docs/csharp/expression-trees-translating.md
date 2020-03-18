---
title: Преобразование деревьев выражений
description: Сведения о том, как перейти к каждому узлу в дереве выражения при создании измененной копии этого дерева выражений.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: b453c591-acc6-4e08-8175-97e5bc65958e
ms.openlocfilehash: f60c447d5c89aa83f85073e642e621608131ed8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76115779"
---
# <a name="translate-expression-trees"></a>Преобразование деревьев выражений

[Предыдущий раздел — "Построение выражений"](expression-trees-building.md)

В этом заключительном разделе вы узнаете, как перейти к каждому узлу в дереве выражения при создании измененной копии этого дерева выражений. В разделе представлены методы, которые будут использоваться в двух важных сценариях. Первый — понимание алгоритмов, выраженных деревом выражения, для преобразования в другую среду. Второй — необходимость изменить созданный алгоритм. Сюда можно отнести необходимость добавить ведение журнала и осуществлять перехват вызовов методов и отслеживать их, а также другие задачи.

## <a name="translating-is-visiting"></a>Преобразование — это обход

Код, создаваемый для преобразования дерева выражения, является расширением кода, который используется для обхода всех узлов в дереве. Во время преобразования дерева выражения вы выполняете обход всех узлов и, таким образом, построение нового дерева. Новое дерево может содержать ссылки на исходные узлы или новые узлы, которые были помещены в дерево.

Рассмотрим это на примере, выполнив обход дерева выражения и создав новое дерево, заменяя в нем несколько узлов. В этом примере мы заменим любую константу константой, которая в десять раз больше.
В противном случае мы оставим дерево выражения без изменений. Вместо того чтобы считывать значение константы и заменять ее новой константой, мы осуществим такую подстановку, заменив узел константы новым узлом, который выполняет умножение.

Итак, вы находите узел константы, создаете новый узел умножения, дочерний элемент которого является исходной константой, и константу `10`:

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

При замене исходного узла новым узлом формируется новое дерево, содержащее наши изменения. Мы можем проверить это, скомпилировав и выполнив измененное дерево.

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

Создание нового дерева представляет собой сочетание обхода узлов в существующем дереве и создания новых узлов и вставки их в дерево.

Этот пример демонстрирует значимость неизменяемых деревьев выражений. Обратите внимание, что созданное нами новое дерево содержит сочетание вновь созданных узлов и узлов из существующего дерева. Это безопасно, поскольку узлы в существующем дереве изменить нельзя. Это позволяет существенно сократить потребление памяти.
Одни и те же узлы можно использовать в одном дереве или в нескольких деревьях выражений. Поскольку узлы нельзя изменить, один узел можно при необходимости использовать повторно.

## <a name="traversing-and-executing-an-addition"></a>Обход и выполнение добавления

Давайте проверим это, создав второй посетитель, который обходит дерево дополнительных узлов и вычисляет результат. Для этого вы можете просто внести пару изменений в уже готовый посетитель. В этой новой версии посетитель вернет частичную сумму операции сложения до этой точки. Для константного выражения это будет просто значением константного выражения. Для выражения добавления результатом будет сумма левого и правого операндов, поскольку выполняется обход этих деревьев.

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

Нам потребуется написать небольшой фрагмент кода, однако основные принципы очень просты.
Этот код обходит дочерние элементы при поиске в глубину. При обнаружении узла константы посетитель возвращает значение этой константы. После обхода обоих дочерних элементов для них вычисляется сумма для этого поддерева. Теперь добавленный узел может вычислить свою сумму.
После обхода всех узлов в дереве выражений будут вычислена сумма. Вы можете отслеживать выполнение, запустив пример в отладчике с трассировкой выполнения.

Мы можем упростить трассировку анализа узлов и вычисления суммы путем обхода дерева. Вот обновленная версия метода агрегирования, который включает совсем немного данных трассировки:

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

Если выполнить его в том же выражении, получаются следующие выходные данные:

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

Проследите выходные данные по приведенному выше коду. Вы наверняка поймете, каким образом код обходит каждый узел и вычисляет сумму по мере обхода дерева и нахождения суммы.

Теперь рассмотрим другое выполнение, где выражение задается объектом `sum1`:

```csharp
Expression<Func<int> sum1 = () => 1 + (2 + (3 + 4));
```

Ниже вы видите выходные данные проверки этого выражения:

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

Хотя окончательный ответ совпадает, способ обхода дерева совершенно другой. Узлы обходятся в другом порядке, так как дерево было создано с помощью других начальных операций.

## <a name="learning-more"></a>Дополнительные сведения

В этом примере показана малая часть кода, который необходимо создать для обхода и интерпретации алгоритмов, представляемых деревом выражения. Более полное рассмотрение всех действий, необходимых для создания библиотеки общего назначения, которая преобразует деревья выражений в другой язык, см. в [этой серии публикаций](https://docs.microsoft.com/archive/blogs/mattwar/linq-building-an-iqueryable-provider-series) Мэтта Уоррена (Matt Warren). Здесь преобразование кода, который можно найти в дереве выражения, рассматривается гораздо подробнее.

Надеюсь, теперь вы оценили эффективность и удобство деревьев выражений.
Вы можете проверить фрагмент кода, внести в него необходимые изменения и выполнить измененную версию. Поскольку деревья выражений являются неизменяемыми, вы можете создавать новые деревья на основе компонентов существующих деревьев. Это позволяет свести к минимуму потребление памяти для создания измененных деревьев выражений.

[Далее — "Заключение"](expression-trees-summary.md)
