---
title: "События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами | Microsoft Docs"
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
  - "bc30594"
  - "vbc30594"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30594"
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Переменная, объявленная с модификатором `Shared`, является совместно используемой.  Совместно используемая переменная указывает только одно место хранения.  Если переменная объявлена с модификатором `WithEvents`, то набор событий, вызываемых переменной, обрабатывается ее типом.  Когда переменной присваивается значение, свойство, созданное в результате объявления `WithEvents`, отсоединяется от любого существующего обработчика событий и соединяется с новым обработчиком событий с помощью метода `Add`.  
  
 **Идентификатор ошибки:** BC30594  
  
### Чтобы исправить эту ошибку  
  
-   Объявите обработчик событий `Shared`.  
  
## См. также  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)