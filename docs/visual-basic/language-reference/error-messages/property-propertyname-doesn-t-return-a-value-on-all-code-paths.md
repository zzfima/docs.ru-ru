---
title: Свойство &#39; &lt;propertyname&gt; &#39; &#39;t возвращает значение во всех путях кода
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 72bc7e45cadd2528f29c88bf6e80ee5f381052dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594218"
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Свойство &#39; &lt;propertyname&gt; &#39; &#39;t возвращает значение во всех путях кода
Свойство "\<имя_свойства >" не возвращает значение во всех путях кода. Во время выполнения может возникнуть исключение, связанное с пустой ссылкой, когда используется результат.  
  
 Свойство `Get` процедура имеет по крайней мере один возможный путь во всем коде, который не возвращает значение.  
  
 Может возвращать значение из свойства `Get` процедура в любой из следующих способов:  
  
-   Присвойте значение имени свойства, а затем выполнить `Exit Property` инструкции.  
  
-   Присвойте значение имени свойства, а затем выполнить `End Get` инструкции.  
  
-   Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Если управление передается `Exit Property` или `End Get` и имя свойства, не назначенным любое значение `Get` процедура возвращает значение по умолчанию для типа данных свойства. Дополнительные сведения см. в разделе «Поведение» в [Function, инструкция](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42107  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждым оператором, вызывающим возврат.  
  
     Проще гарантировать, что каждый возврата из процедуры возвращает значение, если всегда использовать `Return` инструкции. После этого, последней инструкцией перед `End Get` должно быть `Return` инструкции.  
  
## <a name="see-also"></a>См. также  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)
