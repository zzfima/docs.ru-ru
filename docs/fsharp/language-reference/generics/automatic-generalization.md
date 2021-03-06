---
title: Автоматическое обобщение
description: Узнайте, F# как автоматически обобщает аргументы и типы функций, чтобы они работали с несколькими типами, когда это возможно.
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630622"
---
# <a name="automatic-generalization"></a>Автоматическое обобщение

F#использует определение типа для вычисления типов функций и выражений. В этом разделе описывается F# , как автоматически обобщает аргументы и типы функций, чтобы они работали с несколькими типами, когда это возможно.

## <a name="automatic-generalization"></a>Автоматическое обобщение

F# Компилятор при выполнении определения типа для функции определяет, может ли заданный параметр быть универсальным. Компилятор проверяет каждый параметр и определяет, зависит ли функция от конкретного типа этого параметра. Если это не так, тип выводится как универсальный.

В следующем примере кода показана функция, которую компилятор выводит как универсальный.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

Тип выводится `'a -> 'a -> 'a`как.

Тип указывает, что это функция, принимающая два аргумента одного и того же неизвестного типа и возвращающая значение того же типа. Одна из причин, по которой функция Previous может быть универсальной, заключается в том, что оператор`>`«больше» () является универсальным. Оператор "больше чем" имеет сигнатуру `'a -> 'a -> bool`. Не все операторы являются универсальными, и если код в функции использует тип параметра вместе с неуниверсальной функцией или оператором, этот тип параметра не может быть обобщенным.

Поскольку `max` является универсальным, его можно использовать с типами, такими `int`как `float`, и т. д., как показано в следующих примерах.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

Однако оба аргумента должны иметь один и тот же тип. Сигнатура — `'a -> 'a -> 'a`, а `'a -> 'b -> 'a`не. Поэтому следующий код выдает ошибку, так как типы не совпадают.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

`max` Функция также работает с любым типом, поддерживающим оператор "больше чем". Таким образом, его также можно использовать в строке, как показано в следующем коде.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a>Ограничение значения

Компилятор выполняет автоматическое обобщение только для полных определений функций, имеющих явные аргументы, и для простых неизменяемых значений.

Это означает, что компилятор выдает ошибку при попытке компиляции кода, который не ограничен конкретным типом, но также не является обобщением. Сообщение об ошибке для этой проблемы связано с этим ограничением на автоматическую обобщение значений в качестве *ограничения*по значению.

Как правило, ошибка ограничения значения возникает либо в том случае, если требуется, чтобы конструкция была универсальной, но компилятор имеет недостаточную информацию для его обобщения, или если непреднамеренно опустить достаточно сведений о типе в неуниверсальной конструкции. Решением для ошибки ограничения значения является предоставление более явных сведений для более полного ограничения проблемы вывода типа одним из следующих способов:

- Ограничьте тип как неуниверсальный, добавив явную аннотацию типа к значению или параметру.

- Если проблема заключается в использовании необобщенной конструкции для определения универсальной функции, например композиции функций или неполностью примененных аргументов функции, попробуйте переписать функцию как обычное определение функции.

- Если проблема является выражением, которое является слишком сложным для обобщенного типа, сделайте его функцией, добавив дополнительный неиспользуемый параметр.

- Добавьте явные параметры универсального типа. Этот параметр редко используется.

- В следующих примерах кода демонстрируется каждый из этих сценариев.

Вариант 1. Слишком сложное выражение. В этом примере список `counter` должен быть `int option ref`, но не определен как простое неизменяемое значение.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

Вариант 2. Использование необобщенной конструкции для определения универсальной функции. В этом примере конструкция не является обобщением, так как она включает в себя частичное применение аргументов функции.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

Вариант 3. Добавление дополнительного неиспользуемого параметра. Поскольку это выражение недостаточно просто для обобщения, компилятор выдает ошибку ограничения значения.

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

Вариант 4. Добавление параметров типа.

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

В последнем случае значение превращается в функцию типа, которая может использоваться для создания значений различных типов, например следующим образом:

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>См. также

- [Вывод типа](../type-inference.md)
- [Универсальные шаблоны](index.md)
- [Статически разрешаемые параметры типов](statically-resolved-type-parameters.md)
- [Ограничения](constraints.md)
