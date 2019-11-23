---
title: Коллекции
ms.date: 07/20/2015
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
ms.openlocfilehash: ba16d04e781bcf69356b1f603d92e104816a0860
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347095"
---
# <a name="collections-visual-basic"></a>Collections (Visual Basic)

Во многих приложениях требуется создавать группы связанных объектов и управлять ими. Существует два способа группировки объектов: создать массив объектов и создать коллекцию.

Массивы удобнее всего использовать для создания и работы с фиксированным числом строго типизированных объектов. Информацию о массивах см. в разделе [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).

Коллекции предоставляют более гибкий способ работы с группами объектов. В отличие от массивов, коллекция, с которой вы работаете, может расти или уменьшаться динамически при необходимости. Некоторые коллекции допускают назначение ключа любому объекту, который добавляется в коллекцию, чтобы в дальнейшем можно было быстро извлечь связанный с ключом объект из коллекции.

Коллекция является классом, поэтому необходимо объявить экземпляр класса перед добавлением в коллекцию элементов.

Если коллекция содержит элементы только одного типа данных, можно использовать один из классов в пространстве имен <xref:System.Collections.Generic?displayProperty=nameWithType>. Универсальная коллекция обеспечивает строгую типизацию, так что в нее нельзя добавить другие типы данных. При извлечении элемента из универсальной коллекции не нужно определять или преобразовывать его тип данных.

> [!NOTE]
> For the examples in this topic, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections.Generic` and `System.Linq` namespaces.

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a>Использование простой коллекции

В примерах этого раздела используется универсальный класс <xref:System.Collections.Generic.List%601>, который позволяет работать со строго типизированными списками объектов.

The following example creates a list of strings and then iterates through the strings by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.

```vb
' Create a list of strings.
Dim salmons As New List(Of String)
salmons.Add("chinook")
salmons.Add("coho")
salmons.Add("pink")
salmons.Add("sockeye")

' Iterate through the list.
For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook coho pink sockeye
```

Если содержимое коллекции известно заранее, для ее инициализации можно использовать *инициализатор коллекции*. Дополнительные сведения см. в разделе [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

Следующий пример аналогичен предыдущему за исключением того, что для добавления элементов в коллекцию используется инициализатор коллекции.

```vb
' Create a list of strings by using a
' collection initializer.
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook coho pink sockeye
```

You can use a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement instead of a `For Each` statement to iterate through a collection. Для этого доступ к элементам коллекции осуществляется по позиции индекса. Индекс элементов начинается с 0 и заканчивается числом, равным количеству элементов минус 1.

В приведенном ниже примере выполняется перебор элементов коллекции с помощью оператора `For…Next` вместо `For Each`.

```vb
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For index = 0 To salmons.Count - 1
    Console.Write(salmons(index) & " ")
Next
'Output: chinook coho pink sockeye
```

В приведенном ниже примере элемент удаляется из коллекции путем указания удаляемого объекта.

```vb
' Create a list of strings by using a
' collection initializer.
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

' Remove an element in the list by specifying
' the object.
salmons.Remove("coho")

For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook pink sockeye
```

В приведенном ниже примере удаляются элементы из универсального списка. Instead of a `For Each` statement, a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement that iterates in descending order is used. Связано это с тем, что в результате работы метода <xref:System.Collections.Generic.List%601.RemoveAt%2A> элементы, следующие за удаленным элементом, получают меньшее значение индекса.

```vb
Dim numbers As New List(Of Integer) From
    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}

' Remove odd numbers.
For index As Integer = numbers.Count - 1 To 0 Step -1
    If numbers(index) Mod 2 = 1 Then
        ' Remove the element by specifying
        ' the zero-based index in the list.
        numbers.RemoveAt(index)
    End If
Next

' Iterate through the list.
' A lambda expression is placed in the ForEach method
' of the List(T) object.
numbers.ForEach(
    Sub(number) Console.Write(number & " "))
' Output: 0 2 4 6 8
```

Для типа элементов в <xref:System.Collections.Generic.List%601> можно также определить собственный класс. В приведенном ниже примере класс `Galaxy`, который используется объектом <xref:System.Collections.Generic.List%601>, определен в коде.

```vb
Private Sub IterateThroughList()
    Dim theGalaxies As New List(Of Galaxy) From
        {
            New Galaxy With {.Name = "Tadpole", .MegaLightYears = 400},
            New Galaxy With {.Name = "Pinwheel", .MegaLightYears = 25},
            New Galaxy With {.Name = "Milky Way", .MegaLightYears = 0},
            New Galaxy With {.Name = "Andromeda", .MegaLightYears = 3}
        }

    For Each theGalaxy In theGalaxies
        With theGalaxy
            Console.WriteLine(.Name & "  " & .MegaLightYears)
        End With
    Next

    ' Output:
    '  Tadpole  400
    '  Pinwheel  25
    '  Milky Way  0
    '  Andromeda  3
