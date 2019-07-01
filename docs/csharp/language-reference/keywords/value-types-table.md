---
title: Справочник по C#. Таблица типов значений
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 98829f30c2c25c0710cf3fe044359d3c7538fe76
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424042"
---
# <a name="value-types-table-c-reference"></a>Таблица типов значений (справочник по C#)

В следующей таблице показаны значения для типов C#.

|Тип значения|Категория|Суффикс типа|
|----------------|--------------|-----------------|
|[bool](bool.md)|Boolean||
|[byte](../builtin-types/integral-numeric-types.md)|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||
|[char](char.md)|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)
)||
|[decimal](decimal.md)|Числовой, [с плавающей запятой](floating-point-types-table.md)|M или m|
|[double](double.md)|Числовой, [с плавающей запятой](floating-point-types-table.md)|D или d|
|[enum](enum.md)|Перечисление||
|[float](float.md)|Числовой, [с плавающей запятой](floating-point-types-table.md)|F или f|
|[int](../builtin-types/integral-numeric-types.md)|Со знаком, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||
|[long](../builtin-types/integral-numeric-types.md)|Со знаком, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)|L или l|
|[sbyte](../builtin-types/integral-numeric-types.md)|Со знаком, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||
|[short](../builtin-types/integral-numeric-types.md)|Со знаком, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||
|[struct](struct.md)|Определяемая пользователем структура||
|[uint](../builtin-types/integral-numeric-types.md)|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)|U или u|
|[ulong](../builtin-types/integral-numeric-types.md)|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)|UL, Ul, uL, ul, LU, Lu, lU или lu|
|[ushort](../builtin-types/integral-numeric-types.md)|Без знака, числовой, [целочисленный](../builtin-types/integral-numeric-types.md)||

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
