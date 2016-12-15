---
title: "Тип данных Integer (Visual Basic) | Microsoft Docs"
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
  - "vb.Integer"
  - "Integer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "% - знак типа идентификатора"
  - "типы данных [Visual Basic], назначение"
  - "типы данных [Visual Basic], интеграл"
  - "перечисляемые значения"
  - "знак типа литерала I"
  - "символы типа идентификатора, %"
  - "Integer - тип данных"
  - "целые числа"
  - "целые числа, типы данных"
  - "целые числа, типы"
  - "целочисленные типы данных"
  - "символы типа литерала, I"
  - "числа, целочисленный"
  - "числа, целый"
  - "целое число"
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип данных Integer (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Содержит 32\-разрядные \(4\-байтовые\) целые числа со знаком в диапазоне от \-2 147 483 648 до 2 147 483 647.  
  
## Заметки  
 Тип данных `Integer` обеспечивает оптимальную производительность на 32\-разрядных процессорах.  Другие целочисленные типы загружаются в память и сохраняются в памяти с более низкой скоростью.  
  
 Значение по умолчанию для типа `Integer` — 0.  
  
## Советы по программированию  
  
-   **Вопросы взаимодействия.** При взаимодействие с компонентами, которые не написаны для платформы .NET Framework \(например, автоматизация или COM\-объекты\), необходимо помнить, что в других средах ширина данных типа `Integer` отличается \(16 бит\).  При передаче 16\-разрядного аргумента такому компоненту в новом коде Visual Basic следует объявить его как `Short`, а не как `Integer`.  
  
-   **Расширение.** Тип данных `Integer` можно расширить до `Long`, `Decimal`, `Single` или `Double`.  Это означает, что тип `Integer` можно преобразовать в любой из этих типов без возникновения ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Символы типов.** При добавлении к литералу символа типа литерала `I` производится принудительное приведение литерала к типу данных `Integer`.  При добавлении символа идентификатора типа `%` к любому идентификатору производится принудительное приведение этого идентификатора к типу `Integer`.  
  
-   **Тип Framework.** В .NET Framework данный тип соответствует структуре <xref:System.Int32?displayProperty=fullName>.  
  
## Диапазон  
 При попытке присвоить целочисленной переменной значение, лежащее за пределами диапазона данного типа, возникает ошибка.  При попытке задать дробное значение оно округляется вверх или вниз до ближайшего целого значения.  Если число находится точно посередине между двумя целыми числами, значение округляется до ближайшего четного целого.  Такое поведение минимизирует ошибки округления, происходящие от постоянного округления среднего значения в одном направлении.  В следующем коде приведены примеры округления.  
  
```  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```  
  
## См. также  
 <xref:System.Int32?displayProperty=fullName>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Тип данных Long](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)