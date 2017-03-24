---
title: "Использование вариативности в Func и Action универсальные делегаты (Visual Basic) | Документы Microsoft"
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
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
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
ms.openlocfilehash: 28c3f84d21f9fbc7e57ba079461194acf7612add
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a>Использование вариативности в Func и Action универсальные делегаты (Visual Basic)
Эти примеры демонстрируют использование ковариации и контравариации в `Func` и `Action` универсальные делегаты для обеспечения возможности многократного использования методов и обеспечивают большую гибкость в коде.  
  
 Дополнительные сведения о ковариации и контрвариации см. в разделе [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
## <a name="using-delegates-with-covariant-type-parameters"></a>Использование делегатов с ковариантными параметрами типа  
 В следующем примере показано преимущество использования поддержки ковариации в универсальном `Func` делегатов. `FindByTitle` Метод принимает параметр `String` типа и возвращает объект `Employee` типа. Тем не менее, можно назначить этот метод, чтобы `Func(Of String, Person)` делегата, поскольку `Employee` наследует `Person`.  
  
```vb  
' Simple hierarchy of classes.  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class Finder  
    Public Shared Function FindByTitle(  
        ByVal title As String) As Employee  
        ' This is a stub for a method that returns  
        ' an employee that has the specified title.  
        Return New Employee  
    End Function  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim findEmployee As Func(Of String, Employee) =  
            AddressOf FindByTitle  
  
        ' The delegate expects a method to return Person,  
        ' but you can assign it a method that returns Employee.  
        Dim findPerson As Func(Of String, Person) =  
            AddressOf FindByTitle  
  
        ' You can also assign a delegate   
        ' that returns a more derived type to a delegate   
        ' that returns a less derived type.  
        findPerson = findEmployee  
    End Sub  
End Class  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a>Использование делегатов с контравариантными параметрами типа  
 В следующем примере демонстрируется преимущества поддержки контравариация в универсальных `Action` делегатов. `AddToContacts` Метод принимает параметр `Person` типа. Тем не менее, можно назначить этот метод, чтобы `Action(Of Employee)` делегата, поскольку `Employee` наследует `Person`.  
  
```vb  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class AddressBook  
    Shared Sub AddToContacts(ByVal person As Person)  
        ' This method adds a Person object  
        ' to a contact list.  
    End Sub  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim addPersonToContacts As Action(Of Person) =  
            AddressOf AddToContacts  
  
        ' The Action delegate expects   
        ' a method that has an Employee parameter,  
        ' but you can assign it a method that has a Person parameter  
        ' because Employee derives from Person.  
        Dim addEmployeeToContacts As Action(Of Employee) =  
            AddressOf AddToContacts  
  
        ' You can also assign a delegate   
        ' that accepts a less derived parameter   
        ' to a delegate that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>См. также  
 [Ковариация и контравариация (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/covariance-and-contravariance.md)   
 [Универсальные шаблоны](https://msdn.microsoft.com/library/ms172192)
