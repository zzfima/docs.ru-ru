---
title: "Тип данных SByte (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.sbyte"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], интеграл"
  - "целые числа"
  - "целые числа, типы данных"
  - "целые числа, типы"
  - "целочисленные типы данных"
  - "числа, целочисленный"
  - "числа, целый"
  - "SByte тип данных"
  - "целое число"
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Тип данных SByte (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Содержит 8\-разрядные \(1\-байтовые\) целые числа со знаком в диапазоне от\-128 до 127.  
  
## Заметки  
 Используйте тип данных `SByte` для хранения целых значений, которые не требуют полного размера `Integer` или даже половины размера типа данных `Short`.  В некоторых случаях общая среда исполнения может использовать возможность упаковки переменных `SByte` вместе для уменьшения потребления памяти.  
  
 Значение по умолчанию для типа `SByte` равно 0.  
  
## Советы по программированию  
  
-   **CLS\-совместимость**. Тип данных `SByte` не является частью [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), поэтому в CLS\-совместимом коде нельзя использовать компонент, который его использует.  
  
-   **Расширение**. Тип данных`SByte` расширяется до типов `Short`, `Integer`, `Long`, `Decimal`, `Single` и `Double`.  Это означает, что можно преобразовать `SByte` к любому из этих типов без появления ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Символы типа.** `SByte` не имеет символов типа литерала или символов типа идентификатора.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.SByte?displayProperty=fullName>.  
  
## См. также  
 <xref:System.SByte?displayProperty=fullName>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)