---
title: Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: f6355cf7fc2e43651c1112d048220a8179968c76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic
В этом разделе перечислены распространенные проблемы, связанные с обработчиками событий в наследуемых компонентах.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Код в обработчик событий выполняется дважды для каждого вызова  
  
-   Наследуемый обработчик события не должны содержать [обрабатывает](../../../../visual-basic/language-reference/statements/handles-clause.md) предложения. Метод в базовом классе уже связан с событием и будет запущен. Удалить `Handles` предложения из унаследованного метода.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   Если производный метод не имеет `Handles` ключевое слово, убедитесь, что код не содержит лишних [оператор AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) или любые дополнительные методы, обрабатывающие того же события.  
  
## <a name="see-also"></a>См. также  
 [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
