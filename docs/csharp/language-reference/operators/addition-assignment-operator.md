---
title: Оператор +=. Справочник по C#
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: 5d48f2fe53a9bb6f781f8d35f1e0983bcaa30f88
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240935"
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

Можно также использовать оператор `+=`, который позволяет указать метод обработчика событий при подписке на [событие](../keywords/event.md). Дополнительные сведения см. в разделе [Как подписке и отмене подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

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
