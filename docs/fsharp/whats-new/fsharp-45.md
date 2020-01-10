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
# <a name="whats-new-in-f-45"></a><span data-ttu-id="513d6-103">Новые возможности в F# 4,5</span><span class="sxs-lookup"><span data-stu-id="513d6-103">What's new in F# 4.5</span></span>

<span data-ttu-id="513d6-104">F#4,5 добавляет несколько улучшений в F# язык.</span><span class="sxs-lookup"><span data-stu-id="513d6-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="513d6-105">Многие из этих функций были добавлены вместе, что позволяет писать эффективный код в F# , а также обеспечивать безопасность этого кода.</span><span class="sxs-lookup"><span data-stu-id="513d6-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="513d6-106">Это означает добавление нескольких концепций к языку и значительного объема анализа компилятора при использовании этих конструкций.</span><span class="sxs-lookup"><span data-stu-id="513d6-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="513d6-107">Приступая к работе</span><span class="sxs-lookup"><span data-stu-id="513d6-107">Get started</span></span>

<span data-ttu-id="513d6-108">F#4,5 доступна во всех дистрибутивах .NET Core и средствах Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="513d6-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="513d6-109">Дополнительные сведения см. в статье Приступая к [работе с F# ](../get-started/index.md) .</span><span class="sxs-lookup"><span data-stu-id="513d6-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="513d6-110">Структуры Span и ByRef-Like</span><span class="sxs-lookup"><span data-stu-id="513d6-110">Span and byref-like structs</span></span>

<span data-ttu-id="513d6-111">Тип <xref:System.Span%601>, введенный в .NET Core, позволяет представлять буферы в памяти строго типизированным способом, который теперь разрешен в F# начале с F# 4,5.</span><span class="sxs-lookup"><span data-stu-id="513d6-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="513d6-112">В следующем примере показано, как можно повторно использовать функцию, работающую на <xref:System.Span%601> с различными представлениями буфера.</span><span class="sxs-lookup"><span data-stu-id="513d6-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

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

