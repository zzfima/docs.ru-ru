---
title: "Тип данных ULong (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ulong"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], интеграл"
  - "целые числа"
  - "целые числа, типы данных"
  - "целые числа, типы"
  - "целочисленные типы данных"
  - "символы типа литерала, UL"
  - "числа, целочисленный"
  - "числа, целый"
  - "символы типа литерала UL"
  - "тип данных ULong"
  - "целое число"
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Тип данных ULong (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Содержит 64\-разрядные \(8\-байтные\) целые числа без знака, значения которых находятся в диапазоне от 0 до 18 446 744 073 709 551 615 \(в 1,84 раза больше чем 10 ^ 18\).  
  
## Заметки  
 Используйте тип данных `ULong` для хранения двоичных данных, которые слишком велики для типа `UInteger`, или для наибольших возможных целых значений без знака.  
  
 Значение по умолчанию для типа `ULong` равно 0.  
  
## Советы по программированию  
  
-   **Отрицательные числа**. Поскольку `ULong` — это тип без знака, он не может представлять отрицательное число.  Если используется оператор унарного минуса \(`-`\) в выражении, вычисляющем значение типа `ULong`, то в Visual Basic сначала выполняется преобразование выражения к типу `Decimal`.  
  
-   **CLS\-совместимость**. Тип данных `ULong` не является частью [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), поэтому в CLS\-совместимом коде нельзя использовать компонент, который его использует.  
  
-   **Вопросы взаимодействия**. Если осуществляется взаимодействие с компонентами, не написанными под .NET Framework, например объектами автоматизации или COM\-объектами, имейте в виду, что такие типы, как `ulong`, могут иметь различную ширину данных \(32 бита\) в других средах.  Если в такой компонент передается 32\-разрядный аргумент, объявите его в управляемом коде Visual Basic как `UInteger`, а не как `ULong`.  
  
     Кроме того, модель автоматизации не поддерживает 64\-разрядные целые числа в Windows 95, в Windows 98, в Windows ME и в Windows 2000.  Компоненту автоматизации на этих платформах нельзя передавать аргумент Visual Basic `ULong`.  
  
-   **Расширение**. Тип данных`ULong` расширяется до типов `Decimal`, `Single` и `Double`.  Это означает, что можно преобразовать `ULong` к любому из этих типов без появления ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Символы типов**. При добавлении знаков `UL` типа литерала к литералу происходит приведение литерала к типу данных `ULong`.  У `ULong` нет символа типа идентификатора.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.UInt64?displayProperty=fullName>.  
  
## См. также  
 <xref:System.UInt64>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)