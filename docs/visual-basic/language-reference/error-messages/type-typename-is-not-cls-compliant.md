---
title: "Тип &lt;имяТипа&gt; несовместим с CLS | Microsoft Docs"
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
  - "bc40041"
  - "vbc40041"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40041"
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип &lt;имяТипа&gt; несовместим с CLS
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Переменная, свойство или функция возврата объявлены с типом данных, который не совместим с CLS.  
  
 Для совместимости приложения с [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) оно должно использовать только типы, совместимые с CLS.  
  
 Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не являются CLS\-совместимыми:  
  
-   [Тип данных SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Тип данных ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Тип данных UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **Идентификатор ошибки**: BC40041  
  
### Чтобы исправить эту ошибку  
  
-   Если приложению необходимо быть совместимым с CLS, измените тип данных этого элемента на схожий с типом, совместимым с CLS.  Например, вместо `UInteger` можно использовать `Integer`, если не требуется значение диапазона, превышающее 2 147 483 647.  Если необходим расширенный диапазон, можно заменить `UInteger` на `Long`.  
  
-   Если приложению не требуется быть совместимым с CLS, необязательно что либо менять.  Однако следует иметь это в виду.  
  
## См. также  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)