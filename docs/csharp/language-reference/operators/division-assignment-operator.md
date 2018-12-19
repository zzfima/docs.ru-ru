---
title: Справочник по C#. Оператор /=
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286524"
---
# <a name="-operator-c-reference"></a>Оператор /= (Справочник по C#)

Оператор присваивания деления.

Выражение, использующее оператор `/=`, такое как

```csharp
x /= y
```

эквивалентно

```csharp
x = x / y
```

за исключением того, что `x` вычисляется только один раз.

[Оператор деления](division-operator.md) (`/`) делит первый операнд на второй. Он поддерживается всеми числовыми типами данных.

В следующем примере иллюстрируется использование оператора `/=`.

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Если пользовательский тип [перегружает](../keywords/operator.md) [оператор деления](division-operator.md) `/`, оператор присваивания деления `/=` неявно перегружается. Пользовательский тип не может перегружать оператор присваивания деления явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
