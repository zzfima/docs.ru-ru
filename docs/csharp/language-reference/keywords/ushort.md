---
title: "ushort (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d27a7b3b44d91b5b52e82b13fb111d865f851297
ms.lasthandoff: 03/13/2017

---
# <a name="ushort-c-reference"></a>ushort (справочник по C#)
Ключевое слово `ushort` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`ushort`|От 0 до 65 535|16-разрядное целое число без знака|<xref:System.UInt16?displayProperty=fullName>|  
  
## <a name="literals"></a>Литералы  
 Переменную типа `ushort` можно объявить и инициализировать, как показано в примере:  
  
```  
  
ushort myShort = 65535;  
```  
  
 В приведенном выше объявлении целочисленный литерал `65535` неявным образом преобразуется из типа [int](../../../csharp/language-reference/keywords/int.md) в тип `ushort`. Если целочисленный литерал выходит за пределы диапазона значений типа `ushort`, происходит ошибка компиляции.  
  
 При вызове перегруженных методов необходимо использовать приведение типов. Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ushort` и [int](../../../csharp/language-reference/keywords/int.md):  
  
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
  
## <a name="conversions"></a>Преобразования  
 Существует предопределенное преобразование типа `ushort` в типы [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `ushort`. В противном случае для выполнения явного преобразования следует использовать приведение. Рассмотрим, например, следующие две переменные `x` и `y` типа `ushort`:  
  
```  
  
ushort x = 5, y = 12;  
```  
  
 Следующая инструкция назначения приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора назначения, по умолчанию оценивается как имеющее тип `int`.  
  
```  
  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 Для устранения этой проблемы используйте приведение:  
  
```  
  
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 Тем не менее можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `ushort` не существует. Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.UInt16>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
