---
title: "Использование вариативности в делегатах (Visual Basic) | Документы Microsoft"
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
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
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
ms.openlocfilehash: 5bd3e60031eac713cee3dee1399af8c6b83e6656
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-delegates-visual-basic"></a>Использование вариативности в делегатах (Visual Basic)
При назначении метода делегату, *Ковариация* и *контравариация* обеспечивают гибкость сопоставления типа делегата с сигнатурой метода. Ковариация позволяет методу иметь тип возвращаемого значения, более производный, чем указано в делегате. Контрвариация использовать метод с типами параметров, которые являются менее производным, чем у типа делегата.  
  
## <a name="example-1-covariance"></a>Пример 1: ковариация  
  
### <a name="description"></a>Описание  
 В этом примере демонстрируется использование делегатов с методами, типы возвращаемых значений, которые являются производными от типа возвращаемого значения в сигнатуре делегата. Тип данных, возвращаемый `DogsHandler` типа `Dogs`, который является производным от `Mammals` типа, определенного в делегате.  
  
### <a name="code"></a>Код  
  
```vb  
Class Mammals  
End Class  
  
Class Dogs  
    Inherits Mammals  
End Class  
Class Test  
    Public Delegate Function HandlerMethod() As Mammals  
    Public Shared Function MammalsHandler() As Mammals  
        Return Nothing  
    End Function  
    Public Shared Function DogsHandler() As Dogs  
        Return Nothing  
    End Function  
    Sub Test()  
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler  
        ' Covariance enables this assignment.  
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler  
    End Sub  
End Class  
```  
  
## <a name="example-2-contravariance"></a>Пример 2: контрвариация  
  
### <a name="description"></a>Описание  
 В этом примере демонстрируется использование делегатов с методами, параметры типа которых являются базовыми типами типа параметра подписи делегата. Контравариация можно использовать один обработчик событий вместо отдельных обработчиков. Например, можно создать обработчик событий, который принимает `EventArgs` входной параметр и использовать его с `Button.MouseClick` событие, которое отправляет `MouseEventArgs` типа в качестве параметра, а также с `TextBox.KeyDown` событие, которое отправляет `KeyEventArgs` параметр.  
  
### <a name="code"></a>Код  
  
```vb  
' Event hander that accepts a parameter of the EventArgs type.  
Private Sub MultiHandler(ByVal sender As Object,  
                         ByVal e As System.EventArgs)  
    Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Form1_Load(ByVal sender As System.Object,  
    ByVal e As System.EventArgs) Handles MyBase.Load  
  
    ' You can use a method that has an EventArgs parameter,  
    ' although the event expects the KeyEventArgs parameter.  
    AddHandler Button1.KeyDown, AddressOf MultiHandler  
  
    ' You can use the same method   
    ' for the event that expects the MouseEventArgs parameter.  
    AddHandler Button1.MouseClick, AddressOf MultiHandler  
End Sub  
```  
  
## <a name="see-also"></a>См. также  
 [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)   
 [Использование вариативности в Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
