---
title: Что такое F#
description: Узнайте о том, F# что такое язык программирования и F# как его можно программировать. Узнайте о типах данных, функциях и способах их совместного размещения.
ms.date: 08/03/2018
ms.openlocfilehash: 0c576fe49fadebd68e4fc9d2b20ea8f0cb991af5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630459"
---
# <a name="what-is-f"></a>Что такое F\#

F#— Это функциональный язык программирования, упрощающий написание правильного и сопровождаемого кода.

F#Программирование в основном включает определение типов и функций, которые выводятся и обобщены автоматически. Это позволяет сосредоточиться на проблемном домене и манипулировать его данными, а не на деталях программирования.

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

F#содержит множество функций, включая:

* Упрощенный синтаксис
* Неизменяемое по умолчанию
* Определение типа и автоматическое обобщение
* Функции первого класса
* Мощные типы данных
* Регулярные выражения
* Асинхронное программирование

Полный набор функций приведен в справочнике по [ F# языку](./language-reference/index.md).

## <a name="rich-data-types"></a>Типы данных с богатыми возможностями

Типы данных, такие как [записи](./language-reference/records.md) и [Размеченные объединения](./language-reference/discriminated-unions.md) , позволяют представлять сложные данные и домены.

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

F#записи и размеченные объединения не равны NULL, неизменяемы и сравнимы по умолчанию, что делает их очень простыми в использовании.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Принудительная правильность с помощью функций и сопоставления шаблонов

F#функции легко объявляют и являются мощными на практике. В сочетании с [сопоставлением шаблонов](./language-reference/pattern-matching.md)они позволяют определить поведение, корректность которого обеспечивается компилятором.

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

F#функции являются также первыми классами, то есть их можно передавать как параметры и возвращаться из других функций.

## <a name="functions-to-define-operations-on-objects"></a>Функции для определения операций с объектами

F#обладает полной поддержкой объектов, которые являются полезными типами данных, когда требуется смешивать данные и функциональность. F#функции используются для работы с объектами.

```fsharp
type Set<[<EqualityConditionOn>] 'T when 'T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

Вместо написания кода, который является объектно-ориентированным F#, в часто создается код, который обрабатывает объекты как другой тип данных для функций, которыми нужно управлять. В больших F# программах часто используются такие функции, как [универсальные интерфейсы](./language-reference/interfaces.md), [выражения объектов](./language-reference/object-expressions.md)и разумное использование [элементов](./language-reference/members/index.md) .

## <a name="next-steps"></a>Следующие шаги

Дополнительные сведения о большом наборе F# функций см. в этом [ F# обзоре](tour.md).
