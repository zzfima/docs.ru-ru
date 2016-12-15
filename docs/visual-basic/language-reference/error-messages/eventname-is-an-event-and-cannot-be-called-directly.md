---
title: "&lt;имяСобытия&gt; является событием, поэтому его прямой вызов невозможен | Microsoft Docs"
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
  - "bc32022"
  - "vbc32022"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32022"
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;имяСобытия&gt; является событием, поэтому его прямой вызов невозможен
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\<`eventname`\> является событием, поэтому его прямой вызов невозможен.  Для создания события используйте оператор `RaiseEvent`.  
  
 При вызове процедуры указывается событие, связанное с ее именем.  Обработчик событий представляет собой процедуру, но само событие является сигнальным устройством, которое должно быть создано и обработано.  
  
 **Идентификатор ошибки:** BC32022  
  
### Чтобы исправить эту ошибку  
  
1.  Используйте оператор `RaiseEvent` для генерации события и вызова процедуры или процедуры его обработки.  
  
## См. также  
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)