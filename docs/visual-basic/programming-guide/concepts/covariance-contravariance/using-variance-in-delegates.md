---
title: Использование вариативности в делегатах (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: e0b0df354c6c31eed41ead2bb0b2a1aaa4ac9922
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690830"
---
# <a name="using-variance-in-delegates-visual-basic"></a>Использование вариативности в делегатах (Visual Basic)
При назначении метода делегату *ковариация* и *контравариантость* обеспечивают гибкость сопоставления типа делегата с сигнатурой метода. Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в делегате. Контравариантность позволяет использовать метод с типами параметров, степень наследования которых меньше, чем у типа делегата.  
  
## <a name="example-1-covariance"></a>Пример 1. Ковариация  
  
### <a name="description"></a>Описание:  
 В этом примере демонстрируется использование делегатов с методами, типы возвращаемых значений которых являются производными от типа возвращаемого значения в сигнатуре делегата. Тип данных, возвращаемый `DogsHandler`, является типом `Dogs`, производным от определенного в делегате типа `Mammals`.  
  
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
  
## <a name="example-2-contravariance"></a>Пример 2: Контрвариантность  
  
### <a name="description"></a>Описание  
 В этом примере демонстрируется использование делегатов с методами, параметры типа которых являются базовыми типами типа параметра сигнатуры делегата. Контравариантность позволяет использовать один обработчик событий вместо нескольких. Например, можно создать обработчик событий, принимающих входной параметр `EventArgs`, и использовать его с событием `Button.MouseClick`, которое отправляет тип `MouseEventArgs` в качестве параметра, а также с событием `TextBox.KeyDown`, которое отправляет параметр `KeyEventArgs`.  
  
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
- [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [Использование вариативности в универсальных методах-делегатах Func и Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
