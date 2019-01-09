---
title: Справочник по C#. Оператор ==
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: 6d86348eefc87e847267f262141ff49e5d51faae
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655963"
---
# <a name="-operator-c-reference"></a>Оператор == (справочник по C#)

Оператор равенства `==` возвращает значение `true`, если его операнды равны. В противном случае возвращается значение `false`.

## <a name="value-types-equality"></a>Равенство типов значений

Операнды [встроенных типов значений](../keywords/value-types-table.md) равны, если равны их значения.

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> Если для операторов отношения `==`, `>`, `<`, `>=` и `<=` любой из операндов не является числом (<xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>), результат операции имеет значение `false`. Это означает, что значение `NaN` не больше, не меньше и не равно любому другому значению `double` (или `float`). Дополнительные сведения и примеры см. в справочных статьях по <xref:System.Double.NaN?displayProperty=nameWithType> или <xref:System.Single.NaN?displayProperty=nameWithType>.

Два операнда одного типа [enum](../keywords/enum.md) равны, если равны соответствующие значения базового целочисленного типа.

По умолчанию оператор `==` не определен для пользовательского типа [struct](../keywords/struct.md). Определяемый пользователем тип может [перегружать](#operator-overloadability) оператор `==`.

Начиная с версии C# 7.3 операторы `==` и [`!=`](not-equal-operator.md) поддерживаются [кортежами](../../tuples.md) C#. Дополнительные сведения см. в разделе [Равенство и кортежи](../../tuples.md#equality-and-tuples) статьи [Типы кортежей в C#](../../tuples.md).

## <a name="string-equality"></a>Равенство строк

Два операнда [string](../keywords/string.md) равны, если они оба имеют значение `null` или оба экземпляра строки имеют одинаковую длину и идентичные символы в каждой позиции символа.

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

Это порядковое сравнение, учитывающее регистр. Дополнительные сведения о том, как сравнивать строки, см. в статье [Сравнение строк в C#](../../how-to/compare-strings.md).

## <a name="reference-types-equality"></a>Равенство ссылочных типов

Два операнда, отличных от операндов ссылочного типа `string`, являются равными, если они ссылаются на один и тот же объект.

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

В этом примере показано, что оператор `==` поддерживается определяемыми пользователем ссылочными типами. Однако определяемый пользователем ссылочный тип может перегружать оператор `==`. Если ссылочный тип перегружает оператор `==`, воспользуйтесь методом <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>, чтобы проверить, что две ссылки этого типа указывают на один и тот же объект.

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `==`. Если тип перегружает оператор равенства `==`, он также должен перегружать [оператор неравенства](not-equal-operator.md) `!=`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы отношения и проверки типа](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) в статье по [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Сравнения на равенство](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
