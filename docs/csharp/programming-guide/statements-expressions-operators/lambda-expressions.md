---
title: Лямбда-выражения (руководство по программированию на C#)
ms.date: 07/29/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: c549b9fcc91401aed846afd39e656b60e16afb74
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937603"
---
# <a name="lambda-expressions-c-programming-guide"></a>Лямбда-выражения (руководство по программированию на C#)

*Лямбда-выражение* является выражением любой из следующих двух форм:

- [Лямбда выражения](#expression-lambdas), имеющая выражение в качестве текста:

  ```csharp
  (input-parameters) => expression
  ```

- [Лямбда оператора](#statement-lambdas), имеющая блок операторов в качестве текста:

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

Используйте [оператор объявления лямбда-выражения`=>`](../../language-reference/operators/lambda-operator.md) для отделения списка параметров лямбда-выражения от исполняемого кода. Чтобы создать лямбда-выражение, необходимо указать входные параметры (если они есть) с левой стороны лямбда-оператора и блок выражений или операторов с другой стороны.

Лямбда-выражение может быть преобразовано в тип [делегата](../../language-reference/builtin-types/reference-types.md#the-delegate-type). Тип делегата, в который может быть преобразовано лямбда-выражение, определяется типами его параметров и возвращаемым значением. Если лямбда-выражение не возвращает значение, оно может быть преобразовано в один из типов делегата `Action`; в противном случае его можно преобразовать в один из типов делегатов `Func`. Например, лямбда-выражение, которое имеет два параметра и не возвращает значение, можно преобразовать в делегат <xref:System.Action%602>. Лямбда-выражение, которое имеет два параметра и возвращает значение, можно преобразовать в делегат <xref:System.Func%602>. В следующем примере лямбда-выражение `x => x * x`, которое указывает параметр с именем `x` и возвращает значение `x` в квадрате, присваивается переменной типа делегата:

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

Лямбда выражений также можно преобразовать в типы [дерева выражения](../concepts/expression-trees/index.md), как показано в следующем примере:

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

Лямбда-выражения можно использовать в любом коде, для которого требуются экземпляры типов делегатов или деревьев выражений, например в качестве аргумента метода <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> для передачи кода, который должен выполняться в фоновом режиме. Можно также использовать лямбда-выражения при применении [LINQ в C#](../../linq/index.md), как показано в следующем примере:

[!code-csharp-interactive[lambda is argument in LINQ](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

При использовании синтаксиса на основе методов для вызова метода <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> в классе <xref:System.Linq.Enumerable?displayProperty=nameWithType> (например, в LINQ to Objects и LINQ to XML) параметром является тип делегата <xref:System.Func%602?displayProperty=nameWithType>. При вызове метода <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> в классе <xref:System.Linq.Queryable?displayProperty=nameWithType> (например, в LINQ to SQL) типом параметра является тип дерева выражения [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>). В обоих случаях можно использовать одно и то же лямбда-выражение для указания значения параметра. Поэтому оба вызова `Select` выглядят одинаково, хотя на самом деле объект, созданный из лямбда-выражения, имеет другой тип.
  
## <a name="expression-lambdas"></a>Выражения-лямбды

Лямбда-выражение с выражением с правой стороны оператора `=>` называется *выражением лямбда*. Выражения-лямбды широко используются при конструировании [деревьев выражений](../concepts/expression-trees/index.md). Выражения-лямбды возвращают результат выражения и принимают следующую основную форму.

```csharp
(input-parameters) => expression
```

Если лямбда-выражение имеет только один входной параметр, скобки можно не ставить; во всех остальных случаях они обязательны.

Нулевое количество входных параметры задается пустыми скобками:  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

Два и более входных параметра разделяются запятыми и заключаются в скобки:

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

Иногда компилятору не удается определить входные типы. Вы можете указать типы данных в явном виде, как показано в следующем примере:

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

Для входных параметров все типы нужно задать либо в явном, либо в неявном виде. В противном случае компилятор выдает ошибку [CS0748](../../misc/cs0748.md).

Текст выражения лямбды может состоять из вызова метода. Но при создании деревьев выражений, которые вычисляются вне контекста поддержки общеязыковой среды выполнения .NET, например в SQL Server, вызовы методов не следует использовать в лямбда-выражениях. Эти методы не имеют смысла вне контекста среды CLR .NET.

## <a name="statement-lambdas"></a>Лямбды операторов

Лямбда оператора напоминает выражение-лямбду, за исключением того, что оператор (или операторы) заключается в фигурные скобки:

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

Тело лямбды оператора может состоять из любого количества операторов; однако на практике обычно используется не более двух-трех.

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

Лямбды операторов нельзя использовать для создания деревьев выражений.
  
## <a name="async-lambdas"></a>Асинхронные лямбда-выражения

С помощью ключевых слов [async](../../language-reference/keywords/async.md) и [await](../../language-reference/operators/await.md) можно легко создавать лямбда-выражения и операторы, включающие асинхронную обработку. Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.

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

Такой же обработчик событий можно добавить с помощью асинхронного лямбда-выражения. Чтобы добавить этот обработчик, поставьте модификатор `async` перед списком параметров лямбда-выражения, как показано в следующем примере:

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

Дополнительные сведения о создании и использовании асинхронных методов см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../concepts/async/index.md).

## <a name="lambda-expressions-and-tuples"></a>Лямбда-выражения и кортежи

В C# 7.0 представлена встроенная поддержка [кортежей](../../tuples.md). Кортеж можно ввести в качестве аргумента лямбда-выражения, и лямбда-выражение также может возвращать кортеж. В некоторых случаях компилятор C# использует определение типа для определения типов компонентов кортежа.

Кортеж определяется путем заключения в скобки списка его компонентов с разделителями-запятыми. В следующем примере кортеж с тремя компонентами используется для передачи последовательности чисел в лямбда-выражение. Оно удваивает каждое значение и возвращает кортеж с тремя компонентами, содержащий результат операций умножения.

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

Как правило, поля кортежи именуются как `Item1`, `Item2` и т. д. Тем не менее кортеж с именованными компонентами можно определить, как показано в следующем примере:

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

См. дополнительные сведения о [типах кортежей в C#](../../tuples.md).

## <a name="lambdas-with-the-standard-query-operators"></a>Лямбда-выражения со стандартными операторами запросов

В LINQ to Objects, наряду с другими реализациями, есть входной параметр, тип которого принадлежит к семейству универсальных делегатов <xref:System.Func%601>. Эти делегаты используют параметры типа для определения количества и типов входных параметров, а также тип возвращаемого значения делегата. Делегаты`Func` очень полезны для инкапсуляции пользовательских выражений, которые применяются к каждому элементу в наборе исходных данных. В качестве примера рассмотрим следующий тип делегата <xref:System.Func%602>:  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

Экземпляр этого делегата можно создать как `Func<int, bool>`, где `int` — входной параметр, а `bool` — возвращаемое значение. Возвращаемое значение всегда указывается в последнем параметре типа. Например, `Func<int, string, bool>` определяет делегат с двумя входными параметрами, `int` и `string`, и типом возвращаемого значения `bool`. Следующий делегат `Func` при вызове возвращает логическое значение, которое показывает, равен ли входной параметр 5:

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

Лямбда-выражения также можно использовать, когда аргумент имеет тип <xref:System.Linq.Expressions.Expression%601>, например в стандартных операторах запросов, которые определены в типе <xref:System.Linq.Queryable>. При указании аргумента <xref:System.Linq.Expressions.Expression%601> лямбда-выражение компилируется в дерево выражения.
  
В этом примере используется стандартный оператор запроса <xref:System.Linq.Enumerable.Count%2A>:

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

Компилятор может вывести тип входного параметра ввода; но его также можно определить явным образом. Данное лямбда-выражение подсчитывает указанные целые значения (`n`), которые при делении на два дают остаток 1.

В следующем примере кода показано, как создать последовательность, которая содержит все элементы массива `numbers`, предшествующие 9, так как это первое число последовательности, не удовлетворяющее условию:

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

В следующем примере показано, как указать несколько входных параметров путем их заключения в скобки. Этот метод возвращает все элементы в массиве `numbers` до того числа, значение которого меньше его порядкового номера в массиве:

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a>Определение типа в лямбда-выражениях

При написании лямбда-выражений обычно не требуется указывать тип входных параметров, так как компилятор может выводить этот тип на основе тела лямбда-выражения, типов параметров и других факторов, как описано в спецификации языка C#. Для большинства стандартных операторов запросов первой входное значение имеет тип элементов в исходной последовательности. При запросе `IEnumerable<Customer>` входная переменная считается объектом `Customer`, а это означает, что у вас есть доступ к его методам и свойствам.  

```csharp
customers.Where(c => c.City == "London");
```

Общие правила определения типа для лямбда-выражений формулируются следующим образом:

- лямбда-выражение должно содержать то же число параметров, что и тип делегата;

- каждый входной параметр в лямбда-выражении должен быть неявно преобразуемым в соответствующий параметр делегата;

- возвращаемое значение лямбда-выражения (если таковое имеется) должно быть неявно преобразуемым в возвращаемый тип делегата.
  
Обратите внимание, что у лямбда-выражений нет типа, так как в системе общих типов изначально отсутствует такое понятие, как лямбда-выражения. Но применительно к лямбда-выражениям иногда бывает удобно оперировать понятием типа. При этом под типом понимается тип делегата или тип <xref:System.Linq.Expressions.Expression> , в который преобразуется лямбда-выражение.

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a>Запись внешних переменных и области видимости переменной в лямбда-выражениях

Лямбда-выражения могут ссылаться *на внешние переменные*. Это переменные в области метода, в котором определено лямбда-выражение, или области типа, который содержит лямбда-выражение. Переменные, полученные таким способом, сохраняются для использования в лямбда-выражениях, даже если бы в ином случае они оказались за границами области действия и уничтожились сборщиком мусора. Внешняя переменная должна быть определенным образом присвоена, прежде чем она сможет использоваться в лямбда-выражениях. В следующем примере демонстрируются эти правила.

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

Следующие правила применимы к области действия переменной в лямбда-выражениях.  

- Захваченная переменная не будет уничтожена сборщиком мусора до тех пор, пока делегат, который на нее ссылается, не перейдет в статус подлежащего уничтожению при сборке мусора.

- Переменные, представленные в лямбда-выражении, невидимы в заключающем методе.

- Лямбда-выражение не может непосредственно захватывать параметры [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) или [out](../../language-reference/keywords/out-parameter-modifier.md) из заключающего метода.

- Оператор [return](../../language-reference/keywords/return.md) в лямбда-выражении не вызывает возврат значения заключающим методом.

- Лямбда-выражение не может содержать операторы [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md) или [continue](../../language-reference/keywords/continue.md), если целевой объект этого оператора перехода находится за пределами блока лямбда-выражения. Если целевой объект находится внутри блока, использование оператора перехода за пределами лямбда-выражения также будет ошибкой.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Выражения анонимных функций](~/_csharplang/spec/expressions.md#anonymous-function-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="featured-book-chapter"></a>Важная глава книги

[Делегаты, события и лямбда-выражения](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) в [справочном руководстве по C# 3.0, третье издание. Более 250 решений для программистов на C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Встроенный язык запросов LINQ](../concepts/linq/index.md)
- [Деревья выражений](../concepts/expression-trees/index.md)
- [Локальные функции в сравнении с лямбда-выражениями](../../local-functions-vs-lambdas.md)
- [Неявно типизированные лямбда-выражения](../../implicitly-typed-lambda-expressions.md)
- [Примеры C# в Visual Studio 2008 (см. файлы примеров запросов LINQ и программу XQuery)](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [Рекурсивные лямбда-выражения](https://docs.microsoft.com/archive/blogs/madst/recursive-lambda-expressions)
