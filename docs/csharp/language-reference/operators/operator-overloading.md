---
title: Перегрузка операторов — справочник по C#
description: Узнайте, как перегрузить оператор C# и какие операторы C# можно перегружать.
ms.date: 07/05/2019
f1_keywords:
- operator_CSharpKeyword
helpviewer_keywords:
- operator keyword [C#]
- operator overloading [C#]
ms.openlocfilehash: 04c8731867e32ce1000a511c9ab36db554664a97
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73038955"
---
# <a name="operator-overloading-c-reference"></a>Перегрузка операторов (справочник по C#)

Определяемый пользователем тип может перегружать предопределенный оператор C#. То есть тип может указать пользовательскую реализацию операции, если один или оба операнда принадлежат этому типу. В разделе [Перегружаемые операторы](#overloadable-operators) показано, какие операторы C# можно перегружать.

Для объявления оператора используйте ключевое слово `operator`. Объявление оператора должно соответствовать следующим правилам:

- Оно должно включать `public` и модификатор `static`.
- У унарного оператора один входной параметр. У бинарного оператора два входных параметра. В каждом случае хотя бы один параметр должен иметь тип `T` или `T?`, где `T` — тип, который содержит объявление оператора.

В следующем примере определяется упрощенная структура, представляющая рациональное число. Структура перегружает некоторые [арифметические операторы](arithmetic-operators.md):

[!code-csharp[fraction example](~/samples/csharp/language-reference/operators/OperatorOverloading.cs)]

Вы можете расширить предыдущий пример, [определив неявное преобразование](user-defined-conversion-operators.md) из `int` в `Fraction`. Затем перегруженные операторы будут поддерживать аргументы этих двух типов. То есть можно будет добавить целое число к дроби и получить дробь.

Можно также использовать ключевое слово `operator` для определения пользовательского преобразования типа. Дополнительные сведения см. в разделе [Операторы пользовательского преобразования](user-defined-conversion-operators.md).

## <a name="overloadable-operators"></a>Перегружаемые операторы

Следующая таблица содержит сведения о возможности перегрузки операторов C#:

| Операторы | Возможность перегрузки |
| --------- | --------------- |
|[+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](arithmetic-operators.md#increment-operator-), [--](arithmetic-operators.md#decrement-operator---), [true](true-false-operators.md), [false](true-false-operators.md)|Эти унарные операторы могут быть перегружены.|
|[x + y](addition-operator.md), [x - y](subtraction-operator.md), [x \* y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-), [x & y](boolean-logical-operators.md#logical-and-operator-), [x &#124; y](boolean-logical-operators.md#logical-or-operator-), [x ^ y](boolean-logical-operators.md#logical-exclusive-or-operator-), [x \<\< y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-), [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-), [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-)|Эти бинарные операторы могут быть перегружены. Некоторые операторы должны перегружаться парами; дополнительные сведения см. в примечаниях после этой таблицы.|
|[x && y](boolean-logical-operators.md#conditional-logical-and-operator-), [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-)|Условный логический оператор не может быть перегружен. При этом, если тип с перегруженными [операторами `true` и `false`](true-false-operators.md) также перегружает оператор `&` или <code>&#124;</code>, оператор `&&` или <code>&#124;&#124;</code>, соответственно, может быть применен для операндов этого типа. Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).|
|[a&#91;i&#93;](member-access-operators.md#indexer-operator-)|Доступ к элементам не считается перегружаемым оператором, но вы можете определить [индексатор](../../programming-guide/indexers/index.md).|
|[(T)x](type-testing-and-cast.md#cast-operator-)|Оператор приведения типов не может быть перегружен, но можно определить новые операторы преобразования. Дополнительные сведения см. в разделе [Операторы пользовательского преобразования](user-defined-conversion-operators.md).|
|[+=](arithmetic-operators.md#compound-assignment), [-=](arithmetic-operators.md#compound-assignment), [\*=](arithmetic-operators.md#compound-assignment), [/=](arithmetic-operators.md#compound-assignment), [%=](arithmetic-operators.md#compound-assignment), [&=](boolean-logical-operators.md#compound-assignment), [&#124;=](boolean-logical-operators.md#compound-assignment), [^=](boolean-logical-operators.md#compound-assignment), [\<\<=](bitwise-and-shift-operators.md#compound-assignment), [>>=](bitwise-and-shift-operators.md#compound-assignment)|Составные операторы присваивания не могут быть перегружены явным образом. Однако при перегрузке бинарного оператора соответствующий составной оператор присваивания (если таковой имеется) также неявно перегружается. Например, `+=` вычисляется с помощью `+`, который может быть перегружен.|
|[^x](member-access-operators.md#index-from-end-operator-), [x = y](assignment-operator.md), [x.y](member-access-operators.md#member-access-operator-), [c ? t : f](conditional-operator.md), [x ?? y](null-coalescing-operator.md), [x ??= y](null-coalescing-operator.md), [x..y](member-access-operators.md#range-operator-), [x->y](pointer-related-operators.md#pointer-member-access-operator--), [=>](lambda-operator.md), [f(x)](member-access-operators.md#invocation-operator-), [as](type-testing-and-cast.md#as-operator), [await](await.md), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [delegate](delegate-operator.md), [is](type-testing-and-cast.md#is-operator), [nameof](nameof.md), [new](new-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [typeof](type-testing-and-cast.md#typeof-operator)|Эти операторы не могут быть перегружены.|

> [!NOTE]
> Операторы сравнения должны перегружаться парами. То есть при перегрузке оператора из пары другой оператор тоже должен перегружаться. Ниже приведены эти пары:
>
> - Операторы `==` и `!=`
> - Операторы `<` и `>`
> - Операторы `<=` и `>=`

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Перегрузка операторов](~/_csharplang/spec/expressions.md#operator-overloading)
- [Инструкции](~/_csharplang/spec/classes.md#operators)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Операторы пользовательского преобразования](user-defined-conversion-operators.md)
- [Почему перегруженные операторы всегда являются статическими в C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
