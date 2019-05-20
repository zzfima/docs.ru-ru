---
title: Справочник по C#. Оператор ()
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 412d3ac5296eaf7d67f4a5e84b7a42f6fa5bb8a5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633855"
---
# <a name="-operator-c-reference"></a>Оператор (). Справочник по C#

Круглые скобки, `()`, обычно используются для вызова метода или делегата либо же в выражениях приведения.

Кроме того, с помощью круглых скобок можно указывать порядок выполнения операций в выражении. Дополнительные сведения см. в разделе [Добавление скобок](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) руководства по использованию [операторов](../../programming-guide/statements-expressions-operators/operators.md). Список операторов, упорядоченных по уровню приоритета, см. в статье [Операторы в C#](index.md).

## <a name="method-invocation"></a>Вызов метода

Приведенный ниже пример демонстрирует вызов делегата и метода с аргументами или без них.

[!code-csharp-interactive[use for invocation](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

Круглые скобки также можно использовать при вызове [конструктора](../../programming-guide/classes-and-structs/constructors.md) с оператором [`new`](../keywords/new-operator.md).

См. дополнительные сведения о [методах](../../programming-guide/classes-and-structs/methods.md) и [делегатах](../../programming-guide/delegates/index.md).

## <a name="cast-expression"></a>Выражение приведения

Выражение приведения формы `(T)E` вызывает оператор преобразования для преобразования значения выражения `E` в тип `T`. Если явного преобразования из типа `E` в тип `T` не существует, возникает ошибка времени компиляции. Сведения о том, как определять операторы преобразования, см. в статьях о ключевых словах [explicit](../keywords/explicit.md) и [implicit](../keywords/implicit.md).

В приведенном ниже примере показано преобразование типов между числовыми типами.

[!code-csharp-interactive[use for cast](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

См. дополнительные сведения о [предопределенных явных числовых преобразованиях](../keywords/explicit-numeric-conversions-table.md),

[приведении и преобразовании типов](../../programming-guide/types/casting-and-type-conversions.md) и [операторах преобразования](../../programming-guide/statements-expressions-operators/conversion-operators.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Оператор `()` перегрузить нельзя.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделах [Выражения вызова](~/_csharplang/spec/expressions.md#invocation-expressions) и [Выражения приведения](~/_csharplang/spec/expressions.md#cast-expressions) [спецификации C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
