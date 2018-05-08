---
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 4a6f1f59f43cdb351d49fbcbfd18362db888586e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Объект или класс не поддерживает набор событий
Предпринята попытка использования `WithEvents` переменной с компонентом, который не может служить источником событий для указанного набора событий. Например, требуется приемник событий объекта, создайте другой объект, `Implements` первый объект. Хотя может показаться, что может управлять событиями из реализованного объекта, это не всегда так. `Implements` реализует только интерфейс для методов и свойств. `WithEvents` не поддерживается для частного `UserControls`, так как информация о типе, необходимые для вызова `ObjectEvent` доступен не во время выполнения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не удается получить события для компонента, который не является источником событий.  
  
## <a name="see-also"></a>См. также  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
