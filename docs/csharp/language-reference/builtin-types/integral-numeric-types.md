---
title: Справочник по C#. Целочисленные типы
description: Сведения о диапазоне значений, размере занимаемой памяти и способах использования каждого из целочисленных типов.
ms.date: 10/22/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: 394a809a9a2f45f4aee652d0eca892f62f0f2e54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093205"
---
# <a name="integral-numeric-types--c-reference"></a>Целочисленные типы (справочник по C#)

*Целочисленные типы* представляют целые числа. Все целочисленные типы являются [типами значений](value-types.md). Они также представляют собой [простые типы](value-types.md#built-in-value-types) и могут быть инициализированы [литералами](#integer-literals). Все целочисленные типы поддерживают [арифметические](../operators/arithmetic-operators.md) операторы, [побитовые логические](../operators/bitwise-and-shift-operators.md) операторы, операторы [сравнения](../operators/comparison-operators.md) и [равенства](../operators/equality-operators.md).

## <a name="characteristics-of-the-integral-types"></a>Характеристики целочисленных типов

C# поддерживает следующие предварительно определенные целочисленные типы:

|Ключевое слово или тип C#|Диапазон|Размер|Тип .NET|
|----------|-----------|----------|-------------|
|`sbyte`|От -128 до 127|8-разрядное целое число со знаком|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|От 0 до 255|8-разрядное целое число без знака|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|От -32 768 до 32 767|16-разрядное целое число со знаком|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|От 0 до 65 535|16-разрядное целое число без знака|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|От -2 147 483 648 до 2 147 483 647|32-разрядное целое число со знаком|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|От 0 до 4 294 967 295|32-разрядное целое число без знака|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|От -9 223 372 036 854 775 808 до 9 223 372 036 854 775 807|64-разрядное целое число со знаком|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|От 0 до 18 446 744 073 709 551 615|64-разрядное целое число без знака|<xref:System.UInt64?displayProperty=nameWithType>|

В приведенной выше таблице каждый тип ключевого слова C# из крайнего левого столбца является псевдонимом для соответствующего типа .NET. Они взаимозаменяемые. Например, следующие объявления объявляют переменные одного типа:

```csharp
int a = 123;
System.Int32 b = 123;
```

По умолчанию все целочисленные типы имеют значение `0`. Все целочисленные типы имеют константы `MinValue` и `MaxValue` с минимальным и максимальными итоговыми значениями этого типа.

Используйте структуру <xref:System.Numerics.BigInteger?displayProperty=nameWithType>, чтобы представить целое число со знаком без верхней и нижней границ.

## <a name="integer-literals"></a>Целочисленные литералы

Целочисленные литералы могут быть:

- *десятичным числом*: без префикса;
- *шестнадцатеричным числом*: с префиксом `0x` или `0X`;
- *двоичными*: с префиксом `0b` или `0B` (доступно в C# 7.0 и более поздних версиях).

В приведенном ниже коде показан пример каждого из них.

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

В предыдущем примере также показано использование `_` в качестве *цифрового разделителя*, который поддерживается, начиная с версии C# 7.0. Цифровой разделитель можно использовать со всеми видами числовых литералов.

Тип целочисленного литерала определяется его суффиксом следующим образом:

- Если литерал не имеет суффикса, его типом будет первый из следующих типов, в котором может быть представлено его значение: `int`, `uint`, `long`, `ulong`.
- Если у литерала есть суффикс `U` или `u`, его типом будет первый из следующих типов, в котором может быть представлено его значение: `uint`, `ulong`.
- Если у литерала есть суффикс `L` или `l`, его типом будет первый из следующих типов, в котором может быть представлено его значение: `long`, `ulong`.

  > [!NOTE]
  > Строчную букву `l` можно использовать в качестве суффикса. Однако при этом выдается предупреждение компилятора, так как букву `l` можно перепутать с цифрой `1`. Для ясности используйте `L`.

- Если у литерала есть суффикс `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` или `lu`, его тип — `ulong`.

Если значение, представленное целочисленным литералом, превышает <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, происходит ошибка компиляции [CS1021](../../misc/cs1021.md).

Если определенный тип целочисленного литерала — `int`, а значение, представленное литералом, находится в диапазоне целевого типа, значение можно неявно преобразовать в `sbyte`, `byte`, `short`, `ushort`, `uint` или `ulong`:

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

Как показано в предыдущем примере, если значение литерала выходит за пределы диапазона целевого типа, возникает ошибка компилятора [CS0031](../../misc/cs0031.md).

Можно также использовать приведение для преобразования значения, представленного целочисленным литералом, в тип, отличный от определенного типа литерала.

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a>Преобразования

Любой целочисленный тип можно преобразовать в любой другой целочисленный тип. Если целевой тип может хранить все значения исходного типа, преобразование является неявным. В противном случае используйте [оператор приведения `()`](../operators/type-testing-and-cast.md#cast-operator-) для вызова явного преобразования. Для получения дополнительной информации см. статью [Встроенные числовые преобразования](numeric-conversions.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Целочисленные типы](~/_csharplang/spec/types.md#integral-types)
- [Целочисленные литералы](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Типы значений](value-types.md)
- [Типы с плавающей запятой](floating-point-numeric-types.md)
- [Строки стандартных числовых форматов](../../../standard/base-types/standard-numeric-format-strings.md)
- [Числовые значения в .NET](../../../standard/numerics.md)
