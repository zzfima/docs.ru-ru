---
title: Операторы C# — справочник по C#
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 13ad16ab768cdaee96cab29811e2ed058dee977a
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512241"
---
# <a name="c-operators-c-reference"></a>Операторы C# (справочник по C#)

C# предоставляет ряд стандартных операторов, поддерживаемых встроенными типами. Например [арифметические операторы](arithmetic-operators.md) выполняют арифметические операции с операндами встроенных числовых типов, а [логические операторы](boolean-logical-operators.md) выполняют логические операции с операндами [bool](../keywords/bool.md).

Определяемый пользователем тип может перегружать некоторые операторы для определения соответствующего поведения операндов этого типа. Для получения дополнительной информации см. раздел [Перегрузка операторов](operator-overloading.md).

В следующих разделах перечислены операторы C# в порядке убывания приоритета. Операторы в каждом разделе совместно используют один и тот же уровень приоритета.

## <a name="primary-operators"></a>Основные операторы

Это операторы с наивысшим приоритетом.

[x.y](member-access-operators.md#member-access-operator-) — доступ к членам.

[x?.y](member-access-operators.md#null-conditional-operators--and-) — доступ к членам с проверкой NULL. Возвращает значение `null`, если левый операнд имеет значение `null`.

[x?[y]](member-access-operators.md#null-conditional-operators--and-) — условный доступ к элементу массива или индексатору типов со значением NULL. Возвращает значение `null`, если левый операнд имеет значение `null`.

[f(x)](member-access-operators.md#invocation-operator-) — вызов метода или делегата.

[&#91;x&#93; ](member-access-operators.md#indexer-operator-) — доступ к элементу массива или индексатору типов.

[x++](arithmetic-operators.md#increment-operator-) — постфиксный инкремент. Возвращает значение x и затем обновляет расположение хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).

[x--](arithmetic-operators.md#decrement-operator---) — постфиксный декремент. Возвращает значение x и затем обновляет расположение хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).

[new](new-operator.md) – создание экземпляра типа.

[typeof](type-testing-and-conversion-operators.md#typeof-operator) — возвращает объект <xref:System.Type>, представляющий операнд.

[checked](../keywords/checked.md) — включает проверку на переполнение при выполнении операций с целыми числами.

[unchecked](../keywords/unchecked.md) — отключает проверку на переполнение при выполнении операций с целыми числами. Это поведение установлено для компилятора по умолчанию.

[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) — создает значение типа T по умолчанию.

[nameof](nameof.md) — используется для получения простого (неполного) имени переменной, типа или члена в виде строковой константы.

[delegate](delegate-operator.md) — объявляет и возвращает экземпляр делегата.

[sizeof](sizeof.md) — возвращает размер в байтах для типа операнда.

[stackalloc](stackalloc.md) — выделяет блок памяти в стеке.

[->](pointer-related-operators.md#pointer-member-access-operator--) — косвенное обращение к указателю в сочетании с доступом к члену.

## <a name="unary-operators"></a>Унарные операторы

Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[+x](addition-operator.md) — возвращает значение x.

[-x](subtraction-operator.md) — числовое отрицание.

[\!x](boolean-logical-operators.md#logical-negation-operator-) — логическое отрицание.

[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) — поразрядное дополнение.

[++x](arithmetic-operators.md#increment-operator-) — префиксный инкремент. Возвращает значение x после обновления расположения хранения значением x, которое увеличено на единицу (обычно добавляется целочисленное значение 1).

[--x](arithmetic-operators.md#decrement-operator---) — префиксный декремент. Возвращает значение x после обновления расположения хранения значением x, которое уменьшено на единицу (обычно вычитается целочисленное значение 1).

[(T)x](type-testing-and-conversion-operators.md#cast-operator-) — приведение типов.

[await`Task` — ожидание выполнения ](../keywords/await.md).

[&x](pointer-related-operators.md#address-of-operator-) — адрес переменной.

[*x](pointer-related-operators.md#pointer-indirection-operator-) — косвенное обращение к указателю или разыменование.

[Оператор true](true-false-operators.md) — возвращает [логическое](../keywords/bool.md) значение `true`, указывая, что операнд имеет значение true.

[Оператор false](true-false-operators.md) — возвращает [логическое](../keywords/bool.md) значение `true`, указывая, что операнд имеет значение false.

## <a name="multiplicative-operators"></a>Мультипликативные операторы

Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[x * y](arithmetic-operators.md#multiplication-operator-) — умножение.

[x / y](arithmetic-operators.md#division-operator-) — деление. Если операнды имеют целые числа, результатом является целочисленное значение, усеченное в сторону нуля (например, `-7 / 2 is -3`).

[x % y](arithmetic-operators.md#remainder-operator-) — остаток. Если операнды имеют целые числа, это возвращает остаток от деления x на y.  Если `q = x / y` и `r = x % y`, то `x = q * y + r`.

## <a name="additive-operators"></a>Аддитивные операторы

Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[x + y](arithmetic-operators.md#addition-operator-) — сложение.

[x – y](arithmetic-operators.md#subtraction-operator--) — вычитание.

## <a name="shift-operators"></a>Операторы сдвига

Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[x <\< y](bitwise-and-shift-operators.md#left-shift-operator-) — сдвиг битов влево и заполнение правого бита нулем.

[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) — сдвиг битов вправо. Если левым операндом является `int` или `long`, затем левые биты заполняются битом знака. Если левым операндом является `uint` или `ulong`, затем левые биты заполняются нулем.

## <a name="relational-and-type-testing-operators"></a>Относительные операторы и операторы тестирования типа

Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[x \< y](comparison-operators.md#less-than-operator-) — меньше чем (возвращает true, если x меньше y).

[x > ](comparison-operators.md#greater-than-operator-) — больше чем (возвращает true, если x больше y).

[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – меньше или равно

[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – больше или равно.

[is](type-testing-and-conversion-operators.md#is-operator) — совместимость типов. Возвращает значение `true`, если вычисленный левый операнд может быть приведен к типу, заданному правым операндом.

[as](type-testing-and-conversion-operators.md#as-operator) — преобразование типов. Возвращает левый операнд, приведенный к типу, заданному правым операндом, но `as` возвращает `null`, где `(T)x` вызывает исключение.

## <a name="equality-operators"></a>Операторы равенства

Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[x == y](equality-operators.md#equality-operator-) — тождество. По умолчанию для ссылочных типов, отличных от `string`, этот оператор возвращает равенство ссылок (проверка удостоверения). Однако типы могут перегрузить `==`, поэтому если планируется проверять удостоверения, лучше использовать метод `ReferenceEquals` для `object`.

[x != y](equality-operators.md#inequality-operator-) — неравенство. См. примечание для `==`. Если тип перегружает `==`, то его необходимо перегрузить `!=`.

## <a name="logical-and-operator"></a>Логический оператор AND

Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

`x & y` — [логическое И](boolean-logical-operators.md#logical-and-operator-) для операндов `bool` или [побитовое логическое И](bitwise-and-shift-operators.md#logical-and-operator-) для операндов целочисленных типов.

## <a name="logical-xor-operator"></a>Оператор логического исключающего ИЛИ

Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

`x ^ y` — [логическое исключающее ИЛИ](boolean-logical-operators.md#logical-exclusive-or-operator-) для операндов `bool` или [побитовое логическое исключающее ИЛИ](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) для операндов целочисленных типов.

## <a name="logical-or-operator"></a>Логический оператор ИЛИ

Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

`x | y` — [логическое ИЛИ](boolean-logical-operators.md#logical-or-operator-) для операндов `bool` или [побитовое логическое ИЛИ](bitwise-and-shift-operators.md#logical-or-operator-) для операндов целочисленных типов.

## <a name="conditional-and-operator"></a>Условный оператор И

Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) — логическое И. Если `x` имеет значение `false`, тогда `y` не вычисляется.

## <a name="conditional-or-operator"></a>Условный оператор ИЛИ

Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) — логическое ИЛИ. Если `x` имеет значение `true`, тогда `y` не вычисляется.

## <a name="null-coalescing-operator"></a>Оператор объединения с NULL

Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[x ?? y](null-coalescing-operator.md) — возвращает `x`, если значение отличается от `null`; в противном случае возвращает `y`.

## <a name="conditional-operator"></a>Условный оператор

Этот оператор имеет более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[t ? x : y](conditional-operator.md) — если условие `t` имеет значение true, вычисляет и возвращает `x`, в противном случае вычисляет и возвращает `y`.

## <a name="assignment-and-lambda-operators"></a>Операторы назначения и лямбда-операторы

Эти операторы имеют более высокий приоритет по сравнению со следующим разделом и более низкий приоритет по сравнению с предыдущим.

[x = y](assignment-operator.md) — назначение.

[x += y](arithmetic-operators.md#compound-assignment) — инкремент. Добавьте значение `y` к значению `x`, сохраните результат в `x` и возвратите новое значение. Если `x` назначает [событие](../keywords/event.md), то `y` должен быть соответствующим методом, который C# добавляет в качестве обработчика событий.

[x -= y](arithmetic-operators.md#compound-assignment) — декремент. Вычтите значение `y` из значения `x`, сохраните результат в `x` и возвратите новое значение. Если `x` назначает [событие](../keywords/event.md), то `y` должен быть соответствующим методом, который C# удаляет в качестве обработчика событий.

[x *= y](arithmetic-operators.md#compound-assignment) — назначение с умножением. Умножьте значение `y` на значение `x`, сохраните результат в `x` и возвратите новое значение.

[x /= y](arithmetic-operators.md#compound-assignment) — назначение с делением. Разделите значение `x` на значение `y`, сохраните результат в `x` и возвратите новое значение.

[x %= y](arithmetic-operators.md#compound-assignment) — присваивание остатка. Разделите значение `x` на значение `y`, сохраните остаток в `x` и возвратите новое значение.

[x &= y](boolean-logical-operators.md#compound-assignment) — назначение с операцией И. Выполните операцию И для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.

[x &#124;= y](boolean-logical-operators.md#compound-assignment) — назначение с операцией ИЛИ. Выполните операцию ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.

[x ^= y](boolean-logical-operators.md#compound-assignment) — назначение с операцией исключающего ИЛИ. Выполните операцию исключающего ИЛИ для значения `y` и значения `x`, сохраните результат в `x` и возвратите новое значение.

[x <<= ](bitwise-and-shift-operators.md#compound-assignment) — назначение со сдвигом влево. Сдвиньте значение `x` влево на `y` позиций, сохраните результат в `x` и возвратите новое значение.

[x >>= y](bitwise-and-shift-operators.md#compound-assignment) — назначение со сдвигом вправо. Сдвиньте значение `x` вправо на `y` позиций, сохраните результат в `x` и возвратите новое значение.

[=>](lambda-operator.md) — объявление лямбда-выражения.

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Инструкции](../../programming-guide/statements-expressions-operators/operators.md)
