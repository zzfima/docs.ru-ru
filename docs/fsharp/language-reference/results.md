---
title: Результаты
description: Узнайте, как использовать тип F# "Result" для написания отказоустойчивого кода.
ms.date: 04/24/2017
ms.openlocfilehash: 187aa26ccbaac7e0ec998756377bb7b0489eb1ab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424851"
---
# <a name="results"></a><span data-ttu-id="cf6ad-103">Результаты</span><span class="sxs-lookup"><span data-stu-id="cf6ad-103">Results</span></span>

<span data-ttu-id="cf6ad-104">Начиная с F# 4,1 существует тип `Result<'T,'TFailure>`, который можно использовать для написания отказоустойчивого кода, который можно составить.</span><span class="sxs-lookup"><span data-stu-id="cf6ad-104">Starting with F# 4.1, there is a `Result<'T,'TFailure>` type which you can use for writing error-tolerant code which can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf6ad-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf6ad-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="cf6ad-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="cf6ad-106">Remarks</span></span>

<span data-ttu-id="cf6ad-107">Обратите внимание, что тип результата — это [отличительное объединение структуры](discriminated-unions.md#struct-discriminated-unions), которое представляет собой еще F# один компонент, представленный в 4,1.</span><span class="sxs-lookup"><span data-stu-id="cf6ad-107">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions), which is another feature introduced in F# 4.1.</span></span>  <span data-ttu-id="cf6ad-108">Семантика структурного равенства применяется здесь.</span><span class="sxs-lookup"><span data-stu-id="cf6ad-108">Structural equality semantics apply here.</span></span>

<span data-ttu-id="cf6ad-109">Тип `Result` обычно используется в собственной обработке ошибок, которую часто называют [раилвай-ориентированным программированием](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) в F# сообществе.</span><span class="sxs-lookup"><span data-stu-id="cf6ad-109">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="cf6ad-110">Следующий тривиальный пример демонстрирует этот подход.</span><span class="sxs-lookup"><span data-stu-id="cf6ad-110">The following trivial example demonstrates this approach.</span></span>

```fsharp
// Define a simple type which has fields that can be validated
type Request =
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() =
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="cf6ad-111">Как видите, в цепочку можно легко объединить различные функции проверки, если вы принудительно возвращаете `Result`.</span><span class="sxs-lookup"><span data-stu-id="cf6ad-111">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="cf6ad-112">Это позволяет разбивать такие функциональные возможности на небольшие части, которые являются взаимокомпозициями по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="cf6ad-112">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="cf6ad-113">Это также имеет добавленное *значение применения* [сопоставления шаблонов](pattern-matching.md) в конце круга проверки, что в свою сторону принуждает к более высокой степени правильности программы.</span><span class="sxs-lookup"><span data-stu-id="cf6ad-113">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf6ad-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cf6ad-114">See also</span></span>

- [<span data-ttu-id="cf6ad-115">Размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="cf6ad-115">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="cf6ad-116">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="cf6ad-116">Pattern Matching</span></span>](pattern-matching.md)
