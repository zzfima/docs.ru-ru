---
title: Справочник по C#. Таблица значений по умолчанию
ms.custom: seodec18
description: Узнайте значения по умолчанию для типов значений в C#.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: ec5fb4681f0e0562c5aefdf336841416f96bdf98
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661411"
---
# <a name="default-values-table-c-reference"></a>Таблица значений по умолчанию (справочник по C#)

В следующей таблице показаны значения по умолчанию для [типов значений](value-types.md).

|Тип значения|Значение по умолчанию|
|----------------|-------------------|
|[bool](bool.md)|`false`|
|[byte](../builtin-types/integral-numeric-types.md)|0|
|[char](char.md)|'\0'|
|[decimal](../builtin-types/floating-point-numeric-types.md)|0M|
|[double](../builtin-types/floating-point-numeric-types.md)|0,0D|
|[enum](enum.md)|Значение, создаваемое выражением `(E)0`, где `E` — это идентификатор перечисления.|
|[float](../builtin-types/floating-point-numeric-types.md)|0,0F|
|[int](../builtin-types/integral-numeric-types.md)|0|
|[long](../builtin-types/integral-numeric-types.md)|0L|
|[sbyte](../builtin-types/integral-numeric-types.md)|0|
|[short](../builtin-types/integral-numeric-types.md)|0|
|[struct](struct.md)|Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.|
|[uint](../builtin-types/integral-numeric-types.md)|0|
|[ulong](../builtin-types/integral-numeric-types.md)|0|
|[ushort](../builtin-types/integral-numeric-types.md)|0|

## <a name="remarks"></a>Примечания

Неинициализированные переменные нельзя использовать в C#. Вы можете инициализировать переменную со значением по умолчанию для ее типа. Вы также можете использовать значение типа по умолчанию для указания значения по умолчанию [необязательного аргумента](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) метода.

Используйте [выражение значения по умолчанию](../../programming-guide/statements-expressions-operators/default-value-expressions.md), чтобы получить значение типа по умолчанию, как показано в следующем примере:

```csharp
int a = default(int);
```

Начиная с C# 7.1 вы можете использовать литерал [`default` ](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) для инициализации переменной со значением по умолчанию для ее типа:

```csharp
int a = default;
```

Также можно использовать конструктор без параметров или неявный конструктор без параметров, чтобы получить значение по умолчанию для типа значения, как показано в следующем примере. Дополнительные сведения о конструкторах см. в статье [Конструкторы](../../programming-guide/classes-and-structs/constructors.md).

```csharp
int a = new int();
```

Значение по умолчанию любого [ссылочного типа](reference-types.md) — `null`. Значение по умолчанию для [типа, допускающего значение null](../../programming-guide/nullable-types/index.md), — это экземпляр, свойство <xref:System.Nullable%601.HasValue%2A> которого имеет значение `false` и свойство <xref:System.Nullable%601.Value%2A> которого не определено.

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Типы значений](value-types.md)
- [Таблица типов значений](value-types-table.md)
- [Таблица встроенных типов](built-in-types-table.md)
