---
title: Контексты объявления и уровни доступа по умолчанию
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: 1ba25d830b1e7529bdf09c1195cc1fe7f9b2243b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354104"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Контексты объявления и уровни доступа по умолчанию (Visual Basic)
В этом разделе описано, какие типы Visual Basic могут быть объявлены, в которых можно объявлять другие типы, а также уровни доступа по умолчанию, если они не указаны.  
  
## <a name="declaration-context-levels"></a>Уровни контекста объявления  
 *Контекстом объявления* программного элемента является область кода, в которой он объявлен. Часто это другой программный элемент, который затем называется *содержащим элементом*.  
  
 Ниже приведены уровни для контекстов объявления.  
  
- *Уровень пространства имен* — в исходном файле или пространстве имен, но не в классе, структуре, модуле или интерфейсе  
  
- *Уровень модуля* — в классе, структуре, модуле или интерфейсе, но не внутри процедуры или блока  
  
- *Уровень процедуры* — внутри процедуры или блока (например, `If` или `For`).  
  
 В следующей таблице показаны уровни доступа по умолчанию для различных объявленных программных элементов в зависимости от контекстов объявления.  
  
|Объявленный элемент|Уровень пространства имен|Уровень модуля|Уровень процедуры|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md))|Нельзя использовать|`Private` (`Public` в `Structure`, запрещено в `Interface`)|`Public`|  
|Constant ([оператор Const](../../../visual-basic/language-reference/statements/const-statement.md))|Нельзя использовать|`Private` (`Public` в `Structure`, запрещено в `Interface`)|`Public`|  
|Enumeration ([оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|Нельзя использовать|  
|Class ([оператор Class](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|Нельзя использовать|  
|Structure ([оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|Нельзя использовать|  
|Module ([оператор Module](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|Нельзя использовать|Нельзя использовать|  
|Interface ([оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|Нельзя использовать|  
|PROCEDURE ([оператор Function](../../../visual-basic/language-reference/statements/function-statement.md), [оператор подвыражения](../../../visual-basic/language-reference/statements/sub-statement.md))|Нельзя использовать|`Public`|Нельзя использовать|  
|Внешняя ссылка ([Инструкция DECLARE](../../../visual-basic/language-reference/statements/declare-statement.md))|Нельзя использовать|`Public` (не допускается в `Interface`)|Нельзя использовать|  
|Оператор operator (оператор[operator](../../../visual-basic/language-reference/statements/operator-statement.md))|Нельзя использовать|`Public` (не допускается в `Interface` или `Module`)|Нельзя использовать|  
|Property ([Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md))|Нельзя использовать|`Public`|Нельзя использовать|  
|Свойство по умолчанию ([по умолчанию](../../../visual-basic/language-reference/modifiers/default.md))|Нельзя использовать|`Public` (не допускается в `Module`)|Нельзя использовать|  
|Event ([оператор Event](../../../visual-basic/language-reference/statements/event-statement.md))|Нельзя использовать|`Public`|Нельзя использовать|  
|Delegate ([оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|Нельзя использовать|  
  
 Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>См. также

- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
