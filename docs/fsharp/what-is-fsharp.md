---
title: 'Что такое F #'
description: 'Узнайте, какие F # является языком программирования и программирование на F # выглядит. Дополнительные сведения о расширенных типов данных, функции и как они работают вместе.'
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43256714"
---
# <a name="what-is-f"></a>Что такое F # #

F # — это функциональный язык программирования, который позволяет легко написать правильный и поддерживаемого кода.

Программирование на F # в основном заключается в определении типов и функций, определить тип и обобщить автоматически. Это позволяет сосредоточить внимание на предметной области и обработки данных, а не сведения о программировании.

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

F # входит множество функций, включая:

* Упрощенный синтаксис
* Неизменяемость по умолчанию
* Вывод типа и Автоматическое обобщение
* Функций первого класса
* Типы данных
* Регулярные выражения
* Асинхронное программирование

Весь набор функций описаны в [Справочник по языку F #](language-reference/index.md).

## <a name="rich-data-types"></a>Расширенные типы данных

Типы данных, такие как [записей](language-reference/records.md) и [размеченные объединения](language-reference/discriminated-unions.md) позволяют представлять сложных данных и домены.

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

F # записи и размеченные объединения, отличных от null, неизменяемый и сравним по умолчанию, что делает их очень прост в использовании.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Принудительная правильности с помощью функций и сопоставление шаблонов

F #-функции обладают легко объявить и возможностями на практике. В сочетании с [сопоставление шаблонов](language-reference/pattern-matching.md), они позволяют определять поведение, правильность которого обеспечивается компилятором.

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

Функции F #, также первого класса, то есть они могут передаваться как параметры и возвращена другими функциями.

## <a name="functions-to-define-operations-on-objects"></a>Функции для определения операций с объектами

F # имеет полную поддержку для объектов, которые являются типы полезных данных, при необходимости для объединения данных и функциональные возможности. F # функции используются для управления объектами.

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
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

Вместо того чтобы писать код, который является объектно ориентированной, в F #, будет часто написать код, обрабатывает объекты в другой тип данных для функций для управления. Такие функции, как [универсальных интерфейсов](language-reference/interfaces.md), [выражения объектов](language-reference/object-expressions.md)и разумно использовать [члены](language-reference/members/index.md) часто используются в более крупных программ F #.

## <a name="next-steps"></a>Следующие шаги

Дополнительные сведения о функции F # большого набора, извлечение [Обзор F #](tour.md).