---
title: Оператор &gt;=. Справочник по C#
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 34437742d33cff97e53c6dfb163df083e80d41f3
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655937"
---
# <a name="gt-operator-c-reference"></a>Оператор &gt;= (справочник по C#)

Оператор отношения "больше или равно" `>=` возвращает `true`, если его первый операнд больше или равен второму. В противном случае возвращается `false`. Оператор `>=` поддерживают все числовые типы и типы перечисления. Если операнды имеют одинаковый тип [enum](../keywords/enum.md), сравниваются соответствующие значения базового целочисленного типа.

> [!NOTE]
> Если для операторов отношения `==`, `>`, `<`, `>=` и `<=` любой из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результат операции имеет значение `false`. Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`). Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.

В следующем примере иллюстрируется использование оператора `>=`.

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `>=`. Если тип перегружает оператор "больше или равно" `>=`, он также должен перегружать [оператор "меньше или равно"](less-than-equal-operator.md) `<=`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Оператор >](greater-than-operator.md)
- [Оператор ==](equality-comparison-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
