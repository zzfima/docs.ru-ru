---
title: Что такое F#
description: Узнайте о том, F# что такое язык программирования и F# как его можно программировать. Узнайте о типах данных, функциях и способах их совместного размещения.
ms.date: 08/03/2018
ms.openlocfilehash: 3cba509f59a8e81e1a0264de7451e9d80304d768
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332736"
---
# <a name="what-is-f"></a><span data-ttu-id="0c367-104">Что такое F\#</span><span class="sxs-lookup"><span data-stu-id="0c367-104">What is F\#</span></span>

<span data-ttu-id="0c367-105">F#— Это функциональный язык программирования, упрощающий написание правильного и сопровождаемого кода.</span><span class="sxs-lookup"><span data-stu-id="0c367-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="0c367-106">F#Программирование в основном включает определение типов и функций, которые выводятся и обобщены автоматически.</span><span class="sxs-lookup"><span data-stu-id="0c367-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="0c367-107">Это позволяет сосредоточиться на проблемном домене и манипулировать его данными, а не на деталях программирования.</span><span class="sxs-lookup"><span data-stu-id="0c367-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

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

<span data-ttu-id="0c367-108">F#содержит множество функций, включая:</span><span class="sxs-lookup"><span data-stu-id="0c367-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="0c367-109">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c367-109">Lightweight syntax</span></span>
* <span data-ttu-id="0c367-110">Неизменяемое по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0c367-110">Immutable by default</span></span>
* <span data-ttu-id="0c367-111">Определение типа и автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="0c367-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="0c367-112">Функции первого класса</span><span class="sxs-lookup"><span data-stu-id="0c367-112">First-class functions</span></span>
* <span data-ttu-id="0c367-113">Мощные типы данных</span><span class="sxs-lookup"><span data-stu-id="0c367-113">Powerful data types</span></span>
* <span data-ttu-id="0c367-114">Регулярные выражения</span><span class="sxs-lookup"><span data-stu-id="0c367-114">Pattern matching</span></span>
* <span data-ttu-id="0c367-115">Асинхронное программирование</span><span class="sxs-lookup"><span data-stu-id="0c367-115">Async programming</span></span>

<span data-ttu-id="0c367-116">Полный набор функций приведен в [ F# справочнике по языку](./language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="0c367-116">A full set of features are documented in the [F# language reference](./language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="0c367-117">Типы данных с богатыми возможностями</span><span class="sxs-lookup"><span data-stu-id="0c367-117">Rich data types</span></span>

<span data-ttu-id="0c367-118">Типы данных, такие как [записи](./language-reference/records.md) и [Размеченные объединения](./language-reference/discriminated-unions.md) , позволяют представлять сложные данные и домены.</span><span class="sxs-lookup"><span data-stu-id="0c367-118">Data types such as [Records](./language-reference/records.md) and [Discriminated Unions](./language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

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

<span data-ttu-id="0c367-119">F#записи и размеченные объединения не равны NULL, неизменяемы и сравнимы по умолчанию, что делает их очень простыми в использовании.</span><span class="sxs-lookup"><span data-stu-id="0c367-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="0c367-120">Принудительная правильность с помощью функций и сопоставления шаблонов</span><span class="sxs-lookup"><span data-stu-id="0c367-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="0c367-121">F#функции легко объявляют и являются мощными на практике.</span><span class="sxs-lookup"><span data-stu-id="0c367-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="0c367-122">В сочетании с [сопоставлением шаблонов](./language-reference/pattern-matching.md)они позволяют определить поведение, корректность которого обеспечивается компилятором.</span><span class="sxs-lookup"><span data-stu-id="0c367-122">When combined with [pattern matching](./language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

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

<span data-ttu-id="0c367-123">F#функции являются также первыми классами, то есть их можно передавать как параметры и возвращаться из других функций.</span><span class="sxs-lookup"><span data-stu-id="0c367-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="0c367-124">Функции для определения операций с объектами</span><span class="sxs-lookup"><span data-stu-id="0c367-124">Functions to define operations on objects</span></span>

<span data-ttu-id="0c367-125">F#обладает полной поддержкой объектов, которые являются полезными типами данных, когда требуется смешивать данные и функциональность.</span><span class="sxs-lookup"><span data-stu-id="0c367-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="0c367-126">F#функции используются для работы с объектами.</span><span class="sxs-lookup"><span data-stu-id="0c367-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<'T when 'T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="0c367-127">Вместо написания кода, который является объектно-ориентированным F#, в часто создается код, который обрабатывает объекты как другой тип данных для функций, которыми нужно управлять.</span><span class="sxs-lookup"><span data-stu-id="0c367-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="0c367-128">В больших F# программах часто используются такие функции, как [универсальные интерфейсы](./language-reference/interfaces.md), [выражения объектов](./language-reference/object-expressions.md)и разумное использование [элементов](./language-reference/members/index.md) .</span><span class="sxs-lookup"><span data-stu-id="0c367-128">Features such as [generic interfaces](./language-reference/interfaces.md), [object expressions](./language-reference/object-expressions.md), and judicious use of [members](./language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c367-129">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="0c367-129">Next steps</span></span>

<span data-ttu-id="0c367-130">Дополнительные сведения о большом наборе F# функций см. в этом [ F# обзоре](tour.md).</span><span class="sxs-lookup"><span data-stu-id="0c367-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
