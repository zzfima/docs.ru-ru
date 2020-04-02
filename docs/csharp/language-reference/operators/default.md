---
title: Выражения default value. Справочник по C#
description: Используйте выражения default value, чтобы получить значение по умолчанию для типа.
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 2adfd8d24066e9dad50c3c18407d3ade71b4b68e
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507182"
---
# <a name="default-value-expressions-c-reference"></a>Выражения default value (справочник по C#)

Выражение default value создает [значение по умолчанию](../builtin-types/default-values.md) для типа. Выражения default value бывают двух видов: вызов [оператора default](#default-operator) и [литерал default](#default-literal).

Также используется ключевое слово `default` в качестве метки варианта по умолчанию в [инструкции `switch`](../keywords/switch.md).

## <a name="default-operator"></a>оператор default

Оператор `default` принимает в качестве аргумента имя типа или параметр типа, как показано в следующем примере:

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a>Литерал default

Начиная с C# 7.1, можно использовать литерал `default` для создания значения по умолчанию для типа, если компилятор может вывести тип выражения. Литеральное выражение `default` создает то же значение, что и выражение `default(T)`, где `T` является выведенным типом. Литерал `default` можно использовать в любом из следующих случаев:

- при назначении или инициализации переменной;
- в объявлении значения по умолчанию для [необязательного параметра метода](../../methods.md#optional-parameters-and-arguments);
- в вызове метода для предоставления значения аргумента;
- в [инструкции `return`](../keywords/return.md) или в качестве выражения в [элементе в тексте выражения](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

Ниже приведен пример применения литерала `default`.

[!code-csharp-interactive[default literal](snippets/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе о [выражениях значения по умолчанию](~/_csharplang/spec/expressions.md#default-value-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

Дополнительные сведения о литерале `default` см. в [примечании к предлагаемой функции](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Значения по умолчанию типов C#](../builtin-types/default-values.md)
- [Универсальные шаблоны в .NET](../../../standard/generics/index.md)
