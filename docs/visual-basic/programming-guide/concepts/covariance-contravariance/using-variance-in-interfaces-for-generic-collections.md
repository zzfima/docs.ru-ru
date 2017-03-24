---
title: "Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86184c7de3fe16148bf954b16d703ca682216337
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a>Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)
Ковариантный интерфейс позволяет своим методам возвращать более производные типы, чем указаны в интерфейсе. Контравариантный интерфейс позволяет своим методам принимать параметры менее производных типов, чем указаны в интерфейсе.  
  
 В .NET Framework 4 несколько существующих интерфейсов стала ковариантными и контравариантными. К ним относятся <xref:System.Collections.Generic.IEnumerable%601>и <xref:System.IComparable%601>.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601> Это дает возможность повторно использовать методы, которые используют универсальные коллекции базовых типов, для коллекций производных типов.  
  
 Список вариативных интерфейсов в платформе .NET Framework см. в разделе [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).  
  
## <a name="converting-generic-collections"></a>Преобразование универсальных коллекций  
 В следующем примере показано преимущество использования поддержки ковариации в <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601> `PrintFullName` Метод принимает коллекцию `IEnumerable(Of Person)` тип в качестве параметра. Тем не менее, можно повторно использовать его для коллекции `IEnumerable(Of Person)` типа, так как `Employee` наследует `Person`.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="comparing-generic-collections"></a>Сравнение универсальных коллекций  
 В следующем примере демонстрируется преимущества поддержки контравариации в <xref:System.Collections.Generic.IComparer%601>интерфейса.</xref:System.Collections.Generic.IComparer%601> Класс `PersonComparer` реализует интерфейс `IComparer(Of Person)`. Тем не менее, вы можете повторно использовать этот класс для сравнения последовательности объектов `Employee` типа, так как `Employee` наследует `Person`.  
  
```vb  
' Simple hierarhcy of classes.  
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
 [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
