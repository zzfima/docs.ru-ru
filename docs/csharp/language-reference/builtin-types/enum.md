---
title: Справочник по C#. Типы перечислений
description: Общие сведения о типах перечислений на C#, которые предоставляют выбор или комбинацию вариантов выбора.
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: ac4dafef92bbc900d291a5b653c55ba295f1a6d6
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093231"
---
# <a name="enumeration-types-c-reference"></a>Типы перечислений (справочник по C#)

*Тип перечисления* (или *тип enum*) — это [тип значения](value-types.md), определенный набором именованных констант применяемого [целочисленного типа](integral-numeric-types.md). Чтобы определить тип перечисления, используйте ключевое слово `enum` и укажите имена *элементов перечисления*:

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

По умолчанию связанные значения констант элементов перечисления имеют тип `int`. Они начинаются с нуля и увеличиваются на единицу в соответствии с порядком текста определения. Вы можете явно указать любой другой [целочисленный](integral-numeric-types.md) тип в качестве базового типа перечисления. Вы также можете явно указать соответствующие значения констант, как показано в следующем примере:

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

Вы не можете определить метод внутри определения типа перечисления. Чтобы добавить функциональные возможности к типу перечисления, создайте [метод расширения](../../programming-guide/classes-and-structs/extension-methods.md).

Значением по умолчанию для типа перечисления `E` является значение, созданное выражением `(E)0`, даже если ноль не имеет соответствующего элемента перечисления.

Тип перечисления используется для представления выбора из набора взаимоисключающих значений или комбинации вариантов выбора. Чтобы представить комбинацию вариантов выбора, определите тип перечисления как битовые флаги.

## <a name="enumeration-types-as-bit-flags"></a>Типы перечислений как битовые флаги

Если вам необходимо, чтобы тип перечисления представлял комбинацию вариантов выбора, определите элементы перечисления для этих вариантов так, чтобы отдельный выбор был битовым полем. То есть связанные значения этих элементов перечисления должны быть степенями двух. Затем вы можете использовать [побитовые логические операторы `|` или `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators), чтобы комбинировать варианты выбора или пересекать комбинации вариантов выбора соответственно. Чтобы указать, что тип перечисления объявляет битовые поля, примените к нему атрибут [Flags](xref:System.FlagsAttribute). Как показано в следующем примере, вы также можете включить некоторые типичные комбинации в определение типа перечисления.

[!code-csharp[enum flags](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Flags)]

Дополнительные сведения и примеры см. на странице справочника по API <xref:System.FlagsAttribute?displayProperty=nameWithType> и в разделе о [неисключительных элементах и атрибутах Flags](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) страницы справочника по API <xref:System.Enum?displayProperty=nameWithType>.

## <a name="the-systemenum-type-and-enum-constraint"></a>Тип System.Enum и ограничение перечисления

Тип <xref:System.Enum?displayProperty=nameWithType> является абстрактным базовым классом всех типов перечисления. Он предоставляет различные методы, позволяющие получить информацию о типе перечисления и его значениях. Дополнительные сведения и примеры см. на странице справочника по API <xref:System.Enum?displayProperty=nameWithType>.

Начиная с C# версии 7.3, вы можете использовать тип `System.Enum` в ограничении базового класса (которое известно как [ограничение перечисления](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)), чтобы указать, что параметр типа является типом перечисления.

## <a name="conversions"></a>Преобразования

Для любого типа перечисления существуют явные преобразования между типом перечисления и его базовым целочисленным типом. Если вы [привели](../operators/type-testing-and-cast.md#cast-operator-) значение перечисления к его базовому типу, то результатом будет связанное целочисленное значение элемента перечисления.

[!code-csharp[enum conversions](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Conversions)]

Используйте метод <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>, чтобы определить, содержит ли тип перечисления элемент перечисления с определенным связанным значением.

Для любого типа перечисления существует [упаковка — преобразование и распаковка — преобразование](../../programming-guide/types/boxing-and-unboxing.md) в тип <xref:System.Enum?displayProperty=nameWithType> и из него соответственно.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Перечисления](~/_csharplang/spec/enums.md)
- [Значения перечислений и операции с ними](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [Enumeration logical operators](~/_csharplang/spec/expressions.md#enumeration-logical-operators) (Логические операторы перечисления)
- [Enumeration comparison operators](~/_csharplang/spec/expressions.md#enumeration-comparison-operators) (Операторы сравнения перечислений)
- [Explicit enumeration conversions](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions) (Явные преобразования перечислений)
- [Implicit enumeration conversions](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions) (Неявные преобразования перечислений)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Строки форматов перечисления](../../../standard/base-types/enumeration-format-strings.md)
- [Соглашения об именовании перечислений](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [Оператор switch](../keywords/switch.md)
