---
title: Справочник по C#. Оператор default
description: Создания значения по умолчанию для типа с помощью оператора default
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 0d37fe952e71e74f014872231a2e58663dea9d18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398187"
---
# <a name="default-operator-c-reference"></a>Оператор default (справочник по C#)

Оператор `default` создает значение [по умолчанию](../builtin-types/default-values.md) для типа. Оператор `default` принимает в качестве аргумента имя типа или параметр типа.

В следующем примере показано применение оператора `default`.

[!code-csharp-interactive[default of T](snippets/DefaultOperator.cs#WithOperand)]

Также используется ключевое слово `default` в качестве метки варианта по умолчанию в [инструкции `switch`](../keywords/switch.md).

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

## <a name="see-also"></a>См. также раздел

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Значения по умолчанию типов C#](../builtin-types/default-values.md)
- [Универсальные шаблоны в .NET](../../../standard/generics/index.md)
