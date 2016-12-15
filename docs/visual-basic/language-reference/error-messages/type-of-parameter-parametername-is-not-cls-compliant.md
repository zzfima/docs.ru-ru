---
title: "Тип параметра &lt;имяПараметра&gt; не является CLS-совместимым | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40028"
  - "bc40028"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40028"
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип параметра &lt;имяПараметра&gt; не является CLS-совместимым
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Процедура помечена как `<CLSCompliant(True)>`, но объявляет параметр с типом, который помечен как `<CLSCompliant(False)>`, не помечен или не квалифицирован, так как он является несовместимым типом.  
  
 Для совместимости процедуры с [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) она должна использовать только CLS–совместимые типы.  Это относится к типам параметров, возвращаемому типу и типам всех ее локальных переменных.  
  
 Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не являются CLS\-совместимыми:  
  
-   [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу параметру атрибута `isCompliant` присваивается значение `True` или `False`, указывающее на совместимость или несовместимость.  Значение по умолчанию для этого параметра отсутствует, поэтому значение необходимо указать.  
  
 Если к элементу не применяется атрибут <xref:System.CLSCompliantAttribute>, элемент считается несовместимым.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC40028  
  
### Чтобы исправить эту ошибку  
  
-   Если процедура должна принимать параметр этого конкретного типа, то удалите <xref:System.CLSCompliantAttribute>.  Процедура не может быть CLS–совместимой.  
  
-   Если процедура должна быть CLS–совместимой, то измените тип этого параметра на ближайший CLS–совместимый тип.  Например, вместо `UInteger` можно использовать `Integer`, если не требуется значение диапазона, превышающее 2 147 483 647.  Если необходим расширенный диапазон, можно заменить `UInteger` на `Long`.  
  
-   Если производится взаимодействие с объектами автоматизации или COM–объектами, то имейте в виду, что некоторые типы имеют ширину данных, отличающуюся от ширины данных в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] .  Например, в других средах тип `int` часто является 16\-разрядным.  Если из таких компонентов принимается 16\-разрядное целое число, следует объявить его в качестве `Short` вместо `Integer` в управляемом коде [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## См. также  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)