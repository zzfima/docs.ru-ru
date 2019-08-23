---
title: Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 3174d463744303e8c90ed0b2e1a4d86ed08fbcfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947698"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
Переменная экземпляра класса или структуры используется для доступа к `Shared` переменной, свойству, процедуре или событию, определенному в этом классе или структуре. Это предупреждение также может возникать, если переменная экземпляра используется для доступа к неявно используемому члену класса или структуры, например константы или перечисления, или вложенного класса или структуры.  
  
 Целью совместного использования элемента является создание только одной копии этого члена и предоставление доступа к этой копии каждому экземпляру класса или структуры, в которой он объявлен. Это согласуется с этой целью для доступа к `Shared` члену через имя класса или структуры, а не через переменную, содержащую отдельный экземпляр этого класса или структуры.  
  
 Доступ к `Shared`члену через переменную экземпляра может сделать код более сложным для понимания, скрывая тот факт, что он является членом. `Shared` Более того, если такой доступ является частью выражения, выполняющего другие действия, такие как `Function` процедура, возвращающая экземпляр общего члена, Visual Basic обходит выражение и другие действия, которые в противном случае будут выполнены.  
  
 Дополнительные сведения и пример см. в разделе [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте имя класса или структуры, определяющей `Shared` элемент для доступа к нему, как показано в следующем примере.  
  
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
> Будьте предупреждать о влиянии области видимости, если два программных элемента имеют одинаковые имена. В предыдущем примере, если экземпляр объявляется с помощью `Dim testClass as testClass = Nothing`, компилятор рассматривает `testClass.sayHello()` вызов как доступ к методу через имя класса, и предупреждение не возникает.  
  
## <a name="see-also"></a>См. также

- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [Область в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