<span data-ttu-id="513d6-113">Важным аспектом этого является то, что диапазон и другие [структуры, подобные ByRef](../language-reference/structures.md#byreflike-structs) , имеют очень строгий статический анализ, выполняемый компилятором, который ограничивает их использование способами, которые могут оказаться неожиданными.</span><span class="sxs-lookup"><span data-stu-id="513d6-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="513d6-114">Это фундаментальный компромисс между производительностью, выразительным и безопасностью, представленным в F# 4,5.</span><span class="sxs-lookup"><span data-stu-id="513d6-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="513d6-115">Пересмотренные ByRef</span><span class="sxs-lookup"><span data-stu-id="513d6-115">Revamped byrefs</span></span>

<span data-ttu-id="513d6-116">До F# 4,5, [ByRef](../language-reference/byrefs.md) в F# были ненадежными и незвуковыми для многочисленных приложений.</span><span class="sxs-lookup"><span data-stu-id="513d6-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="513d6-117">Проблемы с звуком в параметрах ByRef были устранены в F# 4,5, а также был применен один и тот же статический анализ для структур, связанных с Span и ByRef.</span><span class="sxs-lookup"><span data-stu-id="513d6-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="513d6-118">инреф < > и аутреф < ></span><span class="sxs-lookup"><span data-stu-id="513d6-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="513d6-119">Чтобы представить понятие управляемого указателя, доступного только для чтения, только для записи и чтения и записи, F# 4,5 вводит `inref<'T>`, `outref<'T>` типы для представления указателей только для чтения и только для записи, соответственно.</span><span class="sxs-lookup"><span data-stu-id="513d6-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="513d6-120">Каждый из них имеет разную семантику.</span><span class="sxs-lookup"><span data-stu-id="513d6-120">Each have different semantics.</span></span> <span data-ttu-id="513d6-121">Например, невозможно выполнить запись в `inref<'T>`:</span><span class="sxs-lookup"><span data-stu-id="513d6-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="513d6-122">По умолчанию вывод типа будет выводить управляемые указатели как `inref<'T>` в виде неизменяемой природы F# кода, если только что не было объявлено как изменяющееся.</span><span class="sxs-lookup"><span data-stu-id="513d6-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="513d6-123">Чтобы сделать запись доступной для записи, необходимо объявить тип как `mutable` перед передачей его адреса в функцию или член, управляющий этим элементом.</span><span class="sxs-lookup"><span data-stu-id="513d6-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="513d6-124">Дополнительные сведения см. в разделе [ByRef](../language-reference/byrefs.md).</span><span class="sxs-lookup"><span data-stu-id="513d6-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="513d6-125">Структуры только для чтения</span><span class="sxs-lookup"><span data-stu-id="513d6-125">Readonly structs</span></span>

<span data-ttu-id="513d6-126">Начиная с F# 4,5 можно снабдить структуру аннотацией <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> следующим образом:</span><span class="sxs-lookup"><span data-stu-id="513d6-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="513d6-127">Это не позволяет объявить изменяемый элемент в структуре и выдает метаданные, которые позволяют F# и C# обрабатывать его как ReadOnly при использовании из сборки.</span><span class="sxs-lookup"><span data-stu-id="513d6-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="513d6-128">Дополнительные сведения см. в разделе [структуры только для чтения](../language-reference/structures.md#readonly-structs).</span><span class="sxs-lookup"><span data-stu-id="513d6-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="513d6-129">Указатели void</span><span class="sxs-lookup"><span data-stu-id="513d6-129">Void pointers</span></span>

<span data-ttu-id="513d6-130">Тип `voidptr` добавляется в F# 4,5, как в следующих функциях:</span><span class="sxs-lookup"><span data-stu-id="513d6-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="513d6-131">`NativePtr.ofVoidPtr` преобразовать указатель void в собственный указатель int</span><span class="sxs-lookup"><span data-stu-id="513d6-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="513d6-132">`NativePtr.toVoidPtr` преобразовать собственный указатель int в указатель void</span><span class="sxs-lookup"><span data-stu-id="513d6-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="513d6-133">Это полезно при взаимодействии с собственным компонентом, который использует указатели void.</span><span class="sxs-lookup"><span data-stu-id="513d6-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="513d6-134">Ключевое слово `match!`.</span><span class="sxs-lookup"><span data-stu-id="513d6-134">The `match!` keyword</span></span>

<span data-ttu-id="513d6-135">Ключевое слово `match!` улучшает сопоставление шаблонов в вычислительном выражении:</span><span class="sxs-lookup"><span data-stu-id="513d6-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

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

<span data-ttu-id="513d6-136">Это позволяет сократить код, который часто включает в себя смешение параметров (или других типов) с вычислительными выражениями, такими как async.</span><span class="sxs-lookup"><span data-stu-id="513d6-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="513d6-137">Дополнительные сведения см. в разделе [Match!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="513d6-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="513d6-138">Ослабленные требования к преобразованию в выражениях массивов, списков и последовательностей</span><span class="sxs-lookup"><span data-stu-id="513d6-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="513d6-139">Смешивание типов, которые могут наследовать друг от друга в выражениях массивов, списков и последовательностей, традиционно требовали преобразования любого производного типа в его родительский тип с `:>` или `upcast`.</span><span class="sxs-lookup"><span data-stu-id="513d6-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="513d6-140">Теперь это неявное, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="513d6-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="513d6-141">Ослабление отступов для выражений массива и списка</span><span class="sxs-lookup"><span data-stu-id="513d6-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="513d6-142">До F# 4,5 требовалось слишком много отступов массивов и выражений списка при передаче в качестве аргументов в вызовы методов.</span><span class="sxs-lookup"><span data-stu-id="513d6-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="513d6-143">Это больше не требуется:</span><span class="sxs-lookup"><span data-stu-id="513d6-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting = 
    System.Console.WriteLine(format="{0}", arg = [| 
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
