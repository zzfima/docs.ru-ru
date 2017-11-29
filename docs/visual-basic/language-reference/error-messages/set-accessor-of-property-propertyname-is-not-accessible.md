---
title: "&#39; Выбрать &#39; метод доступа свойства &#39; &lt;propertyname&gt;&#39; недоступен"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords: BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9256a09b719ad3890e1d7c2cc23ffb0d40eec62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39; Выбрать &#39; метод доступа свойства &#39; &lt;propertyname&gt;&#39; недоступен
Оператор пытается сохранить значение свойства, если он не имеет доступа к свойству `Set` процедуры.  
  
 Если [инструкции Set](../../../visual-basic/language-reference/statements/set-statement.md) помечается более строгий доступ уровня, чем его [оператор Property](../../../visual-basic/language-reference/statements/property-statement.md), попытка задать значение свойства может завершиться ошибкой в следующих случаях:  
  
-   `Set` Оператор помечен [закрытый](../../../visual-basic/language-reference/modifiers/private.md) и вызывающий код находится за пределами класса или структуры, в котором определено свойство.  
  
-   `Set` Оператор помечен [Protected](../../../visual-basic/language-reference/modifiers/protected.md) и вызывающий код находится не в классе или структуре, в котором определено свойство, ни в производном классе.  
  
-   `Set` Оператор помечен [Friend](../../../visual-basic/language-reference/modifiers/friend.md) и вызывающий код не находится в той же сборке, в котором определено свойство.  
  
 **Идентификатор ошибки:** BC31102  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если вы управляете исходного кода, определяющего свойство, рассмотрите возможность объявления `Set` процедуру с тем же уровнем доступа, как и само свойство.  
  
-   Если вы не управляете исходного кода, определяющего свойство или необходимо ограничить `Set` уровень доступа процедуры больше, чем к самому свойству, попробуйте переместить инструкцию, которая задает значение свойства в область кода, имеющего более удобный доступ к свойство.  
  
## <a name="see-also"></a>См. также  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
