---
title: Лямбда-выражение не будет удалено из этого обработчика событий
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 69228bbb5f659a8e500e85dea1ef87cb43b0356e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a>Лямбда-выражение не будет удалено из этого обработчика событий
Лямбда-выражение не удаляется из этого обработчика событий. Присвойте переменной лямбда-выражение и используйте переменную для добавления и удаления события.  
  
 При использовании лямбда-выражения с обработчиками событий, могут не отображаться ожидаемое поведение. Компилятор создает новый метод для каждого определения лямбда-выражения, даже если они идентичны. Таким образом, следующий код отображает `False`.  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 При использовании лямбда-выражения с обработчиками событий, это может привести к непредвиденным результатам. В следующем примере лямбда-выражения, добавленные `AddHandler` не удаляется с `RemoveHandler` инструкции.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Sub Main()  
  
        ' The following line adds one listener to the event.  
        AddHandler ProcessInteger, Function(m As Integer) m  
  
        ' The following statement searches the current listeners   
        ' for a match to remove. However, this lambda is not the same  
        ' as the previous one, so nothing is removed.  
        RemoveHandler ProcessInteger, Function(m As Integer) m  
  
    End Sub  
End Module  
```  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42326  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Чтобы избежать этого предупреждения и удалить лямбда-выражение, присвойте переменной лямбда-выражение и используйте переменную в обоих `AddHandler` и `RemoveHandler` инструкции, как показано в следующем примере.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Dim PrintHandler As ProcessIntegerEventHandler  
  
    Sub Main()  
  
        ' Assign the lambda expression to a variable.  
        PrintHandler = Function(m As Integer) m  
  
        ' Use the variable to add the listener.  
        AddHandler ProcessInteger, PrintHandler  
  
        ' Use the variable again when you want to remove the listener.  
        RemoveHandler ProcessInteger, PrintHandler  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)
