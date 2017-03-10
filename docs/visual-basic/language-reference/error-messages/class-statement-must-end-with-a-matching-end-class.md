---
title: "Оператор Class должен заканчиваться соответствующим End Class | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30481"
  - "bc30481"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30481"
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Оператор Class должен заканчиваться соответствующим End Class
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

`Class` используется для инициации блока `Class`; следовательно, он может располагаться только в начале блока, при этом блок должен заканчиваться соответствующим оператором `End Class`.  Либо имеется лишний оператор `Class`, либо блок `Class` не заканчивается оператором `End Class`.  
  
 **Идентификатор ошибки:** BC30481  
  
### Чтобы исправить эту ошибку  
  
-   Найдите и удалите лишний оператор `Class`.  
  
-   Завершите блок `Class` соответствующим оператором `End Class`.  
  
## См. также  
 [Оператор End \<ключевое\_слово\>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)   
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)