---
title: "&lt;имяСобытия&gt; является событием, поэтому его прямой вызов невозможен | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32022"
  - "vbc32022"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32022"
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;имяСобытия&gt; является событием, поэтому его прямой вызов невозможен
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

\<`eventname`\> является событием, поэтому его прямой вызов невозможен.  Для создания события используйте оператор `RaiseEvent`.  
  
 При вызове процедуры указывается событие, связанное с ее именем.  Обработчик событий представляет собой процедуру, но само событие является сигнальным устройством, которое должно быть создано и обработано.  
  
 **Идентификатор ошибки:** BC32022  
  
### Чтобы исправить эту ошибку  
  
1.  Используйте оператор `RaiseEvent` для генерации события и вызова процедуры или процедуры его обработки.  
  
## См. также  
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)