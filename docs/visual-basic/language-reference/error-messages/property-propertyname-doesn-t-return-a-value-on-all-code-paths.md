---
title: Свойство ''<propertyname>'' возвращает значение не для всех ветвей кода
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: a535a6b951dc9872109527f78d7de5f3fcdd3292
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821885"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a>Свойство "\<имя_свойства >" не возвращает значение на всех путях кода
Свойство "\<имя_свойства >" не возвращает значение на всех путях кода. Во время выполнения может возникнуть исключение, связанное с пустой ссылкой, когда используется результат.  
  
 Свойство `Get` процедура имеет по крайней мере один возможный путь во всем коде, который не возвращает значение.  
  
 Может возвращать значение из свойства `Get` процедуры в любой из следующих способов:  
  
-   Присвойте значение имени свойства, а затем выполнить `Exit Property` инструкции.  
  
-   Присвойте значение имени свойства, а затем выполнить `End Get` инструкции.  
  
-   Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Если управление передается `Exit Property` или `End Get` и не назначенные любое значение в имя свойства `Get` процедура возвращает значение по умолчанию тип данных свойства. Дополнительные сведения см. в разделе «Поведение» в [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42107  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждой инструкции, которая вызывает возврат.  
  
     Проще гарантировать, что каждое возвращение из процедуры возвращает значение, если всегда использовать `Return` инструкции. После этого, последней инструкцией перед `End Get` должно быть `Return` инструкции.  
  
## <a name="see-also"></a>См. также

- [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)
