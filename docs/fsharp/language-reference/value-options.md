---
title: Параметры значения
description: Дополнительные сведения о F# значение параметра типа — версии структуры типа параметра.
ms.date: 02/06/2019
ms.openlocfilehash: e1036c83189c853b3704d94ca245e4818acc98c1
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828037"
---
# <a name="value-options"></a>Параметры значения

Тип значения параметра в F# используется, если выполнено следующих двух случаях:

1. Сценарий подходит для [ F# параметр](options.md).
2. С помощью структуры обеспечивает повышение производительности в вашем сценарии.

Не все сценарии быстродействие» разрешаются» с помощью структуры. Необходимо учитывать дополнительные издержки копирования при использовании их вместо ссылочных типов. Однако большие F# программ часто создания экземпляра многие дополнительные типы, которые проходят через критических путей, и в таком случае структур часто приносит повышения общей производительности в течение времени существования программы.

## <a name="definition"></a>Определение

Значение параметра определяется как [размеченные объединения](discriminated-unions.md#struct-discriminated-unions) подобный вариант в ссылочный тип. Таким образом можно рассматривать его определения:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

Значение параметра соответствует структурного равенства и сравнения. Основное различие является то, что скомпилированный имя, имя типа и регистра имен указать, что не типом значения.

## <a name="using-value-options"></a>С помощью параметров значений

Параметры значения используются так же, как [параметры](options.md). `ValueSome` Указывает, что значение будет присутствовать, и `ValueNone` используется, если значение отсутствует:

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

Как и в [параметры](options.md), соглашение об именовании для функции, которая возвращает `ValueOption` является перед ними `try`.

## <a name="value-option-properties-and-methods"></a>Значение параметра свойства и методы

В настоящее время есть одно свойство для возможных значений: `Value`. <xref:System.InvalidOperationException> Возникает, если значение не присутствует, при вызове этого свойства.

## <a name="value-option-functions"></a>Значение параметра функции

В данный момент одного связанного с модулем функции для параметров значение `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

Как и в `defaultArg` функции `defaultValueArg` Возвращает базовое значение данного параметра значение, если он существует; в противном случае возвращает значение указанного по умолчанию.

В настоящее время нет других функций связанного с модулем для возможных значений.

## <a name="see-also"></a>См. также

- [Параметры](options.md)
