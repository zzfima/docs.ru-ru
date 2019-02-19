---
title: Оператор <<= — справочник по C#
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: d2105fbee4ddfe1b2cb3325d82b0f2f8c5559297
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219455"
---
# <a name="-operator-c-reference"></a>Справочник по C#. Оператор \<\<=

Оператор присваивания сдвига влево.

Выражение, использующее оператор `<<=`, такое как

```csharp
x <<= y
```

эквивалентно

```csharp
x = x << y
```

за исключением того, что `x` вычисляется только один раз.

[Оператор `<<`](left-shift-operator.md) сдвигает первый операнд влево на число битов, определяемое вторым операндом.

В следующем примере иллюстрируется использование оператора `<<=`.

[!code-csharp-interactive[left shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftAssignment)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор `<<`](left-shift-operator.md), то оператор присваивания сдвига влево `<<=` неявно перегружается. Пользовательский тип не может перегружать оператор присваивания сдвига влево явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
