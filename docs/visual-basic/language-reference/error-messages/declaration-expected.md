---
title: "Ожидается объявление | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30188"
  - "bc30188"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30188"
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Ожидается объявление
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Недекларативный оператор, например оператор присваивания или цикла, находится вне процедуры.  Вне процедур могут находиться только объявления.  
  
 Кроме того, возможно, что программный элемент был объявлен без зарезервированного слова объявления, например `Dim` или `Const`.  
  
 **Идентификатор ошибки**: BC30188  
  
### Чтобы исправить эту ошибку  
  
-   Переместите недекларативный оператор в текст процедуры.  
  
-   В начале объявления используйте соответствующее зарезервированное слово объявления.  
  
-   Проверьте правильность написания зарезервированного слова объявления.  
  
## См. также  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)