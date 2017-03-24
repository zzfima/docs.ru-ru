---
title: "Оператор недопустим в теле метода/многострочного лямбда-оператора | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30024"
  - "bc30024"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30024"
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Оператор недопустим в теле метода/многострочного лямбда-оператора
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Недопустимый оператор в `Sub`, `Function`, процедуре свойства `Get` или `Set`.  Некоторые операторы можно поместить на уровне модуля или класса.  Другие, например `Option Strict`, должны находиться на уровне пространства имен и предшествовать всем остальным объявлениям.  
  
 **Идентификатор ошибки**: BC30024  
  
### Чтобы исправить эту ошибку  
  
-   Удалите оператор из процедуры.  
  
## См. также  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)