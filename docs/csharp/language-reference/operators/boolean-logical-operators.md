---
title: Логические операторы. Справочник по C#
description: Узнайте об операторах C#, которые выполняют такие логические операции, как отрицание, конъюнкция (И), а также инклюзивная и эксклюзивная дизъюнкция (ИЛИ), с использованием соответствующих операндов.
ms.date: 09/27/2019
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
ms.openlocfilehash: e355a89e27ea5bd6e4335b39c4e669610c4b0553
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319111"
---
# <a name="boolean-logical-operators-c-reference"></a>Логические операторы (справочник по C#)

Следующие операторы выполняют логические операции с использованием [логических](../keywords/bool.md) операндов:

- Унарный [`!` (логическое отрицание)](#logical-negation-operator-) оператор.
- Бинарные [`&` (логическое И)](#logical-and-operator-), [`|` (логическое ИЛИ)](#logical-or-operator-), а также [`^` (логическое исключающее ИЛИ)](#logical-exclusive-or-operator-) операторы. Эти операторы всегда обрабатывают оба операнда.
- Бинарные [`&&` (условное логическое И)](#conditional-logical-and-operator-) и [`||` (условное логическое ИЛИ)](#conditional-logical-or-operator-) операторы. Эти операторы вычисляют правый операнд, только если это необходимо.

Для операндов [целочисленных](../builtin-types/integral-numeric-types.md) типов операторы `&`, `|` и `^` выполняют побитовые логические операции. Дополнительные сведения см. в разделе [Побитовые операторы и операторы сдвига](bitwise-and-shift-operators.md).

## <a name="logical-negation-operator-"></a>Оператор логического отрицания !

Унарный префиксный оператор `!` выполняет логическое отрицание операнда, возвращая `true`, если операнд имеет значение `false`, и `false`, если операнд имеет значение `true`.

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

Начиная с C# 8.0, унарный постфиксный оператор `!` [допускает значение NULL](null-forgiving.md).

## <a name="logical-and-operator-"></a> Оператор логического И &amp;

Оператор `&` вычисляет логическое И для всех своих операндов. Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`. В противном случае результат будет `false`.

Оператор `&` вычисляет оба операнда, даже если левый операнд имеет значение `false` и результат должен принять значение `false`, независимо от значения правого операнда.

В следующем примере правый операнд оператора `&` является вызовом метода, который выполняется независимо от значения левого операнда:

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

[Условный оператор логического И](#conditional-logical-and-operator-) `&&` также вычисляет логическое И для своих операндов, но не вычисляет правый операнд, если левый операнд имеет значение `false`.

Для операндов целочисленного типа оператор `&` вычисляет [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) своих операндов. Унарный оператор `&` является оператором [AddressOf](pointer-related-operators.md#address-of-operator-).

## <a name="logical-exclusive-or-operator-"></a>Оператор логического исключения ИЛИ ^

Оператор `^` вычисляет логическое исключение ИЛИ для всех своих операндов, возвращая `true` для `x ^ y`, если `x` имеет значение `true` и `y` имеет значение `false` или `x` имеет значение `false` и `y` имеет значение `true`. В противном случае результат будет `false`. То есть для операндов `bool` оператор `^` возвращает тот же результат, что и [оператор неравенства](equality-operators.md#inequality-operator-) `!=`.

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

Для операндов целочисленного типа оператор `^` вычисляет [побитовое логическое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) своих операндов.

## <a name="logical-or-operator-"></a>Оператор логического ИЛИ |

Оператор `|` вычисляет логическое ИЛИ для всех своих операндов. Результат операции `x | y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`. В противном случае результат будет `false`.

Оператор `|` вычисляет оба операнда, даже если левый операнд имеет значение `true` и результат должен принять значение `true`, независимо от значения правого операнда.

В следующем примере правый операнд оператора `|` является вызовом метода, который выполняется независимо от значения левого операнда:

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

[Условный оператор логического ИЛИ](#conditional-logical-or-operator-) `||` также вычисляет логическое ИЛИ для своих операндов, но не вычисляет правый операнд, если левый операнд имеет значение `true`.

Для операндов целочисленного типа оператор `|` вычисляет [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) своих операндов.

## <a name="conditional-logical-and-operator-"></a> Условный оператор логического И &amp;&amp;

Условный оператор логического И `&&` (оператор короткого замыкания) вычисляет логическое И для своих операндов. Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`. В противном случае результат будет `false`. Если `x` имеет значение `false`, `y` не вычисляется.

В следующем примере правый операнд оператора `&&` является вызовом метода, который не выполняется, если левый операнд имеет значение `false`:

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

[Оператор логического И](#logical-and-operator-) `&` также вычисляет логическое И для своих операндов, но он всегда вычисляет оба операнда.

## <a name="conditional-logical-or-operator-"></a>Условный оператор логического ИЛИ ||

Условный оператор логического ИЛИ `||` (оператор короткого замыкания) вычисляет логическое ИЛИ для своих операндов. Результат операции `x || y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`. В противном случае результат будет `false`. Если `x` имеет значение `true`, `y` не вычисляется.

В следующем примере правый операнд оператора `||` является вызовом метода, который не выполняется, если левый операнд имеет значение `true`:

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

[Оператор логического ИЛИ](#logical-or-operator-) `|` также вычисляет логическое ИЛИ для своих операндов, но всегда вычисляет оба операнда.

## <a name="nullable-boolean-logical-operators"></a>Операторы, допускающие логическое значение NULL

Для операндов `bool?` операторы `&` и `|` поддерживают троичную логику. Семантика этих операторов определяется по следующей таблице:  
  
|п|y|x&y|x&#124;y|  
|----|----|----|----|  
|true|true|true|true|  
|true|Ложь|false|true|  
|true|null|null|true|  
|Ложь|true|Ложь|true|  
|Ложь|Ложь|Ложь|Ложь|  
|Ложь|null|Ложь|null|  
|null|true|null|true|  
|null|Ложь|Ложь|null|  
|null|null|null|null|  

Поведение этих операторов отличается от типичного поведения операторов, допускающих значение NULL. Как правило, оператор, который определяется для операндов типа значения, можно также использовать с соответствующими операндами типа, допускающего значение NULL. Такой оператор возвращает `null`, если какой-либо из операндов имеет значение `null`. При этом операторы `&` и `|` могут возвращать отличное от NULL значение, даже если один из операндов имеет значение `null`. См. подробнее о поведении [операторов](../../programming-guide/nullable-types/using-nullable-types.md#operators), допускающих значение NULL, в руководстве по [использованию типов, допускающих значение NULL](../../programming-guide/nullable-types/using-nullable-types.md).

Вы также можете также использовать операторы `!` и `^` с операндами `bool?`, как показано в следующем примере:

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

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

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

Условные логические операторы `&&` и `||` не поддерживают составное присваивание.

## <a name="operator-precedence"></a>Приоритет операторов

В следующем списке перечислены логические операторы в порядке убывания приоритета:

- Оператор логического отрицания `!`
- Оператор логического И `&`
- Оператор логического исключающего ИЛИ `^`
- Оператор логического ИЛИ `|`
- Условный оператор логического И `&&`
- Условный оператор логического ИЛИ `||`

Порядок вычисления, определяемый приоритетом операторов, можно изменить с помощью скобок (`()`).

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

Полный список операторов C#, упорядоченных по уровню приоритета, см. в статье [Операторы C#](index.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип может [перегружать](operator-overloading.md) операторы `!`, `&`, `|` и `^`. При перегрузке бинарного оператора соответствующий оператор составного присваивания также неявно перегружается. Определяемый пользователем тип не может перегружать оператор составного присваивания явным образом.

Определяемый пользователем тип не может перегружать условные логические операторы `&&` и `||`. При этом, если определяемый пользователем тип каким-либо образом перегружает операторы [true и false](true-false-operators.md) и операторы `&` и `|`, операция `&&` или `||` может быть применена для операндов этого типа. Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Оператор логического отрицания](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [Логические операторы](~/_csharplang/spec/expressions.md#logical-operators)
- [Условные логические операторы](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Побитовые операторы и операторы сдвига](bitwise-and-shift-operators.md)