End Sub

Public Class Galaxy
    Public Property Name As String
    Public Property MegaLightYears As Integer
End Class
```

<a name="BKMK_KindsOfCollections"></a>

## <a name="kinds-of-collections"></a>Виды коллекций

Многие типовые коллекции предоставляются платформой .NET Framework. Каждый тип коллекции предназначен для определенной цели.

В этом разделе описываются следующие часто используемые классы коллекций:

- Классы <xref:System.Collections.Generic>

- Классы <xref:System.Collections.Concurrent>

- Классы <xref:System.Collections>

- класс `Collection` в Visual Basic.

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a>Классы System.Collections.Generic

Универсальную коллекцию можно создать, используя один из классов в пространстве имен <xref:System.Collections.Generic>. Универсальная коллекция применяется в том случае, если все элементы в коллекции имеют одинаковый тип данных. Универсальная коллекция обеспечивает строгую типизацию, позволяя добавлять данные только необходимого типа.

В таблице ниже перечислены некоторые из часто используемых классов пространства имен <xref:System.Collections.Generic?displayProperty=nameWithType>.

|Class|Описание|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|Предоставляет коллекцию пар «ключ-значение», которые упорядочены по ключу.|
|<xref:System.Collections.Generic.List%601>|Представляет список объектов, доступных по индексу. Предоставляет методы для поиска по списку, его сортировки и изменения.|
|<xref:System.Collections.Generic.Queue%601>|Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).|
|<xref:System.Collections.Generic.SortedList%602>|Представляет коллекцию пар "ключ-значение", упорядоченных по ключу на основе реализации <xref:System.Collections.Generic.IComparer%601>.|
|<xref:System.Collections.Generic.Stack%601>|Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).|

Дополнительные сведения см. в разделе [Часто используемые типы коллекций](../../../standard/collections/commonly-used-collection-types.md), [Выбор класса коллекции](../../../standard/collections/selecting-a-collection-class.md) и <xref:System.Collections.Generic?displayProperty=nameWithType>.

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a>Классы System.Collections.Concurrent

В .NET Framework 4 или более поздней версии коллекции пространства имен <xref:System.Collections.Concurrent> предоставляют эффективные потокобезопасные операции для доступа к элементам коллекции из нескольких потоков.

Классы пространства имен <xref:System.Collections.Concurrent> следует использовать вместо соответствующих типов пространств имен <xref:System.Collections.Generic?displayProperty=nameWithType> и <xref:System.Collections?displayProperty=nameWithType>, если несколько потоков параллельно обращаются к такой коллекции. Дополнительные сведения см. в статьях [Потокобезопасные коллекции](../../../standard/collections/thread-safe/index.md) и <xref:System.Collections.Concurrent>.

Некоторые из классов, входящих в пространство имен <xref:System.Collections.Concurrent>, — это <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a>Классы System.Collections

Классы в пространстве имен <xref:System.Collections?displayProperty=nameWithType> хранят элементы не в виде конкретно типизированных объектов, а как объекты типа `Object`.

Везде, где это возможно, следует использовать универсальные коллекции пространства имен <xref:System.Collections.Generic?displayProperty=nameWithType> или пространства имен <xref:System.Collections.Concurrent> вместо устаревших типов пространства имен `System.Collections`.

В следующей таблице перечислены некоторые из часто используемых классов пространства имен `System.Collections`:

|Class|Описание|
|---|---|
|<xref:System.Collections.ArrayList>|Представляет массив объектов, размер которого динамически увеличивается по мере необходимости.|
|<xref:System.Collections.Hashtable>|Представляет коллекцию пар «ключ-значение», которые упорядочены по хэш-коду ключа.|
|<xref:System.Collections.Queue>|Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).|
|<xref:System.Collections.Stack>|Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).|

Пространство имен <xref:System.Collections.Specialized> предоставляет специализированные и строго типизированные классы коллекций, такие как коллекции строк, связанные списки и гибридные словари.

<a name="BKMK_VisualBasic"></a>

### <a name="visual-basic-collection-class"></a>Класс Collection в Visual Basic

Класс <xref:Microsoft.VisualBasic.Collection> в Visual Basic можно использовать для доступа к элементу коллекции по числовому индексу или ключу `String`. Элементы можно добавлять в объект коллекции с указанием или без указания ключа. Если добавить объект без ключа, необходимо использовать его числовой индекс для доступа к нему.

Класс `Collection` в Visual Basic хранит все свои элементы как тип `Object`, поэтому можно добавить элемент любого типа данных. Нет никакой защиты от добавления неподходящих типов данных.

При использовании класса `Collection` в Visual Basic первый элемент в коллекции имеет индекс 1. Этим он отличается от классов коллекций платформы .NET Framework, для которых начальный индекс равен 0.

Везде, где это возможно, следует использовать универсальные коллекции в пространстве имен <xref:System.Collections.Generic?displayProperty=nameWithType> или пространстве имен <xref:System.Collections.Concurrent> вместо класса `Collection` в Visual Basic.

Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Collection>.

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a>Реализация коллекции пар «ключ-значение»

Универсальная коллекция <xref:System.Collections.Generic.Dictionary%602> позволяет получить доступ к элементам коллекции с помощью ключа каждого элемента. Каждый элемент, добавляемый в словарь, состоит из значения и связанного с ним ключа. Извлечение значения по его ключу происходит быстро, так как класс `Dictionary` реализован как хэш-таблица.

В приведенном ниже примере создается коллекция `Dictionary` и выполняется перебор словаря с помощью оператора `For Each`.

```vb
Private Sub IterateThroughDictionary()
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    For Each kvp As KeyValuePair(Of String, Element) In elements
        Dim theElement As Element = kvp.Value

        Console.WriteLine("key: " & kvp.Key)
        With theElement
            Console.WriteLine("values: " & .Symbol & " " &
                .Name & " " & .AtomicNumber)
        End With
    Next
