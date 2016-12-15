---
title: "Имя члена анонимного типа может быть определено только из простого или уточненного имени без аргументов | Microsoft Docs"
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
  - "vbc36556"
  - "bc36556"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36556"
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Имя члена анонимного типа может быть определено только из простого или уточненного имени без аргументов
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Нельзя вывести имя члена анонимного типа из сложного выражения.  
  
```vb#  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Дополнительные сведения об источниках, из которых можно или нельзя вывести имена и типы членов, см. в разделе [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
 **Идентификатор ошибки:** BC36556  
  
### Чтобы исправить эту ошибку  
  
-   Назначьте выражение для имени члена, как показано в следующем коде:  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## См. также  
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)