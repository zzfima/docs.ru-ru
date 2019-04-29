---
title: Что такоеF#
description: Дополнительные сведения о том, что F# язык программирования — и что F# аналогичен программирования. Дополнительные сведения о расширенных типов данных, функции и как они работают вместе.
ms.date: 08/03/2018
ms.openlocfilehash: ea82147e4e6d3c980fb224eeafd805c7ed53f8f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756342"
---
# <a name="what-is-f"></a>Что такое F\#

F#— Это функциональный язык программирования, который позволяет легко написать правильный и поддерживаемого кода.

F#программирование в основном заключается в определении типов и функций, определить тип и обобщить автоматически. Это позволяет сосредоточить внимание на предметной области и обработки данных, а не сведения о программировании.

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

F#средство имеет множество функций, включая:

* Упрощенный синтаксис
* Неизменяемость по умолчанию
* Вывод типа и Автоматическое обобщение
* Функций первого класса
* Типы данных
* Регулярные выражения
* Асинхронное программирование

Весь набор функций описаны в [ F# Справочник по языку](language-reference/index.md).

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

F#записи и размеченные объединения, отличных от null, неизменяемый и сравним по умолчанию, что делает их очень прост в использовании.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Принудительная правильности с помощью функций и сопоставление шаблонов

F#функции являются простым для объявления и мощные на практике. В сочетании с [сопоставление шаблонов](language-reference/pattern-matching.md), они позволяют определять поведение, правильность которого обеспечивается компилятором.

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

F#функции также являются первого класса, то есть они могут передаваться как параметры и возвращена другими функциями.

## <a name="functions-to-define-operations-on-objects"></a>Функции для определения операций с объектами

F#имеет полную поддержку для объектов, которые являются типы полезных данных, при необходимости для объединения данных и функциональные возможности. F#функции используются для управления объектами.

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

Вместо того чтобы писать код, который является объектно ориентированной, в F#, часто будет написан код, который обрабатывает объекты в другой тип данных для функций для управления. Такие функции, как [универсальных интерфейсов](language-reference/interfaces.md), [выражения объектов](language-reference/object-expressions.md)и разумно использовать [члены](language-reference/members/index.md) часто используются в больших F# программы.

## <a name="next-steps"></a>Следующие шаги

Дополнительные сведения о больший набор F# функции, ознакомьтесь с [ F# Обзор](tour.md).