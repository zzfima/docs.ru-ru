---
title: "Свойство &quot;&lt;propertyname&gt;&quot; возвращает значение не для всех путей кода | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
dev_langs:
- VB
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e7c94d827761ad26d517b44a06734c5db4480a62
ms.lasthandoff: 03/13/2017

---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Свойство "&lt;propertyname&gt;" возвращает значение не для всех путей кода
Свойство "\<propertyname настроек" возвращает значение не для всех ветвей кода. Во время выполнения может возникнуть исключение, связанное с пустой ссылкой, когда используется результат.  
  
 Свойство `Get` процедура имеет хотя бы один возможный путь во всем коде, который не возвращает значение.  
  
 Может возвращать значение из свойства `Get` процедура в любой из следующих способов:  
  
-   Присвойте значение имени свойства, а затем выполнить `Exit Property` инструкции.  
  
-   Присвойте значение имени свойства, а затем выполнить `End Get` инструкции.  
  
-   Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Если управление передается `Exit Property` или `End Get` и имя свойства не назначить любое значение `Get` процедура возвращает значение по умолчанию для типа данных свойства. Дополнительные сведения см. в разделе «Поведение» в [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42107  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждым оператором, вызывающим возврат.  
  
     Проще гарантировать, что каждое возвращение из процедуры возвращает значение, если всегда использовать `Return` инструкции. После этого, последним оператором перед `End Get` должно быть `Return` инструкции.  
  
## <a name="see-also"></a>См. также  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)
