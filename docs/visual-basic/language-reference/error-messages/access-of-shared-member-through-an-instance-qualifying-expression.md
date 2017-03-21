---
title: "Доступ к общему члену через экземпляр; выражение уточнения не вычисляется | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
dev_langs:
- VB
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 39be3c95d5acc20afe3a33be9d4db48c09f99a9c
ms.lasthandoff: 03/13/2017

---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
Экземпляр переменной класса или структуры используется для доступа к `Shared` переменной, свойства, процедуры или события, определенного в классе или структуре. Это предупреждение может возникать, если переменная экземпляра используется для доступа к неявному общему члену класса или структуры, например, константа или перечисление, или вложенного класса или структуры.  
  
 Совместное использование членов предназначен для создания только одной копии этого члена и доступность этой копии для каждого экземпляра класса или структуры, в котором она объявлена. Совместимо с этой целью для доступа к `Shared` член через имя класса или структуры, а не через переменную, содержащую отдельный экземпляр этого класса или структуры.  
  
 Доступ к `Shared` члену через экземпляр переменной делает код более трудным для понимания, поскольку этот член является `Shared`. Кроме того, если такой доступ является частью выражения, которое производит другие действия, такие как `Function` процедура, которая возвращает экземпляр общего члена [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] пропустит выражения и любые другие действия, в противном случае он будет выполнять.  
  
 Дополнительные сведения и пример см. в разделе [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте имя класса или структуры, определяющей `Shared` элемента к нему доступ, как показано в следующем примере.  
  
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
>  Будьте внимательны эффектов области при двух элементы программирования могут иметь то же имя. В предыдущем примере, если объявить экземпляр с помощью `Dim testClass as testClass = Nothing`, компилятор обрабатывает вызов `testClass.sayHello()` как доступ метода посредством имени класса и предупреждение не возникает.  
  
## <a name="see-also"></a>См. также  
 [Общие](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Область видимости в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
