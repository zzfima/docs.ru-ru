---
title: "int (справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "int_CSharpKeyword"
  - "int"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "int - ключевое слово [C#]"
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# int (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `int` обозначает целочисленный тип, в котором хранятся значения, размер и диапазон которых приведены в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|Значение по умолчанию|  
|---------|--------------|------------|----------------------------------|---------------------------|  
|`int`|От \-2 147 483 648 до 2 147 483 647|32\-разрядное знаковое целое число|<xref:System.Int32?displayProperty=fullName>|0|  
  
## Литералы  
 Переменную типа `int` можно объявить и инициализировать, как показано в этом примере:  
  
```  
  
int i = 123;  
```  
  
 Если целочисленный литерал не имеет суффикса, его тип — первый из этих типов, в котором может быть представлено его значение: `int`, [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md).  В этом примере таким типом является `int`.  
  
## Преобразования  
 Существует предопределенное преобразование типа `int` в тип [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  Например:  
  
```  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 Существует предопределенное неявное преобразование типа [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `int`.  Например, следующий оператор назначения вызывает ошибку компиляции без приведения:  
  
```  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `int` не существует.  Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```  
  
        int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 Дополнительные сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделе [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 <xref:System.Int32>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)