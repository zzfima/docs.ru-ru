---
title: Справочник по C#. Оператор --
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 4fba014e8dabc13cd874e17f23515dc29d93f24b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236932"
---
# <a name="---operator-c-reference"></a>Оператор -- (Справочник по C#)

Унарный оператор декремента `--` уменьшает операнд на 1. Оператор поддерживается в двух формах: постфиксный оператор декремента `x--`и префиксный оператор декремента `--x`.

## <a name="postfix-decrement-operator"></a>Постфиксный оператор уменьшения

Результатом `x--` является значение `x` *перед* выполнением операции, как показано в следующем примере:

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixDecrement)]

## <a name="prefix-decrement-operator"></a>Префиксный оператор декремента

Результатом `--x` является значение `x` *после* выполнения операции, как показано в следующем примере:

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixDecrement)]

## <a name="remarks"></a>Примечания

Оператор декремента является стандартным для всех [целочисленных типов](../keywords/integral-types-table.md) (включая тип [char](../keywords/char.md)), [типы с плавающей запятой](../keywords/floating-point-types-table.md) и любой тип [enum](../keywords/enum.md).

Операндом оператора декремента должна быть переменная, [свойство](../../programming-guide/classes-and-structs/properties.md) или [индексатор](../../../csharp/programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `--`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе о [постфиксных](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) и [префиксных](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) операторах инкремента и декремента в [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Оператор ++](increment-operator.md)
- [Практическое руководство. Увеличение и уменьшение указателей](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
