---
title: Операторы сравнения. Справочник по C#
description: Дополнительные сведения об операторах сравнения C#, которые можно использовать для проверки очередности числовых значений.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: bb28e2adba896ae85b189858283376fbe3250dce
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039070"
---
# <a name="comparison-operators-c-reference"></a>Операторы сравнения (справочник по C#)

Операторы сравнения [`<` (меньше чем)](#less-than-operator-), [`>` (больше чем)](#greater-than-operator-), [`<=` (меньше или равно)](#less-than-or-equal-operator-) и [`>=` (больше или равно)](#greater-than-or-equal-operator-) (или реляционные операторы) сравнивают операнды. Эти операторы поддерживаются всеми [целочисленными](../builtin-types/integral-numeric-types.md) типами и типами с [плавающей запятой](../builtin-types/floating-point-numeric-types.md).

> [!NOTE]
> Если какой-то из операндов операторов `==`, `<`, `>`, `<=` и `>=` не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результатом операции будет `false`. Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`), включая `NaN`. Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.

Типы перечисления также поддерживают операторы сравнения. Если операнды имеют одинаковый тип [enum](../keywords/enum.md), сравниваются соответствующие значения базового целочисленного типа.

Операторы [`==` и `!=`](equality-operators.md) проверяют равенство или неравенство своих операндов.

## <a name="less-than-operator-"></a>Оператор "меньше чем" \<

Оператор `<` возвращает `true`, если его левый операнд меньше правого. В противном случае возвращается `false`:

[!code-csharp-interactive[less than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a>Оператор "больше чем" >

Оператор `>` возвращает `true`, если его левый операнд больше правого. В противном случае возвращается `false`:

[!code-csharp-interactive[greater than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a>Оператор "меньше или равно" \<=

Оператор `<=` возвращает `true`, если его левый операнд меньше правого или равен ему. В противном случае возвращается `false`:

[!code-csharp-interactive[less than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a>Оператор "больше или равно" >=

Оператор `>=` возвращает `true`, если его левый операнд больше правого или равен ему. В противном случае возвращается `false`:

[!code-csharp-interactive[greater than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип может [перегружать](operator-overloading.md) операторы `<`, `>`, `<=` и `>=`.

Если тип перегружает один из операторов `<` и `>`, он должен также перегружать операторы `<` и `>`. Если тип перегружает один из операторов `<=` и `>=`, он должен также перегружать операторы `<=` и `>=`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [Операторы равенства](equality-operators.md)
