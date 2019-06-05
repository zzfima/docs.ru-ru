---
title: + и += (операторы) — справочник по C#
ms.custom: seodec18
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d03743bad47c60925462d027d18445047ebc0fc9
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300117"
---
# <a name="-and--operators-c-reference"></a>+ и += (операторы) (справочник по C#)

Оператор `+` поддерживается встроенными числовыми типами, типом [string](../keywords/string.md) и типами [delegate](../keywords/delegate.md).

Сведения об арифметическом операторе `+` см. в разделе [Операторы унарного плюса и минуса](arithmetic-operators.md#unary-plus-and-minus-operators) и [Оператор сложения +](arithmetic-operators.md#addition-operator-) в статье [Арифметические операторы](arithmetic-operators.md).

## <a name="string-concatenation"></a>Объединение строк

Если один или оба операнда имеют тип [string](../keywords/string.md), оператор `+` сцепляет строковые представления этих операндов.

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

В C#, начиная с версии 6, реализован более удобный способ форматирования строк, который называется [интерполяция строк](../tokens/interpolated.md):

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Объединение делегатов

Для операндов того же типа [delegate](../keywords/delegate.md) оператор `+` возвращает новый экземпляр делегата, при вызове которого вызывается сначала первый, а затем второй операнд. Если какой-либо из операндов имеет значение `null`, оператор `+` возвращает значение другого операнда (это тоже может быть `null`). Следующий пример демонстрирует объединение делегатов с помощью оператора `+`:

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

См. дополнительные сведения о [типах делегатов](../../programming-guide/delegates/index.md).

## <a name="addition-assignment-operator-"></a>Оператор присваивания сложения (+=)

Выражение, использующее оператор `+=`, такое как

```csharp
x += y
```

эквивалентно

```csharp
x = x + y
```

за исключением того, что `x` вычисляется только один раз.
  
В следующем примере иллюстрируется использование оператора `+=`.

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

Можно также использовать оператор `+=`, который позволяет указать метод обработчика событий при подписке на [событие](../keywords/event.md). Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип может [перегружать](../keywords/operator.md) оператор `+`. При перегрузке бинарного оператора `+` неявно перегружается и соответствующий оператор `+=`. Определяемый пользователем тип не может перегружать оператор `+=` явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

См. дополнительные сведения об [унарном операторе сложение](~/_csharplang/spec/expressions.md#unary-plus-operator) и [операторе сложения](~/_csharplang/spec/expressions.md#addition-operator) в [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Интерполяция строк](../tokens/interpolated.md)
- [Практическое руководство. Сцепка нескольких строк](../../how-to/concatenate-multiple-strings.md)
- [Делегаты](../../programming-guide/delegates/index.md)
- [События](../../programming-guide/events/index.md)
- [Инструкции checked и unchecked](../keywords/checked-and-unchecked.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Операторы - и -=](subtraction-operator.md)
