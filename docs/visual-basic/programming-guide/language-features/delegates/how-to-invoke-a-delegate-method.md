---
title: Практическое руководство. Вызов метода делегата (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c2bdb65c9d060e854db3319e4aa5b2e93b9681af
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629590"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Практическое руководство. Вызов метода делегата (Visual Basic)

В этом примере показано, как связать метод с делегатом, а затем вызвать этот метод через делегат.

### <a name="create-the-delegate-and-matching-procedures"></a>Создание делегата и процедур сопоставления

1. Создайте делегат с именем `MySubDelegate`.

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. Объявите класс, содержащий метод с той же сигнатурой, что и у делегата.

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. Определите метод, который создает экземпляр делегата и вызывает метод, связанный с делегатом, вызвав встроенный `Invoke` метод.

    ```vb
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
