---
title: "Тип возвращаемого значения функции &lt;имяПроцедуры&gt; несовместим с CLS | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40027"
  - "vbc40027"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40027"
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Тип возвращаемого значения функции &lt;имяПроцедуры&gt; несовместим с CLS
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Процедура `Function` помечена как `<CLSCompliant(True)>`, но возвращает тип, который помечен как `<CLSCompliant(False)>`, не помечен или не квалифицирован, так как он является несовместимым типом.  
  
 Для совместимости процедуры с [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) она должна использовать только CLS–совместимые типы.  Это относится к типам параметров, возвращаемому типу и типам всех ее локальных переменных.  
  
 Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] не являются CLS\-совместимыми:  
  
-   [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу параметру атрибута `isCompliant` присваивается значение `True` или `False`, указывающее на совместимость или несовместимость.  Значение по умолчанию для этого параметра отсутствует, поэтому значение необходимо указать.  
  
 Если к элементу не применяется атрибут <xref:System.CLSCompliantAttribute>, элемент считается несовместимым.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40027  
  
### Чтобы исправить эту ошибку  
  
-   Если процедура `Function` должна возвращать этот конкретный тип, удалите <xref:System.CLSCompliantAttribute>.  Процедура не может быть CLS–совместимой.  
  
-   Если процедура `Function` должна быть CLS\-совместимой, то измените тип возвращаемого значения на ближайший CLS\-совместимый тип.  Например, вместо `UInteger` можно использовать `Integer`, если не требуется значение диапазона, превышающее 2 147 483 647.  Если необходим расширенный диапазон, можно заменить `UInteger` на `Long`.  
  
-   Если производится взаимодействие с объектами автоматизации или COM–объектами, то имейте в виду, что некоторые типы имеют ширину данных, отличающуюся от ширины данных в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] .  Например, в других средах тип `int` часто является 16\-разрядным.  Если возвращается 16\-разрядное целое число в такой компонент, объявите его как `Short` вместо `Integer` в управляемом коде [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## См. также  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)