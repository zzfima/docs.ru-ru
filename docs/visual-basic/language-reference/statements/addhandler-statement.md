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
ms.openlocfilehash: 95277f532488b0cf56114e5ee94dc3528e3a2e02
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004540"
---
# <a name="addhandler-statement"></a>Оператор AddHandler
Связывает событие с обработчиком событий во время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Части  
|||
|---|---|
|event|Имя обрабатываемого события.|  
|`eventhandler`|Имя процедуры, которая обрабатывает событие.|
|||
  
## <a name="remarks"></a>Примечания  
 Операторы `AddHandler` и `RemoveHandler` позволяют запускать и прекращать обработку событий в любое время во время выполнения программы.  
  
 Сигнатура процедуры `eventhandler` должна соответствовать сигнатуре события `event`.  
  
 Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия. Оператор `AddHandler` подключает процедуры к событиям во время выполнения. Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие. Дополнительные сведения см. в разделе [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
> Для пользовательских событий оператор `AddHandler` вызывает метод доступа `AddHandler` события. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также

- [Оператор RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [События](../../../visual-basic/programming-guide/language-features/events/index.md)
