---
title: Iterators
ms.date: 07/20/2015
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
ms.openlocfilehash: 465a8e6650c3d015520164030a146c9502ebe603
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353739"
---
# <a name="iterators-visual-basic"></a>Iterators (Visual Basic)

*Итератор* можно использовать для прохода по коллекции, такой как список или массив.

Метод итератора или метод доступа `get` выполняет настраиваемую итерацию по коллекции. An iterator method uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element one at a time. При достижении инструкции `Yield` текущее расположение в коде запоминается. При следующем вызове функции итератора выполнение возобновляется с этого места.

You consume an iterator from client code by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement, or by using a LINQ query.

В приведенном ниже примере первая итерация цикла `For Each` приводит к вызову метода итератора `SomeNumbers`, пока не будет достигнут первый оператор `Yield`. Эта итерация возвращает значение 3. Текущее расположение в методе итератора сохраняется. В следующей итерации цикла выполнение метода итератора возобновляется с того же места и снова приостанавливается при достижении оператора `Yield`. Эта итерация возвращает значение 5. Текущее расположение в методе итератора снова сохраняется. Цикл завершается при достижении конца метода итератора.

```vb
Sub Main()
    For Each number As Integer In SomeNumbers()
        Console.Write(number & " ")
    Next
    ' Output: 3 5 8
    Console.ReadKey()
End Sub

Private Iterator Function SomeNumbers() As System.Collections.IEnumerable
    Yield 3
    Yield 5
    Yield 8
End Function
```

Типом возвращаемого метода итератора или метода доступа `get` может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.

You can use an `Exit Function` or `Return` statement to end the iteration.

A Visual Basic iterator function or `get` accessor declaration includes an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.

Iterators were introduced in Visual Basic in Visual Studio 2012.

**Содержание раздела**

