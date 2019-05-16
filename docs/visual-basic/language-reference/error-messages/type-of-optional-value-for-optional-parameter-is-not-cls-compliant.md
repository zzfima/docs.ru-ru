---
title: Тип необязательного значения для необязательного параметра <parametername> несовместим с CLS
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: 88f8b7ea1e0a9b4cb115646f40abbf8a567a2b1d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641393"
---
# <a name="type-of-optional-value-for-optional-parameter-parametername-is-not-cls-compliant"></a>Тип необязательного значения для необязательного параметра \<имя_параметра > не является CLS-совместимым
Процедура помечена как `<CLSCompliant(True)>`, но она объявляет [необязательный](../../../visual-basic/language-reference/modifiers/optional.md) параметр со значением по умолчанию несовместимого типа.  
  
 Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), процедура должна использовать только типы, совместимые с CLS. Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных. Это также касается значений по умолчанию для необязательных параметров.  
  
 Следующие типы данных Visual Basic не являются CLS-совместимыми:  
  
- [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Когда вы применяете атрибут <xref:System.CLSCompliantAttribute> к программному элементу, вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать на соответствие или несоответствие требованиям. Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.  
  
 Если вы не примените <xref:System.CLSCompliantAttribute> к элементу, он считается несоответствующим требованиям.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40042  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Если необязательный параметр должен иметь значение по умолчанию этого конкретного типа, удалите <xref:System.CLSCompliantAttribute>. Процедура не может соответствовать CLS.  
  
- Если процедура должна быть совместимой с CLS, измените тип этого значения по умолчанию на ближайший тип, совместимый с CLS. Например, вместо `UInteger` вы можете использовать `Integer`, если вам не нужен диапазон значений, превышающий 2 147 483 647. Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.  
  
- При взаимодействии с автоматизация или COM-объектами, имейте в виду, что некоторые типы имеют разные данные от длины в .NET Framework. Например, данные типа `int` часто являются 16-битными в других средах. Если вы принимаете 16-разрядное целое число из таких компонентов, объявите его как `Short` вместо `Integer` в управляемом коде Visual Basic.
