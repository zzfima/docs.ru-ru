---
title: Операторы C# — справочник по C#
ms.date: 08/20/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- operators [C#]
- operator precedence [C#]
- operator associativity [C#]
- expressions [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 11c544e7fc923b0820141fb2e096ef7707f0a95f
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552478"
---
# <a name="c-operators-c-reference"></a>Операторы C# (справочник по C#)

C# предоставляет ряд операторов, поддерживаемых встроенными типами. Например [арифметические операторы](arithmetic-operators.md) выполняют арифметические операции с числовыми операндами, а [логические операторы](boolean-logical-operators.md) выполняют логические операции с операндами [bool](../builtin-types/bool.md). Большинство операторов могут быть [перегружены](operator-overloading.md). С помощью перегрузки операторов можно указать поведение оператора для операндов определяемого пользователем типа.

В [выражении](../../programming-guide/statements-expressions-operators/expressions.md) приоритет и ассоциативность операторов определяют порядок выполнения операций. Порядок вычисления, определяемый приоритетом и ассоциативностью операторов, можно изменить с помощью скобок.

## <a name="operator-precedence"></a>Приоритет операторов

В выражении с несколькими операторами операторы с более высоким приоритетом оцениваются до операторов с более низким приоритетом. В следующем примере умножение выполняется сначала, так как оно имеет более высокий приоритет, чем сложение:

```csharp-interactive
var a = 2 + 2 * 2;
Console.WriteLine(a); //  output: 6
```

Используйте скобки, чтобы изменить порядок вычисления, накладываемый приоритетом операторов:

```csharp-interactive
var a = (2 + 2) * 2;
Console.WriteLine(a); //  output: 8
```

В следующей таблице перечислены операторы C# в порядке убывания приоритета. Операторы в каждой строке имеют одинаковый приоритет.

| Операторы | Категория или имя |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-operator-), [x?.y](member-access-operators.md#null-conditional-operators--and-), [x?[y]](member-access-operators.md#null-conditional-operators--and-), [f(x)](member-access-operators.md#invocation-operator-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [new](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--) | Первичный |
| [+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [^x](member-access-operators.md#index-from-end-operator-), [(T)x](type-testing-and-cast.md#cast-operator-), [await](await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true и false](true-false-operators.md) | Унарный |
| [x..y](member-access-operators.md#range-operator-) | Диапазон |
| [x * y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-) | Мультипликативный|
| [x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--) | Аддитивный |
| [x \<\< y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | Сдвиг |
| [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-cast.md#is-operator), [as](type-testing-and-cast.md#as-operator) | Тестирование типов и относительный |
| [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-) | Равенство |
| `x & y` | [Логическое И](boolean-logical-operators.md#logical-and-operator-) или [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [Логическое исключающее ИЛИ](boolean-logical-operators.md#logical-exclusive-or-operator-) или [побитовое логическое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [Логическое ИЛИ](boolean-logical-operators.md#logical-or-operator-) или [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | Условное И |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | Условное ИЛИ |
| [x ?? y](null-coalescing-operator.md) | Оператор объединения с NULL |
| [c ? t : f](conditional-operator.md) | Условный оператор |
| [x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x *= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [x ??= y](null-coalescing-operator.md), [=>](lambda-operator.md) | Назначение и объявление лямбда-выражений |

## <a name="operator-associativity"></a>Ассоциативность операторов

Если операторы имеют одинаковый приоритет, порядок их выполнения определяется ассоциативностью операторов:

- Операторы с *левой ассоциативностью* вычисляются слева направо. За исключением [операторов присваивания](assignment-operator.md) и [оператора объединения со значением NULL](null-coalescing-operator.md), все бинарные операторы имеют левую ассоциативность. Например, выражение `a + b - c` вычисляется как `(a + b) - c`.
- Операторы с *правой ассоциативностью* вычисляются справа налево. Операторы присваивания, оператор объединения со значением NULL и [условный оператор `?:`](conditional-operator.md) имеют правую ассоциативность. Например, выражение `x = y = z` вычисляется как `x = (y = z)`.

Используйте скобки, чтобы изменить порядок вычисления, накладываемый ассоциативностью операторов:

```csharp-interactive
int a = 13 / 5 / 2;
int b = 13 / (5 / 2);
Console.WriteLine($"a = {a}, b = {b}");  // output: a = 1, b = 6
```

## <a name="operand-evaluation"></a>Вычисление операнда

Не связанные с приоритетом и ассоциативностью операторов операнды в выражении вычисляются слева направо. В следующих примерах иллюстрируется порядок вычисления операторов и операндов:

| Выражение | Порядок вычислений |
| ---------- | ------------------- |
|`a + b`|a, b, +|
|`a + b * c`|a, b, c, *, +|
|`a / b + c * d`|a, b, /, c, d, *, +|
|`a / (b + c) * d`|a, b, c, +, /, d, *|

Как правило, оцениваются все операнды операторов. Однако некоторые операторы оценивают операнды условно. То есть значение крайнего левого операнда такого оператора определяет, следует ли оценивать другие операнды. Эти операторы являются условными логическими операторами [И (`&&`)](boolean-logical-operators.md#conditional-logical-and-operator-) и [ИЛИ (`||`) ](boolean-logical-operators.md#conditional-logical-or-operator-), [операторами объединения со значением NULL`??` и `??=`](null-coalescing-operator.md), [условными операторами со значением NULL `?.` и `?[]` и ](member-access-operators.md#null-conditional-operators--and-)[условным оператором `?:`](conditional-operator.md). Дополнительные сведения см. в описании каждого оператора.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы](~/_csharplang/spec/expressions.md#operators) статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Выражения](../../programming-guide/statements-expressions-operators/expressions.md)
