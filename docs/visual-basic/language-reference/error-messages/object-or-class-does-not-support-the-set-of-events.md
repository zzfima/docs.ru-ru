---
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 82f3acff1730b4b31b0118a46376825c8807e1da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552155"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>Объект или класс не поддерживает набор событий
Предпринята попытка использования `WithEvents` переменной с компонентом, который не может служить источником событий для указанного набора событий. Например, вы хотели приемник событий объекта, а затем создать другой объект, который `Implements` первый объект. Несмотря на то, что может показаться, что удалось приемник событий из реализованного объекта, это не всегда так. `Implements` реализует только интерфейс для методов и свойств. `WithEvents` не поддерживается для частных `UserControls`, так как сведения о типе требуется для вызова `ObjectEvent` недоступен во время выполнения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не удается получить события для компонента, который не является источником событий.  
  
## <a name="see-also"></a>См. также
- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
