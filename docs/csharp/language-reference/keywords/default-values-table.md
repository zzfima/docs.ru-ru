---
title: Таблица значений по умолчанию — справочник по C#
ms.custom: seodec18
description: Узнайте значения по умолчанию для типов в C#.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 48aa294fa9e37e2e138444e493faa5474011097e
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74551827"
---
# <a name="default-values-table-c-reference"></a>Таблица значений по умолчанию (справочник по C#)

В следующей таблице показаны значения по умолчанию для типов C#:

|Тип|Значение по умолчанию|
|---------|------------------|
|любой ссылочный тип;|`null`|
|Любой [встроенный целочисленный тип](../builtin-types/integral-numeric-types.md)|Ноль (0)|
|Любой [встроенный тип с плавающей запятой](../builtin-types/floating-point-numeric-types.md)|Ноль (0)|
|[bool](../builtin-types/bool.md)|`false`|
|[char](../builtin-types/char.md)|`'\0'` (U+0000)|
|[enum](enum.md)|Значение, создаваемое выражением `(E)0`, где `E` — это идентификатор перечисления.|
|[struct](struct.md)|Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.|
|Любой [тип значения, допускающий значение NULL](../builtin-types/nullable-value-types.md)|Экземпляр, свойство `false` которого имеет значение <xref:System.Nullable%601.HasValue%2A>, а свойство <xref:System.Nullable%601.Value%2A> не определено. Это значение по умолчанию также называется значением *NULL* типа значения, допускающего значение NULL.|

Используйте [оператор по умолчанию](../operators/default.md), чтобы получить значение типа по умолчанию, как показано в следующем примере:

```csharp
int a = default(int);
```

Начиная с C# 7.1 вы можете использовать литерал [`default` ](../operators/default.md#default-literal) для инициализации переменной со значением по умолчанию для ее типа:

```csharp
int a = default;
```

Для типа значения неявный конструктор без параметров также создает значение по умолчанию для типа, как показано в следующем примере:

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Значения по умолчанию](~/_csharplang/spec/variables.md#default-values)
- [Конструкторы по умолчанию](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Ключевые слова C#](index.md)
- [Таблица встроенных типов](built-in-types-table.md)
- [Конструкторы](../../programming-guide/classes-and-structs/constructors.md)
