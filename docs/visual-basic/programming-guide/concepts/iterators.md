---
title: Итераторы
ms.date: 07/20/2015
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
ms.openlocfilehash: 2789ac66690ebfd472b9bae5ccf08b1bdfaa0922
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628739"
---
# <a name="iterators-visual-basic"></a>Итераторы (Visual Basic)

*Итератор* можно использовать для прохода по коллекции, такой как список или массив.

Метод итератора или метод доступа `get` выполняет настраиваемую итерацию по коллекции. Метод итератора использует оператор [yield](../../../visual-basic/language-reference/statements/yield-statement.md) для возвращения каждого элемента по одному за раз. При достижении инструкции `Yield` текущее расположение в коде запоминается. При следующем вызове функции итератора выполнение возобновляется с этого места.

Вы используете итератор из клиентского кода, используя [для каждого... Оператор Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) или с помощью запроса LINQ.

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

Для завершения итерации можно использовать инструкцию `Exit Function` или `Return`.

Visual Basic функция итератора или `get` объявление метода доступа содержит модификатор [итератора](../../../visual-basic/language-reference/modifiers/iterator.md) .

Итераторы появились в Visual Basic в Visual Studio 2012.

**В этом разделе**

- [Простой итератор](#BKMK_SimpleIterator)

- [Создание класса коллекции](#BKMK_CollectionClass)

- [Блоки try](#BKMK_TryBlocks)

- [Анонимные методы](#BKMK_AnonymousMethods)

- [Использование итераторов с универсальным списком](#BKMK_GenericList)

- [Сведения о синтаксисе](#BKMK_SyntaxInformation)

- [Техническая реализация](#BKMK_Technical)

- [Использование итераторов](#BKMK_UseOfIterators)

> [!NOTE]
> Для всех примеров в разделе, за исключением простого примера итератора, включите операторы [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для `System.Collections` и `System.Collections.Generic` пространства имен.

## <a name="BKMK_SimpleIterator"></a> Простой итератор

В следующем примере используется одна инструкция `Yield`, которая находится внутри блока [for... Следующий](../../../visual-basic/language-reference/statements/for-next-statement.md) цикл. В методе `Main` каждая итерация оператора `For Each` создает вызов функции итератора, которая выполняет следующий оператор `Yield`.

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

Метод `GetEnumerator` возвращает каждую строку по одной за раз с помощью инструкции `Yield`, а модификатор `Iterator` — в объявлении функции.

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

## <a name="BKMK_TryBlocks"></a>Блоки try

Visual Basic допускает инструкцию `Yield` в блоке `Try` конструкции [try... Перехватить... Оператор finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Блок `Try`, содержащий инструкцию `Yield`, может иметь `Catch` блоки и может иметь блок `Finally`.

В следующем примере в функцию итератора включены блоки `Try`, `Catch`и `Finally`. Блок `Finally` в функции итератора выполняется до завершения `For Each` итерации.

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

Оператор `Yield` не может находиться в блоке `Catch` или в блоке `Finally`.

Если тело `For Each` (вместо метода итератора) создает исключение, блок `Catch` в функции-итераторе не выполняется, но выполняется блок `Finally` в функции итератора. Блок `Catch` внутри функции итератора перехватывает только исключения, происходящие внутри функции итератора.

## <a name="BKMK_AnonymousMethods"></a>Анонимные методы

В Visual Basic анонимная функция может быть функцией итератора. Это показано в следующем примере.

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

В следующем примере имеется метод, не являющийся итератором, который проверяет аргументы. Метод возвращает результат анонимного итератора, который описывает элементы коллекции.

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

Если в функцию итератора выполняется проверка, то проверка не может быть выполнена до начала первой итерации тела `For Each`.

## <a name="BKMK_GenericList"></a> Использование итераторов с универсальным списком

В следующем примере универсальный класс `Stack(Of T)` также реализует универсальный интерфейс <xref:System.Collections.Generic.IEnumerable%601>. Метод `Push` присваивает значения массиву типа `T`. Метод <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> возвращает массив значений с помощью оператора `Yield`.

Помимо универсального метода <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> должен быть реализован и неуниверсальный метод <xref:System.Collections.IEnumerable.GetEnumerator%2A>. Это связано с тем, что <xref:System.Collections.Generic.IEnumerable%601> наследуется от <xref:System.Collections.IEnumerable>. Неуниверсальная реализация подчиняется универсальной реализации.

В этом примере используются именованные итераторы для поддержки различных способов итерации по одной и той же коллекции данных. Эти именованные итераторы являются свойствами `TopToBottom` и `BottomToTop` и методом `TopN`.

Объявление свойства `BottomToTop` включает ключевое слово `Iterator`.

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

В Visual Basic метод итератора не может иметь никаких `ByRef` параметров.

В Visual Basic «yield» не является зарезервированным словом и имеет специальное значение только в том случае, если оно используется в методе `Iterator` или методе доступа `get`.

## <a name="BKMK_Technical"></a> Техническая реализация

Хотя итератор создается как метод, компилятор переводит его во вложенный класс, который фактически является конечным автоматом. Этот класс отслеживает положение итератора, пока в клиентском коде выполняется цикл `For Each...Next`.

Чтобы просмотреть операции компилятора, воспользуйтесь средством Ildasm.exe для отображения кода промежуточного языка Майкрософт, создаваемого для метода итератора.

При создании итератора для [класса](../../language-reference/statements/class-statement.md) или [структуры](../../language-reference/statements/structure-statement.md)не нужно реализовывать весь интерфейс <xref:System.Collections.IEnumerator>. Когда компилятор обнаруживает итератор, он автоматически создает методы `Current`, `MoveNext` и `Dispose` интерфейса <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.

В каждой последовательной итерации цикла `For Each…Next` (или непосредственном вызове метода `IEnumerator.MoveNext`) код тела следующего итератора возобновляет выполнение после предыдущего оператора `Yield`. Затем он переходит к следующему `Yield` оператору до достижения конца тела итератора или до тех пор, пока не будет обнаружена инструкция `Exit Function` или `Return`.

Итераторы не поддерживают метод <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType>. Для повторной итерации сначала необходимо получить новый итератор.

Дополнительные сведения см. в разделе [Спецификация языка Visual Basic](../../../visual-basic/reference/language-specification/index.md).

## <a name="BKMK_UseOfIterators"></a> Использование итераторов

Итераторы позволяют поддерживать простоту цикла `For Each`, когда необходимо использовать сложный код для заполнения последовательности списков. Это может оказаться полезным в следующих случаях:

- Изменение последовательности списков после первой итерации цикла `For Each`.

- Если необходимо избежать полной загрузки большого списка перед первой итерацией цикла `For Each`. Пример: при постраничной загрузке пакета строк таблицы. Другой пример — метод <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, реализующий итераторы в .NET Framework.

- Инкапсулирование построения списка в итераторе. В методе итератора можно построить список, а затем выдавать каждый результат в цикле.

## <a name="see-also"></a>См. также раздел

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Оператор Yield](../../../visual-basic/language-reference/statements/yield-statement.md)
- [Итератор](../../../visual-basic/language-reference/modifiers/iterator.md)
