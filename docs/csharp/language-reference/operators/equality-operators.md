---
title: Операторы равенства. Справочник по C#
description: Из этой статьи вы узнаете об операторах сравнения на равенство и типах равенства в C#.
ms.date: 06/26/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 7dd3e544dc03fb94577892b42aecd1a15a6621ac
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80110923"
---
# <a name="equality-operators-c-reference"></a>Операторы равенства (справочник по C#)

Операторы [`==` (равенство)](#equality-operator-) и [`!=` (неравенство)](#inequality-operator-) проверяют равенство или неравенство своих операндов.

## <a name="equality-operator-"></a>Оператор равенства ==

Оператор равенства `==` возвращает значение `true`, если его операнды равны. В противном случае возвращается значение `false`.

### <a name="value-types-equality"></a>Равенство типов значений

Операнды [встроенных типов значений](../builtin-types/value-types.md#built-in-value-types) равны, если равны их значения.

[!code-csharp-interactive[value types equality](snippets/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> У операторов `==`, [`<`, `>`, `<=` и `>=`](comparison-operators.md), если какой-то из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результатом операции является `false`. Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`), включая `NaN`. Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.

Два операнда одного типа [enum](../builtin-types/enum.md) равны, если равны соответствующие значения базового целочисленного типа.

По умолчанию пользовательские типы [struct](../builtin-types/struct.md) не поддерживают оператор `==`. Чтобы поддерживать оператор `==`, пользовательская структура должна [перегружать](operator-overloading.md) его.

Начиная с версии C# 7.3 операторы `==` и `!=` поддерживаются [кортежами](../../tuples.md) C#. Дополнительные сведения см. в разделе [Равенство и кортежи](../../tuples.md#equality-and-tuples) статьи [Типы кортежей в C#](../../tuples.md).

### <a name="reference-types-equality"></a>Равенство ссылочных типов

По умолчанию два операнда ссылочного типа являются равными, если они ссылаются на один и тот же объект:

[!code-csharp[reference type equality](snippets/EqualityOperators.cs#ReferenceTypesEquality)]

Как показано в примере, определяемые пользователем ссылочные типы поддерживают оператор `==` по умолчанию. Однако ссылочный тип может перегружать оператор `==`. Если ссылочный тип перегружает оператор `==`, воспользуйтесь методом <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>, чтобы проверить, что две ссылки этого типа указывают на один и тот же объект.

### <a name="string-equality"></a>Равенство строк

Два операнда [string](../builtin-types/reference-types.md#the-string-type) равны, если они оба имеют значение `null` или оба экземпляра строки имеют одинаковую длину и идентичные символы в каждой позиции символа.

[!code-csharp-interactive[string equality](snippets/EqualityOperators.cs#StringEquality)]

Это порядковое сравнение, учитывающее регистр. Дополнительные сведения о том, как сравнивать строки, см. в статье [Сравнение строк в C#](../../how-to/compare-strings.md).

### <a name="delegate-equality"></a>Равенство делегатов

Два операнда [delegate](../../programming-guide/delegates/index.md) одного типа среды выполнения равны, если оба из них имеют значение `null` или их списки вызовов имеют одинаковую длину и содержат одинаковые записи в каждой позиции:

[!code-csharp-interactive[delegate equality](snippets/EqualityOperators.cs#DelegateEquality)]

Подробные сведения см. в разделе [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) (Операторы равенства делегатов) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

Делегаты, созданные в результате оценки семантически идентичных [лямбда-выражений](../../programming-guide/statements-expressions-operators/lambda-expressions.md) не будут равны, как показано в примере ниже:

[!code-csharp-interactive[from identical lambdas](snippets/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a>Оператор неравенства !=

Оператор неравенства `!=` возвращает значение `true`, если его операнды не равны. В противном случае возвращается значение `false`. Для операндов [встроенных типов](../builtin-types/built-in-types.md) выражение `x != y` дает тот же результат, что и выражение `!(x == y)`. Дополнительные сведения о равенстве типов см. в разделе [Оператор равенства](#equality-operator-).

В следующем примере иллюстрируется использование оператора `!=`.

[!code-csharp-interactive[non-equality examples](snippets/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип может [перегружать](operator-overloading.md) операторы `==` и `!=`. Если тип перегружает один из двух операторов, он должен также перегружать и другой.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [Сравнения на равенство](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [Операторы сравнения](comparison-operators.md)
