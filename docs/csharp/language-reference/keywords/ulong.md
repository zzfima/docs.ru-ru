---
title: Ключевое слово ulong (справочник по C#)
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: d0c7df4ebda13a59e51e9599699f6abf4bbf1d71
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143432"
---
# <a name="ulong-c-reference"></a>ulong (справочник по C#)

Ключевое слово `ulong` обозначает целочисленный тип данных, в котором хранятся значения, размер и диапазон которых приведен в следующей таблице.

|Тип|Диапазон|Размер|Тип .NET|
|----------|-----------|----------|-------------------------|
|`ulong`|От 0 до 18 446 744 073 709 551 615|64-разрядное целое число без знака|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a>Литералы

Переменную `ulong` можно объявить и инициализировать, назначив ей десятичный, шестнадцатеричный или (начиная с C# 7.0) двоичный литерал.  Если целочисленный литерал выходит за пределы диапазона `ulong` (то есть если он меньше <xref:System.UInt64.MinValue?displayProperty=nameWithType> или больше <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), возникает ошибка компиляции.

В следующем примере целые числа, равные 7 934 076 125 и представленные в виде десятичного, шестнадцатеричного и двоичного литерала, назначаются значениям `ulong`.

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> Для обозначения шестнадцатеричного литерала используйте префикс `0x` или `0X`, а для обозначения двоичного литерала — префикс `0b` или `0B`. У десятичных литералов префиксов нет.

Начиная с C# 7.0 было добавлено несколько возможностей для повышения удобства чтения.

- В C# 7.0 поддерживается использование символа подчеркивания (`_`) в качестве разделителя цифр.
- В C# 7.2 поддерживается использование `_` (после префикса) в качестве разделителя для двоичного или шестнадцатеричного литерала. Десятичный литерал не может начинаться с символа подчеркивания.

Ниже приведено несколько примеров.

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

Целочисленные литералы могут также содержать суффикс, обозначающий тип. Суффикс `UL` или `ul` однозначно идентифицирует числовой литерал как значение `ulong`. Суффикс `L` обозначает `ulong`, если значение литерала превышает <xref:System.Int64.MaxValue?displayProperty=nameWithType>. Суффикс `U` или `u` обозначает `ulong`, если значение литерала превышает <xref:System.UInt32.MaxValue?displayProperty=nameWithType>. В следующем примере суффикс `ul` используется для обозначения длинного целого числа:

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

Если целочисленный литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение:

1. [int](int.md)
2. [uint](uint.md)
3. [long](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a>Разрешение перегрузки компилятора

Обычно суффикс используется для вызова перегруженных методов. Рассмотрим, например, следующие перегруженные методы, в которых используются параметры типов `ulong` и [int](int.md):

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

Существует предопределенное неявное преобразование типа `ulong` в тип [float](float.md), [double](double.md) или [decimal](decimal.md).

Неявного преобразования типа `ulong` в любой целочисленный тип не существует. Например, следующий оператор вызывает ошибку компиляции без явного приведения:

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

Существует предопределенное неявное преобразование типа [byte](byte.md), [ushort](ushort.md), [uint](uint.md) или [char](char.md) в тип `ulong`.

Кроме того, неявного преобразования типов с плавающей запятой в тип `ulong` не существует. Например, следующая инструкция приводит к ошибке компилятора, если не выполнить явное приведение типов:

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

Сведения об арифметических выражениях, в которых одновременно используются переменные типов с плавающей запятой и целочисленных типов, см. в разделах [float](float.md) и [double](double.md).

Дополнительные сведения о правилах выполнения неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Целочисленные типы](~/_csharplang/spec/types.md#integral-types) в [Спецификации языка C#](../language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.

## <a name="see-also"></a>См. также

- <xref:System.UInt64>
- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Таблица целых типов](integral-types-table.md)
- [Таблица встроенных типов](built-in-types-table.md)
- [Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md)
- [Таблица явных числовых преобразований](explicit-numeric-conversions-table.md)
