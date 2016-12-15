---
title: "Лямбда-выражение не будет удалено из этого обработчика событий | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc42326"
  - "vbc42326"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42326"
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Лямбда-выражение не будет удалено из этого обработчика событий
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Лямбда\-выражение не удаляется из этого обработчика событий.Назначьте лямбда\-выражение переменной и используйте ее для добавления и удаления события.  
  
 Если лямбда\-выражение используется вместе с обработчиками событий, ожидаемое поведение может не наблюдаться.  Для каждого определения лямбда\-выражения компилятор создает новый метод, даже если они идентичны.  Поэтому следующий код отображает `False`.  
  
```vb#  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 Использование лямбда\-выражений вместе с обработчиками событий может привести к непредвиденным результатам.  В приведенном ниже примере лямбда\-выражение, добавленное с помощью `AddHandler` не удаляется оператором `RemoveHandler`.  
  
```vb#  
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
  
 По умолчанию это сообщение является предупреждающим.  Сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки, см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC42326  
  
### Чтобы исправить эту ошибку  
  
-   Чтобы избежать появления предупреждающего сообщения и удалить лямбда\-выражение, назначьте его переменной и используйте последнюю в операторах `AddHandler` и `RemoveHandler`, как показано в примере ниже.  
  
    ```vb#  
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
  
## См. также  
 [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/events.md)