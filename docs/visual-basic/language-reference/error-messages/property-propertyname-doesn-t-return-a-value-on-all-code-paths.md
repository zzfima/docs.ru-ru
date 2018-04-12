---
title: Свойство &#39; &lt;propertyname&gt;&#39; &#39; t возвращает значение во всех путях кода
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c9ef5b2ac62412f5684cbc78ab6bebf6bc7b6752
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Свойство &#39; &lt;propertyname&gt;&#39; &#39; t возвращает значение во всех путях кода
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
