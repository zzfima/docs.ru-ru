---
title: Практическое руководство. Вызов метода делегата (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 9fea3ddbc9fb553041671713a64e4b866ee38b50
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392442"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Практическое руководство. Вызов метода делегата (Visual Basic)
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
 [Оператор Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Делегаты](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Многопоточные приложения](https://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
