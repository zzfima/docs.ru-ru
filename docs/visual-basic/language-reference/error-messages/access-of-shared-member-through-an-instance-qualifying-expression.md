---
title: Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 773a97c301e7cb5bec0234ae466d487ec9716437
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250348"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Доступ к общему члену через экземпляр; выражение уточнения не вычисляется

Переменная экземпляра класса или структуры используется для доступа к переменной, свойству, процедуре или событию `Shared`, определенному в этом классе или структуре. Это предупреждение также может возникать, если переменная экземпляра используется для доступа к неявно используемому члену класса или структуры, например константы или перечисления, или вложенного класса или структуры.

Целью совместного использования элемента является создание только одной копии этого члена и предоставление доступа к этой копии каждому экземпляру класса или структуры, в которой он объявлен. Это согласуется с этой целью для доступа к члену `Shared` через имя класса или структуры, а не через переменную, содержащую отдельный экземпляр этого класса или структуры.

Доступ к члену `Shared` через переменную экземпляра может сделать код более сложным для понимания, скрывая тот факт, что элемент `Shared`. Более того, если такой доступ является частью выражения, выполняющего другие действия, такие как процедура `Function`, возвращающая экземпляр общего члена, Visual Basic обходит выражение и другие действия, которые в противном случае будут выполнены.  
  
Дополнительные сведения и пример см. в разделе [Shared](../modifiers/shared.md).  
  
По умолчанию данное сообщение является предупреждением. Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
**Идентификатор ошибки:** BC42025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
Используйте имя класса или структуры, определяющей элемент `Shared` для доступа к нему, как показано в следующем примере:
  
```vb
Public Class TestClass
    Public Shared Sub SayHello()
        MsgBox("Hello")
    End Sub
End Class
  
Module Program
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New TestClass()
        tc.SayHello()
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        TestClass.SayHello()
    End Sub  
End Module  
```  
  
> [!NOTE]
> Будьте предупреждать о влиянии области видимости, если два программных элемента имеют одинаковые имена. В предыдущем примере, если экземпляр объявляется с помощью `Dim testClass as testClass = Nothing`, компилятор рассматривает вызов `testClass.sayHello()` как доступ к методу через имя класса, и предупреждение не возникает.
  
## <a name="see-also"></a>См. также

- [Общие](../modifiers/shared.md)
- [Область в Visual Basic](../../programming-guide/language-features/declared-elements/scope.md)
