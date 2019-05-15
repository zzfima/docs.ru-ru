---
title: Базовый тип <typename> перечисления несовместим с CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 7d4566637da74726867c55ddf89b965d055e5d14
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589928"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a>Базовый тип \<typename > перечисления несовместим с CLS
Тип данных, указанный для этого перечисления не является частью [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS). Это не ошибка в компоненте, так как .NET Framework и Visual Basic поддерживает этот тип данных. Тем не менее другой компонент, написанный в строго CLS-совместимого кода могут не поддерживать этот тип данных. Такой компонент не может иметь возможность успешно взаимодействовать с данным компонентом.  
  
 Следующие типы данных Visual Basic не являются CLS-совместимыми:  
  
- [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40032  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Если компонент взаимодействует только с другими компонентами .NET Framework, или не взаимодействует с любых других компонентов, ничего менять не нужно.  
  
- При взаимодействии с компонентом, не написаны для платформы .NET Framework, может быть возможность определить, либо через отражение, либо из документации, поддерживает ли он этот тип данных. В этом случае ничего менять не нужно.  
  
- При взаимодействии с компонентом, который не поддерживает этот тип данных, его необходимо заменить на ближайший CLS-совместимый тип. Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647. Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.  
  
- При взаимодействии с автоматизация или COM-объектами, имейте в виду, что некоторые типы имеют разные данные от длины в .NET Framework. Например, данные типа `uint` часто являются 16-битными в других средах. Если вы передаете 16-разрядного аргумента такому компоненту, объявите его как `UShort` вместо `UInteger` в управляемом коде Visual Basic.  
  
## <a name="see-also"></a>См. также

- [Reflection (Visual Basic)](../../programming-guide/concepts/reflection.md) (Отражение (Visual Basic))
- [Отражение](../../../framework/reflection-and-codedom/reflection.md)
