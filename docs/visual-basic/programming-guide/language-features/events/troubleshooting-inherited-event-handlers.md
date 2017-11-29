---
title: "Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0e8f0b669566bbee6530931bfba9808fad0c085
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
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
