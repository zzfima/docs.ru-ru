---
title: Числовые типы с плавающей запятой — справочник по C#
description: Общие сведения о встроенных типах с плавающей запятой в C#
ms.date: 10/22/2019
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 9c8b11f9337ee9de90f2d4d96b5be162713bfcbd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093218"
---
# <a name="floating-point-numeric-types-c-reference"></a>Числовые типы с плавающей запятой (справочник по C#)

*Числовые типы с плавающей запятой* представляют действительные числа. Все числовые типы с плавающей запятой являются [типами значений](value-types.md). Они также представляют собой [простые типы](value-types.md#built-in-value-types) и могут быть инициализированы [литералами](#real-literals). Все числовые типы с плавающей запятой поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, а также операторы [сравнения](../operators/comparison-operators.md) и [равенства](../operators/equality-operators.md).

## <a name="characteristics-of-the-floating-point-types"></a>Характеристики типов с плавающей запятой

C# поддерживает следующие предварительно определенные типы с плавающей запятой:
  
|Ключевое слово или тип C#|Приблизительный диапазон значений|Точность|Размер|Тип .NET|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup>|6–9 цифр|4 байта|<xref:System.Single?displayProperty=nameWithType>|
|`double`|от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup>|15–17 цифр|8 байт|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup>|28-29 знаков|16 байт|<xref:System.Decimal?displayProperty=nameWithType>|

В приведенной выше таблице каждый тип ключевого слова C# из крайнего левого столбца является псевдонимом для соответствующего типа .NET. Они взаимозаменяемые. Например, следующие объявления объявляют переменные одного типа:

```csharp
double a = 12.3;
System.Double b = 12.3;
```

По умолчанию все типы с плавающей запятой имеют значение `0`. Все типы с плавающей запятой имеют константы `MinValue` и `MaxValue` с минимальным и максимальными итоговыми значениями этого типа. Типы `float` и `double` также предоставляют константы, обозначающие бесконечные и нечисловые значения. Например, тип `double` предоставляет следующие константы: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> и <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.

Так как тип `decimal` характеризуется более высокой точностью и меньшим диапазоном, чем `float` и `double`, он подходит для финансовых расчетов.

В одном и том же выражении можно сочетать и [целочисленные типы](integral-numeric-types.md), и типы с плавающей запятой. В этом случае целочисленные типы преобразуются в типы с плавающей запятой. Выражение вычисляется по следующим правилам:

- Если одним из типов с плавающей запятой является `double`, выражение оценивается как `double` или [bool](bool.md) в реляционных сравнениях или сравнениях на равенство.
- Если в выражении нет типа `double`, оно оценивается как `float` или [bool](bool.md) в реляционных сравнениях или сравнениях на равенство.

Выражение с плавающей запятой может содержать следующие наборы значений:

- Положительный и отрицательный ноль
- Положительная и отрицательная бесконечность
- Нечисловое значение (NaN)
- Конечный набор ненулевых значений

Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](https://www.ieee.org).

Можно использовать [строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md) или [строки пользовательских числовых форматов](../../../standard/base-types/custom-numeric-format-strings.md) для форматирования значения с плавающей запятой.

## <a name="real-literals"></a>Вещественные литералы

Тип реального литерала определяется его суффиксом следующим образом:

- Литерал без суффикса или с суффиксом `d` или `D` имеет тип `double`.
- Литерал с суффиксом `f` или `F` имеет тип `float`.
- Литерал с суффиксом `m` или `M` имеет тип `decimal`.

В приведенном ниже коде показан пример каждого из них.

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

В предыдущем примере также показано использование `_` в качестве *цифрового разделителя*, который поддерживается, начиная с версии C# 7.0. Цифровой разделитель можно использовать со всеми видами числовых литералов.

Можно также использовать экспоненциальное представление, то есть указать экспоненту вещественного литерала, как показано в следующем примере:

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a>Преобразования

Существует только одно неявное преобразование между числовыми типами с плавающей запятой: из `float` в `double`. Однако можно преобразовать любой тип с плавающей запятой в любой другой тип с плавающей запятой с помощью[явного приведения](../operators/type-testing-and-cast.md#cast-operator-). Для получения дополнительной информации см. статью [Встроенные числовые преобразования](numeric-conversions.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Типы с плавающей запятой](~/_csharplang/spec/types.md#floating-point-types)
- Тип [decimal](~/_csharplang/spec/types.md#the-decimal-type)
- [Вещественные литералы](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Типы значений](value-types.md)
- [Целочисленные типы](integral-numeric-types.md)
- [Строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md)
- [Числовые значения в .NET](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
