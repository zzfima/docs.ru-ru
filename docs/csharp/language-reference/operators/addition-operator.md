---
title: + Оператор (ссылка C#)
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 27ea47d698b20f112880750ec0bc931f1917f142
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "50192308"
---
# <a name="-operator-c-reference"></a>Оператор + (справочник по C#)

Оператор `+` поддерживается в двух формах: унарный оператор сложения или бинарный оператор сложения.

## <a name="unary-plus-operator"></a>Оператор унарного сложения

Унарный оператор `+` возвращает значение полученного операнда. Он поддерживается всеми числовыми типами данных.

## <a name="numeric-addition"></a>Арифметическое сложение

Для числовых типов оператор `+` вычисляет сумму двух операндов:

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

## <a name="string-concatenation"></a>Объединение строк

Если один или оба операнда имеют тип [string](../keywords/string.md), оператор `+` сцепляет строковые представления этих операндов.

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

В C#, начиная с версии 6, реализован более удобный способ форматирования строк, который называется [интерполяция строк](../tokens/interpolated.md):

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Объединение делегатов

Для типов [делегата](../keywords/delegate.md) оператор `+` возвращает новый экземпляр делегата, при вызове которого вызывается сначала первый, а затем второй операнд. Если какой-либо из операндов имеет значение `null`, оператор `+` возвращает значение другого операнда (это тоже может быть `null`). Следующий пример демонстрирует объединение делегатов с помощью оператора `+`:

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

См. дополнительные сведения о [типах делегатов](../../programming-guide/delegates/index.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Пользовательские типы могут [перегружать](../keywords/operator.md) унарный и бинарный операторы `+`. При перегрузке бинарного оператора `+` неявно перегружается и соответствующий [оператор присвоения сложения](addition-assignment-operator.md) `+=`.

## <a name="c-language-specification"></a>Спецификация языка C#

См. дополнительные сведения об [унарном операторе сложение](~/_csharplang/spec/expressions.md#unary-plus-operator) и [операторе сложения](~/_csharplang/spec/expressions.md#addition-operator) в [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Интерполяция строк](../tokens/interpolated.md)
- [Практическое руководство. Сцепка нескольких строк](../../how-to/concatenate-multiple-strings.md)
- [Делегаты](../../programming-guide/delegates/index.md)
- [Операторы checked и unchecked](../keywords/checked-and-unchecked.md)
