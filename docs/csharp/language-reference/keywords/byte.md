---
title: "byte (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "byte"
  - "byte_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "byte - ключевое слово [C#]"
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# byte (справочник по C#)
Ключевое слово `byte` обозначает целочисленный тип данных, в котором хранятся значения, описанные в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|---------|--------------|------------|----------------------------------|  
|`byte`|От 0 до 255|8\-разрядное целое число без знака|<xref:System.Byte?displayProperty=fullName>|  
  
## Литералы  
 Переменную типа `byte` можно объявить и инициализировать, как показано в этом примере:  
  
```  
byte myByte = 255;  
```  
  
 В приведенном выше объявлении целочисленный литерал `255` неявным образом преобразуется из типа [int](../../../csharp/language-reference/keywords/int.md) в тип `byte`.  Если целочисленный литерал выходит за пределы диапазона значений типа `byte`, то происходит ошибка компиляции.  
  
## Преобразования  
 Существует предопределенное преобразование типа `byte` в тип [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Невозможно неявным образом преобразовать не являющиеся литералами числовые типы большего размера при хранении в тип `byte`.  Дополнительные сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md).  Рассмотрим, например, следующие две переменные `x` и `y` типа `byte`:  
  
```  
  
byte x = 10, y = 20;  
```  
  
 Следующая инструкция назначения приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора назначения, по умолчанию оценивается как имеющее тип `int`.  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 Для устранения этой проблемы выполните преобразование:  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 Тем не менее, существует возможность использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Кроме того, неявного преобразования типов с плавающей запятой в тип `byte` не существует.  Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 При вызове перегруженных методов необходимо использовать приведение типов.  Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `byte` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 Использование приведения типа `byte` гарантирует вызов метода правильного типа, например:  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделе [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 <xref:System.Byte>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)