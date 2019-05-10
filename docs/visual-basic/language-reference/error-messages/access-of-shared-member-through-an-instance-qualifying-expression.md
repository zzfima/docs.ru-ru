---
title: Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 311f4c025072162e0cfb6b87587f8602d33fcd19
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646870"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
Переменная экземпляра класса или структуры используется для доступа к `Shared` переменной, свойства, процедуры или события, определенного в классе или структуре. Это предупреждение также может возникнуть, если переменная экземпляра используется для доступа к неявному общему члену класса или структуры, такие как константа перечисления, или вложенного класса или структуры.  
  
 Совместное использование членов предназначена для создания только одной копии этого элемента и предоставления этой копии для каждого экземпляра класса или структуры, в котором она объявлена. Он был совместим с этой цели, для доступа к `Shared` член через имя класса или структуры, а не через переменную, содержащую отдельный экземпляр этого класса или структуры.  
  
 Доступ к `Shared` элементу через переменную экземпляра может сделать код более трудным для понимания, поскольку этот член является `Shared`. Кроме того, если такой доступ является частью выражения, который выполняет другие действия, такие как `Function` процедуру, которая возвращает экземпляр общего члена, Visual Basic пропустит выражения и любые другие действия, в противном случае выполняет.  
  
 Дополнительные сведения и пример см. в разделе [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте имя класса или структуры, который определяет `Shared` члена к нему доступ, как показано в следующем примере.  
  
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
>  Предупреждение для эффектов области Будьте в том случае, если два программных элемента имеют одинаковое имя. В предыдущем примере, если вы объявите экземпляр с помощью `Dim testClass as testClass = Nothing`, компилятор обрабатывает вызов `testClass.sayHello()` как доступа метода через имя класса и предупреждение не возникает.  
  
## <a name="see-also"></a>См. также

- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [Область, в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
