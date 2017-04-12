---
title: "Практическое руководство: объявление пользовательских событий для предотвращения блокировки (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34b222bdbfdae0673b7150c220ca477b7e286dda
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)
Существует несколько случаев, когда важно, что один обработчик событий не блокировал последующие. Пользовательские события позволяют событию асинхронный вызов обработчикам событий.  
  
 По умолчанию поле резервного хранилища для объявления события является многоадресным делегатом, последовательно объединяющим все обработчики событий. Это означает, что если одного обработчика занимает много времени, он блокирует другие обработчики до завершения. (Хороший обработчик событий никогда не будет выполнять длинные или потенциально блокирующие операции.)  
  
 Вместо использования реализации событий, которую Visual Basic предоставляет по умолчанию, можно использовать пользовательское событие для асинхронного выполнения обработчиков событий.  
  
## <a name="example"></a>Пример  
 В этом примере `AddHandler` доступа добавляет делегат для каждого обработчика из `Click` событие <xref:System.Collections.ArrayList>хранятся в `EventHandlerList` поле.</xref:System.Collections.ArrayList>  
  
 Когда код вызывает `Click` событий, `RaiseEvent` доступа вызывает все асинхронно с помощью делегатов обработчиков событий <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>метод.</xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> Этот метод вызывает каждый обработчик на рабочем потоке и немедленно возвращает, чтобы обработчики не могли блокировать друг с другом.  
  
 [!code-vb[VbVbalrEvents&#27;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.ArrayList></xref:System.Collections.ArrayList>   
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>   
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Практическое руководство. Объявление пользовательских событий для экономии памяти](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
