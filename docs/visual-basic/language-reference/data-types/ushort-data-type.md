---
title: "Тип данных UShort (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ushort"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], интеграл"
  - "целые числа"
  - "целые числа, типы данных"
  - "целые числа, типы"
  - "целочисленные типы данных"
  - "символы типа литерала, US"
  - "числа, целочисленный"
  - "числа, целый"
  - "символы типа литерала US"
  - "UShort - тип данных"
  - "целое число"
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Тип данных UShort (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Содержит 16\-разрядные \(2\-байтные\) беззнаковые целые числа в диапазоне от 0 до 65 535.  
  
## Заметки  
 Используйте тип данных `UShort` для хранения двоичных данных, слишком больших для типа `Byte`.  
  
 Значение по умолчанию для типа `UShort` равно 0.  
  
## Советы по программированию  
  
-   **Отрицательные числа**. Поскольку `UShort` — это тип без знака, он не может представлять отрицательное число.  Если используется оператор унарного минуса \(`-`\) в выражении, вычисляющем значение типа `UShort`, то в Visual Basic сначала выполняется преобразование выражения к типу `Integer`.  
  
-   **CLS\-совместимость**. Тип данных `UShort` не является частью [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), поэтому в CLS\-совместимом коде нельзя использовать компонент, который его использует.  
  
-   **Расширение**. Тип данных `UShort` расширяется до типов `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` и `Double`.  Это означает, что можно преобразовать `UShort` к любому из этих типов без появления ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Символы типов**. При добавлении знаков `US` типа литерала к литералу происходит приведение литерала к типу данных `UShort`.  У `UShort` нет символа типа идентификатора.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.UInt16?displayProperty=fullName>.  
  
## См. также  
 <xref:System.UInt16>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)