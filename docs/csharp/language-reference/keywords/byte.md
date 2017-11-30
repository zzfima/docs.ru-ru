---
title: "byte (справочник по C#)"
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords: byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 231a491914071b1d43b5a8938e677be531726e75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="byte-c-reference"></a>byte (справочник по C#)

Ключевое слово `byte` обозначает целочисленный тип данных, в котором хранятся значения, описанные в приведенной ниже таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`byte`|От 0 до 255|8-разрядное целое число без знака|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Литералы  

 Переменную `byte` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `byte` (то есть если он меньше <xref:System.Byte.MinValue?displayProperty=nameWithType> или больше <xref:System.Byte.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 201 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](../../../csharp/language-reference/keywords/int.md) в значения `byte`.    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`. У десятичных литералов префиксов нет.

Начиная с C# 7, ваши возможности были добавлены для повышения удобства чтения. 
 - C# 7.0 допускает использование символа подчеркивания, `_`, в качестве разделителя цифр.
 - 7.2 C# позволяет `_` должен использоваться как разделитель для двоичных или шестнадцатеричное литерала, после префикса. Десятичный литерал не может иметь с символа подчеркивания.

Ниже приведены некоторые примеры.

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a>Преобразования  
 Существует предопределенное неявное преобразование типа `byte` в типы [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Невозможно неявным образом преобразовать не являющиеся литералами числовые типы большего размера при хранении в тип `byte`. Дополнительные сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md). Рассмотрим, например, следующие две переменные `x` и `y` типа `byte`:  
  
```  
byte x = 10, y = 20;  
```  
  
 Следующий оператор присваивания приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора присваивания, по умолчанию оценивается как имеющее тип `int`.  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 Для устранения этой проблемы используйте приведение:  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 Однако можно использовать следующие операторы, в которых переменная назначения имеет такой же или больший размер при хранении:  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Кроме того, неявного преобразования типов с плавающей запятой в тип `byte` не существует. Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 При вызове перегруженных методов необходимо использовать приведение типов. Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `byte` и [int](../../../csharp/language-reference/keywords/int.md):  
  
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
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Byte>  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
