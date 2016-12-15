---
title: "Операнд IsNot типа &lt;имяТипа&gt; можно сравнить только с Nothing, так как &lt;имяТипа&gt; является типом, допускающим значение NULL | Microsoft Docs"
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
  - "bc32128"
  - "vbc32128"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32128"
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Операнд IsNot типа &lt;имяТипа&gt; можно сравнить только с Nothing, так как &lt;имяТипа&gt; является типом, допускающим значение NULL
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Переменная типа nullable сравнивается с выражением, отличным от `Nothing`, с помощью оператора `IsNot`.  
  
 **Идентификатор ошибки**: BC32128  
  
### Чтобы исправить эту ошибку  
  
1.  Чтобы сравнить тип nullable и выражение, отличное от `Nothing`, с помощью оператора `IsNot`, вызовите метод `GetType` для типа nullable и сравните результат выражения, как показано в следующем примере.  
  
    ```vb#  
    Dim number? As Integer = 5  
  
    If number IsNot Nothing Then  
      If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
      End If  
    End If  
    ```  
  
## См. также  
 [Типы значения, допускающие Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)