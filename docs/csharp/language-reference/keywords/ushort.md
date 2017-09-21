---
title: "ushort (справочник по C#)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ushort
- ushort_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2b067a2ffd0fbffe06dc5c9f2a9910c9563eec4b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ushort-c-reference"></a>ushort (справочник по C#)

Ключевое слово `ushort` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`ushort`|От 0 до 65 535|16-разрядное целое число без знака|<xref:System.UInt16?displayProperty=fullName>|  
  
## <a name="literals"></a>Литералы  

Переменную `ushort` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал. Если целочисленный литерал выходит за пределы диапазона `ushort` (то есть если он меньше <xref:System.UInt16.MinValue?displayProperty=fullName> или больше <xref:System.UInt16.MaxValue?displayProperty=fullName>), возникает ошибка компиляции.

В следующем примере целые числа, равные 65 034 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](../../../csharp/language-reference/keywords/int.md) в значения `ushort`.    
  
[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]  

> [!NOTE] 
> Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`. У десятичных литералов префиксов нет.

Начиная с версии C# 7, для повышения удобочитаемости в качестве разделителя разрядов можно также использовать символ подчеркивания (`_`), как показано в следующем примере.

[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]  
 
## <a name="compiler-overload-resolution"></a>Разрешение перегрузки компилятора
  
 При вызове перегруженных методов необходимо использовать приведение типов. Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ushort` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 Использование приведения типа `ushort` гарантирует вызов метода правильного типа, например:  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a>Преобразования  
 Существует предопределенное преобразование типа `ushort` в типы [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `ushort`. В противном случае для выполнения явного преобразования следует использовать приведение. Рассмотрим, например, следующие две переменные `x` и `y` типа `ushort`:  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 Следующая инструкция назначения приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора назначения, по умолчанию оценивается как имеющее тип `int`.  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 Для устранения этой проблемы используйте приведение:  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 Тем не менее можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `ushort` не существует. Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.UInt16>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

