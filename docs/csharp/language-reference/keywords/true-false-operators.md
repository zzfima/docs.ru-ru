---
title: Справочник по C#. Операторы true и false
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 0a75566fdb6222157ecda12a50fd78e22f92fcb4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245735"
---
# <a name="true-and-false-operators-c-reference"></a>Справочник по C#. Операторы true и false

Оператор `true` возвращает [логическое](bool.md) значение `true`, указывая, что операнд имеет значение true. Оператор `false` возвращает значение `bool` `true`, указывая, что операнд имеет значение false. Операторы `true` и `false` не обязательно дополняют друг друга. То есть оба оператора `true` и `false` могут вернуть значение `bool` `false` для одного операнда. Если тип определяет один из двух операторов, он должен также определять другой оператор.

Если тип с определенными операторами `true` и `false` [перегружает](operator.md) логические операторы [OR](../operators/or-operator.md) `|` или [AND](../operators/and-operator.md) `&` определенным образом, [условные логические операторы OR](../operators/conditional-or-operator.md) `||` или [AND](../operators/conditional-and-operator.md) `&&` соответственно могут вычисляться для операндов этого типа. Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).

Тип с определенным оператором `true` может быть типом результата управляющего условного выражения в операторах [if](if-else.md), [do](do.md), [while](while.md) и [for](for.md) и [условном операторе`?:`](../operators/conditional-operator.md). Дополнительные сведения см. в описании [логических выражений](~/_csharplang/spec/expressions.md#boolean-expressions) в [спецификации языка C#](../language-specification/index.md).

> [!TIP]
> Используйте тип `bool?`, если вам нужно поддерживать трехзначную логику, например при работе с базами данных, которые поддерживают трехзначный логический тип. Дополнительные сведения см. в описании [типа bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) в руководстве по [использованию типов, допускающих значение NULL](../../programming-guide/nullable-types/using-nullable-types.md).

В следующем примере представлен тип, который определяет операторы `true` и `false`. Кроме того, он перегружает логический оператор AND `&` таким образом, что оператор `&&` также может быть вычислен для операндов этого типа.

[!code-csharp-interactive[true and false operators example](~/samples/snippets/csharp/keywords/TrueFalseOperatorsExample.cs)]

Обратите внимание на поведение сокращенного вычисления оператора `&&`. Когда метод `GetFuelLaunchStatus` возвращает `LaunchStatus.Red`, второй операнд оператора `&&` не вычисляется. Это обусловлено тем, что `LaunchStatus.Red` имеет значение false. Результат логического оператора AND не зависит от значения второго операнда. Выходные данные примера могут быть следующими:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Операторы в C#](../operators/index.md)
- [Литерал `true`](true-literal.md)
- [Литерал `false`](false-literal.md)