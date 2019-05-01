---
title: Тип члена <membername> не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 0d87adee65f491f8c968e4ba93cf4b9df03aff85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013625"
---
# <a name="type-of-member-membername-is-not-cls-compliant"></a>Тип члена "\<имя_члена >" не является CLS-совместимым
Тип данных, указанный для этого элемента не является частью [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS). Это не ошибка в компоненте, поскольку [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] и Visual Basic поддерживает этот тип данных. Тем не менее другой компонент, написанный в строго CLS-совместимого кода могут не поддерживать этот тип данных. Такой компонент не может иметь возможность успешно взаимодействовать с данным компонентом.  
  
 Следующие типы данных Visual Basic не являются CLS-совместимыми:  
  
- [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Если компонент взаимодействует только с другими [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] компонентов, или не взаимодействует с любых других компонентов, не нужно ничего менять.  
  
- При взаимодействии с компонентом, не написаны для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], можно определить, либо через отражение или из документации, является ли он поддерживает этот тип данных. В этом случае ничего менять не нужно.  
  
- При взаимодействии с компонентом, который не поддерживает этот тип данных, его необходимо заменить на ближайший CLS-совместимый тип. Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647. Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.  
  
- При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Например, данные типа `uint` часто являются 16-битными в других средах. Если вы передаете 16-разрядного аргумента такому компоненту, объявите его как `UShort` вместо `UInteger` в управляемом коде Visual Basic.  
  
## <a name="see-also"></a>См. также

- [Отражение](../../../framework/reflection-and-codedom/reflection.md)
