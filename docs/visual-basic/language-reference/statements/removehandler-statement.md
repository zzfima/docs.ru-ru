---
title: "Оператор RemoveHandler | Microsoft Docs"
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
  - "vb.RemoveHandlerMethod"
  - "vb.RemoveHandler"
  - "RemoveHandler"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "RemoveHandler - ключевое слово"
  - "RemoveHandler - оператор"
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор RemoveHandler
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Удаляет связь между событием и обработчиком событий.  
  
## Синтаксис  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`event`|Имя обрабатываемого события.|  
|`eventhandler`|Имя процедуры, которая обрабатывает событие.|  
  
## Заметки  
 Операторы `AddHandler` и `RemoveHandler` позволяют в любой момент выполнения программы начать и закончить обработку указанного события.  
  
> [!NOTE]
>  Для пользовательских событий оператор `RemoveHandler` вызывает метод доступа события `RemoveHandler`.  Дополнительные сведения о пользовательских событиях см. в разделе [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Пример  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## См. также  
 [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)   
 [События](../../../visual-basic/programming-guide/language-features/events/events.md)