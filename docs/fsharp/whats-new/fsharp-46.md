---
title: Новые возможности в F# 4,6- F# Guide
description: Ознакомьтесь с обзором новых функций, доступных в F# 4,6.
ms.date: 11/27/2019
ms.openlocfilehash: 81d3e988d044cb16f8ec079118fd0ede2dabc587
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644136"
---
# <a name="whats-new-in-f-46"></a>Новые возможности в F# 4,6

F#4,6 добавляет несколько улучшений в F# язык.

## <a name="get-started"></a>Начало работы

F#4,6 доступна во всех дистрибутивах .NET Core и средствах Visual Studio. Дополнительные сведения см. в статье Приступая к [работе с F# ](../get-started/index.md) .

## <a name="anonymous-records"></a>Анонимные записи

[Анонимные записи](../language-reference/anonymous-records.md) — это новый F# тип, представленный F# в 4,6. Они представляют собой простые статистические выражения именованных значений, которые не нужно объявлять перед использованием. Их можно объявить как структуры или ссылочные типы. По умолчанию они являются ссылочными типами.

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

Они также могут быть объявлены как структуры для случаев, когда требуется группировать типы значений и работать в сценариях с учетом производительности.

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    struct {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

Они являются достаточно мощными и могут использоваться во многих сценариях. Дополнительные сведения см. в статье [анонимные записи](../language-reference/anonymous-records.md).

## <a name="valueoption-functions"></a>Функции Валуеоптион

Тип Валуеоптион, добавленный F# в 4,5, теперь имеет тип параметра, привязанный к модулю. Ниже приведены некоторые из наиболее часто используемых примеров.

```fsharp
// Multiply a value option by 2 if it has  value
let xOpt = ValueSome 99
let result = xOpt |> ValueOption.map (fun v -> v * 2)

// Reverse a string if it exists
let strOpt = ValueSome "Mirror image"
let reverse (str: string) =
    match str with
    | null
    | "" -> None
    | s ->
        str.ToCharArray()
        |> Array.rev
        |> string
        |> Some

let reversedString = strOpt |> Option.bind reverse
```

Это позволяет использовать Валуеоптион так же, как вариант в сценариях, где тип значения повышает производительность.
