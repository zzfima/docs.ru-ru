---
title: "Выражение не выдает значение | Microsoft Docs"
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
  - "vbc30491"
  - "bc30491"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30491"
ms.assetid: 8399d7ae-bc0a-49e6-81dc-2e7229708bc9
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Выражение не выдает значение
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Предпринята попытка использовать выражение, не порождающее значение, в контексте, его порождающем, например, вызов процедуры `Sub` вместо ожидающейся по контексту процедуры `Function`.  
  
 **Идентификатор ошибки:** BC30491  
  
### Чтобы исправить эту ошибку  
  
-   Измените выражение таким образом, чтобы оно возвращало значение.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)