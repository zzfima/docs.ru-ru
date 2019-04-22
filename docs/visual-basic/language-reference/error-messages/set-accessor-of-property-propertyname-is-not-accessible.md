---
title: Метод доступа Set свойства <propertyname> недоступен
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 3bc50d6762998ca5d8f445d84c8b698c9f46436f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834469"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a>Метод доступа свойства «set» "\<имя_свойства >" не доступен
Оператор пытается сохранить значение свойства, если он не имеет доступа к свойству `Set` процедуры.  
  
 Если [инструкция Set](../../../visual-basic/language-reference/statements/set-statement.md) помечается более строгий доступ уровня, чем его [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), попытка задать значение свойства может завершиться ошибкой в следующих случаях:  
  
-   `Set` Оператор помечен [частного](../../../visual-basic/language-reference/modifiers/private.md) и вызывающий код находится за пределами класса или структуры, в котором оно определено свойство.  
  
-   `Set` Оператор помечен [Protected](../../../visual-basic/language-reference/modifiers/protected.md) и вызывающий код находится не в классе или структуре, в котором оно определено свойство, ни в производном классе.  
  
-   `Set` Оператор помечен [Friend](../../../visual-basic/language-reference/modifiers/friend.md) и вызывающий код не находится в той же сборке, в котором оно определено свойство.  
  
 **Идентификатор ошибки:** BC31102  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если у вас есть контроль исходного кода, определяющего свойство, рассмотрим следующее объявление `Set` процедуру с тот же уровень доступа, как и само свойство.  
  
-   Если у вас нет контроля исходного кода, определяющего свойство или необходимо ограничить `Set` больше, чем у самого свойства, попробуйте переместить оператор, который задает значение свойства в область кода, имеющего более удобный доступ к процедуре уровень доступа свойство.  
  
## <a name="see-also"></a>См. также

- [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
