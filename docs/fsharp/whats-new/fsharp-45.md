---
title: Новые возможности в F# 4,5- F# Guide
description: Ознакомьтесь с обзором новых функций, доступных в F# 4,5.
ms.date: 11/27/2019
ms.openlocfilehash: b699165125d345ad783b24da8a0a994cba72d4ba
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715688"
---
# <a name="whats-new-in-f-45"></a>Новые возможности в F# 4,5

F#4,5 добавляет несколько улучшений в F# язык. Многие из этих функций были добавлены вместе, что позволяет писать эффективный код в F# , а также обеспечивать безопасность этого кода. Это означает добавление нескольких концепций к языку и значительного объема анализа компилятора при использовании этих конструкций.

## <a name="get-started"></a>Приступая к работе

F#4,5 доступна во всех дистрибутивах .NET Core и средствах Visual Studio. Дополнительные сведения см. в статье Приступая к [работе с F# ](../get-started/index.md) .

## <a name="span-and-byref-like-structs"></a>Структуры Span и ByRef-Like

Тип <xref:System.Span%601>, введенный в .NET Core, позволяет представлять буферы в памяти строго типизированным способом, который теперь разрешен в F# начале с F# 4,5. В следующем примере показано, как можно повторно использовать функцию, работающую на <xref:System.Span%601> с различными представлениями буфера.

```fsharp
let safeSum (bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do 
        sum <- sum + int bytes.[i]
    sum

// managed memory
let arrayMemory = Array.zeroCreate<byte>(100)
let arraySpan = new Span<byte>(arrayMemory)

safeSum(arraySpan) |> printfn "res = %d"

// native memory
let nativeMemory = Marshal.AllocHGlobal(100);
let nativeSpan = new Span<byte>(nativeMemory.ToPointer(), 100)

safeSum(nativeSpan) |> printfn "res = %d"
Marshal.FreeHGlobal(nativeMemory)

// stack memory
let mem = NativePtr.stackalloc<byte>(100)
let mem2 = mem |> NativePtr.toVoidPtr
let stackSpan = Span<byte>(mem2, 100)

safeSum(stackSpan) |> printfn "res = %d"
```

Важным аспектом этого является то, что диапазон и другие [структуры, подобные ByRef](../language-reference/structures.md#byreflike-structs) , имеют очень строгий статический анализ, выполняемый компилятором, который ограничивает их использование способами, которые могут оказаться неожиданными. Это фундаментальный компромисс между производительностью, выразительным и безопасностью, представленным в F# 4,5.

## <a name="revamped-byrefs"></a>Пересмотренные ByRef

До F# 4,5, [ByRef](../language-reference/byrefs.md) в F# были ненадежными и незвуковыми для многочисленных приложений. Проблемы с звуком в параметрах ByRef были устранены в F# 4,5, а также был применен один и тот же статический анализ для структур, связанных с Span и ByRef.

### <a name="inreft-and-outreft"></a>инреф < > и аутреф < >

Чтобы представить понятие управляемого указателя, доступного только для чтения, только для записи и чтения и записи, F# 4,5 вводит `inref<'T>`, `outref<'T>` типы для представления указателей только для чтения и только для записи, соответственно. Каждый из них имеет разную семантику. Например, невозможно выполнить запись в `inref<'T>`:

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

По умолчанию вывод типа будет выводить управляемые указатели как `inref<'T>` в виде неизменяемой природы F# кода, если только что не было объявлено как изменяющееся. Чтобы сделать запись доступной для записи, необходимо объявить тип как `mutable` перед передачей его адреса в функцию или член, управляющий этим элементом. Дополнительные сведения см. в разделе [ByRef](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Структуры только для чтения

Начиная с F# 4,5 можно снабдить структуру аннотацией <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> следующим образом:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Это не позволяет объявить изменяемый элемент в структуре и выдает метаданные, которые позволяют F# и C# обрабатывать его как ReadOnly при использовании из сборки. Дополнительные сведения см. в разделе [структуры только для чтения](../language-reference/structures.md#readonly-structs).

## <a name="void-pointers"></a>Указатели void

Тип `voidptr` добавляется в F# 4,5, как в следующих функциях:

* `NativePtr.ofVoidPtr` преобразовать указатель void в собственный указатель int
* `NativePtr.toVoidPtr` преобразовать собственный указатель int в указатель void

Это полезно при взаимодействии с собственным компонентом, который использует указатели void.

## <a name="the-match-keyword"></a>Ключевое слово `match!`.

Ключевое слово `match!` улучшает сопоставление шаблонов в вычислительном выражении:

```fsharp
// Code that returns an asynchronous option
let checkBananaAsync (s: string) =
    async {
        if s = "banana" then
            return Some s
        else
            return None
    }
    
// Now you can use 'match!'
let funcWithString (s: string) =
    async { 
        match! checkBananaAsync s with
        | Some bananaString -> printfn "It's banana!"
        | None -> printfn "%s" s
}
```

Это позволяет сократить код, который часто включает в себя смешение параметров (или других типов) с вычислительными выражениями, такими как async. Дополнительные сведения см. в разделе [Match!](../language-reference/computation-expressions.md#match).

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a>Ослабленные требования к преобразованию в выражениях массивов, списков и последовательностей

Смешивание типов, которые могут наследовать друг от друга в выражениях массивов, списков и последовательностей, традиционно требовали преобразования любого производного типа в его родительский тип с `:>` или `upcast`. Теперь это неявное, как показано ниже.

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Ослабление отступов для выражений массива и списка

До F# 4,5 требовалось слишком много отступов массивов и выражений списка при передаче в качестве аргументов в вызовы методов. Это больше не требуется:

```fsharp
module NoExcessiveIndenting = 
    System.Console.WriteLine(format="{0}", arg = [| 
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
