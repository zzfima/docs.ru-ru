---
title: Практическое руководство. Вызов метода делегата
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 520bacfbe6103490e0459cd5af149c1d55a8fce4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345255"
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

3. Определите метод, который создает экземпляр делегата и вызывает метод, связанный с делегатом, вызвав встроенный метод `Invoke`.

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
