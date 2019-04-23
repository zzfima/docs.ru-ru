---
title: Справочник по C#. Логические операторы
description: Узнайте об операторах C#, которые выполняют такие логические операции, как отрицание, конъюнкция (И), а также инклюзивная и эксклюзивная дизъюнкция (ИЛИ), с использованием соответствующих операндов.
ms.date: 04/08/2019
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: de621b26334bbc9679ba7e48a9d5a0cbaec67eab
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427322"
---
# <a name="boolean-logical-operators-c-reference"></a>Справочник по C#. Логические операторы

Следующие операторы выполняют логические операции с использованием [логических](../keywords/bool.md) операндов:

- Унарный [`!` (логическое отрицание)](#logical-negation-operator-) оператор.
- Бинарные [`&` (логическое И)](#logical-and-operator-), [`|` (логическое ИЛИ)](#logical-or-operator-), а также [`^` (логическое исключающее ИЛИ)](#logical-exclusive-or-operator-) операторы. Эти операторы всегда обрабатывают оба операнда.
- Бинарные [`&&` (условное логическое И)](#conditional-logical-and-operator-) и [`||` (условное логическое ИЛИ)](#conditional-logical-or-operator-) операторы. Эти операторы вычисляют второй операнд, только если это необходимо.

Для операндов типа [integral](../keywords/integral-types-table.md) операторы `&`, `|` и `^` выполняют побитовые логические операции.

## <a name="logical-negation-operator-"></a>Оператор логического отрицания !

Оператор `!` выполняет логическое отрицание операнда, возвращая `true`, если операнд имеет значение `false`, и `false`, если операнд имеет значение `true`.

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a>Оператор логического И &amp;

Оператор `&` вычисляет логическое И для всех своих операндов. Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`. В противном случае результат будет `false`.

Оператор `&` вычисляет оба операнда, даже если первый операнд имеет значение `false` и результат должен принять значение `false`, независимо от значения второго операнда.

В следующем примере второй операнд оператора `&` является вызовом метода, который выполняется независимо от значения первого операнда:

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

[Условный оператор логического И](#conditional-logical-and-operator-) `&&` также вычисляет логическое И для своих операндов, но он не вычисляет второй операнд, если первый операнд имеет значение `false`.

Для операндов оператор типа integral оператор `&` выполняет [побитовое вычисление логического И](and-operator.md#integer-logical-bitwise-and-operator). Унарный оператор `&` является оператором [AddressOf](and-operator.md#unary-address-of-operator).

## <a name="logical-exclusive-or-operator-"></a>Оператор логического исключения ИЛИ ^

Оператор `^` вычисляет логическое исключение ИЛИ для всех своих операндов, возвращая `true` для `x ^ y`, если `x` имеет значение `true` и `y` имеет значение `false` или `x` имеет значение `false` и `y` имеет значение `true`. В противном случае результат будет `false`. То есть для операндов `bool` оператор `^` возвращает тот же результат, что и [оператор неравенства](equality-operators.md#inequality-operator-) `!=`.

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

Для операндов типа integral оператор `^` выполняет [побитовое вычисление исключающего логического ИЛИ](xor-operator.md).

## <a name="logical-or-operator-"></a>Оператор логического ИЛИ |

Оператор `|` вычисляет логическое ИЛИ для всех своих операндов. Результат операции `x | y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`. В противном случае результат будет `false`.

Оператор `|` вычисляет оба операнда, даже если первый операнд имеет значение `true` и результат должен принять значение `true`, независимо от значения второго операнда.

В следующем примере второй операнд оператора `|` является вызовом метода, который выполняется независимо от значения первого операнда:

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

[Условный оператор логического ИЛИ](#conditional-logical-or-operator-) `||` также вычисляет логическое ИЛИ для своих операндов, но не вычисляет второй операнд, если первый операнд имеет значение `true`.

Для операндов типа integral оператор `|` выполняет [побитовое вычисление логического ИЛИ](or-operator.md).

## <a name="conditional-logical-and-operator-ampamp"></a>Условный оператор логического И &amp;&amp;

Условный оператор логического И `&&` (оператор короткого замыкания) вычисляет логическое И для своих операндов. Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`. В противном случае результат будет `false`. Если результатом первого операнда является значение `false`, второй операнд не вычисляется.

В следующем примере второй операнд оператора `&&` является вызовом метода, который не выполняется, если первый операнд имеет значение `false`:

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

[Оператор логического И](#logical-and-operator-) `&` также вычисляет логическое И для своих операндов, но он всегда вычисляет оба операнда.

## <a name="conditional-logical-or-operator-"></a>Условный оператор логического ИЛИ ||

Условный оператор логического ИЛИ `||` (оператор короткого замыкания) вычисляет логическое ИЛИ для своих операндов. Результат операции `x || y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`. В противном случае результат будет `false`. Если результатом первого операнда является значение `true`, второй операнд не вычисляется.

В следующем примере второй операнд оператора `||` является вызовом метода, который не выполняется, если первый операнд имеет значение `true`:

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

[Оператор логического ИЛИ](#logical-or-operator-) `|` также вычисляет логическое ИЛИ для своих операндов, но всегда вычисляет оба операнда.

## <a name="nullable-boolean-logical-operators"></a>Операторы, допускающие логическое значение NULL

Для операндов `bool?` операторы `&` и `|` поддерживают троичную логику. Семантика этих операторов определяется по следующей таблице:  
  
|x|y|x&y|x&#124;y|  
|----|----|----|----|  
|true|true|true|true|  
|true|False|false|true|  
|true|null|null|true|  
|False|true|False|true|  
|False|False|False|False|  
|False|null|False|null|  
|null|true|null|true|  
|null|False|False|null|  
|null|null|null|null|  

Поведение этих операторов отличается от типичного поведения операторов, допускающих значение NULL. Как правило, оператор, который определяется для операндов типа значения, можно также использовать с соответствующими операндами типа, допускающего значение NULL. Такой оператор возвращает `null`, если какой-либо из операндов имеет значение `null`. При этом операторы `&` и `|` могут возвращать отличное от NULL значение, даже если один из операндов имеет значение `null`. См. подробнее о поведении [операторов](../../programming-guide/nullable-types/using-nullable-types.md#operators), допускающих значение NULL, в руководстве по [использованию типов, допускающих значение NULL](../../programming-guide/nullable-types/using-nullable-types.md).

Вы также можете также использовать операторы `!` и `^` с операндами `bool?`, как показано в следующем примере:

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

Условные логические операторы `&&` и `||` не поддерживают операнды типа `bool?`.

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

Операторы `&`, `|` и `^` поддерживают составное присваивание, как показано в следующем примере:

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

Условные логические операторы `&&` и `||` не поддерживают составное присваивание.

## <a name="operator-precedence"></a>Приоритет операторов

В следующем списке перечислены логические операторы в порядке убывания приоритета:

- Оператор логического отрицания: `!`
- Логический оператор AND `&`
- Оператор исключающего логического ИЛИ `^`
- Логический оператор ИЛИ `|`
- Условный оператор логического И `&&`
- Условный оператор логического ИЛИ `||`

Порядок вычисления, определяемый приоритетом операторов, можно изменить с помощью скобок (`()`).

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

Полный список операторов C#, упорядоченных по уровню приоритета, см. в статье [Операторы C#](index.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип может [перегружать](../keywords/operator.md) операторы `!`, `&`, `|` и `^`. При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается. Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.

Определяемый пользователем тип не может перегружать условные логические операторы `&&` и `||`. При этом, если определяемый пользователем тип каким-либо образом перегружает операторы [true и false](../keywords/true-false-operators.md) и операторы `&` и `|`, операция `&&` или `||` может быть применена для операндов этого типа. Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Оператор логического отрицания:](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [Логические операторы](~/_csharplang/spec/expressions.md#logical-operators)
- [Условные логические операторы](~/_csharplang/spec/expressions.md#conditional-logical-operators)

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы C#](index.md)