- [Простой итератор](#BKMK_SimpleIterator)

- [Создание класса коллекции](#BKMK_CollectionClass)

- [Try Blocks](#BKMK_TryBlocks)

- [Анонимные методы](#BKMK_AnonymousMethods)

- [Использование итераторов с универсальным списком](#BKMK_GenericList)

- [Сведения о синтаксисе](#BKMK_SyntaxInformation)

- [Техническая реализация](#BKMK_Technical)

- [Использование итераторов](#BKMK_UseOfIterators)

> [!NOTE]
> For all examples in the topic except the Simple Iterator example, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections` and `System.Collections.Generic` namespaces.

## <a name="BKMK_SimpleIterator"></a> Простой итератор

The following example has a single `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop. В методе `Main` каждая итерация оператора `For Each` создает вызов функции итератора, которая выполняет следующий оператор `Yield`.

```vb
Sub Main()
    For Each number As Integer In EvenSequence(5, 18)
        Console.Write(number & " ")
    Next
    ' Output: 6 8 10 12 14 16 18
    Console.ReadKey()
End Sub

Private Iterator Function EvenSequence(
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _
As System.Collections.Generic.IEnumerable(Of Integer)

    ' Yield even numbers in the range.
    For number As Integer = firstNumber To lastNumber
        If number Mod 2 = 0 Then
            Yield number
        End If
    Next
End Function
```

## <a name="BKMK_CollectionClass"></a> Создание класса коллекции

В следующем примере класс `DaysOfTheWeek` реализует интерфейс <xref:System.Collections.IEnumerable>, которому требуется метод <xref:System.Collections.IEnumerable.GetEnumerator%2A>. Компилятор неявно вызывает метод `GetEnumerator`, который возвращает <xref:System.Collections.IEnumerator>.

The `GetEnumerator` method returns each string one at a time by using the `Yield` statement, and  an `Iterator` modifier is in the function declaration.

```vb
Sub Main()
    Dim days As New DaysOfTheWeek()
    For Each day As String In days
        Console.Write(day & " ")
    Next
    ' Output: Sun Mon Tue Wed Thu Fri Sat
    Console.ReadKey()
End Sub

Private Class DaysOfTheWeek
    Implements IEnumerable

    Public days =
        New String() {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"}

    Public Iterator Function GetEnumerator() As IEnumerator _
        Implements IEnumerable.GetEnumerator

        ' Yield each day of the week.
        For i As Integer = 0 To days.Length - 1
            Yield days(i)
        Next
    End Function
End Class
```

В приведенном ниже примере создается класс `Zoo`, содержащий коллекцию животных.

Оператор `For Each`, который обращается к экземпляру класса (`theZoo`), неявно вызывает метод `GetEnumerator`. Операторы `For Each`, которые обращаются к свойствам `Birds` и `Mammals`, используют метод итератора с именем `AnimalsForType`.

```vb
Sub Main()
    Dim theZoo As New Zoo()

    theZoo.AddMammal("Whale")
    theZoo.AddMammal("Rhinoceros")
    theZoo.AddBird("Penguin")
    theZoo.AddBird("Warbler")

    For Each name As String In theZoo
        Console.Write(name & " ")
    Next
    Console.WriteLine()
    ' Output: Whale Rhinoceros Penguin Warbler

    For Each name As String In theZoo.Birds
        Console.Write(name & " ")
    Next
    Console.WriteLine()
    ' Output: Penguin Warbler

    For Each name As String In theZoo.Mammals
        Console.Write(name & " ")
    Next
    Console.WriteLine()
    ' Output: Whale Rhinoceros

    Console.ReadKey()
End Sub

Public Class Zoo
    Implements IEnumerable

    ' Private members.
    Private animals As New List(Of Animal)

    ' Public methods.
    Public Sub AddMammal(ByVal name As String)
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Mammal})
    End Sub

    Public Sub AddBird(ByVal name As String)
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Bird})
    End Sub

    Public Iterator Function GetEnumerator() As IEnumerator _
        Implements IEnumerable.GetEnumerator

        For Each theAnimal As Animal In animals
            Yield theAnimal.Name
        Next
    End Function

    ' Public members.
    Public ReadOnly Property Mammals As IEnumerable
        Get
            Return AnimalsForType(Animal.TypeEnum.Mammal)
        End Get
    End Property

    Public ReadOnly Property Birds As IEnumerable
        Get
            Return AnimalsForType(Animal.TypeEnum.Bird)
        End Get
    End Property

    ' Private methods.
    Private Iterator Function AnimalsForType( _
    ByVal type As Animal.TypeEnum) As IEnumerable
        For Each theAnimal As Animal In animals
            If (theAnimal.Type = type) Then
                Yield theAnimal.Name
            End If
        Next
    End Function

    ' Private class.
    Private Class Animal
        Public Enum TypeEnum
            Bird
            Mammal
        End Enum

        Public Property Name As String
        Public Property Type As TypeEnum
    End Class
End Class
```

## <a name="BKMK_TryBlocks"></a> Try Blocks

Visual Basic allows a `Yield` statement in the `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.

The following example includes `Try`, `Catch`, and `Finally` blocks in an iterator function. The `Finally` block in the iterator function executes before the `For Each` iteration finishes.

```vb
Sub Main()
    For Each number As Integer In Test()
        Console.WriteLine(number)
    Next
    Console.WriteLine("For Each is done.")

    ' Output:
    '  3
    '  4
    '  Something happened. Yields are done.
    '  Finally is called.
    '  For Each is done.
    Console.ReadKey()
End Sub

Private Iterator Function Test() As IEnumerable(Of Integer)
    Try
        Yield 3
        Yield 4
        Throw New Exception("Something happened. Yields are done.")
        Yield 5
        Yield 6
    Catch ex As Exception
        Console.WriteLine(ex.Message)
    Finally
        Console.WriteLine("Finally is called.")
    End Try
End Function
```

A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.

If the `For Each` body (instead of the iterator method) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed. A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.

## <a name="BKMK_AnonymousMethods"></a> Anonymous Methods

In Visual Basic, an anonymous function can be an iterator function. Это показано в следующем примере.

```vb
Dim iterateSequence = Iterator Function() _
                      As IEnumerable(Of Integer)
                          Yield 1
                          Yield 2
                      End Function

For Each number As Integer In iterateSequence()
    Console.Write(number & " ")
Next
' Output: 1 2
Console.ReadKey()
```

The following example has a non-iterator method that validates the arguments. The method returns the result of an anonymous iterator that describes the collection elements.

```vb
Sub Main()
    For Each number As Integer In GetSequence(5, 10)
        Console.Write(number & " ")
    Next
    ' Output: 5 6 7 8 9 10
    Console.ReadKey()
End Sub

Public Function GetSequence(ByVal low As Integer, ByVal high As Integer) _
As IEnumerable
    ' Validate the arguments.
    If low < 1 Then
        Throw New ArgumentException("low is too low")
    End If
    If high > 140 Then
        Throw New ArgumentException("high is too high")
    End If

    ' Return an anonymous iterator function.
    Dim iterateSequence = Iterator Function() As IEnumerable
                              For index = low To high
                                  Yield index
                              Next
                          End Function
    Return iterateSequence()
End Function
```

If validation is instead inside the iterator function, the validation cannot be performed until the start of the first iteration of the `For Each` body.

## <a name="BKMK_GenericList"></a> Использование итераторов с универсальным списком

В следующем примере универсальный класс `Stack(Of T)` также реализует универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>. Метод `Push` присваивает значения массиву типа `T`. Метод <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> возвращает массив значений с помощью оператора `Yield`.

Помимо универсального метода <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> должен быть реализован и неуниверсальный метод <xref:System.Collections.IEnumerable.GetEnumerator%2A>. Это связано с тем, что <xref:System.Collections.Generic.IEnumerable%601> наследуется от <xref:System.Collections.IEnumerable>. Неуниверсальная реализация подчиняется универсальной реализации.

В этом примере используются именованные итераторы для поддержки различных способов итерации по одной и той же коллекции данных. Эти именованные итераторы являются свойствами `TopToBottom` и `BottomToTop` и методом `TopN`.

The `BottomToTop` property declaration includes the `Iterator` keyword.

```vb
Sub Main()
    Dim theStack As New Stack(Of Integer)

    ' Add items to the stack.
    For number As Integer = 0 To 9
        theStack.Push(number)
    Next

    ' Retrieve items from the stack.
    ' For Each is allowed because theStack implements
    ' IEnumerable(Of Integer).
    For Each number As Integer In theStack
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 9 8 7 6 5 4 3 2 1 0

    ' For Each is allowed, because theStack.TopToBottom
    ' returns IEnumerable(Of Integer).
    For Each number As Integer In theStack.TopToBottom
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 9 8 7 6 5 4 3 2 1 0

    For Each number As Integer In theStack.BottomToTop
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 0 1 2 3 4 5 6 7 8 9

    For Each number As Integer In theStack.TopN(7)
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 9 8 7 6 5 4 3

    Console.ReadKey()
End Sub

Public Class Stack(Of T)
    Implements IEnumerable(Of T)

    Private values As T() = New T(99) {}
    Private top As Integer = 0

    Public Sub Push(ByVal t As T)
        values(top) = t
        top = top + 1
    End Sub

    Public Function Pop() As T
        top = top - 1
        Return values(top)
    End Function

    ' This function implements the GetEnumerator method. It allows
    ' an instance of the class to be used in a For Each statement.
    Public Iterator Function GetEnumerator() As IEnumerator(Of T) _
        Implements IEnumerable(Of T).GetEnumerator

        For index As Integer = top - 1 To 0 Step -1
            Yield values(index)
        Next
    End Function

    Public Iterator Function GetEnumerator1() As IEnumerator _
        Implements IEnumerable.GetEnumerator

        Yield GetEnumerator()
    End Function

    Public ReadOnly Property TopToBottom() As IEnumerable(Of T)
        Get
            Return Me
        End Get
    End Property

    Public ReadOnly Iterator Property BottomToTop As IEnumerable(Of T)
        Get
            For index As Integer = 0 To top - 1
                Yield values(index)
            Next
        End Get
    End Property

    Public Iterator Function TopN(ByVal itemsFromTop As Integer) _
        As IEnumerable(Of T)

        ' Return less than itemsFromTop if necessary.
        Dim startIndex As Integer =
            If(itemsFromTop >= top, 0, top - itemsFromTop)

        For index As Integer = top - 1 To startIndex Step -1
            Yield values(index)
        Next
    End Function
End Class
```

## <a name="BKMK_SyntaxInformation"></a> Сведения о синтаксисе

Итератор может являться методом или методом доступа `get`. Итератор не может использоваться в событии, конструкторе экземпляра, статическом конструкторе или статическом деструкторе.

Должно существовать неявное преобразование выражения типа в операторе `Yield` в возвращаемый тип итератора.

In Visual Basic, an iterator method cannot have any `ByRef` parameters.

In Visual Basic, "Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` method or `get` accessor.

## <a name="BKMK_Technical"></a> Техническая реализация

Хотя итератор создается как метод, компилятор переводит его во вложенный класс, который фактически является конечным автоматом. Этот класс отслеживает положение итератора, пока в клиентском коде выполняется цикл `For Each...Next`.

Чтобы просмотреть операции компилятора, воспользуйтесь средством Ildasm.exe для отображения кода промежуточного языка Майкрософт, создаваемого для метода итератора.

When you create an iterator for a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md), you do not have to implement the whole <xref:System.Collections.IEnumerator> interface. Когда компилятор обнаруживает итератор, он автоматически создает методы `Current`, `MoveNext` и `Dispose` интерфейса <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.

В каждой последовательной итерации цикла `For Each…Next` (или непосредственном вызове метода `IEnumerator.MoveNext`) код тела следующего итератора возобновляет выполнение после предыдущего оператора `Yield`. It then continues to the next `Yield` statement until the end of the iterator body is reached, or until an `Exit Function` or `Return` statement is encountered.

Iterators do not support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> method. Для повторной итерации сначала необходимо получить новый итератор.

For additional information, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).

## <a name="BKMK_UseOfIterators"></a> Использование итераторов

Итераторы позволяют поддерживать простоту цикла `For Each`, когда необходимо использовать сложный код для заполнения последовательности списков. Это может оказаться полезным в следующих случаях:

- Изменение последовательности списков после первой итерации цикла `For Each`.

- Если необходимо избежать полной загрузки большого списка перед первой итерацией цикла `For Each`. Пример: при постраничной загрузке пакета строк таблицы. Другой пример — метод <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, реализующий итераторы в .NET Framework.

- Инкапсулирование построения списка в итераторе. В методе итератора можно построить список, а затем выдавать каждый результат в цикле.

## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Оператор Yield](../../../visual-basic/language-reference/statements/yield-statement.md)
- [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)
