---
title: Справочник по C#. Оператор ||
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: f4bb7ada12fbcebcb90fb7cd22d6e6bccad5fb57
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244574"
---
# <a name="-operator-c-reference"></a>Оператор || (Справочник по C#)

Условный логический оператор ИЛИ `||`, также известный как "сокращенный" логический оператор ИЛИ, вычисляет логическое ИЛИ операндов типа [bool](../keywords/bool.md). Результат операции `x || y` принимает значение `true`, если хотя бы один из операторов `x` или `y` имеет значение `true`. В противном случае результат будет `false`. Если результатом первого операнда является значение `true`, второй операнд не вычисляется, и результат принимает значение `true`. В следующем примере продемонстрировано такое поведение.

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

[Логический оператор ИЛИ](or-operator.md) `|` также вычисляет логическое ИЛИ операндов типа `bool`, но он всегда вычисляет оба операнда.

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип не может перегружать условный логический оператор ИЛИ. Тем не менее, если определяемый пользователем тип каким-либо образом перегружает операторы [логическое OR](or-operator.md), [true и false](../keywords/true-false-operators.md), то операция `||` может быть применена для операндов этого типа. Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Условные логические операторы](~/_csharplang/spec/expressions.md#conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Оператор &&](conditional-and-operator.md)
- [Оператор !](logical-negation-operator.md)
- [Оператор |](or-operator.md)
