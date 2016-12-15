---
title: "Базовый тип &lt;имяТипа&gt; перечисления несовместим с CLS | Microsoft Docs"
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
  - "vbc40032"
  - "bc40032"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40032"
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Базовый тип &lt;имяТипа&gt; перечисления несовместим с CLS
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Тип данных, указанный для этого перечисления не является частью [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\).  Это не ошибка в компоненте, поскольку [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] и [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] поддерживают этот тип данных.  Тем не менее другой компонент, написанный в строгом CLS\-совместимом коде, может не поддерживать этот тип данных.  Такой компонент может быть неспособен успешно взаимодействовать с данным компонентом.  
  
 Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не являются CLS\-совместимыми:  
  
-   [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений и их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40032  
  
### Чтобы исправить эту ошибку  
  
-   Если компонент взаимодействует только с другими компонентами [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] или не взаимодействует с какими\-либо иными компонентами, нет необходимости изменять что\-либо.  
  
-   При взаимодействии с компонентом, записанном не для [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], можно определить \(либо через отражение, либо из документации\), поддерживает ли он этот тип данных.  Если этот тип данных поддерживается, нет необходимости изменять что\-либо.  
  
-   При взаимодействии с компонентом, который не поддерживает этот тип данных, необходимо заменить его на наиболее подходящий CLS\-совместимый тип.  Например, вместо `UInteger` можно использовать `Integer`, если не требуется значение диапазона, превышающее 2 147 483 647.  Если необходим расширенный диапазон, можно заменить `UInteger` на `Long`.  
  
-   Если производится взаимодействие с объектами автоматизации или COM–объектами, то имейте в виду, что некоторые типы имеют ширину данных, отличающуюся от ширины данных в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] .  Например, в других средах `uint` часто является 16\-битным.  Если производится передача 16\-разрядного аргумента такому компоненту, следует объявить ее как `UShort` вместо `UInteger` в управляемом коде [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## См. также  
 [Отражение](../Topic/Reflection%20\(C%23%20and%20Visual%20Basic\).md)   
 [Reflection](../Topic/Reflection%20in%20the%20.NET%20Framework.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)