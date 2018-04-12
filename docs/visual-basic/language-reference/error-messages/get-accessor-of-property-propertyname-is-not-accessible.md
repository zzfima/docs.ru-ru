---
title: '&#39; Получить &#39; метод доступа свойства &#39; &lt;propertyname&gt;&#39; недоступен'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 167e040570af1fc78ce48f5e930e54981ba909ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39; Получить &#39; метод доступа свойства &#39; &lt;propertyname&gt;&#39; недоступен
Оператор пытается извлечь значение свойства, если он не имеет доступа к свойству `Get` процедуры.  
  
 Если [оператор Get](../../../visual-basic/language-reference/statements/get-statement.md) помечается более строгий доступ уровня, чем его [оператор Property](../../../visual-basic/language-reference/statements/property-statement.md), попытка прочитать значение свойства может завершиться ошибкой в следующих случаях:  
  
-   `Get` Оператор помечен [закрытый](../../../visual-basic/language-reference/modifiers/private.md) и вызывающий код находится за пределами класса или структуры, в котором определено свойство.  
  
-   `Get` Оператор помечен [Protected](../../../visual-basic/language-reference/modifiers/protected.md) и вызывающий код находится не в классе или структуре, в котором определено свойство, ни в производном классе.  
  
-   `Get` Оператор помечен [Friend](../../../visual-basic/language-reference/modifiers/friend.md) и вызывающий код не находится в той же сборке, в котором определено свойство.  
  
 **Идентификатор ошибки:** BC31103  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если вы управляете исходного кода, определяющего свойство, рассмотрите возможность объявления `Get` процедуру с тем же уровнем доступа, как и само свойство.  
  
-   Если вы не управляете исходного кода, определяющего свойство или необходимо ограничить `Get` уровень доступа процедуры больше, чем к самому свойству, попробуйте переместить инструкцию, которая считывает значение свойства в область кода, который имеет более удобный доступ к свойство.  
  
## <a name="see-also"></a>См. также  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
