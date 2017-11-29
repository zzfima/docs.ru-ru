---
title: "Доступ к общему члену через экземпляр; выражение уточнения не вычисляется"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords: BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bcf3c37852e73464eec612e9e1d458ca707342e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
Переменная экземпляра класса или структуры используется для доступа к `Shared` переменная, свойство, процедура или событие, определенное в классе или структуре. Это предупреждение также может возникнуть, если переменная экземпляра используется для доступа к неявному общему члену класса или структуры, например константу перечисления или вложенного класса или структуры.  
  
 Совместное использование членов предназначено для создать только одну копию этого элемента и сделать доступной для каждого экземпляра класса или структуры, в котором она объявлена этой копии. Он был совместим с этой цели, для доступа к `Shared` член через имя класса или структуры, а не через переменную, содержащую отдельный экземпляр этого класса или структуры.  
  
 Доступ к `Shared` члена с помощью переменной экземпляра может сделать код более сложно понять, поскольку этот член является `Shared`. Кроме того, если такой доступ является частью выражения, которое производит другие действия, такие как `Function` процедуру, которая возвращает экземпляр общего члена [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] пропустит выражения и любые другие действия, в противном случае выполняет.  
  
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
