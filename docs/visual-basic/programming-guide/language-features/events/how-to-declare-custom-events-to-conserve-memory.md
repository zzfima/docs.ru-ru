---
title: Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3bd58a09d016d818c4cc88c1d2527e81a95411e6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967130"
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
