---
title: "Таблица неявных числовых преобразований (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "преобразования [C#], неявный числовой"
  - "неявные числовые преобразования [C#]"
  - "числовые преобразования [C#], неявные"
  - "типы [C#], неявные числовые преобразования"
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# Таблица неявных числовых преобразований (Справочник по C#)
В следующей таблице показаны предопределенные неявные преобразования чисел.  Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.  
  
|Исходный тип|Целевой тип|  
|------------------|-----------------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`short`, `int`, `long`, `float`, `double` или `decimal`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`int`, `long`, `float`, `double` или `decimal`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`|  
|[Целочисленное значение.](../../../csharp/language-reference/keywords/int.md)|`long`, `float`, `double` или `decimal`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`long`, `ulong`, `float`, `double` или `decimal`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`float`, `double` или `decimal`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` или `decimal`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`float`,  `double` или `decimal`|  
  
## Заметки  
  
-   Точность, но не величина может потери в преобразованиях с `int`, `uint`, `long`, или `ulong` для `float` и `long` или `ulong` для `double`.  
  
-   Не поддерживается неявное преобразование в тип `char`.  
  
-   Неявные преобразования между типами с плавающей запятой и типом `decimal` отсутствуют.  
  
-   Выражение константы `int` можно преобразовать в `sbyte`, `byte`, `short`, `ushort`, `uint` или `ulong` при условии, что значение выражения константы находится в диапазоне типа назначения.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md)