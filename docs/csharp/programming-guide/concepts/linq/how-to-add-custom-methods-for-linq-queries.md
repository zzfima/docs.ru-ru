---
title: Практическое руководство. Добавление настраиваемых методов для запросов LINQ (C#)
ms.date: 07/20/2015
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: e16175d3332b6ce36458eaa78af093e4f8772723
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141467"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a><span data-ttu-id="e0450-102">Практическое руководство. Добавление настраиваемых методов для запросов LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="e0450-102">How to add custom methods for LINQ queries (C#)</span></span>

<span data-ttu-id="e0450-103">Вы можете расширить набор методов, которые можно использовать для запросов LINQ, путем добавления методов расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e0450-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="e0450-104">Например, помимо стандартных операций вычисления среднего или максимального значения, можно создать настраиваемый метод агрегирования для вычисления одного значения на основе последовательности значений.</span><span class="sxs-lookup"><span data-stu-id="e0450-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="e0450-105">Также можно создать метод, который работает как настраиваемый фильтр или особое преобразование данных для последовательности значений и возвращает новую последовательность.</span><span class="sxs-lookup"><span data-stu-id="e0450-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="e0450-106">Примерами таких методов являются <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> и <xref:System.Linq.Enumerable.Reverse%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0450-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="e0450-107">При расширении интерфейса <xref:System.Collections.Generic.IEnumerable%601> настраиваемые методы можно применять к любой перечислимой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e0450-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="e0450-108">Дополнительные сведения см. в разделе [Методы расширения](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e0450-108">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="e0450-109">Использование метода агрегирования</span><span class="sxs-lookup"><span data-stu-id="e0450-109">Adding an Aggregate Method</span></span>

<span data-ttu-id="e0450-110">Метод агрегирования вычисляет одно значение на основе набора значений.</span><span class="sxs-lookup"><span data-stu-id="e0450-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="e0450-111">LINQ реализует несколько методов агрегирования, включая <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0450-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="e0450-112">Вы можете создать собственный метод агрегирования, добавив метод расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e0450-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="e0450-113">В следующем примере кода показано, как создать метод расширения `Median` для вычисления срединного значения последовательности чисел типа `double`.</span><span class="sxs-lookup"><span data-stu-id="e0450-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

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

<span data-ttu-id="e0450-114">Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы агрегирования из интерфейса <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e0450-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="e0450-115">В следующем примере кода показано использование метода `Median` для массива типа `double`.</span><span class="sxs-lookup"><span data-stu-id="e0450-115">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

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

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="e0450-116">Перегрузка метода агрегирования для принятия различных типов</span><span class="sxs-lookup"><span data-stu-id="e0450-116">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="e0450-117">Метод агрегирования можно перегрузить, чтобы он принимал последовательности различных типов.</span><span class="sxs-lookup"><span data-stu-id="e0450-117">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="e0450-118">Стандартный способ — создание перегрузки для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="e0450-118">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="e0450-119">Другой подход заключается в создании перегрузки, которая будет принимать универсальный тип и преобразовывать его в конкретный тип с помощью делегата.</span><span class="sxs-lookup"><span data-stu-id="e0450-119">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="e0450-120">Вы можете сочетать оба способа.</span><span class="sxs-lookup"><span data-stu-id="e0450-120">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="e0450-121">Создание перегрузки для каждого типа</span><span class="sxs-lookup"><span data-stu-id="e0450-121">To create an overload for each type</span></span>

<span data-ttu-id="e0450-122">Вы можете создать конкретную перегрузку для каждого типа, который требуется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="e0450-122">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="e0450-123">В следующем примере кода показана перегрузка метода `Median` для типа `integer`.</span><span class="sxs-lookup"><span data-stu-id="e0450-123">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

```csharp
//int overload

public static double Median(this IEnumerable<int> source)
{
    return (from num in source select (double)num).Median();
}
```

<span data-ttu-id="e0450-124">Теперь можно вызвать перегрузки `Median` для типов `integer` и `double`, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="e0450-124">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

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

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="e0450-125">Создание универсальной перегрузки</span><span class="sxs-lookup"><span data-stu-id="e0450-125">To create a generic overload</span></span>

<span data-ttu-id="e0450-126">Вы также можете создать перегрузку, которая принимает последовательность универсальных объектов.</span><span class="sxs-lookup"><span data-stu-id="e0450-126">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="e0450-127">Эта перегрузка принимает делегат в качестве параметра и использует его для преобразования последовательности объектов универсального типа в конкретный тип.</span><span class="sxs-lookup"><span data-stu-id="e0450-127">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="e0450-128">В следующем примере кода демонстрируется перегрузка метода `Median`, принимающая делегат <xref:System.Func%602> в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="e0450-128">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="e0450-129">Этот делегат принимает объект универсального типа T и возвращает объект типа `double`.</span><span class="sxs-lookup"><span data-stu-id="e0450-129">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

```csharp
// Generic overload.

public static double Median<T>(this IEnumerable<T> numbers,
                       Func<T, double> selector)
{
    return (from num in numbers select selector(num)).Median();
}
```

<span data-ttu-id="e0450-130">Теперь вы можете вызвать метод `Median` для последовательности объектов любого типа.</span><span class="sxs-lookup"><span data-stu-id="e0450-130">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="e0450-131">Если тип не содержит собственную перегрузку метода, вам потребуется передать параметр делегата.</span><span class="sxs-lookup"><span data-stu-id="e0450-131">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="e0450-132">В C# для этой цели можно использовать лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="e0450-132">In C#, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="e0450-133">Кроме того, только в Visual Basic, если вы используете предложение `Aggregate` или `Group By` вместо вызова метода, вы можете передать любое значение или выражение, которое находится в области этого предложения.</span><span class="sxs-lookup"><span data-stu-id="e0450-133">Also, in Visual Basic only, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="e0450-134">В следующем примере кода показано, как вызвать метод `Median` для массива целых чисел и массива строк.</span><span class="sxs-lookup"><span data-stu-id="e0450-134">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="e0450-135">Для строк вычисляется срединное значение длин строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="e0450-135">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="e0450-136">В примере демонстрируется передача параметра делегата <xref:System.Func%602> в метод `Median` для каждого из случаев.</span><span class="sxs-lookup"><span data-stu-id="e0450-136">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

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

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="e0450-137">Добавление метода, возвращающего коллекцию</span><span class="sxs-lookup"><span data-stu-id="e0450-137">Adding a Method That Returns a Collection</span></span>

<span data-ttu-id="e0450-138">Вы можете расширить интерфейс <xref:System.Collections.Generic.IEnumerable%601> с помощью метода настраиваемого запроса, который возвращает последовательность значений.</span><span class="sxs-lookup"><span data-stu-id="e0450-138">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="e0450-139">В этом случае метод должен возвращать коллекцию типа <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e0450-139">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e0450-140">Такие методы можно использовать для применения фильтров или преобразований данных к последовательности значений.</span><span class="sxs-lookup"><span data-stu-id="e0450-140">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="e0450-141">В следующем примере показано, как создать метод расширения с именем `AlternateElements`, который возвращает каждый второй элемент в коллекции, начиная с первого элемента.</span><span class="sxs-lookup"><span data-stu-id="e0450-141">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

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

<span data-ttu-id="e0450-142">Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы из интерфейса <xref:System.Collections.Generic.IEnumerable%601>, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="e0450-142">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e0450-143">См. также</span><span class="sxs-lookup"><span data-stu-id="e0450-143">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="e0450-144">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="e0450-144">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
