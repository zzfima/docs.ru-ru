---
title: "Тип данных UInteger | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.uinteger"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], интеграл"
  - "целые числа"
  - "целые числа, типы данных"
  - "целые числа, типы"
  - "целочисленные типы данных"
  - "символы типа литерала, UI"
  - "числа, целочисленный"
  - "числа, целый"
  - "символы типа литерала UI"
  - "UInteger - тип данных"
  - "целое число"
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип данных UInteger
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Содержит 32\-разрядные \(4\-байтные\) беззнаковые целые числа в диапазоне от 0 до 4294967295.  
  
## Заметки  
 Тип данных `UInteger` обеспечивает наибольшее беззнаковое значение при наиболее эффективной ширине данных.  
  
 Значение по умолчанию для типа `UInteger` равно 0.  
  
## Советы по программированию  
 Типы данных `UInteger` и `Integer` обеспечивает оптимальную производительность на 32\-разрядных процессорах, поскольку меньшие типы целых чисел \(`UShort`, `Short`, `Byte` и `SByte`\), даже если они используют меньшее число битов, занимают больше времени на загрузку, хранение и выборку.  
  
-   **Отрицательные числа**. Поскольку `UInteger` — это тип без знака, он не может представлять отрицательное число.  Если используется оператор унарного минуса \(`-`\) в выражении, вычисляющем значение типа `UInteger`, то в Visual Basic сначала выполняется преобразование выражения к типу `Long`.  
  
-   **CLS\-совместимость**. Тип данных `UInteger` не является частью [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), поэтому в CLS\-совместимом коде нельзя использовать компонент, который его использует.  
  
-   **Вопросы взаимодействия**. Если осуществляется взаимодействие с компонентами, не написанными под .NET Framework, например объектами автоматизации или COM\-объектами, имейте в виду, что такие типы, как `uint`, могут иметь различную ширину данных \(16 бита\) в других средах.  Если в такой компонент передается 16\-разрядный аргумент, объявите его в управляемом коде Visual Basic как `UShort`, а не как `UInteger`.  
  
-   **Расширение**. Тип данных`UInteger` расширяется до типов `Long`, `ULong`, `Decimal`, `Single`, `Double` и .  Это означает, что можно преобразовать `UInteger` к любому из этих типов без появления ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Символы типов**. При добавлении знаков `UI` типа литерала к литералу происходит приведение литерала к типу данных `UInteger`.  У `UInteger` нет символа типа идентификатора.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.UInt32?displayProperty=fullName>.  
  
## См. также  
 <xref:System.UInt32>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)