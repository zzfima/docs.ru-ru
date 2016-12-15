---
title: "Практическое руководство. Вызов метода делегата (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Вызов метода делегата (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Этот пример показывает, как связать метод с делегатом, а затем вызвать метод через делегат.  
  
### Создание делегата и согласование процедур  
  
1.  Создайте делегата с именем `MySubDelegate`.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  Объявите класс, содержащий метод с той же сигнатурой, что и у делегата.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  Определите метод, который создает экземпляр делегата и вызывает метод, связанный с делегатом, вызвав встроенный метод `Invoke`.  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## См. также  
 [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [События](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Многопоточные приложения](../Topic/Multithreaded%20Applications%20\(C%23%20and%20Visual%20Basic\).md)