---
title: Оператор RemoveHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 47f35bd76d7734878e7b5b206b4aecd856276593
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582020"
---
# <a name="removehandler-statement"></a>Оператор RemoveHandler
Удаляет связь между событием и обработчиком событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`event`|Имя обрабатываемого события.|  
|`eventhandler`|Имя процедуры, которая в настоящее время обрабатывает событие.|  
  
## <a name="remarks"></a>Заметки  
 Операторы `AddHandler` и `RemoveHandler` позволяют запускать и прекращать обработку событий для определенного события в любое время во время выполнения программы.  
  
> [!NOTE]
> Для пользовательских событий оператор `RemoveHandler` вызывает метод доступа `RemoveHandler` события. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также

- [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [События](../../../visual-basic/programming-guide/language-features/events/index.md)
