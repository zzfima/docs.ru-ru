---
title: "Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)"
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
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eec9a2fc687f481ab40313e35cbde81c25b81ae8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)
Существует несколько случаев, когда важно, что приложение свести использование памяти. Пользовательские события позволяют приложению использовать память только для событий, которые он обрабатывает.  
  
 По умолчанию когда класс объявляет событие, компилятор выделяет память для поля для хранения информации о событиях. Если класс имеет много неиспользуемых событий, они занимают много памяти.  
  
 Вместо использования реализации событий, которые предоставляет Visual Basic по умолчанию, можно использовать пользовательские события для более тщательного управления памятью.  
  
## <a name="example"></a>Пример  
 В этом примере класс использует один экземпляр <xref:System.ComponentModel.EventHandlerList> класса, хранящиеся в `Events` поле для хранения сведений о событиях использования. <xref:System.ComponentModel.EventHandlerList> Класс — это класс оптимизированного списка, созданным для хранения делегатов.  
  
 Все события класса используют `Events` поля для отслеживания какие методы являются обработчиками каждого события.  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ComponentModel.EventHandlerList>  
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
