---
title: Оператор &amp;=. Справочник по C#
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 223d2f30ee77457e1f9d5304ec299517932499d0
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237029"
---
# <a name="amp-operator-c-reference"></a>Оператор &amp;= (справочник по C#)

Оператор присваивания И.

Выражение, использующее оператор `&=`, такое как

```csharp
x &= y
```

эквивалентно

```csharp
x = x & y
```

за исключением того, что `x` вычисляется только один раз.

Для целочисленных операндов [`&`оператор ](and-operator.md) вычисляет побитовую логическую операцию И; для операндов типа [bool](../keywords/bool.md) оператор вычисляет логическую операцию И.

В следующем примере иллюстрируется использование оператора `&=`.

[!code-csharp-interactive[AND assignment example](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#AndAssignmentExample)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор `&`](and-operator.md), то оператор присваивания И `&=` неявно перегружается. Определяемый пользователем тип не может перегружать оператор присваивания И явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
