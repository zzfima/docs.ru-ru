---
title: "Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
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
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом разделе перечислены наиболее распространенные проблемы, связанные с обработчиками событий в наследуемых компонентах.  
  
## Процедуры  
  
#### При каждом вызове код в обработчике событий выполняется дважды  
  
-   Наследуемый обработчик события не должен содержать условие [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md).  Метод базового класса уже связан с событием и будет запускаться соответствующим образом.  Необходимо удалить из унаследованного метода условие `Handles`.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#32)]  
  
-   Если наследуемый метод не содержит ключевого слова `Handles`, то следует убедиться, что код не содержит лишних [Оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) или каких\-либо дополнительных методов, обрабатывающих одно и то же событие.  
  
## См. также  
 [События](../../../../visual-basic/programming-guide/language-features/events/events.md)