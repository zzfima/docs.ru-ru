---
title: Как выполнить Вызов метода делегата (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 42d56fca7e1d33c071db2e7e38935aa00caa5b7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676215"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Как выполнить Вызов метода делегата (Visual Basic)
В этом примере показано, как связать метод с делегатом, а затем вызвать метод через делегат.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Создание делегата и согласование процедур  
  
1.  Создать делегат с именем `MySubDelegate`.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  Объявите класс, который содержит метод с сигнатурой делегата.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  Определите метод, который создает экземпляр делегата и вызывает метод, связанный с делегатом, вызвав встроенный `Invoke` метод.  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a>См. также

- [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Многопоточные приложения](../../../../standard/threading/using-threads-and-threading.md)
