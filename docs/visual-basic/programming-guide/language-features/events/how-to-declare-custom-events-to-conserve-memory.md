---
title: Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: e4132f51f4dd85ad964042d05f7c5bc0a2e6e3cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973164"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)
Существует несколько случаев, когда важно, что приложение усложнять использования памяти. Пользовательские события позволяют приложению использовать память только для событий, которые он обрабатывает.  
  
 По умолчанию когда класс объявляет событие, компилятор выделяет память для поля для хранения сведений о событии. Если у класса имеется много неиспользуемых событий, они занимают много памяти.  
  
 Вместо того чтобы использовать реализацию по умолчанию события, предоставляемые Visual Basic, можно использовать пользовательские события для более тщательного управления памятью.  
  
## <a name="example"></a>Пример  
 В этом примере класс использует один экземпляр <xref:System.ComponentModel.EventHandlerList> классов, хранящихся в `Events` поле для хранения сведений о событиях использования. <xref:System.ComponentModel.EventHandlerList> — Класс оптимизированного списка предназначены для хранения делегатов.  
  
 Все события класса используют `Events` поля для отслеживания какие методы являются обработчиками каждого события.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ComponentModel.EventHandlerList>
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
