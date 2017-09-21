---
title: "ulong (справочник по C#)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
dev_langs:
- CSharp
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
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
ms.openlocfilehash: c2da253e4da7a5d6cfa71116e4fcba7816441e92
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ulong-c-reference"></a>ulong (справочник по C#)

Ключевое слово `ulong` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`ulong`|От 0 до 18 446 744 073 709 551 615|64-разрядное целое число без знака|<xref:System.UInt64?displayProperty=fullName>|  
  
## <a name="literals"></a>Литералы  

Переменную `ulong` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7) двоичный литерал.  Если целочисленный литерал выходит за пределы диапазона `ulong` (то есть если он меньше <xref:System.UInt64.MinValue?displayProperty=fullName> или больше <xref:System.UInt64.MaxValue?displayProperty=fullName>), возникает ошибка компиляции. 

В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ulong`.  
  
[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]  

> [!NOTE] 
> Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`. У десятичных литералов префиксов нет. 

Начиная с версии C# 7, для повышения удобочитаемости в качестве разделителя разрядов можно также использовать символ подчеркивания (`_`), как показано в следующем примере.

[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 Целочисленные литералы могут также содержать суффикс, обозначающий тип. Суффикс `UL` или `ul` однозначно идентифицирует числовой литерал как значение `ulong`. Суффикс `L` обозначает `ulong`, если значение литерала превышает <xref:System.Int64.MaxValue?displayProperty=fullName>. Суффикс `U` или `u` обозначает `ulong`, если значение литерала превышает <xref:System.UInt32.MaxValue?displayProperty=fullName>. В следующем примере суффикс `ul` используется для обозначения длинного целого числа:
 
[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение: 

1. [int](int.md)
2. [uint](../../../csharp/language-reference/keywords/uint.md)
3. [long](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a>Разрешение перегрузки компилятора
  
 Обычно суффикс используется для вызова перегруженных методов. Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ulong` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 Использование суффикса с параметром `ulong` гарантирует вызов метода правильного типа, например:  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a>Преобразования  
 Существует предопределенное неявное преобразование типа `ulong` в тип [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Неявного преобразования типа `ulong` в любой целочисленный тип не существует. Например, следующий оператор вызывает ошибку компиляции без явного приведения:  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 Существует предопределенное неявное преобразование типа [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) или [char](../../../csharp/language-reference/keywords/char.md) в тип `ulong`.  
  
 Кроме того, неявного преобразования типов с плавающей запятой в тип `ulong` не существует. Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.UInt64>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

