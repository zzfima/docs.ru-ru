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
# <a name="whats-new-in-f-45"></a><span data-ttu-id="4d229-103">Что нового в ФЗ 4.5</span><span class="sxs-lookup"><span data-stu-id="4d229-103">What's new in F# 4.5</span></span>

<span data-ttu-id="4d229-104">ФЗ 4.5 добавляет несколько улучшений в язык F..</span><span class="sxs-lookup"><span data-stu-id="4d229-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="4d229-105">Многие из этих функций были добавлены вместе, чтобы вы могли писать эффективный код в F-f, обеспечивая при этом безопасность этого кода.</span><span class="sxs-lookup"><span data-stu-id="4d229-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="4d229-106">Это означает добавление нескольких концепций к языку и значительное количество анализа компилятора при использовании этих конструкций.</span><span class="sxs-lookup"><span data-stu-id="4d229-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="4d229-107">Начало работы</span><span class="sxs-lookup"><span data-stu-id="4d229-107">Get started</span></span>

<span data-ttu-id="4d229-108">ФЗ 4.5 доступен во всех дистрибутивах .NET Core и инструментарии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4d229-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="4d229-109">[Начало работы с ФЗ,](../get-started/index.md) чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="4d229-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="4d229-110">Спан и байреф-подобные структуры</span><span class="sxs-lookup"><span data-stu-id="4d229-110">Span and byref-like structs</span></span>

<span data-ttu-id="4d229-111">Тип, <xref:System.Span%601> введенный в .NET Core, позволяет представлять буферы в памяти в сильно типидированных манере, что теперь разрешено в F-образном f, начиная с F-4.5.</span><span class="sxs-lookup"><span data-stu-id="4d229-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="4d229-112">Ниже приводится следующий пример, как можно <xref:System.Span%601> повторно использовать функцию, работающую на различных буферных представлениях:</span><span class="sxs-lookup"><span data-stu-id="4d229-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

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

