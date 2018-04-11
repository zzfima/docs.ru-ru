---
title: Оператор AddHandler
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07fbfe04ccd01b7d0f99338ef2682238830099dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="addhandler-statement"></a>Оператор AddHandler
Связывает событие с обработчиком событий во время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Части  
 `event`  
 Имя события для обработки.  
  
 `eventhandler`  
 Имя процедуры, которая обрабатывает событие.  
  
## <a name="remarks"></a>Примечания  
 `AddHandler` И `RemoveHandler` инструкции позволяют запускать и останавливать обработку события в любое время во время выполнения программы.  
  
 Подпись `eventhandler` процедуры должна соответствовать сигнатуре события `event`.  
  
 Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия. Оператор `AddHandler` подключает процедуры к событиям во время выполнения. Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие. Дополнительные сведения см. в разделе [обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
>  Для пользовательских событий `AddHandler` инструкция вызывает событие `AddHandler` метода доступа. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)
