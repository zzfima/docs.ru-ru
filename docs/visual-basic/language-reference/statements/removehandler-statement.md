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
ms.openlocfilehash: 8a9dc5874629c1687318496bd7c4016eb318c25a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831687"
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
|`eventhandler`|Имя процедуры, которая обрабатывает событие.|  
  
## <a name="remarks"></a>Примечания  
 `AddHandler` И `RemoveHandler` операторы позволяют запускать и останавливать обработку событий для конкретного события в любое время, во время выполнения программы.  
  
> [!NOTE]
>  Для пользовательских событий `RemoveHandler` инструкция вызывает события `RemoveHandler` метода доступа. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также

- [Оператор AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [События](../../../visual-basic/programming-guide/language-features/events/index.md)
