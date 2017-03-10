---
title: "Тип члена &lt;имяЧлена&gt; не является CLS-совместимым | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40025"
  - "vbc40025"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40025"
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Тип члена &lt;имяЧлена&gt; не является CLS-совместимым
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Тип данных, указанный для этого элемента не является компонентом [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\).  Это не ошибка в компоненте, поскольку [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] и [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] поддерживают этот тип данных.  Тем не менее другой компонент, написанный в строгом CLS\-совместимом коде, может не поддерживать этот тип данных.  Такой компонент может быть неспособен успешно взаимодействовать с данным компонентом.  
  
 Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] не являются CLS\-совместимыми:  
  
-   [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений и их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC40025  
  
### Чтобы исправить эту ошибку  
  
-   Если компонент взаимодействует только с другими компонентами [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] или не взаимодействует с какими\-либо иными компонентами, нет необходимости изменять что\-либо.  
  
-   При взаимодействии с компонентом, записанном не для [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)], можно определить \(либо через отражение, либо из документации\), поддерживает ли он этот тип данных.  Если этот тип данных поддерживается, нет необходимости изменять что\-либо.  
  
-   При взаимодействии с компонентом, который не поддерживает этот тип данных, необходимо заменить его на наиболее подходящий CLS\-совместимый тип.  Например, вместо `UInteger` можно использовать `Integer`, если не требуется значение диапазона, превышающее 2 147 483 647.  Если необходим расширенный диапазон, можно заменить `UInteger` на `Long`.  
  
-   Если производится взаимодействие с объектами автоматизации или COM–объектами, то имейте в виду, что некоторые типы имеют ширину данных, отличающуюся от ширины данных в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] .  Например, в других средах `uint` часто является 16\-битным.  Если производится передача 16\-разрядного аргумента такому компоненту, следует объявить ее как `UShort` вместо `UInteger` в управляемом коде [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## См. также  
 [Reflection](../Topic/Reflection%20in%20the%20.NET%20Framework.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)