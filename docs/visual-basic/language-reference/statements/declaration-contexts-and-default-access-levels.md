---
title: Контексты объявления и уровни доступа по умолчанию (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: 75c5b16164e9ecb6558e445c59e4a312158ff4f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580815"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Контексты объявления и уровни доступа по умолчанию (Visual Basic)
В этом разделе описывается, какие типы Visual Basic, могут быть объявлены внутри других типов, и новые уровни доступа по умолчанию, если не указано.  
  
## <a name="declaration-context-levels"></a>Уровни контекста объявления  
 *Контекст объявления* элемента программирования является область кода, в котором она объявлена. Это часто другой программный элемент, который затем вызывается *содержащий элемент*.  
  
 Ниже перечислены уровни для Контексты объявления.  
  
-   *Уровень пространства имен* — в пределах исходного файла или пространства имен, но не в класс, структура, модуль или интерфейс  
  
-   *Уровень модуля* — в пределах класса, структуры, модуля или интерфейса, но не внутри процедуры или блока  
  
-   *Уровень процедуры* — в пределах процедуры или блока (такие как `If` или `For`)  
  
 В следующей таблице показаны уровни доступа по умолчанию для различных элементов программирования, в зависимости от их контекстов объявления.  
  
|Объявленный элемент|Уровень пространства имен|Уровень модуля|Уровень процедуры|  
|----------------------|---------------------|------------------|---------------------|  
|Переменной ([оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md))|Не допускается|`Private` (`Public` в `Structure`, не допускается в `Interface`)|`Public`|  
|Константы ([оператор Const](../../../visual-basic/language-reference/statements/const-statement.md))|Не допускается|`Private` (`Public` в `Structure`, не допускается в `Interface`)|`Public`|  
|Перечисления ([оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|Не допускается|  
|Класс ([оператор Class](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|Не допускается|  
|Структура ([структуры инструкции](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|Не допускается|  
|Модуль ([оператор Module](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|Не допускается|Не допускается|  
|Интерфейс ([оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|Не допускается|  
|Процедура ([инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md), [оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md))|Не допускается|`Public`|Не допускается|  
|Внешняя ссылка ([Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md))|Не допускается|`Public` (не допускается в `Interface`)|Не допускается|  
|Оператор ([Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md))|Не допускается|`Public` (не допускается в `Interface` или `Module`)|Не допускается|  
|Свойство ([Property Statement](../../../visual-basic/language-reference/statements/property-statement.md))|Не допускается|`Public`|Не допускается|  
|Свойство по умолчанию ([по умолчанию](../../../visual-basic/language-reference/modifiers/default.md))|Не допускается|`Public` (не допускается в `Module`)|Не допускается|  
|События ([оператор Event](../../../visual-basic/language-reference/statements/event-statement.md))|Не допускается|`Public`|Не допускается|  
|Делегат ([оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|Не допускается|  
  
 Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>См. также
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
