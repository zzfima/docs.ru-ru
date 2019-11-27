---
title: Устранение неполадок, связанных с унаследованными обработчиками событий
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: fd2ef1c25233cc1eaad6bcde68923688393b471d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345104"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic
В этом разделе перечислены распространенные проблемы, возникающие при работе с обработчиками событий в наследуемых компонентах.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Код в обработчике событий выполняется дважды для каждого вызова  
  
- Наследуемый обработчик событий не должен включать предложение [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) . Метод в базовом классе уже связан с событием и будет срабатывать соответствующим образом. Удалите предложение `Handles` из унаследованного метода.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- Если наследуемый метод не имеет ключевого слова `Handles`, убедитесь, что код не содержит дополнительную [инструкцию AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) или дополнительные методы, обрабатывающие то же событие.  
  
## <a name="see-also"></a>См. также

- [События](../../../../visual-basic/programming-guide/language-features/events/index.md)
