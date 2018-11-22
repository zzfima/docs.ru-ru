---
title: Оператор &amp;&amp; (справочник по C#)
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: d0e6d9a5aedc7dc87393e3dea070bf442b3268dc
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "43529239"
---
# <a name="ampamp-operator-c-reference"></a>Оператор &amp;&amp; (справочник по C#)

Условный логический оператор И `&&`, также известный как "сокращенный" логический оператор И, вычисляет логическое И операндов типа [bool](../keywords/bool.md). Результат операции `x && y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`. В противном случае результат будет `false`. Если результатом первого операнда является значение `false`, второй операнд не вычисляется, и результат принимает значение `false`. В следующем примере продемонстрировано такое поведение.

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

[Логический оператор И](and-operator.md) `&` также вычисляет логическое И операндов типа `bool`, но он всегда вычисляет оба операнда.

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип не может перегружать условный логический оператор И. Тем не менее, если определяемый пользователем тип каким-либо образом перегружает операторы [логическое И](and-operator.md), [true](../keywords/true-operator.md) и [false](../keywords/false-operator.md), то операция `&&` может быть применена для операндов этого типа. Дополнительные сведения см. в разделе [Пользовательские условные логические операторы](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Условные логические операторы](~/_csharplang/spec/expressions.md#conditional-logical-operators) в [Спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Оператор ||](conditional-or-operator.md)
- [Оператор \!](logical-negation-operator.md)
- [Оператор &](and-operator.md)
