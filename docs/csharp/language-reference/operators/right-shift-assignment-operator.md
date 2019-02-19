---
title: '>>Оператор = — справочник по C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 51914bb5e9ebffd5d868528b5a8d3072a956cea6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220917"
---
# <a name="-operator-c-reference"></a>Оператор >>= (справочник по C#)

Оператор присваивания сдвига вправо.

Выражение, использующее оператор `>>=`, такое как

```csharp
x >>= y
```

эквивалентно

```csharp
x = x >> y
```

за исключением того, что `x` вычисляется только один раз.

[Оператор `>>`](right-shift-operator.md) сдвигает первый операнд вправо на число битов, определяемое вторым операндом.

В следующем примере иллюстрируется использование оператора `>>=`.

[!code-csharp-interactive[right shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftAssignment)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор `>>`](right-shift-operator.md), то оператор присваивания сдвига вправо `>>=` неявно перегружается. Пользовательский тип не может перегружать оператор присваивания сдвига вправо явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) в [Спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)