---
title: "Результаты (F #)"
description: "Узнайте, как использовать тип F # «Привести» для упрощения написания кода на языке."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a15b5cf1-9055-4481-918c-4c8a051b5829
ms.openlocfilehash: 26478ccfbf88d43c0b194e77d9aacc313515283f
ms.sourcegitcommit: 8d14e8c1b15009330c9880f8523686158924e1a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2017
---
# <a name="results"></a>Результаты

Начиная с версии 4.1 F #, имеется `Result<'T,'TFailure>` тип, который можно использовать для написания нечувствительный код, который может быть создан.

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

## <a name="remarks"></a>Примечания

Обратите внимание, что тип результата — [структура размеченные объединения](discriminated-unions.md#struct-discriminated-unions), который является другой функцией, представленные в F # 4.1.  Здесь применяются семантикой структурного равенства.

`Result` Тип обычно используется в результата вычисления обработки ошибок, который часто называют [Железная дорога ориентированном программировании](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) в сообществе F #.  Приведенный ниже тривиальные демонстрирует этот подход.

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
    | String.Empty -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | String.Empty -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> OK req

let validateRequest reqResult =
    reqResult 
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() = 
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (OK req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req1.Name req1.Email
    | Error e -> printfn "Error: %s" e
    // Prints " "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (OK req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req1.Name req1.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

Как видите, это довольно просто цепочку различные функции проверки, если все они будут возвращать принудительно `Result`.  Это позволяет разбить таких функций, как это на мелкие части, которые сочетаются как при необходимости быть.  Этот шаблон также имеет значение added *применения* использование [соответствие шаблону](pattern-matching.md) в конце цикла проверки, который в свою очередь, приводит обеспечивает более высокую степень корректности.

## <a name="see-also"></a>См. также

[Размеченные объединения](discriminated-unions.md)

[Соответствие шаблону](pattern-matching.md)
