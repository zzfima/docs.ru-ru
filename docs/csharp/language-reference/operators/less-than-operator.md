---
title: Оператор &lt;. Справочник по C#
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: bb0f590bb547c4e632bd14c773f095435c8986f0
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655950"
---
# <a name="lt-operator-c-reference"></a>Оператор &lt; (справочник по C#)

Оператор отношения "меньше" `<` возвращает `true`, если его первый операнд меньше второго. В противном случае возвращается `false`. Оператор `<` поддерживают все числовые типы и типы перечисления. Если операнды имеют одинаковый тип [enum](../keywords/enum.md), сравниваются соответствующие значения базового целочисленного типа.

> [!NOTE]
> Если для операторов отношения `==`, `>`, `<`, `>=` и `<=` любой из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результат операции имеет значение `false`. Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`). Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.

В следующем примере иллюстрируется использование оператора `<`.

[!code-csharp-interactive[less than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Less)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `<`. Если тип перегружает оператор "меньше" `<`, он также должен перегружать [оператор "больше"](greater-than-operator.md) `>`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Оператор <=](less-than-equal-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
