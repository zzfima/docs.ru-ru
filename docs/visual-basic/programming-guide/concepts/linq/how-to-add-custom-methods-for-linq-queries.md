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
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a>Как добавить пользовательские методы для запросов LINQ (Visual Basic)

Вы можете расширить набор методов, которые можно использовать для запросов LINQ, путем добавления методов расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>. Например, помимо стандартных операций вычисления среднего или максимального значения, можно создать настраиваемый метод агрегирования для вычисления одного значения на основе последовательности значений. Также можно создать метод, который работает как настраиваемый фильтр или особое преобразование данных для последовательности значений и возвращает новую последовательность. Примерами таких методов являются <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> и <xref:System.Linq.Enumerable.Reverse%2A>.

При расширении интерфейса <xref:System.Collections.Generic.IEnumerable%601> настраиваемые методы можно применять к любой перечислимой коллекции. Дополнительные сведения см. в статье [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).

## <a name="adding-an-aggregate-method"></a>Использование метода агрегирования

Метод агрегирования вычисляет одно значение на основе набора значений. LINQ реализует несколько методов агрегирования, включая <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Max%2A>. Вы можете создать собственный метод агрегирования, добавив метод расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.

В следующем примере кода показано, как создать метод расширения `Median` для вычисления срединного значения последовательности чисел типа `double`.

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

Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы агрегирования из интерфейса <xref:System.Collections.Generic.IEnumerable%601>.

> [!NOTE]
> В Visual Basic можно либо использовать вызов метода, либо стандартный синтаксис запроса для `Aggregate` или предложения `Group By`. Дополнительные сведения см. в разделе [предложение Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение GROUP BY](../../../../visual-basic/language-reference/queries/group-by-clause.md).

В следующем примере кода показано использование метода `Median` для массива типа `double`.

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

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Перегрузка метода агрегирования для принятия различных типов

Метод агрегирования можно перегрузить, чтобы он принимал последовательности различных типов. Стандартный способ — создание перегрузки для каждого типа. Другой подход заключается в создании перегрузки, которая будет принимать универсальный тип и преобразовывать его в конкретный тип с помощью делегата. Вы можете сочетать оба способа.

#### <a name="to-create-an-overload-for-each-type"></a>Создание перегрузки для каждого типа

Вы можете создать конкретную перегрузку для каждого типа, который требуется поддерживать. В следующем примере кода показана перегрузка метода `Median` для типа `integer`.

```vb
' Integer overload

<Extension()>
Function Median(ByVal source As IEnumerable(Of Integer)) As Double
    Return Aggregate num In source Select CDbl(num) Into med = Median()
End Function
```

Теперь можно вызвать перегрузки `Median` для типов `integer` и `double`, как показано в следующем примере кода:

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

#### <a name="to-create-a-generic-overload"></a>Создание универсальной перегрузки

Вы также можете создать перегрузку, которая принимает последовательность универсальных объектов. Эта перегрузка принимает делегат в качестве параметра и использует его для преобразования последовательности объектов универсального типа в конкретный тип.

В следующем примере кода демонстрируется перегрузка метода `Median`, принимающая делегат <xref:System.Func%602> в качестве параметра. Этот делегат принимает объект универсального типа T и возвращает объект типа `double`.

```vb
' Generic overload.

<Extension()>
Function Median(Of T)(ByVal source As IEnumerable(Of T),
                      ByVal selector As Func(Of T, Double)) As Double
    Return Aggregate num In source Select selector(num) Into med = Median()
End Function
```

Теперь вы можете вызвать метод `Median` для последовательности объектов любого типа. Если тип не содержит собственную перегрузку метода, вам потребуется передать параметр делегата. В Visual Basic для этой цели можно использовать лямбда-выражение. Кроме того, если вместо вызова метода используется предложение `Aggregate` или `Group By`, можно передать любое значение или выражение, которое находится в области данного предложения.

В следующем примере кода показано, как вызвать метод `Median` для массива целых чисел и массива строк. Для строк вычисляется срединное значение длин строк в массиве. В примере демонстрируется передача параметра делегата <xref:System.Func%602> в метод `Median` для каждого из случаев.

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

## <a name="adding-a-method-that-returns-a-collection"></a>Добавление метода, возвращающего коллекцию

Вы можете расширить интерфейс <xref:System.Collections.Generic.IEnumerable%601> с помощью метода настраиваемого запроса, который возвращает последовательность значений. В этом случае метод должен возвращать коллекцию типа <xref:System.Collections.Generic.IEnumerable%601>. Такие методы можно использовать для применения фильтров или преобразований данных к последовательности значений.

В следующем примере показано, как создать метод расширения с именем `AlternateElements`, который возвращает каждый второй элемент в коллекции, начиная с первого элемента.

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

Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы из интерфейса <xref:System.Collections.Generic.IEnumerable%601>, как показано в следующем примере кода:

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

## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic.IEnumerable%601>
- [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
