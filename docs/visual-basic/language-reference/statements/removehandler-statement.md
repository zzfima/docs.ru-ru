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
ms.openlocfilehash: 3a839a7d05d05066f6c0f774a683c8fc83c19643
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957726"
---
# <a name="removehandler-statement"></a>Оператор RemoveHandler
Удаляет связь между событием и обработчиком событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`event`|Имя обрабатываемого события.|  
|`eventhandler`|Имя процедуры, которая в настоящее время обрабатывает событие.|  
  
## <a name="remarks"></a>Примечания  
 Инструкции `AddHandler` и`RemoveHandler` позволяют запускать и прекращать обработку событий для определенного события в любое время во время выполнения программы.  
  
> [!NOTE]
> Для пользовательских событий `RemoveHandler` оператор вызывает `RemoveHandler` метод доступа события. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также

- [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [События](../../../visual-basic/programming-guide/language-features/events/index.md)
