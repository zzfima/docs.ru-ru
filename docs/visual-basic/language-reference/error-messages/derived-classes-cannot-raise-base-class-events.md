---
title: Производные классы не могут вызывать события базового класса
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 365ce6ece1d964d3fac2a44f7ed4c1e16f44c95d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Производные классы не могут вызывать события базового класса
Событие можно вызвать только из области объявления, в котором она объявлена. Таким образом класс не может вызвать событие из другого класса, хотя бы один из которого он является производным.  
  
 **Идентификатор ошибки:** BC30029  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переместить `Event` инструкции или `RaiseEvent` инструкции так, чтобы они в том же классе.  
  
## <a name="see-also"></a>См. также  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
