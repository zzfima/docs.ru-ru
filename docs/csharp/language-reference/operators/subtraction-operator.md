---
title: '- Операторы - и -=. Справочник по C#'
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
ms.openlocfilehash: 775f06b05d75078e53ab777d09713d69467ace14
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712615"
---
# <a name="--and---operators-c-reference"></a>Операторы - и -= (справочник по C#)

Операторы `-` и `-=` поддерживаются встроенными [целыми](../builtin-types/integral-numeric-types.md) числовыми типами и числовыми типами [с плавающей запятой](../builtin-types/floating-point-numeric-types.md), а также типами [делегатов](../builtin-types/reference-types.md#the-delegate-type).

Сведения об арифметическом операторе `-` см. в разделе [Операторы унарного плюса и минуса](arithmetic-operators.md#unary-plus-and-minus-operators) и [Оператор вычитания -](arithmetic-operators.md#subtraction-operator--) в статье [Арифметические операторы](arithmetic-operators.md).

## <a name="delegate-removal"></a>Удаление делегатов

Для операндов одного и того же типа [delegate](../builtin-types/reference-types.md#the-delegate-type) оператор `-` возвращает экземпляр делегата, который вычисляется следующим образом:

- Если оба операнда не равны NULL и список вызовов правого операнда является соответствующим подчиненным списком списка вызовов левого операнда, результатом операции является новый список вызовов, который получается путем удаления записей правого операнда из списка вызовов левого операнда. Если список правого операнда соответствует нескольким смежным подчиненным спискам в списке левого операнда, удаляется только крайний правый совпадающий подсписок. Если удаление приводит к пустому списку, возвращается `null`.

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- Если список вызовов правого операнда не является соответствующим смежным подчиненным списком списка вызовов левого операнда, результатом операции является левый операнд. Так, удаление делегата, который не является частью многоадресного делегата, ни к чему не приводит и многоадресный делегат никак не меняется.

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  В предыдущем примере также показано, что во время удаления делегата сравниваются его экземпляры. Например, делегаты, созданные в результате оценки идентичных [лямбда-выражений](../../programming-guide/statements-expressions-operators/lambda-expressions.md) не будут равны. Дополнительные сведения о равенстве делегатов см. в разделе об [операторах равенства делегатов](~/_csharplang/spec/expressions.md#delegate-equality-operators) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

- Если левый операнд имеет значение `null`, результатом операции является `null`. Если правый операнд имеет значение `null`, результатом операции является левый операнд.

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

Определяемый пользователем тип может [перегружать](operator-overloading.md) оператор `-`. При перегрузке бинарного оператора `-` неявно перегружается и соответствующий оператор `-=`. Определяемый пользователем тип не может перегружать оператор `-=` явным образом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор унарного минуса](~/_csharplang/spec/expressions.md#unary-minus-operator) и [Оператор вычитания](~/_csharplang/spec/expressions.md#subtraction-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [События](../../programming-guide/events/index.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Операторы + и +=](addition-operator.md)
