---
title: '&#39;Задайте&#39; метод доступа свойства &#39; &lt;propertyname&gt; &#39; недоступен'
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: a543506b06742f3ee9101edbac962e761ddd531d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606573"
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39;Задайте&#39; метод доступа свойства &#39; &lt;propertyname&gt; &#39; недоступен
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
