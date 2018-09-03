---
title: long (справочник по C#)
ms.date: 03/14/2017
f1_keywords:
- long_CSharpKeyword
- long
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
ms.openlocfilehash: 52755e0914ead3ab61930dd8bfb9ecdd8ced0a14
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400840"
---
# <a name="long-c-reference"></a>long (справочник по C#)

`long` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.  
  
|Тип|Диапазон|Размер|Тип .NET|  
|----------|-----------|----------|-------------------------|  
|`long`|От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807|64-разрядное целое число со знаком|<xref:System.Int64?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Литералы 

Переменную `long` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал. 

В следующем примере целые числа, равные 4 294 967 296 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `long`.  
  
[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]  

> [!NOTE] 
> Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`. У десятичных литералов префиксов нет. 

Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения. 
 - В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.
 - В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала. Десятичный литерал не может начинаться с символа подчеркивания.

Ниже приведено несколько примеров.

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 Целочисленные литералы могут также содержать суффикс, обозначающий тип. Суффикс `L` обозначает `long`. В следующем примере суффикс `L` используется для обозначения длинного целого числа:
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  Также в качестве суффикса можно использовать строчную букву "I". Однако при этом выдается предупреждение компилятора, так как букву "l" легко перепутать с цифрой "1". Для ясности используйте "L".  
  
 При использовании суффикса `L` тип целочисленного литерала определяется как `long` или [ulong](../../../csharp/language-reference/keywords/ulong.md) в зависимости от его размера. В данном случае это тип `long`, поскольку его диапазон меньше, чем требуется для типа [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
 Обычно суффикс используется для вызова перегруженных методов. Например, следующие перегруженные методы имеют параметры типов `long` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 Суффикс `L` обеспечивает вызов нужной перегрузки:  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение: 

1. [int](int.md)
2. [uint](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [ulong](../../../csharp/language-reference/keywords/ulong.md) 

Литерал 4294967296 в предыдущем примере имеет тип `long`, поскольку выходит за пределы типа [uint](../../../csharp/language-reference/keywords/uint.md) (объемы хранения целочисленных типов см. в [таблице целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)).  
  
 Тип `long` можно использовать с другими целочисленными типами в том же выражении, в случае чего выражение вычисляется как `long` (или [bool](../../../csharp/language-reference/keywords/bool.md) для реляционных или логических выражений). Например, следующее выражение вычисляется как `long`:  
  
```csharp  
898L + 88  
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
## <a name="conversions"></a>Преобразования  
 Существует предопределенное неявное преобразование типа `long` в тип [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md). В противном случае необходимо использовать приведение. Например, следующий оператор вызывает ошибку компиляции без явного приведения:  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int y = (int)8L;   // OK: explicit conversion to int  
```  
  
 Существует предопределенное неявное преобразование типа [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) или [char](../../../csharp/language-reference/keywords/char.md) в `long`.  
  
 Обратите внимание, что неявного преобразования типов с плавающей запятой в тип `long` не существует. Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Int64>  
- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
- [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
