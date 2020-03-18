---
title: Практическое руководство. Добавление настраиваемых методов для запросов LINQ (C#)
ms.date: 07/20/2015
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: e16175d3332b6ce36458eaa78af093e4f8772723
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141467"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a>Практическое руководство. Добавление настраиваемых методов для запросов LINQ (C#)

Вы можете расширить набор методов, которые можно использовать для запросов LINQ, путем добавления методов расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>. Например, помимо стандартных операций вычисления среднего или максимального значения, можно создать настраиваемый метод агрегирования для вычисления одного значения на основе последовательности значений. Также можно создать метод, который работает как настраиваемый фильтр или особое преобразование данных для последовательности значений и возвращает новую последовательность. Примерами таких методов являются <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> и <xref:System.Linq.Enumerable.Reverse%2A>.

При расширении интерфейса <xref:System.Collections.Generic.IEnumerable%601> настраиваемые методы можно применять к любой перечислимой коллекции. Дополнительные сведения см. в статье [Методы расширения](../../classes-and-structs/extension-methods.md).

## <a name="adding-an-aggregate-method"></a>Использование метода агрегирования

Метод агрегирования вычисляет одно значение на основе набора значений. LINQ реализует несколько методов агрегирования, включая <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Max%2A>. Вы можете создать собственный метод агрегирования, добавив метод расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.

В следующем примере кода показано, как создать метод расширения `Median` для вычисления срединного значения последовательности чисел типа `double`.

```csharp
public static class LINQExtension
{
    public static double Median(this IEnumerable<double> source)
    {
        if (source.Count() == 0)
        {
            throw new InvalidOperationException("Cannot compute median for an empty set.");
        }

        var sortedList = from number in source
                         orderby number
                         select number;

        int itemIndex = (int)sortedList.Count() / 2;

        if (sortedList.Count() % 2 == 0)
        {
            // Even number of items.
            return (sortedList.ElementAt(itemIndex) + sortedList.ElementAt(itemIndex - 1)) / 2;
        }
        else
        {
            // Odd number of items.
            return sortedList.ElementAt(itemIndex);
        }
    }
}
```

Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы агрегирования из интерфейса <xref:System.Collections.Generic.IEnumerable%601>.

В следующем примере кода показано использование метода `Median` для массива типа `double`.

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("double: Median = " + query1);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
*/
```

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Перегрузка метода агрегирования для принятия различных типов

Метод агрегирования можно перегрузить, чтобы он принимал последовательности различных типов. Стандартный способ — создание перегрузки для каждого типа. Другой подход заключается в создании перегрузки, которая будет принимать универсальный тип и преобразовывать его в конкретный тип с помощью делегата. Вы можете сочетать оба способа.

#### <a name="to-create-an-overload-for-each-type"></a>Создание перегрузки для каждого типа

Вы можете создать конкретную перегрузку для каждого типа, который требуется поддерживать. В следующем примере кода показана перегрузка метода `Median` для типа `integer`.

```csharp
//int overload

public static double Median(this IEnumerable<int> source)
{
    return (from num in source select (double)num).Median();
}
```

Теперь можно вызвать перегрузки `Median` для типов `integer` и `double`, как показано в следующем примере кода:

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("double: Median = " + query1);
```

```csharp
int[] numbers2 = { 1, 2, 3, 4, 5 };

var query2 = numbers2.Median();

Console.WriteLine("int: Median = " + query2);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
 Integer: Median = 3
*/
```

#### <a name="to-create-a-generic-overload"></a>Создание универсальной перегрузки

Вы также можете создать перегрузку, которая принимает последовательность универсальных объектов. Эта перегрузка принимает делегат в качестве параметра и использует его для преобразования последовательности объектов универсального типа в конкретный тип.

В следующем примере кода демонстрируется перегрузка метода `Median`, принимающая делегат <xref:System.Func%602> в качестве параметра. Этот делегат принимает объект универсального типа T и возвращает объект типа `double`.

```csharp
// Generic overload.

public static double Median<T>(this IEnumerable<T> numbers,
                       Func<T, double> selector)
{
    return (from num in numbers select selector(num)).Median();
}
```

Теперь вы можете вызвать метод `Median` для последовательности объектов любого типа. Если тип не содержит собственную перегрузку метода, вам потребуется передать параметр делегата. В C# для этой цели можно использовать лямбда-выражение. Кроме того, только в Visual Basic, если вы используете предложение `Aggregate` или `Group By` вместо вызова метода, вы можете передать любое значение или выражение, которое находится в области этого предложения.

В следующем примере кода показано, как вызвать метод `Median` для массива целых чисел и массива строк. Для строк вычисляется срединное значение длин строк в массиве. В примере демонстрируется передача параметра делегата <xref:System.Func%602> в метод `Median` для каждого из случаев.

```csharp
int[] numbers3 = { 1, 2, 3, 4, 5 };

/*
  You can use the num=>num lambda expression as a parameter for the Median method
  so that the compiler will implicitly convert its value to double.
  If there is no implicit conversion, the compiler will display an error message.
*/

var query3 = numbers3.Median(num => num);

Console.WriteLine("int: Median = " + query3);

string[] numbers4 = { "one", "two", "three", "four", "five" };

// With the generic overload, you can also use numeric properties of objects.

var query4 = numbers4.Median(str => str.Length);

Console.WriteLine("String: Median = " + query4);

/*
 This code produces the following output:

 Integer: Median = 3
 String: Median = 4
*/
```

## <a name="adding-a-method-that-returns-a-collection"></a>Добавление метода, возвращающего коллекцию

Вы можете расширить интерфейс <xref:System.Collections.Generic.IEnumerable%601> с помощью метода настраиваемого запроса, который возвращает последовательность значений. В этом случае метод должен возвращать коллекцию типа <xref:System.Collections.Generic.IEnumerable%601>. Такие методы можно использовать для применения фильтров или преобразований данных к последовательности значений.

В следующем примере показано, как создать метод расширения с именем `AlternateElements`, который возвращает каждый второй элемент в коллекции, начиная с первого элемента.

```csharp
// Extension method for the IEnumerable<T> interface.
// The method returns every other element of a sequence.

public static IEnumerable<T> AlternateElements<T>(this IEnumerable<T> source)
{
    List<T> list = new List<T>();

    int i = 0;

    foreach (var element in source)
    {
        if (i % 2 == 0)
        {
            list.Add(element);
        }

        i++;
    }

    return list;
}
```

Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы из интерфейса <xref:System.Collections.Generic.IEnumerable%601>, как показано в следующем примере кода:

```csharp
string[] strings = { "a", "b", "c", "d", "e" };

var query = strings.AlternateElements();

foreach (var element in query)
{
    Console.WriteLine(element);
}
/*
 This code produces the following output:

 a
 c
 e
*/
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Collections.Generic.IEnumerable%601>
- [Методы расширения](../../classes-and-structs/extension-methods.md)
