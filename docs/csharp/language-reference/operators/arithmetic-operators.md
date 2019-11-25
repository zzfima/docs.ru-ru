---
title: Арифметические операторы. Справочник по C#
description: Сведения об операторах C#, выполняющих операции умножения, деления, вычисления остатка, сложения и вычитания с числовыми типами.
ms.date: 03/27/2019
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: ca2513a0f865fd7da728f7d3247bdb7b50a2f48a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036431"
---
# <a name="arithmetic-operators-c-reference"></a>Арифметические операторы (справочник по C#)

Следующие операторы выполняют арифметические операции с операндами числовых типов:

- унарные — [`++` (приращение)](#increment-operator-), [`--` (уменьшение)](#decrement-operator---), [`+` (плюс)](#unary-plus-and-minus-operators) и [`-` (минус)](#unary-plus-and-minus-operators);
- бинарные — [`*` (умножение)](#multiplication-operator-), [`/` (деление)](#division-operator-), [`%` (остаток от деления)](#remainder-operator-), [`+` (сложение)](#addition-operator-) и [`-` (вычитание)](#subtraction-operator--).

Эти операторы поддерживаются всеми [целочисленными](../builtin-types/integral-numeric-types.md) типами и типами с [плавающей запятой](../builtin-types/floating-point-numeric-types.md).

## <a name="increment-operator-"></a>Оператор инкремента ++

Оператор инкремента `++` увеличивает операнд на 1. Операндом должна быть переменная, [свойство](../../programming-guide/classes-and-structs/properties.md) или [индексатор](../../programming-guide/indexers/index.md).

Оператор инкремента поддерживается в двух формах: постфиксный оператор инкремента (`x++`) и префиксный оператор инкремента (`++x`).

### <a name="postfix-increment-operator"></a>Постфиксный оператор приращения

Результатом `x++` является значение `x` *перед* выполнением операции, как показано в следующем примере:

[!code-csharp-interactive[postfix increment](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a>Префиксный оператор инкремента

Результатом `++x` является значение `x` *после* выполнения операции, как показано в следующем примере:

[!code-csharp-interactive[prefix increment](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a>Оператор декремента --

Унарный оператор декремента `--` уменьшает операнд на 1. Операндом должна быть переменная, [свойство](../../programming-guide/classes-and-structs/properties.md) или [индексатор](../../programming-guide/indexers/index.md).

Оператор декремента поддерживается в двух формах: постфиксный оператор декремента (`x--`) и префиксный оператор декремента (`--x`).

### <a name="postfix-decrement-operator"></a>Постфиксный оператор уменьшения

Результатом `x--` является значение `x` *перед* выполнением операции, как показано в следующем примере:

[!code-csharp-interactive[postfix decrement](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a>Префиксный оператор декремента

Результатом `--x` является значение `x` *после* выполнения операции, как показано в следующем примере:

[!code-csharp-interactive[prefix decrement](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a>Операторы унарного плюса и минуса

Унарный оператор `+` возвращает значение полученного операнда. Унарный оператор `-` изменяет знак операнда на противоположный.

[!code-csharp-interactive[unary plus and minus](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#UnaryPlusAndMinus)]

Тип [ulong](../builtin-types/integral-numeric-types.md) не поддерживает унарный оператор `-`.

## <a name="multiplication-operator-"></a>Оператор умножения *

Оператор умножения `*` вычисляет произведение операндов:

[!code-csharp-interactive[multiplication operator](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#Multiplication)]

Унарный оператор `*` представляет собой [оператор косвенного обращения к указателю](pointer-related-operators.md#pointer-indirection-operator-).

## <a name="division-operator-"></a>Оператор деления /

Оператор деления `/` делит левый операнд на правый.

### <a name="integer-division"></a>Деление целых чисел

Для операндов цельночисленных типов результат оператора `/` является целочисленным типом, который равен частному двух операндов, округленному в сторону нуля:

[!code-csharp-interactive[integer division](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerDivision)]

Чтобы получить частное двух операндов в виде числа с плавающей запятой, используйте тип `float`, `double` или `decimal`:

[!code-csharp-interactive[integer as floating-point division](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a>Деление чисел с плавающей запятой

Для типов `float`, `double` и `decimal` результатом оператора `/` является частное двух операндов:

[!code-csharp-interactive[floating-point division](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointDivision)]

Если один из операндов — это `decimal`, второй операнд не может быть ни `float`, ни `double`, так как ни `float`, ни `double` не преобразуется неявно в тип `decimal`. Необходимо явным образом преобразовать операнд `float` или `double` в тип `decimal`. Дополнительные сведения о числовых преобразованиях см. в разделе [Встроенные числовые преобразования](../builtin-types/numeric-conversions.md).

## <a name="remainder-operator-"></a>Оператор остатка %

Оператор остатка `%` вычисляет остаток от деления левого операнда на правый.

### <a name="integer-remainder"></a>Целочисленный остаток

Для целочисленных операндов результатом `a % b` является значение, произведенное `a - (a / b) * b`. Знак ненулевого остатка такой же, как и у левого операнда, как показано в следующем примере:

[!code-csharp-interactive[integer remainder](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerRemainder)]

Используйте метод <xref:System.Math.DivRem%2A?displayProperty=nameWithType> для вычисления результатов как целочисленного деления, так и определения остатка.

### <a name="floating-point-remainder"></a>Остаток с плавающей запятой

Для операндов типа `float` и `double` результатом `x % y` для конечных `x` и `y` будет значение `z`, так что:

- знак `z`, если отлично от нуля, совпадает со знаком `x`;
- абсолютное значение `z` является значением, произведенным `|x| - n * |y|`, где `n` — это наибольшее возможное целое число, которое меньше или равно `|x| / |y|`, а `|x|` и `|y|` являются абсолютными значениями `x` и `y`, соответственно.

> [!NOTE]
> Этот метод вычисления остатка аналогичен тому, который использовался для целочисленных операндов, но отличается от спецификации IEEE 754. Если вам нужна операция вычисления остатка, которая соответствует спецификации IEEE 754, используйте метод <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.

Сведения о поведение оператора `%` в случае неконечных операндов см. в разделе [Оператор остатка](~/_csharplang/spec/expressions.md#remainder-operator) [спецификации языка C#](~/_csharplang/spec/introduction.md).

Для операндов `decimal` оператор остатка `%` эквивалентен [оператору остатка](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) типа <xref:System.Decimal?displayProperty=nameWithType>.

В следующем примере показано поведение оператора остатка для операндов с плавающей запятой:

[!code-csharp-interactive[floating-point remainder](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a>Оператор сложения +

Оператор сложения `+` вычисляет сумму своих операндов:

[!code-csharp-interactive[addition operator](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#Addition)]

Кроме того, оператор `+` можно использовать для объединения строк и делегатов. Дополнительные сведения см. в статье [Операторы `+` и `+=`](addition-operator.md).

## <a name="subtraction-operator--"></a>Оператор вычитания -

Оператор вычитания `-` вычитает правый операнд из левого:

[!code-csharp-interactive[subtraction operator](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#Subtraction)]

Кроме того, оператор `-` можно использовать для удаления делегатов. Дополнительные сведения см. в статье [Операторы `-` и `-=`](subtraction-operator.md).

## <a name="compound-assignment"></a>Составное присваивание

Для бинарного оператора `op` выражение составного присваивания в форме

```csharp
x op= y
```

эквивалентно

```csharp
x = x op y
```

за исключением того, что `x` вычисляется только один раз.

Следующий пример иллюстрирует использование составного присваивания с арифметическими операторами:

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#CompoundAssignment)]

Из-за [восходящих приведений](~/_csharplang/spec/expressions.md#numeric-promotions) результат операции `op` может быть невозможно неявно преобразовать в тип `T` из `x`. В этом случае, если `op` является предопределенным оператором, и результат операции является явно преобразуемым в тип `T` `x`, выражение составного присваивания формы `x op= y` эквивалентно `x = (T)(x op y)`, за исключением того, что `x` вычисляется только один раз. В следующем примере продемонстрировано такое поведение.

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

Вы также можете использовать операторы `+=` и `-=` для подписки и отмены подписки на [события](../keywords/event.md) соответственно. Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-precedence-and-associativity"></a>Приоритет и ассоциативность операторов

В следующем списке перечислены арифметические операторы в порядке убывания приоритета:

- Постфиксный инкремент `x++` и декремент `x--`
- Префиксный инкремент `++x` и декремент `--x`, унарные операторы `+` и `-`
- Мультипликативные операторы `*`, `/`, и `%`
- Аддитивные операторы `+` и `-`

Бинарные арифметические операторы имеют левую ассоциативность. То есть операторы с одинаковым приоритетом вычисляются в направлении слева направо.

Порядок вычисления, определяемый приоритетом и ассоциативностью операторов, можно изменить с помощью скобок (`()`).

[!code-csharp-interactive[precedence and associativity](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

Полный список операторов C#, упорядоченный по уровню приоритета, можно найти в разделе [Приоритет операторов](index.md#operator-precedence) статьи [Операторы C#](index.md).

## <a name="arithmetic-overflow-and-division-by-zero"></a>Арифметическое переполнение и деление на нуль

Если результат арифметической операции выходит за пределы диапазона возможных конечных значений соответствующего числового типа, поведение арифметического оператора зависит от типа его операндов.

### <a name="integer-arithmetic-overflow"></a>Целочисленное арифметическое переполнение

Деление целого числа на ноль всегда вызывает исключение <xref:System.DivideByZeroException>.

В случае целочисленного арифметического переполнения итоговое поведение определяется контекстом проверки переполнения, который может быть [проверяемым или непроверяемым](../keywords/checked-and-unchecked.md):

- Если в проверяемом контексте переполнение возникает в константном выражении, происходит ошибка времени компиляции. В противном случае, если операция производится во время выполнения, возникает исключение <xref:System.OverflowException>.
- В непроверяемом контексте результат усекается путем удаления старших разрядов, которые не помещаются в целевой тип данных.

Вместе с [проверяемыми и непроверяемыми](../keywords/checked-and-unchecked.md) операторами вы можете использовать операторы `checked` и `unchecked`, чтобы управлять контекстом проверки переполнения, в котором вычисляется выражение:

[!code-csharp-interactive[checked and unchecked](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#CheckedUnchecked)]

По умолчанию арифметические операции выполняются в *непроверяемом* контексте.

### <a name="floating-point-arithmetic-overflow"></a>Арифметическое переполнение с плавающей запятой

Арифметические операции с типами `float` и `double` никогда не вызывают исключение. Результатом арифметических операций с этими типами может быть одно из специальных значений, представляющих бесконечность и объект, не являющийся числовым:

[!code-csharp-interactive[double non-finite values](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointOverflow)]

Для операндов типа `decimal` арифметическое переполнение всегда вызывает исключение <xref:System.OverflowException>, а деление на нуль всегда вызывает исключение <xref:System.DivideByZeroException>.

## <a name="round-off-errors"></a>Ошибки округления

Из-за общих ограничений, касающихся представления вещественных чисел в форме с плавающей запятой и арифметических операций с плавающей запятой, при вычислениях с использованием типов с плавающей запятой могут возникать ошибки округления. То есть полученный результат выражения может отличаться от ожидаемого математического результата. В следующем примере показано несколько таких случаев:

[!code-csharp-interactive[round-off errors](~/samples/csharp/language-reference/operators/ArithmeticOperators.cs#RoundOffErrors)]

См. заметки в справочной документации по [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) и [System.Decimal](/dotnet/api/system.decimal#remarks).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип может [перегружать](operator-overloading.md) унарные (`++`, `--`, `+` и `-`) и бинарные (`*`, `/`, `%`, `+` и `-`) арифметические операторы. При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается. Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Постфиксные операторы инкремента и декремента](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [Префиксные операторы инкремента и декремента](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [Оператор унарного плюса](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [Оператор унарного минуса](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [Оператор умножения](~/_csharplang/spec/expressions.md#multiplication-operator)
- [Оператор деления](~/_csharplang/spec/expressions.md#division-operator)
- [Оператор остатка](~/_csharplang/spec/expressions.md#remainder-operator)
- [Оператор сложения](~/_csharplang/spec/expressions.md#addition-operator)
- [Оператор вычитания](~/_csharplang/spec/expressions.md#subtraction-operator)
- [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment)
- [Операторы checked и unchecked](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [Восходящие приведения числовых типов](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [Числовые значения в .NET](../../../standard/numerics.md)
