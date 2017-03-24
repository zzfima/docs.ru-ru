---
title: "sbyte (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "sbyte_CSharpKeyword"
  - "sbyte"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sbyte - ключевое слово [C#]"
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# sbyte (справочник по C#)
Ключевое слово `sbyte` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|---------|--------------|------------|----------------------------------|  
|`sbyte`|От \-128 до 127|8\-разрядное знаковое целое число|<xref:System.SByte?displayProperty=fullName>|  
  
## Литералы  
 Переменную типа `sbyte` можно объявить и инициализировать следующим образом:  
  
```  
  
sbyte sByte1 = 127;  
```  
  
 В приведенном выше объявлении целочисленный литерал 127 неявным образом преобразуется из типа [int](../../../csharp/language-reference/keywords/int.md) в тип `sbyte`.  Если целочисленный литерал выходит за пределы диапазона значений типа `sbyte`, то происходит ошибка компиляции.  
  
 При вызове перегруженных методов необходимо использовать приведение типов.  Рассмотрите, например, следующие перегруженные методы, в которых используются параметры типов `sbyte` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 Использование приведения типа `sbyte` гарантирует вызов метода правильного типа, например:  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## Преобразования  
 Существует предопределенное преобразование типа `sbyte` в типы [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) и [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Существует возможность преобразовать неявным образом не являющиеся литералами числовые типы большего размера при хранении в тип `sbyte` \(сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)\).  Рассмотрим, например, следующие две переменные переменные `x` и `y` типа `sbyte`:  
  
```  
  
sbyte x = 10, y = 20;  
```  
  
 Следующая инструкция назначения приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора назначения, по умолчанию оценивается как имеющее тип [int](../../../csharp/language-reference/keywords/int.md).  
  
```  
  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 Для устранения этой проблемы нужно привести тип этого выражения, как показано в следующем примере:  
  
```  
  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 Тем не менее, существует возможность использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:  
  
```  
  
        sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `sbyte` не существует.  Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```  
  
        sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделе [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 <xref:System.SByte>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)