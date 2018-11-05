---
title: Что такое F#
description: Узнайте, какие F# является языком программирования и программирование на F# выглядит. Дополнительные сведения о расширенных типов данных, функции и как они работают вместе.
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43863300"
---
# <a name="what-is-f"></a><span data-ttu-id="d37e7-104">Что такое F#</span><span class="sxs-lookup"><span data-stu-id="d37e7-104">What is F#</span></span> #

<span data-ttu-id="d37e7-105">F# — это функциональный язык программирования, который позволяет легко написать правильный и поддерживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="d37e7-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="d37e7-106">Программирование на F# в основном заключается в определении типов и функций, определить тип и обобщить автоматически.</span><span class="sxs-lookup"><span data-stu-id="d37e7-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="d37e7-107">Это позволяет сосредоточить внимание на предметной области и обработки данных, а не сведения о программировании.</span><span class="sxs-lookup"><span data-stu-id="d37e7-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

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

<span data-ttu-id="d37e7-108">F# входит множество функций, включая:</span><span class="sxs-lookup"><span data-stu-id="d37e7-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="d37e7-109">Упрощенный синтаксис</span><span class="sxs-lookup"><span data-stu-id="d37e7-109">Lightweight syntax</span></span>
* <span data-ttu-id="d37e7-110">Неизменяемость по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d37e7-110">Immutable by default</span></span>
* <span data-ttu-id="d37e7-111">Вывод типа и Автоматическое обобщение</span><span class="sxs-lookup"><span data-stu-id="d37e7-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="d37e7-112">Функций первого класса</span><span class="sxs-lookup"><span data-stu-id="d37e7-112">First-class functions</span></span>
* <span data-ttu-id="d37e7-113">Типы данных</span><span class="sxs-lookup"><span data-stu-id="d37e7-113">Powerful data types</span></span>
* <span data-ttu-id="d37e7-114">Регулярные выражения</span><span class="sxs-lookup"><span data-stu-id="d37e7-114">Pattern matching</span></span>
* <span data-ttu-id="d37e7-115">Асинхронное программирование</span><span class="sxs-lookup"><span data-stu-id="d37e7-115">Async programming</span></span>

<span data-ttu-id="d37e7-116">Весь набор функций описаны в [Справочник по языку F#](language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="d37e7-116">A full set of features are documented in the [F# language reference](language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="d37e7-117">Расширенные типы данных</span><span class="sxs-lookup"><span data-stu-id="d37e7-117">Rich data types</span></span>

<span data-ttu-id="d37e7-118">Типы данных, такие как [записей](language-reference/records.md) и [размеченные объединения](language-reference/discriminated-unions.md) позволяют представлять сложных данных и домены.</span><span class="sxs-lookup"><span data-stu-id="d37e7-118">Data types such as [Records](language-reference/records.md) and [Discriminated Unions](language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

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

<span data-ttu-id="d37e7-119">F# записи и размеченные объединения, отличных от null, неизменяемый и сравним по умолчанию, что делает их очень прост в использовании.</span><span class="sxs-lookup"><span data-stu-id="d37e7-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="d37e7-120">Принудительная правильности с помощью функций и сопоставление шаблонов</span><span class="sxs-lookup"><span data-stu-id="d37e7-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="d37e7-121">F#-функции обладают легко объявить и возможностями на практике.</span><span class="sxs-lookup"><span data-stu-id="d37e7-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="d37e7-122">В сочетании с [сопоставление шаблонов](language-reference/pattern-matching.md), они позволяют определять поведение, правильность которого обеспечивается компилятором.</span><span class="sxs-lookup"><span data-stu-id="d37e7-122">When combined with [pattern matching](language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

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

<span data-ttu-id="d37e7-123">Функции F#, также первого класса, то есть они могут передаваться как параметры и возвращена другими функциями.</span><span class="sxs-lookup"><span data-stu-id="d37e7-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="d37e7-124">Функции для определения операций с объектами</span><span class="sxs-lookup"><span data-stu-id="d37e7-124">Functions to define operations on objects</span></span>

<span data-ttu-id="d37e7-125">F# имеет полную поддержку для объектов, которые являются типы полезных данных, при необходимости для объединения данных и функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="d37e7-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="d37e7-126">F# функции используются для управления объектами.</span><span class="sxs-lookup"><span data-stu-id="d37e7-126">F# functions are used to manipulate objects.</span></span>

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

<span data-ttu-id="d37e7-127">Вместо того чтобы писать код, который является объектно ориентированной, в F#, будет часто написать код, обрабатывает объекты в другой тип данных для функций для управления.</span><span class="sxs-lookup"><span data-stu-id="d37e7-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="d37e7-128">Такие функции, как [универсальных интерфейсов](language-reference/interfaces.md), [выражения объектов](language-reference/object-expressions.md)и разумно использовать [члены](language-reference/members/index.md) часто используются в более крупных программ F#.</span><span class="sxs-lookup"><span data-stu-id="d37e7-128">Features such as [generic interfaces](language-reference/interfaces.md), [object expressions](language-reference/object-expressions.md), and judicious use of [members](language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d37e7-129">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="d37e7-129">Next steps</span></span>

<span data-ttu-id="d37e7-130">Дополнительные сведения о функции F# большого набора, извлечение [Обзор F#](tour.md).</span><span class="sxs-lookup"><span data-stu-id="d37e7-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>