---
title: '&#39;Получить&#39; метод доступа свойства &#39; &lt;propertyname&gt; &#39; недоступен'
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 10b7168ac40ca7c7d696cd63cd823454f404bb94
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582218"
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39;Получить&#39; метод доступа свойства &#39; &lt;propertyname&gt; &#39; недоступен
Оператор пытается извлечь значение свойства, если он не имеет доступа к свойству `Get` процедуры.  
  
 Если [оператор Get](../../../visual-basic/language-reference/statements/get-statement.md) помечается более строгий доступ уровня, чем его [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), попытка прочитать значение свойства может завершиться ошибкой в следующих случаях:  
  
-   `Get` Оператор помечен [частного](../../../visual-basic/language-reference/modifiers/private.md) и вызывающий код находится за пределами класса или структуры, в котором оно определено свойство.  
  
-   `Get` Оператор помечен [Protected](../../../visual-basic/language-reference/modifiers/protected.md) и вызывающий код находится не в классе или структуре, в котором оно определено свойство, ни в производном классе.  
  
-   `Get` Оператор помечен [Friend](../../../visual-basic/language-reference/modifiers/friend.md) и вызывающий код не находится в той же сборке, в котором оно определено свойство.  
  
 **Идентификатор ошибки:** BC31103  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если у вас есть контроль исходного кода, определяющего свойство, рассмотрим следующее объявление `Get` процедуру с тот же уровень доступа, как и само свойство.  
  
-   Если у вас нет контроля исходного кода, определяющего свойство или необходимо ограничить `Get` больше, чем у самого свойства, попробуйте переместить инструкцию, которая считывает значение свойства для области кода, имеющий более удобный доступ к процедуре уровень доступа свойство.  
  
## <a name="see-also"></a>См. также
- [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
