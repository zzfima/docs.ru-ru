---
title: Оператор ++ (справочник по C#)
ms.date: 11/26/2018
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: b29f4f1ab00c0f8026f118cb72b090e3b728bfc5
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2018
ms.locfileid: "48030474"
---
# <a name="-operator-c-reference"></a>Оператор ++ (справочник по C#)

Оператор инкремента `++` увеличивает операнд на 1. Он поддерживается в двух формах: постфиксный оператор инкремента и `x++` префиксный оператор инкремента `++x`.

## <a name="postfix-increment-operator"></a>Постфиксный оператор приращения

Результатом `x++` является значение `x` *перед* выполнением операции, как показано в следующем примере:

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixIncrement)]

## <a name="prefix-increment-operator"></a>Префиксный оператор инкремента

Результатом `++x` является значение `x` *после* выполнения операции, как показано в следующем примере:

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixIncrement)]

## <a name="remarks"></a>Примечания

Оператор инкремента является стандартным для всех [целочисленных типов](../keywords/integral-types-table.md) (включая тип [char](../keywords/char.md)), [типы с плавающей запятой](../keywords/floating-point-types-table.md) и любой тип [enum](../keywords/enum.md).

Операндом оператора инкремента должна быть переменная, [свойство](../../programming-guide/classes-and-structs/properties.md) или [индексатор](../../../csharp/programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `++`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе о [постфиксных](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) и [префиксных](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) операторах инкремента и декремента в [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Оператор --](decrement-operator.md)
- [Практическое руководство. Увеличение и уменьшение указателей](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
