---
title: Что нового в F- 4.5 - F' Руководство
description: Получить обзор новых функций, доступных в ФЗ 4.5.
ms.date: 11/27/2019
ms.openlocfilehash: 560e3dd941f79b76d3b864ba0f6560be154ebc1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186133"
---
# <a name="whats-new-in-f-45"></a>Что нового в ФЗ 4.5

ФЗ 4.5 добавляет несколько улучшений в язык F.. Многие из этих функций были добавлены вместе, чтобы вы могли писать эффективный код в F-f, обеспечивая при этом безопасность этого кода. Это означает добавление нескольких концепций к языку и значительное количество анализа компилятора при использовании этих конструкций.

## <a name="get-started"></a>Начало работы

ФЗ 4.5 доступен во всех дистрибутивах .NET Core и инструментарии Visual Studio. [Начало работы с ФЗ,](../get-started/index.md) чтобы узнать больше.

## <a name="span-and-byref-like-structs"></a>Спан и байреф-подобные структуры

Тип, <xref:System.Span%601> введенный в .NET Core, позволяет представлять буферы в памяти в сильно типидированных манере, что теперь разрешено в F-образном f, начиная с F-4.5. Ниже приводится следующий пример, как можно <xref:System.Span%601> повторно использовать функцию, работающую на различных буферных представлениях:

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

Важным аспектом этого является то, что Span и другие [байреф-подобные структуры](../language-reference/structures.md#byreflike-structs) имеют очень жесткий статический анализ, выполняемый компилятором, которые ограничивают их использование таким образом, что вы можете найти, чтобы быть неожиданным. Это фундаментальный компромисс между производительностью, выразительностью и безопасностью, который вводится в ФЗ 4.5.

## <a name="revamped-byrefs"></a>Обновленные байрефы

До 4,5 фз, [Byrefs](../language-reference/byrefs.md) в F'были небезопасными и нездоровыми для многочисленных приложений. Проблемы звукоподобия вокруг byrefs были рассмотрены в F'4.5 и тот же статический анализ, сделанный для диапазона и byref-подобных структур также был применен.

### <a name="inreft-and-outreft"></a>inref<'T> и outref<'T>

Чтобы представить понятие только для чтения, только для записи, и читать / писать управляемый указатель, F q 4.5 вводит `inref<'T>`, `outref<'T>` типы для представления только для чтения и писать только указатели, соответственно. Каждый из них имеет различные семантики. Например, вы не `inref<'T>`можете написать:

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

По умолчанию вывод типа будет делать вывод `inref<'T>` о том, что управляемые указатели соответствуют неизменному характеру кода F-кода, если только что-то уже объявлено невыключаемым. Чтобы сделать что-то допустимым, вам нужно `mutable` объявить тип, как перед передачей его адреса функции или члена, который манипулирует им. Чтобы узнать больше, смотрите [Byrefs](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Только струки

Начиная с ФЗ 4.5, вы можете аннотировать <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> структуру как таковую:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Это запрещает вам объявлять изменяемый элемент в структуре и испускает метаданные, что позволяет F и C' относиться к нему как к простоту при потреблении из сборки. Чтобы узнать больше, [см.](../language-reference/structures.md#readonly-structs)

## <a name="void-pointers"></a>Пустые указатели

Тип `voidptr` добавляется в ФЗ 4.5, как и следующие функции:

* `NativePtr.ofVoidPtr`для преобразования пустоты указатель в родной int указатель
* `NativePtr.toVoidPtr`для преобразования родной указатель int в пустоту указатель

Это полезно при работе с народным компонентом, который использует недействительные указатели.

## <a name="the-match-keyword"></a>Ключевое слово `match!`.

Ключевое `match!` слово улучшает соответствие шаблона, когда внутри выражения вычислений:

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

Это позволяет сократить код, который часто включает в себя параметры смешивания (или других типов) с вычислительными выражениями, такими как async. Чтобы узнать больше, смотрите [матч!](../language-reference/computation-expressions.md#match).

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a>Расслабленные требования к набору, списку и выражениям последовательности

Смешивание типов, где можно наследовать от другого внутри массива, список, и последовательности выражения `:>` традиционно `upcast`требуется, чтобы upcast любого производного типа его родительского типа с или . Это в настоящее время расслабленным, продемонстрировано следующим образом:

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Релаксация отступов для выражения массива и списка

До того, как фз 4.5, необходимо было чрезмерно отвратить массив и перечислять выражения при передавалом в качестве аргументов для вызовов метода. Это больше не требуется:

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
