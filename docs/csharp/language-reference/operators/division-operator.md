---
title: Справочник по C#. Оператор /
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 45bcd64b60e7d13f389064faefeda815ea1f32c9
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286537"
---
# <a name="-operator-c-reference"></a>Оператор / (Справочник по C#)

Оператор деления `/` делит первый операнд на второй. Все числовые типы поддерживают оператор деления.

## <a name="integer-division"></a>Деление целых чисел

Для операндов цельночисленных типов результат оператора `/` является целочисленным типом, который равен частному двух операндов, округленному в сторону нуля:

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#Integer)]

Чтобы получить частное двух операндов в виде числа с плавающей запятой, используйте тип `float`, `double` или `decimal`:

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#IntegerAsFloatingPoint)]

## <a name="floating-point-division"></a>Деление чисел с плавающей запятой

Для типов `float`, `double` и `decimal` результатом оператора `/` является частное двух операндов:

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#FloatingPoint)]

Если один из операндов — это `decimal`, второй операнд не может быть ни `float`, ни `double`, так как ни `float`, ни `double` не преобразуется неявно в тип `decimal`. Необходимо явным образом преобразовать операнд `float` или `double` в тип `decimal`. Дополнительные сведения о неявных числовых преобразованиях см. в [таблице неявных числовых преобразований](../keywords/implicit-numeric-conversions-table.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут [перегружать](../keywords/operator.md) оператор `/`. При перегрузке оператора `/` неявно перегружается и соответствующий [оператор присваивания деления](division-assignment-operator.md) `/=`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор деления](~/_csharplang/spec/expressions.md#division-operator) [спецификация языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Оператор %](remainder-operator.md)
