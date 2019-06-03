---
title: Справочник по C#. Таблица типов значений
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 959d4840344ba041ae1b01fd6d202f2b53936afc
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422369"
---
# <a name="value-types-table-c-reference"></a>Таблица типов значений (справочник по C#)

В следующей таблице показаны значения для типов C#.

|Тип значения|Категория|Суффикс типа|
|----------------|--------------|-----------------|
|[bool](bool.md)|Boolean||
|[byte](byte.md)|Без знака, числовой, [целочисленный](integral-types-table.md)||
|[char](char.md)|Без знака, числовой, [целочисленный](integral-types-table.md)||
|[decimal](decimal.md)|Числовой, [с плавающей запятой](floating-point-types-table.md)|M или m|
|[double](double.md)|Числовой, [с плавающей запятой](floating-point-types-table.md)|D или d|
|[enum](enum.md)|Перечисление||
|[float](float.md)|Числовой, [с плавающей запятой](floating-point-types-table.md)|F или f|
|[int](int.md)|Со знаком, числовой, [целочисленный](integral-types-table.md)||
|[long](long.md)|Со знаком, числовой, [целочисленный](integral-types-table.md)|L или l|
|[sbyte](sbyte.md)|Со знаком, числовой, [целочисленный](integral-types-table.md)||
|[short](short.md)|Со знаком, числовой, [целочисленный](integral-types-table.md)||
|[struct](struct.md)|Определяемая пользователем структура||
|[uint](uint.md)|Без знака, числовой, [целочисленный](integral-types-table.md)|U или u|
|[ulong](ulong.md)|Без знака, числовой, [целочисленный](integral-types-table.md)|UL, Ul, uL, ul, LU, Lu, lU или lu|
|[ushort](ushort.md)|Без знака, числовой, [целочисленный](integral-types-table.md)||

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
