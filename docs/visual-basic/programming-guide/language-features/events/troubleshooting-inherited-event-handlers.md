---
title: "Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "обработчики событий, устранение неполадок"
  - "обработка событий, устранение неполадок"
  - "унаследованные события"
  - "устранение неполадок для событий"
  - "устранение неполадок - Visual Basic, обработчики событий"
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом разделе перечислены наиболее распространенные проблемы, связанные с обработчиками событий в наследуемых компонентах.  
  
## Процедуры  
  
#### При каждом вызове код в обработчике событий выполняется дважды  
  
-   Наследуемый обработчик события не должен содержать условие [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md).  Метод базового класса уже связан с событием и будет запускаться соответствующим образом.  Необходимо удалить из унаследованного метода условие `Handles`.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   Если наследуемый метод не содержит ключевого слова `Handles`, то следует убедиться, что код не содержит лишних [Оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) или каких\-либо дополнительных методов, обрабатывающих одно и то же событие.  
  
## См. также  
 [События](../../../../visual-basic/programming-guide/language-features/events/events.md)