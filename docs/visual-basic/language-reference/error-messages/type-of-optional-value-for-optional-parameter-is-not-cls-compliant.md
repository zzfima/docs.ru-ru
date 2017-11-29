---
title: "Тип необязательного значения для необязательного параметра &lt;имя_параметра&gt; не является CLS-совместимым"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords: BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 442ff2e4b582287e03f425dad98128726fe18c43
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="type-of-optional-value-for-optional-parameter-ltparameternamegt-is-not-cls-compliant"></a>Тип необязательного значения для необязательного параметра &lt;имя_параметра&gt; не является CLS-совместимым
Процедура помечена как `<CLSCompliant(True)>`, но она объявляет [необязательный](../../../visual-basic/language-reference/modifiers/optional.md) параметр со значением по умолчанию несовместимого типа.  
  
 Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), процедура должна использовать только типы, совместимые с CLS. Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных. Это также касается значений по умолчанию для необязательных параметров.  
  
 Следующие типы данных [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не соответствуют CLS:  
  
-   [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Когда вы применяете атрибут <xref:System.CLSCompliantAttribute> к программному элементу, вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать на соответствие или несоответствие требованиям. Для этого параметра нет значения по умолчанию, и вы должны предоставить его.  
  
 Если вы не примените <xref:System.CLSCompliantAttribute> к элементу, он считается несоответствующим требованиям.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40042  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если необязательный параметр должен иметь значение по умолчанию этого конкретного типа, удалите <xref:System.CLSCompliantAttribute>. Процедура не может соответствовать CLS.  
  
-   Если процедура должна быть совместимой с CLS, измените тип этого значения по умолчанию на ближайший тип, совместимый с CLS. Например, вместо `UInteger` вы можете использовать `Integer`, если вам не нужен диапазон значений, превышающий 2 147 483 647. Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.  
  
-   При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Например, данные типа `int` часто являются 16-битными в других средах. Если вы принимаете 16-битное целое число из таких компонентов, объявите его как `Short` (а не `Integer`) в управляемом коде [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="see-also"></a>См. также  
 [\<PAVE НАД > написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
