---
title: "Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic) | Microsoft Docs"
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
  - "пользовательские события"
  - "объявление событий, пользовательский"
  - "события [Visual Basic], пользовательский"
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Существует несколько случаев, когда важно, чтобы один обработчик событий не блокировал последующие.  Пользовательские события позволяют событию вызывать его обработчики событий в асинхронном режиме.  
  
 По умолчанию поле резервного хранения для события является многоадресным делегатом, последовательно объединяющим все обработчики событий.  Это означает, что если завершение работы одного обработчика занимает много времени, он блокирует другие обработчики вплоть до завершения своей работы.  \(Хороший обработчик событий никогда не будет выполнять длинные или потенциально блокирующие операции.\)  
  
 Вместо использования реализации событий, которую Visual Basic предоставляет по умолчанию, можно использовать пользовательское событие для запуска обработчиков событий в асинхронном режиме.  
  
## Пример  
 В этом примере метод доступа `AddHandler` добавляет делегат для каждого обработчика событий`Click` для <xref:System.Collections.ArrayList>, хранящегося в поле `EventHandlerList`.  
  
 Когда код вызывает событие `Click`, метод доступа `RaiseEvent` вызывает все делегаты обработчика события, асинхронно используя метод <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>.  Этот метод вызывает каждый обработчик на рабочем потоке и немедленно возвращает, чтобы обработчики не могли блокировать друг с друга.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## См. также  
 <xref:System.Collections.ArrayList>   
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>   
 [События](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Практическое руководство. Объявление пользовательских событий для экономии памяти](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)