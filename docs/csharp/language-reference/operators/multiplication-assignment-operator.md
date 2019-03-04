---
title: Справочник по C#. Оператор *=
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967390"
---
# <a name="-operator-c-reference"></a>Оператор \*= (справочник по C#)

Оператор присваивания умножения.

Выражение, использующее оператор `*=`, такое как

```csharp
x *= y
```

эквивалентно

```csharp
x = x * y
```

за исключением того, что `x` вычисляется только один раз.

Для числовых типов [оператор \*](multiplication-operator.md) вычисляет результат двух операндов.

В следующем примере иллюстрируется использование оператора `*=`.

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор умножения](multiplication-operator.md) `*`, оператор присваивания умножения `*=` неявно перегружается. Определяемый пользователем тип не может перегружать оператор присваивания умножения явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
