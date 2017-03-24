---
title: "Практическое руководство: объявление пользовательских событий для экономии памяти (Visual Basic) | Документы Microsoft"
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
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 4f8ce32a3b4da411a73010119283ce9661b82a6c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Практическое руководство. Объявление пользовательских событий для экономии памяти (Visual Basic)
Существует несколько случаев, когда важно, что приложение небольшое использование памяти. Пользовательские события позволяют приложению использовать память только для событий, которые он обрабатывает.  
  
 По умолчанию когда класс объявляет событие, компилятор выделяет память под поле для хранения сведений о событии. Если класс имеет много неиспользуемых событий, они занимают много памяти.  
  
 Вместо использования реализации событий, которую Visual Basic предоставляет по умолчанию, можно использовать пользовательские события для более тщательного управления памятью.  
  
## <a name="example"></a>Пример  
 В этом примере класс использует один экземпляр <xref:System.ComponentModel.EventHandlerList>классов, хранящихся в `Events` поле для хранения информации о событиях, используется.</xref:System.ComponentModel.EventHandlerList> <xref:System.ComponentModel.EventHandlerList>— Это класс оптимизированного список, созданным для хранения делегатов.</xref:System.ComponentModel.EventHandlerList>  
  
 Все события класса используют `Events` поля для отслеживания того, какие методы являются обработчиками каждого события.  
  
 [!code-vb[VbVbalrEvents&#22;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ComponentModel.EventHandlerList></xref:System.ComponentModel.EventHandlerList>   
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Практическое руководство. Объявление пользовательских событий для предотвращения блокировки](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
