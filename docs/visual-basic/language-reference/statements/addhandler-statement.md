---
title: Оператор AddHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 6ed6f3d4fd77d714ab554d641c0c0fc4f403bbf8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715107"
---
# <a name="addhandler-statement"></a>Оператор AddHandler
Связывает событие с обработчиком событий во время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Части  
|||
|---|---|
|событие|Имя события для обработки.|  
|`eventhandler`|Имя процедуры, которая обрабатывает событие.|
|||
  
## <a name="remarks"></a>Примечания  
 `AddHandler` И `RemoveHandler` операторы позволяют запускать и останавливать обработку событий в любое время, во время выполнения программы.  
  
 Подпись `eventhandler` процедура должна соответствовать сигнатуре события `event`.  
  
 Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия. Оператор `AddHandler` подключает процедуры к событиям во время выполнения. Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие. Дополнительные сведения см. в разделе [обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
>  Для пользовательских событий `AddHandler` инструкция вызывает события `AddHandler` метода доступа. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>См. также
- [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [События](../../../visual-basic/programming-guide/language-features/events/index.md)
