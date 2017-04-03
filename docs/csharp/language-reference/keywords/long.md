---
title: "long (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- long_CSharpKeyword
- long
dev_langs:
- CSharp
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 17
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
ms.openlocfilehash: c28c8308d7ed32f7240f56113a77a0794cb1ba62
ms.lasthandoff: 03/13/2017

---
# <a name="long-c-reference"></a>long (справочник по C#)
Ключевое слово `long` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип платформы .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`long`|От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807|64-разрядное целое число со знаком|<xref:System.Int64?displayProperty=fullName>|  
  
## <a name="literals"></a>Литералы  
 Переменную типа `long` можно объявить и инициализировать, как показано в примере:  
  
```  
  
long long1 = 4294967296;  
```  
  
 Если целочисленный литерал не имеет суффикса, его тип — первый из этих типов, в котором может быть представлено его значение: [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), `long`, [ulong](../../../csharp/language-reference/keywords/ulong.md). В предыдущем примере он имеет тип `long`, поскольку выходит за пределы типа [uint](../../../csharp/language-reference/keywords/uint.md) (объемы хранения целочисленных типов см. в [таблице целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)).  
  
 Кроме того, с типом `long` можно использовать суффикс L:  
  
```  
  
long long2 = 4294967296L;  
```  
  
 При использовании суффикса L тип целочисленного литерала определяется как `long` или [ulong](../../../csharp/language-reference/keywords/ulong.md) в зависимости его размера. В данном случае это тип `long`, поскольку его диапазон меньше, чем требуется для типа [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
 Обычно суффикс используется для вызова перегруженных методов. Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `long` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 Суффикс L гарантирует вызов верного типа, например:  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5L);   // Calling the method with the long parameter  
```  
  
 Тип `long` можно использовать с другими числовыми целочисленными типами в том же выражении, в случае чего выражение вычисляется как `long` (или [bool](../../../csharp/language-reference/keywords/bool.md) для реляционных или логических выражений). Например, следующее выражение вычисляется как `long`:  
  
```  
898L + 88  
```  
  
> [!NOTE]
>  Также в качестве суффикса можно использовать строчную букву "I". Однако при этом выдается предупреждение компилятора, так как букву "l" легко перепутать с цифрой "1". Для ясности используйте "L".  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
## <a name="conversions"></a>Преобразования  
 Существует предопределенное неявное преобразование типа `long` в тип [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md). В противном случае необходимо использовать приведение. Например, следующий оператор вызывает ошибку компиляции без явного приведения:  
  
```  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 Существует предопределенное неявное преобразование типа [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) или [char](../../../csharp/language-reference/keywords/char.md) в `long`.  
  
 Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `long` не существует. Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```  
  
      long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Int64>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
