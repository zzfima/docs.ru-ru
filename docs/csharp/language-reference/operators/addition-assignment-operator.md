---
title: Оператор += (справочник по C#)
ms.date: 10/29/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ac9330e283cb58ae4e0ee7b644aa2c22bdf64c46
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "50192035"
---
# <a name="-operator-c-reference"></a>Оператор += (справочник по C#)

Оператор присваивания сложения.

Выражение, использующее оператор `+=`, такое как

```csharp
x += y
```

эквивалентно

```csharp
x = x + y
```

за исключением того, что `x` вычисляется только один раз.
  
Для числовых типов [оператор сложения](addition-operator.md) `+` вычисляет сумму операндов. Если один или оба операнда имеют [строковый](../keywords/string.md) тип, оператор сцепляет строковые представления операндов. Для типов делегатов оператор `+` возвращает новый экземпляр делегата, который представляет собой комбинацию операндов.

Можно также использовать оператор `+=`, который позволяет указать метод обработчика событий при подписке на [событие](../keywords/event.md). Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

В следующем примере иллюстрируется использование оператора `+=`.

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Если определяемый пользователем тип [перегружает](../keywords/operator.md) [оператор сложения](addition-operator.md) `+`, оператор присваивания сложения `+=` неявно перегружается. Определяемый пользователем тип не может перегружать оператор присваивания сложения явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделах [Составное присваивание](~/_csharplang/spec/expressions.md#compound-assignment) и [Назначение событий](~/_csharplang/spec/expressions.md#event-assignment) в [Спецификации языка C#](../language-specification/index.md).
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [События](../../programming-guide/events/index.md)
- [Делегаты](../../programming-guide/delegates/index.md)
