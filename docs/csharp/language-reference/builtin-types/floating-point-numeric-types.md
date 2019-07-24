---
title: Числовые типы с плавающей запятой — справочник по C#
description: Общие сведения о встроенных типах с плавающей запятой в C#
ms.date: 06/30/2019
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
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 0d97b3ffd587e8398e5572706a47937716a6e709
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236063"
---
# <a name="floating-point-numeric-types-c-reference"></a>Числовые типы с плавающей запятой (справочник по C#)

**Типы с плавающей запятой** — это подмножество **простых типов**. Они могут инициализироваться [*литералами*](#floating-point-literals). Все типы с плавающей запятой также являются типами значений. Все числовые типы с плавающей запятой поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, а также операторы [сравнения и равенства](../operators/equality-operators.md).

## <a name="characteristics-of-the-floating-point-types"></a>Характеристики типов с плавающей запятой

C# поддерживает следующие предварительно определенные типы с плавающей запятой:
  
|Ключевое слово или тип C#|Приблизительный диапазон значений|Точность|Тип .NET|
|----------|-----------------------|---------------|--------------|
|`float`|От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup>|6–9 цифр|<xref:System.Single?displayProperty=nameWithType>|
|`double`|от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup>|15–17 цифр|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup>|28-29 знаков|<xref:System.Decimal?displayProperty=nameWithType>|

В приведенной выше таблице каждый тип ключевого слова C# из крайнего левого столбца является псевдонимом для соответствующего типа .NET. Они взаимозаменяемые. Например, следующие объявления объявляют переменные одного типа:

```csharp
double a = 12.3;
System.Double b = 12.3;
```

По умолчанию все типы с плавающей запятой имеют значение `0`. Все типы с плавающей запятой имеют константы `MinValue` и `MaxValue` с минимальным и максимальными итоговыми значениями этого типа. Типы `float` и `double` также предоставляют константы, обозначающие бесконечные и нечисловые значения. Например, тип `double` предоставляет следующие константы: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> и <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.

Так как тип `decimal` характеризуется более высокой точностью и меньшим диапазоном, чем `float` и `double`, он подходит для финансовых расчетов.

В одном и том же выражении можно сочетать и [целочисленные типы](integral-numeric-types.md), и типы с плавающей запятой. В этом случае целочисленные типы преобразуются в типы с плавающей запятой. Выражение вычисляется по следующим правилам:

- Если одним из типов с плавающей запятой является `double`, то выражение оценивается как `double` или [bool](../keywords/bool.md) в реляционных сравнениях или сравнениях на равенство.
- Если в выражении нет типа `double`, оно оценивается как `float` или [bool](../keywords/bool.md) в реляционных сравнениях или сравнениях на равенство.

Выражение с плавающей запятой может содержать следующие наборы значений:

- Положительный и отрицательный ноль
- Положительная и отрицательная бесконечность
- Нечисловое значение (NaN)
- Конечный набор ненулевых значений

Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](https://www.ieee.org).

Можно использовать [строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md) или [строки пользовательских числовых форматов](../../../standard/base-types/custom-numeric-format-strings.md) для форматирования значения с плавающей запятой.

## <a name="floating-point-literals"></a>Литералы с плавающей запятой

По умолчанию числовой литерал с плавающей запятой в правой части оператора присваивания обрабатывается как `double`. Суффиксы можно использовать для преобразования литерала с плавающей запятой или целочисленного литерала в определенный тип:

- Суффикс `d` или `D` преобразует литерал в `double`.
- Суффикс `f` или `F` преобразует литерал в `float`.
- Суффикс `m` или `M` преобразует литерал в `decimal`.

В следующем примере показан каждый суффикс:

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a>Преобразования

Существует неявное преобразование (называемое *расширяющим преобразованием*) из `float` в `double`, так как диапазон значений `float` является строгим подмножеством объекта `double` и при преобразовании из `float` в `double` не теряется точность.

Если неявное преобразование между двумя типами с плавающей запятой не определено, необходимо использовать явное приведение. Это называется *сужающим преобразованием*. Явное приведение требуется по той причине, что преобразование может привести к потере данных. Не существует неявного преобразования между другими типами с плавающей запятой и типом `decimal`, так как тип `decimal` имеет большую точность, чем `float` или `double`.

Дополнительные сведения о неявных числовых преобразованиях см. в разделе [Таблица неявных числовых преобразований](../keywords/implicit-numeric-conversions-table.md).

Дополнительные сведения о явных числовых преобразованиях см. в разделе [Таблица явных числовых преобразований](../keywords/explicit-numeric-conversions-table.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Целочисленные типы](integral-numeric-types.md)
- [Таблица встроенных типов](../keywords/built-in-types-table.md)
- [Числовые значения в .NET](../../../standard/numerics.md)
- [Приведение и преобразование типов](../../programming-guide/types/casting-and-type-conversions.md)
- [Таблица неявных числовых преобразований](../keywords/implicit-numeric-conversions-table.md)
- [Таблица явных числовых преобразований](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [Таблица форматирования числовых результатов](../keywords/formatting-numeric-results-table.md)
- [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md)
