---
title: + и += (операторы). Справочник по C#
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
ms.openlocfilehash: cafd07f4b4aefdcc4b43750d61c155fe3d65aa46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398103"
---
# <a name="-and--operators-c-reference"></a>Операторы + и +=. Справочник по C#

Операторы `+` и `+=` поддерживаются встроенными [целыми](../builtin-types/integral-numeric-types.md) числовыми типами и числовыми типами [с плавающей запятой](../builtin-types/floating-point-numeric-types.md), а также [строковым](../builtin-types/reference-types.md#the-string-type) типом и типами[делегатов](../builtin-types/reference-types.md#the-delegate-type).

Сведения об арифметическом операторе `+` см. в разделе [Операторы унарного плюса и минуса](arithmetic-operators.md#unary-plus-and-minus-operators) и [Оператор сложения +](arithmetic-operators.md#addition-operator-) в статье [Арифметические операторы](arithmetic-operators.md).

## <a name="string-concatenation"></a>Объединение строк

Если один или оба операнда имеют тип [string](../builtin-types/reference-types.md#the-string-type), оператор `+` сцепляет строковые представления этих операндов.

[!code-csharp-interactive[string concatenation](snippets/AdditionOperator.cs#AddStrings)]

В C#, начиная с версии 6, реализован более удобный способ форматирования строк, который называется [интерполяция строк](../tokens/interpolated.md):

[!code-csharp-interactive[string interpolation](snippets/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Объединение делегатов

Для операндов того же типа [delegate](../builtin-types/reference-types.md#the-delegate-type) оператор `+` возвращает новый экземпляр делегата, при вызове которого вызывается сначала левый, а затем правый операнд. Если какой-либо из операндов имеет значение `null`, оператор `+` возвращает значение другого операнда (это тоже может быть `null`). Следующий пример демонстрирует объединение делегатов с помощью оператора `+`:

[!code-csharp-interactive[delegate combination](snippets/AdditionOperator.cs#AddDelegates)]

Для удаления делегатов используйте [оператор `-`](subtraction-operator.md#delegate-removal).

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

[!code-csharp-interactive[+= examples](snippets/AdditionOperator.cs#AddAndAssign)]

Можно также использовать оператор `+=`, который позволяет указать метод обработчика событий при подписке на [событие](../keywords/event.md). Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип может [перегружать](operator-overloading.md) оператор `+`. При перегрузке бинарного оператора `+` неявно перегружается и соответствующий оператор `+=`. Определяемый пользователем тип не может перегружать оператор `+=` явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

См. дополнительные сведения об [унарном операторе сложение](~/_csharplang/spec/expressions.md#unary-plus-operator) и [операторе сложения](~/_csharplang/spec/expressions.md#addition-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также раздел

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [Сцепка нескольких строк](../../how-to/concatenate-multiple-strings.md)
- [События](../../programming-guide/events/index.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Операторы - и -=](subtraction-operator.md)
