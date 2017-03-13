---
title: "Оператор AddHandler | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AddHandlerMethod"
  - "addhandler"
  - "vb.addhandler"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddHandler - оператор"
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Оператор AddHandler
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Во время выполнения связывает событие с обработчиком события.  
  
## Синтаксис  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## Части  
 `event`  
 Имя события для обработки.  
  
 `eventhandler`  
 Имя процедуры, которая обрабатывает событие.  
  
## Заметки  
 Операторы `AddHandler` и `RemoveHandler` позволяют в любой момент выполнения программы начать и закончить обработку события.  
  
 Описание процедуры `eventhandler` должно соответствовать описанию события `event`.  
  
 Ключевое слово `Handles` и оператор `AddHandler` позволяют задать конкретные процедуры обработки определенных событий, но между ними существуют различия.  Оператор `AddHandler` подключает процедуры для событий во время выполнения.  Ключевое слово `Handles` используется при определении процедуры, чтобы указать, что она будет обрабатывать конкретное событие.  Дополнительные сведения см. в разделе [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
>  Для пользовательских событий оператор `AddHandler` вызывает метод доступа события `AddHandler`.  Дополнительные сведения о пользовательских событиях см. в разделе [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Пример  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## См. также  
 [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/events.md)