<span data-ttu-id="4d229-113">Важным аспектом этого является то, что Span и другие [байреф-подобные структуры](../language-reference/structures.md#byreflike-structs) имеют очень жесткий статический анализ, выполняемый компилятором, которые ограничивают их использование таким образом, что вы можете найти, чтобы быть неожиданным.</span><span class="sxs-lookup"><span data-stu-id="4d229-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="4d229-114">Это фундаментальный компромисс между производительностью, выразительностью и безопасностью, который вводится в ФЗ 4.5.</span><span class="sxs-lookup"><span data-stu-id="4d229-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="4d229-115">Обновленные байрефы</span><span class="sxs-lookup"><span data-stu-id="4d229-115">Revamped byrefs</span></span>

<span data-ttu-id="4d229-116">До 4,5 фз, [Byrefs](../language-reference/byrefs.md) в F'были небезопасными и нездоровыми для многочисленных приложений.</span><span class="sxs-lookup"><span data-stu-id="4d229-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="4d229-117">Проблемы звукоподобия вокруг byrefs были рассмотрены в F'4.5 и тот же статический анализ, сделанный для диапазона и byref-подобных структур также был применен.</span><span class="sxs-lookup"><span data-stu-id="4d229-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="4d229-118">inref<'T> и outref<'T></span><span class="sxs-lookup"><span data-stu-id="4d229-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="4d229-119">Чтобы представить понятие только для чтения, только для записи, и читать / писать управляемый указатель, F q 4.5 вводит `inref<'T>`, `outref<'T>` типы для представления только для чтения и писать только указатели, соответственно.</span><span class="sxs-lookup"><span data-stu-id="4d229-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="4d229-120">Каждый из них имеет различные семантики.</span><span class="sxs-lookup"><span data-stu-id="4d229-120">Each have different semantics.</span></span> <span data-ttu-id="4d229-121">Например, вы не `inref<'T>`можете написать:</span><span class="sxs-lookup"><span data-stu-id="4d229-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="4d229-122">По умолчанию вывод типа будет делать вывод `inref<'T>` о том, что управляемые указатели соответствуют неизменному характеру кода F-кода, если только что-то уже объявлено невыключаемым.</span><span class="sxs-lookup"><span data-stu-id="4d229-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="4d229-123">Чтобы сделать что-то допустимым, вам нужно `mutable` объявить тип, как перед передачей его адреса функции или члена, который манипулирует им.</span><span class="sxs-lookup"><span data-stu-id="4d229-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="4d229-124">Чтобы узнать больше, смотрите [Byrefs](../language-reference/byrefs.md).</span><span class="sxs-lookup"><span data-stu-id="4d229-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="4d229-125">Только струки</span><span class="sxs-lookup"><span data-stu-id="4d229-125">Readonly structs</span></span>

<span data-ttu-id="4d229-126">Начиная с ФЗ 4.5, вы можете аннотировать <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> структуру как таковую:</span><span class="sxs-lookup"><span data-stu-id="4d229-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="4d229-127">Это запрещает вам объявлять изменяемый элемент в структуре и испускает метаданные, что позволяет F и C' относиться к нему как к простоту при потреблении из сборки.</span><span class="sxs-lookup"><span data-stu-id="4d229-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="4d229-128">Чтобы узнать больше, [см.](../language-reference/structures.md#readonly-structs)</span><span class="sxs-lookup"><span data-stu-id="4d229-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="4d229-129">Пустые указатели</span><span class="sxs-lookup"><span data-stu-id="4d229-129">Void pointers</span></span>

<span data-ttu-id="4d229-130">Тип `voidptr` добавляется в ФЗ 4.5, как и следующие функции:</span><span class="sxs-lookup"><span data-stu-id="4d229-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="4d229-131">`NativePtr.ofVoidPtr`для преобразования пустоты указатель в родной int указатель</span><span class="sxs-lookup"><span data-stu-id="4d229-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="4d229-132">`NativePtr.toVoidPtr`для преобразования родной указатель int в пустоту указатель</span><span class="sxs-lookup"><span data-stu-id="4d229-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="4d229-133">Это полезно при работе с народным компонентом, который использует недействительные указатели.</span><span class="sxs-lookup"><span data-stu-id="4d229-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="4d229-134">Ключевое слово `match!`.</span><span class="sxs-lookup"><span data-stu-id="4d229-134">The `match!` keyword</span></span>

<span data-ttu-id="4d229-135">Ключевое `match!` слово улучшает соответствие шаблона, когда внутри выражения вычислений:</span><span class="sxs-lookup"><span data-stu-id="4d229-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

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

<span data-ttu-id="4d229-136">Это позволяет сократить код, который часто включает в себя параметры смешивания (или других типов) с вычислительными выражениями, такими как async.</span><span class="sxs-lookup"><span data-stu-id="4d229-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="4d229-137">Чтобы узнать больше, смотрите [матч!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="4d229-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="4d229-138">Расслабленные требования к набору, списку и выражениям последовательности</span><span class="sxs-lookup"><span data-stu-id="4d229-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="4d229-139">Смешивание типов, где можно наследовать от другого внутри массива, список, и последовательности выражения `:>` традиционно `upcast`требуется, чтобы upcast любого производного типа его родительского типа с или .</span><span class="sxs-lookup"><span data-stu-id="4d229-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="4d229-140">Это в настоящее время расслабленным, продемонстрировано следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4d229-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="4d229-141">Релаксация отступов для выражения массива и списка</span><span class="sxs-lookup"><span data-stu-id="4d229-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="4d229-142">До того, как фз 4.5, необходимо было чрезмерно отвратить массив и перечислять выражения при передавалом в качестве аргументов для вызовов метода.</span><span class="sxs-lookup"><span data-stu-id="4d229-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="4d229-143">Это больше не требуется:</span><span class="sxs-lookup"><span data-stu-id="4d229-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
