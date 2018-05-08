---
title: Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: d19c91d66e458ca2317dc049d517b92fa7406ef6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
