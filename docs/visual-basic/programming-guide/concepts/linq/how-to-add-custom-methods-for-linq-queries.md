---
title: Практическое руководство. Добавление настраиваемых методов для запросов LINQ
ms.date: 07/20/2015
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
ms.openlocfilehash: 3004a9c9c7abeffd9993b848ad765e7ae2dc8876
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353376"
---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="e3fa2-102">Как добавить пользовательские методы для запросов LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3fa2-102">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>

<span data-ttu-id="e3fa2-103">Вы можете расширить набор методов, которые можно использовать для запросов LINQ, путем добавления методов расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="e3fa2-104">Например, помимо стандартных операций вычисления среднего или максимального значения, можно создать настраиваемый метод агрегирования для вычисления одного значения на основе последовательности значений.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="e3fa2-105">Также можно создать метод, который работает как настраиваемый фильтр или особое преобразование данных для последовательности значений и возвращает новую последовательность.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="e3fa2-106">Примерами таких методов являются <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> и <xref:System.Linq.Enumerable.Reverse%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="e3fa2-107">При расширении интерфейса <xref:System.Collections.Generic.IEnumerable%601> настраиваемые методы можно применять к любой перечислимой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="e3fa2-108">Дополнительные сведения см. в статье [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e3fa2-108">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="e3fa2-109">Использование метода агрегирования</span><span class="sxs-lookup"><span data-stu-id="e3fa2-109">Adding an Aggregate Method</span></span>

<span data-ttu-id="e3fa2-110">Метод агрегирования вычисляет одно значение на основе набора значений.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="e3fa2-111">LINQ реализует несколько методов агрегирования, включая <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="e3fa2-112">Вы можете создать собственный метод агрегирования, добавив метод расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="e3fa2-113">В следующем примере кода показано, как создать метод расширения `Median` для вычисления срединного значения последовательности чисел типа `double`.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module LINQExtension

    ' Extension method for the IEnumerable(of T) interface.
    ' The method accepts only values of the Double type.
    <Extension()>
    Function Median(ByVal source As IEnumerable(Of Double)) As Double
        If source.Count = 0 Then
            Throw New InvalidOperationException("Cannot compute median for an empty set.")
        End If

        Dim sortedSource = From number In source
                           Order By number

        Dim itemIndex = sortedSource.Count \ 2

        If sortedSource.Count Mod 2 = 0 Then
            ' Even number of items in list.
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2
        Else
            ' Odd number of items in list.
            Return sortedSource(itemIndex)
        End If
    End Function
End Module
```

<span data-ttu-id="e3fa2-114">Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы агрегирования из интерфейса <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

> [!NOTE]
> <span data-ttu-id="e3fa2-115">В Visual Basic можно либо использовать вызов метода, либо стандартный синтаксис запроса для `Aggregate` или предложения `Group By`.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-115">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="e3fa2-116">Дополнительные сведения см. в разделе [предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение GROUP BY](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e3fa2-116">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>

<span data-ttu-id="e3fa2-117">В следующем примере кода показано использование метода `Median` для массива типа `double`.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-117">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

```vb
Dim numbers1() As Double = {1.9, 2, 8, 4, 5.7, 6, 7.2, 0}

Dim query1 = Aggregate num In numbers1 Into Median()

Console.WriteLine("Double: Median = " & query1)
```

```vb
' This code produces the following output:
'
' Double: Median = 4.85
```

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="e3fa2-118">Перегрузка метода агрегирования для принятия различных типов</span><span class="sxs-lookup"><span data-stu-id="e3fa2-118">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="e3fa2-119">Метод агрегирования можно перегрузить, чтобы он принимал последовательности различных типов.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-119">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="e3fa2-120">Стандартный способ — создание перегрузки для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-120">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="e3fa2-121">Другой подход заключается в создании перегрузки, которая будет принимать универсальный тип и преобразовывать его в конкретный тип с помощью делегата.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-121">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="e3fa2-122">Вы можете сочетать оба способа.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-122">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="e3fa2-123">Создание перегрузки для каждого типа</span><span class="sxs-lookup"><span data-stu-id="e3fa2-123">To create an overload for each type</span></span>

<span data-ttu-id="e3fa2-124">Вы можете создать конкретную перегрузку для каждого типа, который требуется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-124">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="e3fa2-125">В следующем примере кода показана перегрузка метода `Median` для типа `integer`.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-125">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

```vb
' Integer overload

<Extension()>
Function Median(ByVal source As IEnumerable(Of Integer)) As Double
    Return Aggregate num In source Select CDbl(num) Into med = Median()
End Function
```

<span data-ttu-id="e3fa2-126">Теперь можно вызвать перегрузки `Median` для типов `integer` и `double`, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="e3fa2-126">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

```vb
Dim numbers1() As Double = {1.9, 2, 8, 4, 5.7, 6, 7.2, 0}

Dim query1 = Aggregate num In numbers1 Into Median()

Console.WriteLine("Double: Median = " & query1)
```

```vb
Dim numbers2() As Integer = {1, 2, 3, 4, 5}

Dim query2 = Aggregate num In numbers2 Into Median()

Console.WriteLine("Integer: Median = " & query2)
```

```vb
' This code produces the following output:
'
' Double: Median = 4.85
' Integer: Median = 3
```

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="e3fa2-127">Создание универсальной перегрузки</span><span class="sxs-lookup"><span data-stu-id="e3fa2-127">To create a generic overload</span></span>

<span data-ttu-id="e3fa2-128">Вы также можете создать перегрузку, которая принимает последовательность универсальных объектов.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-128">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="e3fa2-129">Эта перегрузка принимает делегат в качестве параметра и использует его для преобразования последовательности объектов универсального типа в конкретный тип.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-129">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="e3fa2-130">В следующем примере кода демонстрируется перегрузка метода `Median`, принимающая делегат <xref:System.Func%602> в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-130">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="e3fa2-131">Этот делегат принимает объект универсального типа T и возвращает объект типа `double`.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-131">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

```vb
' Generic overload.

<Extension()>
Function Median(Of T)(ByVal source As IEnumerable(Of T),
                      ByVal selector As Func(Of T, Double)) As Double
    Return Aggregate num In source Select selector(num) Into med = Median()
End Function
```

<span data-ttu-id="e3fa2-132">Теперь вы можете вызвать метод `Median` для последовательности объектов любого типа.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-132">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="e3fa2-133">Если тип не содержит собственную перегрузку метода, вам потребуется передать параметр делегата.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-133">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="e3fa2-134">В Visual Basic для этой цели можно использовать лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-134">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="e3fa2-135">Кроме того, если вместо вызова метода используется предложение `Aggregate` или `Group By`, можно передать любое значение или выражение, которое находится в области данного предложения.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-135">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="e3fa2-136">В следующем примере кода показано, как вызвать метод `Median` для массива целых чисел и массива строк.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-136">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="e3fa2-137">Для строк вычисляется срединное значение длин строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-137">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="e3fa2-138">В примере демонстрируется передача параметра делегата <xref:System.Func%602> в метод `Median` для каждого из случаев.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-138">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

```vb
Dim numbers3() As Integer = {1, 2, 3, 4, 5}

' You can use num as a parameter for the Median method
' so that the compiler will implicitly convert its value to double.
' If there is no implicit conversion, the compiler will
' display an error message.

Dim query3 = Aggregate num In numbers3 Into Median(num)

Console.WriteLine("Integer: Median = " & query3)

Dim numbers4() As String = {"one", "two", "three", "four", "five"}

' With the generic overload, you can also use numeric properties of objects.

Dim query4 = Aggregate str In numbers4 Into Median(str.Length)

Console.WriteLine("String: Median = " & query4)

' This code produces the following output:
'
' Integer: Median = 3
' String: Median = 4
```

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="e3fa2-139">Добавление метода, возвращающего коллекцию</span><span class="sxs-lookup"><span data-stu-id="e3fa2-139">Adding a Method That Returns a Collection</span></span>

<span data-ttu-id="e3fa2-140">Вы можете расширить интерфейс <xref:System.Collections.Generic.IEnumerable%601> с помощью метода настраиваемого запроса, который возвращает последовательность значений.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-140">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="e3fa2-141">В этом случае метод должен возвращать коллекцию типа <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-141">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e3fa2-142">Такие методы можно использовать для применения фильтров или преобразований данных к последовательности значений.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-142">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="e3fa2-143">В следующем примере показано, как создать метод расширения с именем `AlternateElements`, который возвращает каждый второй элемент в коллекции, начиная с первого элемента.</span><span class="sxs-lookup"><span data-stu-id="e3fa2-143">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

```vb
' Extension method for the IEnumerable(of T) interface.
' The method returns every other element of a sequence.

<Extension()>
Function AlternateElements(Of T)(
    ByVal source As IEnumerable(Of T)
    ) As IEnumerable(Of T)

    Dim list As New List(Of T)
    Dim i = 0
    For Each element In source
        If (i Mod 2 = 0) Then
            list.Add(element)
        End If
        i = i + 1
    Next
    Return list
End Function
```

<span data-ttu-id="e3fa2-144">Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы из интерфейса <xref:System.Collections.Generic.IEnumerable%601>, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="e3fa2-144">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

```vb
Dim strings() As String = {"a", "b", "c", "d", "e"}

Dim query = strings.AlternateElements()

For Each element In query
    Console.WriteLine(element)
Next

' This code produces the following output:
'
' a
' c
' e
```

## <a name="see-also"></a><span data-ttu-id="e3fa2-145">См. также</span><span class="sxs-lookup"><span data-stu-id="e3fa2-145">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="e3fa2-146">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="e3fa2-146">Extension Methods</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