End Sub

Private Function BuildDictionary() As Dictionary(Of String, Element)
    Dim elements As New Dictionary(Of String, Element)

    AddToDictionary(elements, "K", "Potassium", 19)
    AddToDictionary(elements, "Ca", "Calcium", 20)
    AddToDictionary(elements, "Sc", "Scandium", 21)
    AddToDictionary(elements, "Ti", "Titanium", 22)

    Return elements
End Function

Private Sub AddToDictionary(ByVal elements As Dictionary(Of String, Element),
ByVal symbol As String, ByVal name As String, ByVal atomicNumber As Integer)
    Dim theElement As New Element

    theElement.Symbol = symbol
    theElement.Name = name
    theElement.AtomicNumber = atomicNumber

    elements.Add(Key:=theElement.Symbol, value:=theElement)
End Sub

Public Class Element
    Public Property Symbol As String
    Public Property Name As String
    Public Property AtomicNumber As Integer
End Class
```

Чтобы вместо этого использовать инициализатор коллекции для создания коллекции `Dictionary`, можно заменить методы `BuildDictionary` и `AddToDictionary` приведенным ниже методом.

```vb
Private Function BuildDictionary2() As Dictionary(Of String, Element)
    Return New Dictionary(Of String, Element) From
        {
            {"K", New Element With
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},
            {"Ca", New Element With
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},
            {"Sc", New Element With
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},
            {"Ti", New Element With
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}
        }
End Function
```

В приведенном ниже примере используется метод <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> и свойство <xref:System.Collections.Generic.Dictionary%602.Item%2A> `Dictionary` для быстрого поиска элемента по ключу. The `Item` property enables you to access an item in the `elements` collection by using the `elements(symbol)` code in Visual Basic.

```vb
Private Sub FindInDictionary(ByVal symbol As String)
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    If elements.ContainsKey(symbol) = False Then
        Console.WriteLine(symbol & " not found")
    Else
        Dim theElement = elements(symbol)
        Console.WriteLine("found: " & theElement.Name)
    End If
End Sub
```

В приведенном ниже примере вместо этого используется метод <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> для быстрого поиска элемента по ключу.

```vb
Private Sub FindInDictionary2(ByVal symbol As String)
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    Dim theElement As Element = Nothing
    If elements.TryGetValue(symbol, theElement) = False Then
        Console.WriteLine(symbol & " not found")
    Else
        Console.WriteLine("found: " & theElement.Name)
    End If
