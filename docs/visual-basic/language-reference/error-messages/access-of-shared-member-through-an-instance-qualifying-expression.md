---
title: Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 035882b60c90d9a6141ad0d34b4c40682e0c32a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
Переменная экземпляра класса или структуры используется для доступа к `Shared` переменная, свойство, процедура или событие, определенное в классе или структуре. Это предупреждение также может возникнуть, если переменная экземпляра используется для доступа к неявному общему члену класса или структуры, например константу перечисления или вложенного класса или структуры.  
  
 Совместное использование членов предназначено для создать только одну копию этого элемента и сделать доступной для каждого экземпляра класса или структуры, в котором она объявлена этой копии. Он был совместим с этой цели, для доступа к `Shared` член через имя класса или структуры, а не через переменную, содержащую отдельный экземпляр этого класса или структуры.  
  
 Доступ к `Shared` члена с помощью переменной экземпляра может сделать код более сложно понять, поскольку этот член является `Shared`. Кроме того, если такой доступ является частью выражения, которое производит другие действия, такие как `Function` процедура, которая возвращает экземпляр общего члена, Visual Basic пропустит выражения и любые другие действия, в противном случае выполняет.  
  
 Дополнительные сведения и пример см. в разделе [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте имя класса или структуры, которые определяют `Shared` член к нему доступ, как показано в следующем примере.  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  Предупреждение для эффектов области Будьте в том случае, если два элементы программирования могут иметь то же имя. В предыдущем примере, если объявить экземпляр с помощью `Dim testClass as testClass = Nothing`, компилятор обрабатывает вызов `testClass.sayHello()` как доступ метода посредством имени класса и предупреждение не возникает.  
  
## <a name="see-also"></a>См. также  
 [Общие](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Область в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
