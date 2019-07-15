---
title: Справочник по C#. Таблица типов значений
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 2e2897ff647140b58b3a1812e153a44a6fcdaef7
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859564"
---
# <a name="value-types-table-c-reference"></a>Таблица типов значений (справочник по C#)

В следующей таблице показаны значения для типов C#.

|Тип значения|Категория|Суффикс типа|
|----------------|--------------|-----------------|
|[bool](bool.md)|Boolean||
|`byte`|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||
|[char](char.md)|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)
|`decimal`|Числовой, [с плавающей запятой](../builtin-types/floating-point-numeric-types.md)|M или m|
|`double`|Числовой, [с плавающей запятой](../builtin-types/floating-point-numeric-types.md)|D или d|
|[enum](enum.md)|Перечисление||
|`float`|Числовой, [с плавающей запятой](../builtin-types/floating-point-numeric-types.md)|F или f|
|`int`|Со знаком, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||
|`long`|Со знаком, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)|L или l|
|`sbyte`|Со знаком, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||
|`short`|Со знаком, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||
|[struct](struct.md)|Определяемая пользователем структура||
|`uint`|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)|U или u|
|`ulong`|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)|UL, Ul, uL, ul, LU, Lu, lU или lu|
|`ushort`|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||

## <a name="remarks"></a>Примечания

Суффикс типа позволяет указать тип числового литерала. Например:

```csharp
decimal a = 0.1M;
```

Если [целочисленный числовой литерал](~/_csharplang/spec/lexical-structure.md#integer-literals) не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение: `int`, `uint`, `long`, `ulong`.

Если [числовой литерал с плавающей запятой](~/_csharplang/spec/lexical-structure.md#real-literals) не имеет суффикса, он имеет тип `double`.

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Таблица значений по умолчанию](default-values-table.md)
- [Типы значений](value-types.md)
- [Таблица форматирования числовых результатов](formatting-numeric-results-table.md)
