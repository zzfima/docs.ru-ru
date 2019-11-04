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
# <a name="results"></a>Результаты

Начиная с F# 4,1 существует тип `Result<'T,'TFailure>`, который можно использовать для написания отказоустойчивого кода, который можно составить.

## <a name="syntax"></a>Синтаксис

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a>Заметки

Обратите внимание, что тип результата — это [отличительное объединение структуры](discriminated-unions.md#struct-discriminated-unions), которое представляет собой еще F# один компонент, представленный в 4,1.  Семантика структурного равенства применяется здесь.

Тип `Result` обычно используется в собственной обработке ошибок, которую часто называют [раилвай-ориентированным программированием](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) в F# сообществе.  Следующий тривиальный пример демонстрирует этот подход.

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

Как видите, в цепочку можно легко объединить различные функции проверки, если вы принудительно возвращаете `Result`.  Это позволяет разбивать такие функциональные возможности на небольшие части, которые являются взаимокомпозициями по мере необходимости.  Это также имеет добавленное *значение применения* [сопоставления шаблонов](pattern-matching.md) в конце круга проверки, что в свою сторону принуждает к более высокой степени правильности программы.

## <a name="see-also"></a>См. также

- [Размеченные объединения](discriminated-unions.md)
- [Соответствие шаблону](pattern-matching.md)
