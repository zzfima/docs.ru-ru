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
ms.openlocfilehash: 738368abd9db75fbd97d1913324cab3b6e869c56
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664194"
---
# <a name="floating-point-numeric-types-c-reference"></a>Числовые типы с плавающей запятой (справочник по C#)

**Типы с плавающей запятой** — это подмножество **простых типов**. Они могут инициализироваться [*литералами*](#floating-point-literals). Все типы с плавающей запятой также являются типами значений. Все числовые типы с плавающей запятой поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, операторы [сравнения и равенства](../operators/equality-operators.md).

В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типов с плавающей запятой:
  
|Тип|Приблизительный диапазон значений|Точность|  
|----------|-----------------------|---------------|  
|`float`|От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup>|6–9 цифр|  
|`double`|от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup>|15–17 цифр|  
|`decimal`|от ±1,0 x 10<sup>-28</sup> до ±7,9228 x 10<sup>28</sup>|28-29 знаков|  

По умолчанию типы с плавающей запятой имеют значение `0`. Каждый тип с плавающей запятой имеет константы `MinValue` и `MaxValue` с минимальным и максимальным значениями этого типа. Типы `float` и `double` имеют дополнительные константы для `PositiveInfinity`, `NegativeInfinity` и `NaN` (для параметров "Не число"). Тип `decimal` включает в себя константы для `Zero`, `One` и `MinusOne`.

Типа `decimal` имеет более высокую точность и меньший диапазон, чем `float` и `double`, благодаря чему этот тип подходит для финансовых расчетов.

В одном и том же выражении можно сочетать и целочисленные типы, и типы с плавающей запятой. В этом случае целочисленные типы преобразуются в типы с плавающей запятой. Выражение вычисляется по следующим правилам:

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
- [Таблица значений по умолчанию](../keywords/default-values-table.md)
- [Таблица форматирования числовых результатов](../keywords/formatting-numeric-results-table.md)
- [Таблица встроенных типов](../keywords/built-in-types-table.md)
- [Числовые значения в .NET](../../../standard/numerics.md)
- [Приведение и преобразование типов](../../programming-guide/types/casting-and-type-conversions.md)
- [Таблица неявных числовых преобразований](../keywords/implicit-numeric-conversions-table.md)
- [Таблица явных числовых преобразований](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md)
