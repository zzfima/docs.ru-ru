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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86184c7de3fe16148bf954b16d703ca682216337
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a><span data-ttu-id="7e029-102">Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e029-102">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>
<span data-ttu-id="7e029-103">Ковариантный интерфейс позволяет своим методам возвращать более производные типы, чем указаны в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="7e029-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="7e029-104">Контравариантный интерфейс позволяет своим методам принимать параметры менее производных типов, чем указаны в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="7e029-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="7e029-105">В .NET Framework 4 несколько существующих интерфейсов стала ковариантными и контравариантными.</span><span class="sxs-lookup"><span data-stu-id="7e029-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="7e029-106">К ним относятся <xref:System.Collections.Generic.IEnumerable%601>и <xref:System.IComparable%601>.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="7e029-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="7e029-107">Это дает возможность повторно использовать методы, которые используют универсальные коллекции базовых типов, для коллекций производных типов.</span><span class="sxs-lookup"><span data-stu-id="7e029-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="7e029-108">Список вариативных интерфейсов в платформе .NET Framework см. в разделе [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="7e029-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="7e029-109">Преобразование универсальных коллекций</span><span class="sxs-lookup"><span data-stu-id="7e029-109">Converting Generic Collections</span></span>  
 <span data-ttu-id="7e029-110">В следующем примере показано преимущество использования поддержки ковариации в <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="7e029-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="7e029-111">`PrintFullName` Метод принимает коллекцию `IEnumerable(Of Person)` тип в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="7e029-111">The `PrintFullName` method accepts a collection of the `IEnumerable(Of Person)` type as a parameter.</span></span> <span data-ttu-id="7e029-112">Тем не менее, можно повторно использовать его для коллекции `IEnumerable(Of Person)` типа, так как `Employee` наследует `Person`.</span><span class="sxs-lookup"><span data-stu-id="7e029-112">However, you can reuse it for a collection of the `IEnumerable(Of Person)` type because `Employee` inherits `Person`.</span></span>  
  
<span data-ttu-id="7e029-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7e029-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
## <a name="comparing-generic-collections"></a><span data-ttu-id="7e029-114">Сравнение универсальных коллекций</span><span class="sxs-lookup"><span data-stu-id="7e029-114">Comparing Generic Collections</span></span>  
 <span data-ttu-id="7e029-115">В следующем примере демонстрируется преимущества поддержки контравариации в <xref:System.Collections.Generic.IComparer%601>интерфейса.</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="7e029-115">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="7e029-116">Класс `PersonComparer` реализует интерфейс `IComparer(Of Person)`.</span><span class="sxs-lookup"><span data-stu-id="7e029-116">The `PersonComparer` class implements the `IComparer(Of Person)` interface.</span></span> <span data-ttu-id="7e029-117">Тем не менее, вы можете повторно использовать этот класс для сравнения последовательности объектов `Employee` типа, так как `Employee` наследует `Person`.</span><span class="sxs-lookup"><span data-stu-id="7e029-117">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7e029-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7e029-118">See Also</span></span>  
 [<span data-ttu-id="7e029-119">Вариативность в универсальных интерфейсах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e029-119">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
