---
title: Параметры значений
description: Сведения о типе F# параметра value, который является структурной версией типа параметра.
ms.date: 12/04/2019
ms.openlocfilehash: 0e9882ab4acdf2757705ef6022516d3572d87ef2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837120"
---
# <a name="value-options"></a>Параметры значений

Тип параметра значения в используется F# в следующих двух обстоятельствах:

1. Сценарий подходит для [ F# параметра](options.md).
2. Использование структуры обеспечивает выигрыш в производительности в вашем сценарии.

Не все сценарии с учетом производительности являются "решенными" с помощью структур. При использовании вместо ссылочных типов необходимо учитывать дополнительные затраты на копирование. Однако крупные F# программы часто создают множество необязательных типов, которые проходят через критические пути. в таких случаях структуры часто могут повысить общую производительность в течение всего времени существования программы.

## <a name="definition"></a>Определение

Параметр значения определен как [размеченное объединение структуры](discriminated-unions.md#struct-discriminated-unions) , похожее на тип параметра ссылки. Его определение можно рассматривать следующим образом:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

Параметр value соответствует структурному равенству и сравнению. Основное отличие состоит в том, что имя, имя типа и имена вариантов, как и названия регистров, указывают, что это тип значения.

## <a name="using-value-options"></a>Использование параметров значения

Параметры значения используются так же, как и [Параметры](options.md). `ValueSome` используется для указания на присутствие значения, а `ValueNone` используется, если отсутствует значение:

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

Как и в случае с [параметрами](options.md), соглашение об именовании для функции, возвращающей `ValueOption`, имеет префикс `try`.

## <a name="value-option-properties-and-methods"></a>Свойства и методы параметра value

В настоящее время имеется одно свойство параметров значения: `Value`. Если при вызове этого свойства значение не указано, вызывается <xref:System.InvalidOperationException>.

## <a name="value-option-functions"></a>Функции параметров значений

Модуль `ValueOption` в FSharp. Core содержит эквивалентные функции для модуля `Option`. Существует несколько отличий в имени, например `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

Это действует так же, как `defaultArg` в модуле `Option`, но работает вместо параметра значения.

## <a name="see-also"></a>См. также:

- [Параметры](options.md)
