---
title: "Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a36c855efb67752674615a61f2fa701974ce5f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)
Существует несколько случаев, когда важно, что один обработчик событий не блокировал последующие. Пользовательские события позволяют событий для асинхронного вызова соответствующих обработчиков событий.  
  
 По умолчанию поле резервного хранилища для объявления события является многоадресным делегатом, последовательно объединяющим все обработчики событий. Это означает, что если один обработчик занимает много времени, он блокирует другие обработчики до его завершения. (Хороший обработчик событий никогда не будет выполнять длинные или потенциально блокирующие операции.)  
  
 Вместо использования реализации событий, которые предоставляет Visual Basic по умолчанию, можно использовать пользовательское событие для асинхронного выполнения обработчиков событий.  
  
## <a name="example"></a>Пример  
 В этом примере `AddHandler` доступа добавляет делегат для каждого обработчика из `Click` событий для <xref:System.Collections.ArrayList> хранятся в `EventHandlerList` поле.  
  
 Когда код вызывает `Click` событий, `RaiseEvent` все асинхронно с помощью делегатов обработчиков событий вызывает метод доступа <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> метод. Этот метод вызывает каждый обработчик в рабочем потоке и немедленно возвращает, чтобы обработчики не может блокировать друг с другом.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Практическое руководство. Объявление пользовательских событий для экономии памяти](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
