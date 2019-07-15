---
title: Перегрузка операторов — справочник по C#
description: Узнайте, как перегрузить оператор C# и какие операторы C# можно перегружать.
ms.date: 07/05/2019
f1_keywords:
- operator_CSharpKeyword
helpviewer_keywords:
- operator keyword [C#]
- operator overloading [C#]
ms.openlocfilehash: f9085f2a550dfacc670857a70f5b22de9e028107
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610597"
---
# <a name="operator-overloading-c-reference"></a>Перегрузка операторов (справочник по C#)

Определяемый пользователем тип может перегружать предопределенный оператор C#. То есть тип может указать пользовательскую реализацию операции, когда один или оба операнда принадлежат этому типу. В разделе [Перегружаемые операторы](#overloadable-operators) показано, какие операторы C# можно перегружать.

Для объявления оператора используйте ключевое слово `operator`. Объявление оператора должно соответствовать следующим правилам:

- Оно должно включать `public` и модификатор `static`.
- Унарный оператор принимает один параметр. Бинарный оператор принимает два параметра. В каждом случае хотя бы один параметр должен иметь тип `T` или `T?`, где `T` — тип, который содержит объявление оператора.

В следующем примере определяется упрощенная структура, представляющая рациональное число. Структура перегружает некоторые [арифметические операторы](arithmetic-operators.md):

[!code-csharp[fraction example](~/samples/csharp/language-reference/operators/OperatorOverloading.cs)]

## <a name="overloadable-operators"></a>Перегружаемые операторы

Следующая таблица содержит сведения о возможности перегрузки операторов C#:

| Операторы | Возможность перегрузки |
| --------- | --------------- |
|[+](arithmetic-operators.md#unary-plus-and-minus-operators), [-](arithmetic-operators.md#unary-plus-and-minus-operators), [!](boolean-logical-operators.md#logical-negation-operator-), [~](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](arithmetic-operators.md#increment-operator-), [--](arithmetic-operators.md#decrement-operator---), [true](true-false-operators.md), [false](true-false-operators.md)|Эти унарные операторы могут быть перегружены.|
|[+](addition-operator.md), [-](subtraction-operator.md), [\*](arithmetic-operators.md#multiplication-operator-), [/](arithmetic-operators.md#division-operator-), [%](arithmetic-operators.md#remainder-operator-), [&](boolean-logical-operators.md#logical-and-operator-), [&#124;](boolean-logical-operators.md#logical-or-operator-), [^](boolean-logical-operators.md#logical-exclusive-or-operator-), [\<\<](bitwise-and-shift-operators.md#left-shift-operator-), [>>](bitwise-and-shift-operators.md#right-shift-operator-), [==](equality-operators.md#equality-operator-), [!=](equality-operators.md#inequality-operator-), [\<](comparison-operators.md#less-than-operator-), [>](comparison-operators.md#greater-than-operator-), [\<=](comparison-operators.md#less-than-or-equal-operator-), [>=](comparison-operators.md#greater-than-or-equal-operator-)|Эти бинарные операторы могут быть перегружены. Некоторые операторы должны перегружаться парами; дополнительные сведения см. в примечаниях после этой таблицы.|
|[&&](boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](boolean-logical-operators.md#conditional-logical-or-operator-)|Условный логический оператор не может быть перегружен. При этом, если тип с перегруженными [операторами `true` и `false`](true-false-operators.md) также перегружает оператор `&` или <code>&#124;</code>, оператор `&&` или <code>&#124;&#124;</code>, соответственно, может быть применен для операндов этого типа. Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).|
|[&#91;&#93;](member-access-operators.md#indexer-operator-)|Доступ к элементам не считается перегружаемым оператором, но вы можете определить [индексатор](../../programming-guide/indexers/index.md).|
|[(T)x](type-testing-and-conversion-operators.md#cast-operator-)|Оператор приведения типов не может быть перегружен, но можно определить новые операторы преобразования (см. [explicit](../keywords/explicit.md) и [implicit](../keywords/implicit.md)).|
|[+=](arithmetic-operators.md#compound-assignment), [-=](arithmetic-operators.md#compound-assignment), [\*=](arithmetic-operators.md#compound-assignment), [/=](arithmetic-operators.md#compound-assignment), [%=](arithmetic-operators.md#compound-assignment), [&=](boolean-logical-operators.md#compound-assignment), [&#124;=](boolean-logical-operators.md#compound-assignment), [^=](boolean-logical-operators.md#compound-assignment), [\<\<=](bitwise-and-shift-operators.md#compound-assignment), [>>=](bitwise-and-shift-operators.md#compound-assignment)|Составные операторы присваивания не могут быть перегружены явным образом. Однако при перегрузке бинарного оператора соответствующий составной оператор присваивания (если таковой имеется) также неявно перегружается. Например, `+=` вычисляется с помощью `+`, который может быть перегружен.|
|[=](assignment-operator.md), [.](member-access-operators.md#member-access-operator-), [?:](conditional-operator.md), [??](null-coalescing-operator.md), [->](pointer-related-operators.md#pointer-member-access-operator--), [=>](lambda-operator.md), [f(x)](member-access-operators.md#invocation-operator-), [as](type-testing-and-conversion-operators.md#as-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md), [is](type-testing-and-conversion-operators.md#is-operator), [nameof](../keywords/nameof.md), [new](new-operator.md), [sizeof](../keywords/sizeof.md), [typeof](type-testing-and-conversion-operators.md#typeof-operator)|Эти операторы не могут быть перегружены.|

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
- [Почему перегруженные операторы всегда являются статическими в C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
