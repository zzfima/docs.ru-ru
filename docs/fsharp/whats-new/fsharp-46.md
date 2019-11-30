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
# <a name="whats-new-in-f-46"></a><span data-ttu-id="cd88d-103">Новые возможности в F# 4,6</span><span class="sxs-lookup"><span data-stu-id="cd88d-103">What's new in F# 4.6</span></span>

<span data-ttu-id="cd88d-104">F#4,6 добавляет несколько улучшений в F# язык.</span><span class="sxs-lookup"><span data-stu-id="cd88d-104">F# 4.6 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="cd88d-105">Начало работы</span><span class="sxs-lookup"><span data-stu-id="cd88d-105">Get started</span></span>

<span data-ttu-id="cd88d-106">F#4,6 доступна во всех дистрибутивах .NET Core и средствах Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cd88d-106">F# 4.6 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="cd88d-107">Дополнительные сведения см. в статье Приступая к [работе с F# ](../get-started/index.md) .</span><span class="sxs-lookup"><span data-stu-id="cd88d-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="anonymous-records"></a><span data-ttu-id="cd88d-108">Анонимные записи</span><span class="sxs-lookup"><span data-stu-id="cd88d-108">Anonymous records</span></span>

<span data-ttu-id="cd88d-109">[Анонимные записи](../language-reference/anonymous-records.md) — это новый F# тип, представленный F# в 4,6.</span><span class="sxs-lookup"><span data-stu-id="cd88d-109">[Anonymous records](../language-reference/anonymous-records.md) are a new kind of F# type introduced in F# 4.6.</span></span> <span data-ttu-id="cd88d-110">Они представляют собой простые статистические выражения именованных значений, которые не нужно объявлять перед использованием.</span><span class="sxs-lookup"><span data-stu-id="cd88d-110">They are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="cd88d-111">Их можно объявить как структуры или ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="cd88d-111">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="cd88d-112">По умолчанию они являются ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="cd88d-112">They're reference types by default.</span></span>

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

<span data-ttu-id="cd88d-113">Они также могут быть объявлены как структуры для случаев, когда требуется группировать типы значений и работать в сценариях с учетом производительности.</span><span class="sxs-lookup"><span data-stu-id="cd88d-113">They can also be declared as structs for when you want to group value types and are operating in performance-sensitive scenarios:</span></span>

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

<span data-ttu-id="cd88d-114">Они являются достаточно мощными и могут использоваться во многих сценариях.</span><span class="sxs-lookup"><span data-stu-id="cd88d-114">They're quite powerful and can be used in numerous scenarios.</span></span> <span data-ttu-id="cd88d-115">Дополнительные сведения см. в статье [анонимные записи](../language-reference/anonymous-records.md).</span><span class="sxs-lookup"><span data-stu-id="cd88d-115">Learn more at [Anonymous records](../language-reference/anonymous-records.md).</span></span>

## <a name="valueoption-functions"></a><span data-ttu-id="cd88d-116">Функции Валуеоптион</span><span class="sxs-lookup"><span data-stu-id="cd88d-116">ValueOption functions</span></span>

<span data-ttu-id="cd88d-117">Тип Валуеоптион, добавленный F# в 4,5, теперь имеет тип параметра, привязанный к модулю.</span><span class="sxs-lookup"><span data-stu-id="cd88d-117">The ValueOption type added in F# 4.5 now has "module-bound function parity" with the Option type.</span></span> <span data-ttu-id="cd88d-118">Ниже приведены некоторые из наиболее часто используемых примеров.</span><span class="sxs-lookup"><span data-stu-id="cd88d-118">Some of the more commonly-used examples are as follows:</span></span>

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

<span data-ttu-id="cd88d-119">Это позволяет использовать Валуеоптион так же, как вариант в сценариях, где тип значения повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="cd88d-119">This allows for ValueOption to be used just like Option in scenarios where having a value type improves performance.</span></span>
