---
title: "Лямбда-выражения недопустимы в первом выражении оператора Select Case | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36635"
  - "vbc36635"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36635"
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Лямбда-выражения недопустимы в первом выражении оператора Select Case
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Нельзя использовать лямбда\-выражений для проверки выражения в операторе `Select Case`.  Определения лямбда\-выражений возвращают функции, а тестовое выражение оператора `Select Case` должно иметь простой тип данных.  
  
 Эту ошибку вызывает приведенный ниже код:  
  
```vb#  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Идентификатор ошибки**: BC36635  
  
### Чтобы исправить эту ошибку  
  
-   Проверьте код, чтобы определить будут ли работать другие условные конструкции, такие как оператор `If...Then...Else`.  
  
-   Возможно, потребуется вызвать функцию, как показано в следующем коде:  
  
    ```vb#  
    Dim num? As Integer  
    Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
        ' List of the cases  
    End Select  
    ```  
  
## См. также  
 [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)