End Sub
```

<a name="BKMK_LINQ"></a>

## <a name="using-linq-to-access-a-collection"></a>Использование LINQ для доступа к коллекции

Для доступа к коллекции можно использовать язык LINQ. Запросы LINQ обеспечивают возможности фильтрации, упорядочения и группировки. For more information, see [Getting Started with LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).

В приведенном ниже примере выполняется запрос LINQ применительно к универсальной коллекции `List`. Запрос LINQ возвращает другую коллекцию, содержащую результаты.

```vb
Private Sub ShowLINQ()
    Dim elements As List(Of Element) = BuildList()

    ' LINQ Query.
    Dim subset = From theElement In elements
                  Where theElement.AtomicNumber < 22
                  Order By theElement.Name

    For Each theElement In subset
        Console.WriteLine(theElement.Name & " " & theElement.AtomicNumber)
    Next

    ' Output:
    '  Calcium 20
    '  Potassium 19
    '  Scandium 21
End Sub

Private Function BuildList() As List(Of Element)
    Return New List(Of Element) From
        {
            {New Element With
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},
            {New Element With
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},
            {New Element With
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},
            {New Element With
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}
        }
End Function

Public Class Element
    Public Property Symbol As String
    Public Property Name As String
    Public Property AtomicNumber As Integer
End Class
```

<a name="BKMK_Sorting"></a>

## <a name="sorting-a-collection"></a>Сортировка коллекции

Приведенный ниже пример демонстрирует процедуру сортировки коллекции. В примере сортируются экземпляры класса `Car`, которые хранятся в <xref:System.Collections.Generic.List%601>. Класс `Car` реализует интерфейс <xref:System.IComparable%601>, который требует реализации метода <xref:System.IComparable%601.CompareTo%2A>.

Каждый вызов метода <xref:System.IComparable%601.CompareTo%2A> выполняет одно сравнение, используемое для сортировки. Написанный пользователем код в методе `CompareTo` возвращает значение для каждого сравнения текущего объекта с другим объектом. Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны. Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».

В методе `ListCars` оператор `cars.Sort()` сортирует список. Этот вызов метода <xref:System.Collections.Generic.List%601.Sort%2A> <xref:System.Collections.Generic.List%601> приводит к тому, что метод `CompareTo` вызывается автоматически для объектов `Car` в `List`.

```vb
Public Sub ListCars()

    ' Create some new cars.
    Dim cars As New List(Of Car) From
    {
        New Car With {.Name = "car1", .Color = "blue", .Speed = 20},
        New Car With {.Name = "car2", .Color = "red", .Speed = 50},
        New Car With {.Name = "car3", .Color = "green", .Speed = 10},
        New Car With {.Name = "car4", .Color = "blue", .Speed = 50},
        New Car With {.Name = "car5", .Color = "blue", .Speed = 30},
        New Car With {.Name = "car6", .Color = "red", .Speed = 60},
        New Car With {.Name = "car7", .Color = "green", .Speed = 50}
    }

    ' Sort the cars by color alphabetically, and then by speed
    ' in descending order.
    cars.Sort()

    ' View all of the cars.
    For Each thisCar As Car In cars
        Console.Write(thisCar.Color.PadRight(5) & " ")
        Console.Write(thisCar.Speed.ToString & " ")
        Console.Write(thisCar.Name)
        Console.WriteLine()
    Next

    ' Output:
    '  blue  50 car4
    '  blue  30 car5
    '  blue  20 car1
    '  green 50 car7
    '  green 10 car3
    '  red   60 car6
    '  red   50 car2
End Sub

Public Class Car
    Implements IComparable(Of Car)

    Public Property Name As String
    Public Property Speed As Integer
    Public Property Color As String

    Public Function CompareTo(ByVal other As Car) As Integer _
        Implements System.IComparable(Of Car).CompareTo
        ' A call to this method makes a single comparison that is
        ' used for sorting.

        ' Determine the relative order of the objects being compared.
        ' Sort by color alphabetically, and then by speed in
        ' descending order.

        ' Compare the colors.
        Dim compare As Integer
        compare = String.Compare(Me.Color, other.Color, True)

        ' If the colors are the same, compare the speeds.
        If compare = 0 Then
            compare = Me.Speed.CompareTo(other.Speed)

            ' Use descending order for speed.
            compare = -compare
        End If

        Return compare
    End Function
