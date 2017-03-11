---
title: "Таблица явных числовых преобразований (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "преобразования [C#], явный числовой"
  - "явное числовое преобразование [C#]"
  - "числовые преобразования [C#], явные"
  - "числовые типы данных [C#]"
  - "преобразование типов [С#], явный числовой"
  - "типы [C#], явные числовые преобразования"
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Таблица явных числовых преобразований (Справочник по C#)
Явное числовое преобразование используется для преобразования любого числового типа в любой другой числовой тип, для которого отсутствует неявное преобразование, с помощью выражения приведения.  В следующей таблице приведено описание этих преобразований.  
  
 Дополнительные сведения о преобразованиях см. в разделе [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
|Исходный тип|Целевой тип|  
|------------------|-----------------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`byte`, `ushort`, `uint`, `ulong` или `char`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`Sbyte` или `char`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`sbyte`,  `byte`,  `ushort`,  `uint`,  `ulong` или  `char`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`sbyte`, `byte`, `short` или `char`|  
|[Целочисленное значение.](../../../csharp/language-reference/keywords/int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` `` или `char`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` или `char`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` или `char`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` или `char`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`sbyte`, `byte` или `short`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` `` или `decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` `` или `decimal`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`или `double`|  
  
## Заметки  
  
-   Явное числовое преобразование может привести к потере точности или вызвать исключения.  
  
-   Во время преобразования значения `decimal` в целочисленный тип оно округляется в сторону нуля до ближайшего целого значения.  Если полученное целое значение выходит за допустимые пределы значений конечного типа, возникает исключение <xref:System.OverflowException>.  
  
-   Во время преобразования значения `double` или `float` в целочисленный тип оно усекается.  Если полученное целое значение выходит за допустимые пределы конечного значения, результат зависит от контекста проверки переполнения.  В контексте с проверкой возникает исключение `OverflowException`, а в контексте без проверки результатом является неуказанное значение конечного типа.  
  
-   При преобразовании `double` в `float`, значение `double` округляется до ближайшего значения `float`.  Если значение `double` слишком мало или слишком велико для конечного типа, результатом является нуль или бесконечность.  
  
-   При преобразовании `float` или `double` в `decimal` исходное значение преобразуется в представление `decimal` и округляется до ближайшего числа после 28\-го десятичного знака, если это необходимо.  В зависимости от исходного значения может быть получен один из следующих результатов:  
  
    -   Если исходное значение слишком мало для представления в качестве `decimal`, результатом является нуль.  
  
    -   Если исходное значение не является числом, равно бесконечности или слишком велико для представления в качестве `decimal`, возникает исключение `OverflowException`.  
  
-   При преобразовании `decimal` в `float` или `double`, значение `decimal` округляется до ближайшего значения `double` или `float`.  
  
 Дополнительную информацию о явном преобразовании см. в разделе "Явные операции в спецификации языка C\#".  Дополнительные сведения о доступе к спецификации см. в разделе [Спецификация языка C\#](../../../csharp/language-reference/language-specification.md).  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Оператор \(\)](../../../csharp/language-reference/operators/invocation-operator.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)