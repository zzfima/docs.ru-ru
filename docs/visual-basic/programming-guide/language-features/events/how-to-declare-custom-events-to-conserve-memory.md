---
title: Практическое руководство. Объявление пользовательских событий для экономии памяти
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3cc2d3ea57f1a8daf704c2c929baf3f2acf78c17
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345127"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)
Существует несколько ситуаций, когда важно, чтобы приложение продолжало использовать память в низком объеме. Пользовательские события позволяют приложению использовать память только для обрабатываемых событий.  
  
 По умолчанию, когда класс объявляет событие, компилятор выделяет память для поля, в котором хранятся сведения о событии. Если класс содержит много неиспользуемых событий, они не занимают память.  
  
 Вместо использования реализации по умолчанию событий, предоставляемых Visual Basic, можно использовать пользовательские события для более тщательного управления использованием памяти.  
  
## <a name="example"></a>Пример  
 В этом примере класс использует один экземпляр класса <xref:System.ComponentModel.EventHandlerList>, хранящийся в поле `Events`, для хранения сведений об используемых событиях. Класс <xref:System.ComponentModel.EventHandlerList> является оптимизированным классом списка, предназначенным для хранения делегатов.  
  
 Все события в классе используют поле `Events` для наблюдения за тем, какие методы обрабатывают каждое событие.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ComponentModel.EventHandlerList>
- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
