---
title: "ushort (справочник по C#) | Microsoft Docs"
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
  - "ushort"
  - "ushort_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ushort - ключевое слово [C#]"
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# ushort (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `ushort` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|---------|--------------|------------|----------------------------------|  
|`ushort`|От 0 до 65535|16\-разрядное целое число без знака|<xref:System.UInt16?displayProperty=fullName>|  
  
## Литералы  
 Переменную типа `ushort` можно объявить и инициализировать, как показано в этом примере:  
  
```  
  
ushort myShort = 65535;  
```  
  
 В приведенном выше объявлении целочисленный литерал `65535` неявным образом преобразуется из типа [int](../../../csharp/language-reference/keywords/int.md) в тип `ushort`.  Если целочисленный литерал выходит за пределы диапазона значений типа `ushort`, то происходит ошибка компиляции.  
  
 При вызове перегруженных методов необходимо использовать приведение типов.  Рассмотрите, например, следующие перегруженные методы, в которых используются параметры типов `ushort` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
  
 Использование приведения типа `ushort` гарантирует вызов метода правильного типа, например:  
  
```  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## Преобразования  
 Существует предопределенное преобразование типа `ushort` в [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) и [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md) или [char](../../../csharp/language-reference/keywords/char.md) в `ushort`.  В иных случаях для явного преобразования необходимо использовать приведение типов.  Рассмотрим, например, следующие две переменные `x` и `y` типа `ushort`:  
  
```  
  
ushort x = 5, y = 12;  
```  
  
 Следующая инструкция назначения приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора назначения, по умолчанию оценивается как имеющее тип `int`.  
  
```  
  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 Для устранения этой проблемы выполните преобразование:  
  
```  
  
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 Тем не менее, существует возможность использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `ushort` не существует.  Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделе [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 <xref:System.UInt16>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)