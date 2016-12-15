---
title: "Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов | Microsoft Docs"
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
  - "vbc30506"
  - "bc30506"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30506"
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Переменная `WithEvents` не была предоставлена в предложении `Handles`.  Ключевое слово `Handles` используется в конце объявления процедуры, чтобы задать ее для обработки событий, созданных объектной переменной, объявленной с помощью ключевого слова `WithEvents`.  
  
 **Идентификатор ошибки:** BC30506  
  
### Чтобы исправить эту ошибку  
  
-   Укажите необходимую переменную `WithEvents`.  
  
## См. также  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)