End Class
```

<a name="BKMK_CustomCollection"></a>

## <a name="defining-a-custom-collection"></a>Определение настраиваемой коллекции

Вы можете определить коллекцию, реализовав интерфейс <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Collections.IEnumerable>. For additional information, see [Enumerating a Collection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hwyysy67(v=vs.100)).

Хотя можно определить настраиваемую коллекцию, обычно лучше использовать коллекции, входящие в .NET Framework, которые описаны в подразделе [Виды коллекций](#kinds-of-collections) ранее в этом разделе.

В приведенном ниже примере определяется настраиваемый класс коллекции с именем `AllColors`. Этот класс реализует интерфейс <xref:System.Collections.IEnumerable>, который требует реализации метода <xref:System.Collections.IEnumerable.GetEnumerator%2A>.

Метод `GetEnumerator` возвращает экземпляр класса `ColorEnumerator`. Класс `ColorEnumerator` реализует интерфейс <xref:System.Collections.IEnumerator>, который требует реализации свойства <xref:System.Collections.IEnumerator.Current%2A>, метода <xref:System.Collections.IEnumerator.MoveNext%2A> и метода <xref:System.Collections.IEnumerator.Reset%2A>.

```vb
Public Sub ListColors()
    Dim colors As New AllColors()

    For Each theColor As Color In colors
        Console.Write(theColor.Name & " ")
    Next
    Console.WriteLine()
    ' Output: red blue green
End Sub

' Collection class.
Public Class AllColors
    Implements System.Collections.IEnumerable

    Private _colors() As Color =
    {
        New Color With {.Name = "red"},
        New Color With {.Name = "blue"},
        New Color With {.Name = "green"}
    }

    Public Function GetEnumerator() As System.Collections.IEnumerator _
        Implements System.Collections.IEnumerable.GetEnumerator

        Return New ColorEnumerator(_colors)

        ' Instead of creating a custom enumerator, you could
        ' use the GetEnumerator of the array.
        'Return _colors.GetEnumerator
    End Function

    ' Custom enumerator.
    Private Class ColorEnumerator
        Implements System.Collections.IEnumerator

        Private _colors() As Color
        Private _position As Integer = -1

        Public Sub New(ByVal colors() As Color)
            _colors = colors
        End Sub

        Public ReadOnly Property Current() As Object _
            Implements System.Collections.IEnumerator.Current
            Get
                Return _colors(_position)
            End Get
        End Property

        Public Function MoveNext() As Boolean _
            Implements System.Collections.IEnumerator.MoveNext
            _position += 1
            Return (_position < _colors.Length)
        End Function

        Public Sub Reset() Implements System.Collections.IEnumerator.Reset
            _position = -1
        End Sub
    End Class
End Class

' Element class.
Public Class Color
    Public Property Name As String
End Class
```

<a name="BKMK_Iterators"></a>

## <a name="iterators"></a>Iterators

*Итератор* используется для выполнения настраиваемого перебора коллекции. Итератор может быть методом или методом доступа `get`. An iterator uses a [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element of the collection one at a time.

You call an iterator by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement. Каждая итерация цикла `For Each` вызывает итератор. При достижении оператора `Yield` в итераторе возвращается выражение, и текущее расположение в коде сохраняется. При следующем вызове итератора выполнение возобновляется с этого места.

For more information, see [Iterators (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).

В приведенном ниже примере используется метод-итератор. The iterator method has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop. В методе `ListEvenNumbers` каждая итерация тела оператора `For Each` создает вызов метода-итератора, который переходит к следующему оператору `Yield`.

```vb
Public Sub ListEvenNumbers()
    For Each number As Integer In EvenSequence(5, 18)
        Console.Write(number & " ")
    Next
    Console.WriteLine()
    ' Output: 6 8 10 12 14 16 18
End Sub

Private Iterator Function EvenSequence(
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _
As IEnumerable(Of Integer)

' Yield even numbers in the range.
    For number = firstNumber To lastNumber
        If number Mod 2 = 0 Then
            Yield number
        End If
    Next
End Function
```

## <a name="see-also"></a>См. также

- [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Основные понятия программирования (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)
- [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [Parallel LINQ (PLINQ)](../../../standard/parallel-programming/parallel-linq-plinq.md)
- [Коллекции и структуры данных](../../../standard/collections/index.md)
- [Выбор класса коллекции](../../../standard/collections/selecting-a-collection-class.md)
- [Сравнение и сортировка в коллекциях](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [Когда следует использовать универсальные коллекции](../../../standard/collections/when-to-use-generic-collections.md)
