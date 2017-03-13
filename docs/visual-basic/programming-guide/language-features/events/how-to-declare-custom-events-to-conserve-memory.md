---
title: "Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic) | Microsoft Docs"
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
  - "пользовательские события"
  - "объявление событий, пользовательский"
  - "события [Visual Basic], пользовательский"
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В некоторых случаях важно, чтобы использование памяти приложением было низким.  Пользовательские события позволяют приложению использовать память только для событий, которые оно обрабатывает.  
  
 По умолчанию, когда класс объявляет событие, компилятор выделяет память под поле для хранения сведений события.  Если класс имеет много неиспользуемых событий, они занимают много памяти.  
  
 Вместо использования реализации событий, которую Visual Basic предоставляет по умолчанию, можно использовать пользовательские события для более тщательного управления памятью.  
  
## Пример  
 В этом примере класс использует один экземпляр класса <xref:System.ComponentModel.EventHandlerList>, хранящийся в поле `Events`, для хранения сведений о используемых событиях.  Класс <xref:System.ComponentModel.EventHandlerList> является оптимизированным списочным классом, созданным для хранения делегатов.  
  
 Все события класса используют поле `Events` для наблюдения за тем, какие методы являются обработчиками каждого события.  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## См. также  
 <xref:System.ComponentModel.EventHandlerList>   
 [События](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)