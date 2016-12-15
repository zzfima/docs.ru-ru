---
title: "Тип данных Short (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Short"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], интеграл"
  - "целые числа"
  - "целые числа, типы данных"
  - "целые числа, типы"
  - "целочисленные типы данных"
  - "символы типа литерала, S"
  - "числа, целочисленный"
  - "числа, целый"
  - "знак типа литерала S"
  - "Short - тип данных"
  - "целое число"
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип данных Short (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Содержит 16\-разрядные \(2\-байтовые\) целые числа со знаком в диапазоне от \-32 768 до 32 767.  
  
## Заметки  
 Тип данных `Short` используется для хранения целых значений, которые не требуют полного размера строки данных `Integer`.  В некоторых случаях среда CLR может использовать возможность запаковывания нескольких переменных `Short` вместе максимально плотно с целью экономии памяти.  
  
 Значение по умолчанию для типа `Short` равно 0.  
  
## Советы по программированию  
  
-   **Расширение**. Тип данных `Short` можно расширить до `Integer`, `Long`, `Decimal`, `Single` или `Double`.  Это означает, что можно преобразовать `Short` в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Символы типов**. При добавлении знака `S` типа литерала к литералу происходит приведение литерала к типу данных `Short`.  У `Short` нет символа типа идентификатора.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.Int16?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Int16?displayProperty=fullName>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)