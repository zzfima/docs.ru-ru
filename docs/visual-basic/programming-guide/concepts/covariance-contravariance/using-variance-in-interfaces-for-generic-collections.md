---
title: Использование расхождения в интерфейсах для универсальных коллекций
ms.date: 07/20/2015
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
ms.openlocfilehash: 6ee133dfd61d7d7a88243ca592642ff21e0c2223
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349012"
---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a>Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)

Ковариантный интерфейс позволяет его методам возвращать более производные типы, чем указанные в интерфейсе. Контравариантный интерфейс позволяет его методам принимать параметры менее производных типов, чем указанные в интерфейсе.

В .NET Framework 4 несколько имеющихся интерфейсов стали ковариантными и контравариантными. В их числе <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IComparable%601>. Это позволяет повторно использовать методы, оперирующие универсальными коллекциями базовых типов, для коллекций производных типов.

Список вариативных интерфейсов в .NET Framework см. в разделе [вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).

## <a name="converting-generic-collections"></a>Преобразование универсальных коллекций

Следующий пример иллюстрирует преимущества поддержки ковариантности в интерфейсе <xref:System.Collections.Generic.IEnumerable%601>. Метод `PrintFullName` принимает коллекцию типа `IEnumerable(Of Person)` в качестве параметра. При этом его можно повторно использовать для коллекции типа `IEnumerable(Of Person)`, так как `Employee` наследует `Person`.

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class

' The method has a parameter of the IEnumerable(Of Person) type.
Public Sub PrintFullName(ByVal persons As IEnumerable(Of Person))
    For Each person As Person In persons
        Console.WriteLine(
            "Name: " & person.FirstName & " " & person.LastName)
    Next
End Sub

Sub Main()
    Dim employees As IEnumerable(Of Employee) = New List(Of Employee)

    ' You can pass IEnumerable(Of Employee),
    ' although the method expects IEnumerable(Of Person).

    PrintFullName(employees)

End Sub
```

## <a name="comparing-generic-collections"></a>Сравнение универсальных коллекций

Следующий пример иллюстрирует преимущества поддержки контрвариантности в интерфейсе <xref:System.Collections.Generic.IComparer%601>. Класс `PersonComparer` реализует интерфейс `IComparer(Of Person)`. Тем не менее этот класс можно повторно использовать для сравнения последовательности объектов типа `Employee`, так как `Employee` наследует `Person`.

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class
' The custom comparer for the Person type
' with standard implementations of Equals()
' and GetHashCode() methods.
Class PersonComparer
    Implements IEqualityComparer(Of Person)

    Public Function Equals1(
        ByVal x As Person,
        ByVal y As Person) As Boolean _
        Implements IEqualityComparer(Of Person).Equals

        If x Is y Then Return True
        If x Is Nothing OrElse y Is Nothing Then Return False
        Return (x.FirstName = y.FirstName) AndAlso
            (x.LastName = y.LastName)
    End Function
    Public Function GetHashCode1(
        ByVal person As Person) As Integer _
        Implements IEqualityComparer(Of Person).GetHashCode

        If person Is Nothing Then Return 0
        Dim hashFirstName =
            If(person.FirstName Is Nothing,
            0, person.FirstName.GetHashCode())
        Dim hashLastName = person.LastName.GetHashCode()
        Return hashFirstName Xor hashLastName
    End Function
End Class

Sub Main()
    Dim employees = New List(Of Employee) From {
        New Employee With {.FirstName = "Michael", .LastName = "Alexander"},
        New Employee With {.FirstName = "Jeff", .LastName = "Price"}
    }

    ' You can pass PersonComparer,
    ' which implements IEqualityComparer(Of Person),
    ' although the method expects IEqualityComparer(Of Employee)

    Dim noduplicates As IEnumerable(Of Employee) = employees.Distinct(New PersonComparer())

    For Each employee In noduplicates
        Console.WriteLine(employee.FirstName & " " & employee.LastName)
    Next
End Sub
```

## <a name="see-also"></a>См. также

- [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
