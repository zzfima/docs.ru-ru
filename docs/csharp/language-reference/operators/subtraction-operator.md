---
title: '- и -= (операторы) – справочник по C#'
ms.custom: seodec18
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: aae10f8b03a16e55f0b26981f17585c8790e00c1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816082"
---
# <a name="--and---operators-c-reference"></a>- и -= (операторы) (справочник по C#)

Оператор `-` поддерживается встроенными числовыми типами и типами [delegate](../keywords/delegate.md).

Сведения об арифметическом операторе `-` см. в разделе [Операторы унарного плюса и минуса](arithmetic-operators.md#unary-plus-and-minus-operators) и [Оператор вычитания -](arithmetic-operators.md#subtraction-operator--) в статье [Арифметические операторы](arithmetic-operators.md).

## <a name="delegate-removal"></a>Удаление делегатов

Для операндов одного и того же типа [delegate](../keywords/delegate.md) оператор `-` возвращает экземпляр делегата, который вычисляется следующим образом:

- Если оба операнда не равны NULL и список вызовов второго операнда является соответствующим подсписком списка вызовов первого операнда, результатом операции является новый список вызовов, который получается путем удаления записей второго операнда из списка вызовов первого операнда. Если список второго операнда соответствует нескольким смежным подспискам в списке первого операнда, удаляется только крайний правый совпадающий подсписок. Если удаление приводит к пустому списку, возвращается `null`.

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- Если список вызовов второго операнда не является соответствующим смежным подсписком списка вызовов первого операнда, результатом операции является первый операнд. Так, удаление делегата, который не является частью многоадресного делегата, ни к чему не приводит и многоадресный делегат никак не меняется.

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  В предыдущем примере также показано, что во время удаления делегата сравниваются его экземпляры. Например, делегаты, созданные в результате оценки идентичных [лямбда-выражений](../../programming-guide/statements-expressions-operators/lambda-expressions.md) не будут равны. Дополнительные сведения о равенстве делегатов см. в разделе об [операторах равенства делегатов](~/_csharplang/spec/expressions.md#delegate-equality-operators) в [спецификации языка C#](../language-specification/index.md).

- Если первый операнд — `null`, результатом операции является `null`. Если второй операнд — `null`, результатом операции является первый операнд.

  [!code-csharp-interactive[delegate removal and null](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalAndNull)]

Объединить делегаты можно с помощью [оператора `+`](addition-operator.md#delegate-combination).

См. дополнительные сведения о [типах делегатов](../../programming-guide/delegates/index.md).

## <a name="subtraction-assignment-operator--"></a>Оператор присваивания вычитания (-=)

Выражение, использующее оператор `-=`, такое как

```csharp
x -= y
```

эквивалентно

```csharp
x = x - y
```

за исключением того, что `x` вычисляется только один раз.
  
В следующем примере иллюстрируется использование оператора `-=`.

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

Можно также использовать оператор `-=`, который позволяет указать метод обработчика событий для удаления при отмене подписки на [событие](../keywords/event.md). Дополнительные сведения см. в разделе [Практическое руководство. Подписка и отмена подписки на события](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемый пользователем тип может [перегружать](../keywords/operator.md) оператор `-`. При перегрузке бинарного оператора `-` неявно перегружается и соответствующий оператор `-=`. Определяемый пользователем тип не может перегружать оператор `-=` явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор унарного минуса](~/_csharplang/spec/expressions.md#unary-minus-operator) и [Оператор вычитания](~/_csharplang/spec/expressions.md#subtraction-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Делегаты](../../programming-guide/delegates/index.md)
- [События](../../programming-guide/events/index.md)
- [Инструкции checked и unchecked](../keywords/checked-and-unchecked.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Операторы + и +=](addition-operator.md)
