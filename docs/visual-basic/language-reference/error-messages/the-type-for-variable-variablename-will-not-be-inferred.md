---
title: "Тип для переменной &lt;variablename&gt; не будет определен, так как она привязана к полю во включающей области | Microsoft Docs"
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
  - "vbc42110"
  - "bc42110"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42110"
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
caps.latest.revision: 33
caps.handback.revision: 33
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип для переменной &lt;variablename&gt; не будет определен, так как она привязана к полю во включающей области
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Тип для переменной '\<variablename\>' не будет выведен, поскольку он привязан к полю во внешней области.Либо измените имя variablename '\<\>', или используйте полное имя \(например, «Me.variablename» или «MyBase.variablename "\).  
  
 Имя переменной цикла совпадает с именем поля класса или другой заключающей ее области видимости.  Поскольку управляющая переменная используется без предложения `As`, она присоединена к полю во включающей области, и компилятор не создает новую переменную и не выводит ее тип.  
  
 В следующем примере управляющая переменная `Index` в операторе `For` связана с полем `Index` в классе `Customer`.  Компилятор не создает новую переменную для управляющей переменной `Index` и не выводит ее тип.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
  
```  
  
 По умолчанию это сообщение является предупреждающим.  Сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки, см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC42110  
  
### Чтобы устранить это предупреждение, выполните следующие действия:  
  
-   Сделайте переменную цикла локальной, изменив ее имя на уникальный идентификатор.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   Поясните с помощью префикса `Me.` у имени переменной цикла, что она привязывается к полю класса.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   Вместо того, чтобы полагаться на вывод локального типа, используйте предложение `As` для задания типа переменной цикла.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## Пример  
 В следующем коде показан исправленный первым способом предыдущий пример.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## См. также  
 [Option Infer \- оператор](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Практическое руководство. Ссылка на текущий экземпляр объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)