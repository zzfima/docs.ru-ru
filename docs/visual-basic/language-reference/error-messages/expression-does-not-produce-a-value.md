---
title: "Выражение не выдает значение | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30491"
  - "bc30491"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30491"
ms.assetid: 8399d7ae-bc0a-49e6-81dc-2e7229708bc9
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Выражение не выдает значение
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предпринята попытка использовать выражение, не порождающее значение, в контексте, его порождающем, например, вызов процедуры `Sub` вместо ожидающейся по контексту процедуры `Function`.  
  
 **Идентификатор ошибки:** BC30491  
  
### Чтобы исправить эту ошибку  
  
-   Измените выражение таким образом, чтобы оно возвращало значение.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)