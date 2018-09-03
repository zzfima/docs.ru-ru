---
title: short (справочник по C#)
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: f402b9d2d62bcc3ba265755d59a657b88c197482
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468570"
---
# <a name="short-c-reference"></a>short (справочник по C#)

Ключевое слово `short` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведены в таблице ниже.  
  
|Тип|Диапазон|Размер|Тип .NET|  
|----------|-----------|----------|-------------------------|  
|`short`|От -32 768 до 32 767|16-разрядное целое число со знаком|<xref:System.Int16?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Литералы  

Переменную `short` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.  Если целочисленный литерал выходит за пределы диапазона `short` (то есть если он меньше <xref:System.Int16.MinValue?displayProperty=nameWithType> или больше <xref:System.Int16.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции. 

В следующем примере целые числа, равные 1034 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, неявно преобразуются из типа [int](../../../csharp/language-reference/keywords/int.md) в значения `short`.  
  
[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]  

> [!NOTE] 
> Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`. У десятичных литералов префиксов нет.

Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения. 
 - В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.
 - В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала. Десятичный литерал не может начинаться с символа подчеркивания.

Ниже приведено несколько примеров.

[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]  
 
## <a name="compiler-overload-resolution"></a>Разрешение перегрузки компилятора

 При вызове перегруженных методов необходимо использовать приведение типов. Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `short` и [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 Использование приведения типа `short` гарантирует вызов метода правильного типа, например:  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a>Преобразования  

 Существует предопределенное неявное преобразование типа `short` в тип [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) или [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Нельзя неявно преобразовать не являющиеся литералами числовые типы большего размера при хранении в тип `short` (сведения о размере целочисленных типов при хранении см. в разделе [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)). Рассмотрим, например, следующие две переменные `x` и `y` типа `short`:  
  
```csharp  
short x = 5, y = 12;  
```  
  
 Приведенный ниже оператор присваивания приведет к ошибке компиляции, потому что арифметическое выражение, расположенное справа от оператора присваивания, по умолчанию оценивается как имеющее тип [int](../../../csharp/language-reference/keywords/int.md).  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 Для устранения этой проблемы используйте приведение:  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 Также можно использовать следующие инструкции, в которых переменная назначения имеет такой же или больший размер при хранении:  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 Неявного преобразования типов с плавающей запятой в тип `short` не существует. Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](../../../csharp/language-reference/keywords/float.md) и [double](../../../csharp/language-reference/keywords/double.md).  
  
 Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Int16>  
- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
- [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
