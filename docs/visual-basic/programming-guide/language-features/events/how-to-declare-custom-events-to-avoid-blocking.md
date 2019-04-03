---
title: Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 6eea47ea2c8aee697eb34ca904dad22ca88e6ce4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821261"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>Практическое руководство. Объявление пользовательских событий для предотвращения блокировки (Visual Basic)
Существует несколько случаев, когда важно, что один обработчик событий не блокировал последующие. Пользовательские события позволяют событие асинхронный вызов соответствующих обработчиков событий.  
  
 По умолчанию поле резервного хранилища для объявления события является многоадресным делегатом, который последовательно объединяет все обработчики событий. Это означает, что если один обработчик занимает много времени для завершения, он блокирует другие обработчики до завершения этой операции. (Хороший обработчик событий не должны выполнять длительных или потенциально блокирующих операций.)  
  
 Вместо реализации событий, предоставляемых Visual Basic по умолчанию, можно использовать пользовательское событие для асинхронного выполнения обработчиков событий.  
  
## <a name="example"></a>Пример  
 В этом примере `AddHandler` доступа добавляет делегат для каждого обработчика из `Click` событие <xref:System.Collections.ArrayList> хранятся в `EventHandlerList` поля.  
  
 Когда код вызывает `Click` событий, `RaiseEvent` все асинхронно с помощью делегатов обработчиков событий вызывает метод доступа <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> метод. Этот метод вызывает каждый обработчик в рабочем потоке и немедленно возвращает, чтобы обработчики не блокируют друг друга.  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Практическое руководство. Объявление пользовательских событий для экономии памяти](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
