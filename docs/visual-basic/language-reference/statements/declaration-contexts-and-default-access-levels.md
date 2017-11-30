---
title: "Контексты объявления и уровни доступа по умолчанию (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b89b74a6c0393f6a52a0b5c1ddf6f66c505564ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Контексты объявления и уровни доступа по умолчанию (Visual Basic)
В этом разделе описывается, какие типы Visual Basic могут быть объявлены внутри других типов, и что их уровни доступа по умолчанию, если не указана.  
  
## <a name="declaration-context-levels"></a>Уровни контекста объявления  
 *Контекст объявления* элемента программирования является область кода, в котором она объявлена. Часто это другой программный элемент, который затем будет вызвана *содержащий элемент*.  
  
 Ниже перечислены уровни для контекстов объявления.  
  
-   *Уровень пространства имен* — в пределах исходного файла или пространства имен, но не внутри класса, структуры, модуля или интерфейса  
  
-   *Уровень модуля* — внутри класса, структуры, модуля или интерфейса, но не внутри процедуры или блока  
  
-   *Уровень процедуры* — внутри процедуры или блока (такие как `If` или `For`)  
  
 В следующей таблице показаны уровни доступа по умолчанию для различных элементов программирования, в зависимости от их контекстов объявления.  
  
|Объявленный элемент|Уровень пространства имен|Уровень модуля|Уровень процедуры|  
|----------------------|---------------------|------------------|---------------------|  
|Переменной ([оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md))|Не допускается|`Private`(`Public` в `Structure`, не допускается в `Interface`)|`Public`|  
|Константы ([оператор Const](../../../visual-basic/language-reference/statements/const-statement.md))|Не допускается|`Private`(`Public` в `Structure`, не допускается в `Interface`)|`Public`|  
|Перечисление ([оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|Не допускается|  
|Класс ([оператор Class](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|Не допускается|  
|Структура ([структура инструкции](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|Не допускается|  
|Модуль ([оператор Module](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|Не допускается|Не допускается|  
|Интерфейс ([оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|Не допускается|  
|Процедура ([функции инструкции](../../../visual-basic/language-reference/statements/function-statement.md), [оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md))|Не допускается|`Public`|Не допускается|  
|Внешняя ссылка ([инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md))|Не допускается|`Public`(не допускается в `Interface`)|Не допускается|  
|Оператор ([оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md))|Не допускается|`Public`(не допускается в `Interface` или `Module`)|Не допускается|  
|Свойство ([оператор Property](../../../visual-basic/language-reference/statements/property-statement.md))|Не допускается|`Public`|Не допускается|  
|Свойство по умолчанию ([по умолчанию](../../../visual-basic/language-reference/modifiers/default.md))|Не допускается|`Public`(не допускается в `Module`)|Не допускается|  
|События ([оператор Event](../../../visual-basic/language-reference/statements/event-statement.md))|Не допускается|`Public`|Не допускается|  
|Делегат ([оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|Не допускается|  
  
 Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>См. также  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)
