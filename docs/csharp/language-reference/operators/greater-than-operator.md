---
title: '> Оператор. Справочник по C#'
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 3b036c491d9663bf4ab0971d84a0a8d58d902ee6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287213"
---
# <a name="-operator-c-reference"></a>Оператор > (Справочник по C#)

Оператор отношения "больше" `>` возвращает `true`, если его первый операнд больше второго. В противном случае возвращается `false`. Оператор `>` поддерживают все числовые типы и типы перечисления. Если операнды имеют одинаковый тип [enum](../keywords/enum.md), сравниваются соответствующие значения базового целочисленного типа.

> [!NOTE]
> Если для операторов отношения `==`, `>`, `<`, `>=` и `<=` любой из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результат операции имеет значение `false`. Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`). Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.

В следующем примере иллюстрируется использование оператора `>`.

[!code-csharp-interactive[greater than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Greater)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `>`. Если тип перегружает оператор "больше" `>`, он также должен перегружать [оператор "меньше"](less-than-operator.md) `<`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Оператор >=](greater-than-equal-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
