---
title: Справочник по C#. Операторы true и false
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: b1acf9a16dd977ec49a7f1dc3bea4ee41792e9be
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758141"
---
# <a name="true-and-false-operators-c-reference"></a>Справочник по C#. Операторы true и false

Оператор `true` возвращает [логическое](../keywords/bool.md) значение `true`, указывая, что операнд имеет значение true. Оператор `false` возвращает значение `bool` `true`, указывая, что операнд имеет значение false. Операторы `true` и `false` не обязательно дополняют друг друга. То есть оба оператора `true` и `false` могут вернуть значение `bool` `false` для одного операнда. Если тип определяет один из двух операторов, он должен также определять другой оператор.

Если тип с определенными операторами `true` и `false` [перегружает](../keywords/operator.md) логические операторы [OR](boolean-logical-operators.md#logical-or-operator-) `|` или [AND](boolean-logical-operators.md#logical-and-operator-) `&` определенным образом, [условные логические операторы OR](boolean-logical-operators.md#conditional-logical-or-operator-) `||` или [AND](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` соответственно могут вычисляться для операндов этого типа. Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](~/_csharplang/spec/introduction.md).

Тип с определенным оператором `true` может быть типом результата управляющего условного выражения в операторах [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md) и [for](../keywords/for.md) и [условном операторе`?:`](conditional-operator.md). Дополнительные сведения см. в описании [логических выражений](~/_csharplang/spec/expressions.md#boolean-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

> [!TIP]
> Используйте тип `bool?`, если вам нужно использовать трехзначную логику, например при работе с базами данных, которые поддерживают трехзначный логический тип. В C# предоставляются операторы `&` и `|`, которые поддерживают троичную логику с операндами `bool?`. См. подробнее о [логических операторах, поддерживающих значение NULL](boolean-logical-operators.md#nullable-boolean-logical-operators) в описании [логических операторов](boolean-logical-operators.md).

В следующем примере представлен тип, который определяет операторы `true` и `false`. Кроме того, он перегружает логический оператор AND `&` таким образом, что оператор `&&` также может быть вычислен для операндов этого типа.

[!code-csharp[true and false operators example](~/samples/csharp/language-reference/operators/TrueFalseOperators.cs)]

Обратите внимание на поведение сокращенного вычисления оператора `&&`. Когда метод `GetFuelLaunchStatus` возвращает `LaunchStatus.Red`, второй операнд оператора `&&` не вычисляется. Это обусловлено тем, что `LaunchStatus.Red` имеет значение false. Результат логического оператора AND не зависит от значения второго операнда. Выходные данные примера могут быть следующими:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Литерал `true`](../keywords/true-literal.md)
- [Литерал `false`](../keywords/false-literal.md)
