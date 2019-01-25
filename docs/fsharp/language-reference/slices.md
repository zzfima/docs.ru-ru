---
title: Срезы (F#)
description: Дополнительные сведения об использовании срезов для существующих F# типы данных и как определить свои собственные фрагменты для других типов данных.
ms.date: 01/22/2019
ms.openlocfilehash: c204c6cbb195b33998b92dd940313a132ecc321d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746715"
---
# <a name="slices"></a><span data-ttu-id="560bc-103">Срезы</span><span class="sxs-lookup"><span data-stu-id="560bc-103">Slices</span></span>

<span data-ttu-id="560bc-104">В F#, срез представляет собой подмножество типом данных.</span><span class="sxs-lookup"><span data-stu-id="560bc-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="560bc-105">Чтобы иметь возможность выполнить срез с типом данных, необходимо либо определить тип данных `GetSlice` метода или в [введите расширение](type-extensions.md) то есть в области.</span><span class="sxs-lookup"><span data-stu-id="560bc-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="560bc-106">В этой статье объясняется, как воспользоваться фрагменты на основе существующего F# типы и как определять свои собственные.</span><span class="sxs-lookup"><span data-stu-id="560bc-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="560bc-107">Срезы, аналогичны [индексаторы](members/indexed-properties.md), но вместо одного значения из структуры данных, дают несколько сеансов.</span><span class="sxs-lookup"><span data-stu-id="560bc-107">Slices are similar to [indexers](members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="560bc-108">F#в настоящее время имеет встроенную поддержку для среза строк, списки, массивы и двухмерные массивы.</span><span class="sxs-lookup"><span data-stu-id="560bc-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="560bc-109">Основные срезов с F# списки и массивы</span><span class="sxs-lookup"><span data-stu-id="560bc-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="560bc-110">Наиболее распространенными типами данных, которые разделены являются F# списками и массивами.</span><span class="sxs-lookup"><span data-stu-id="560bc-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="560bc-111">В следующем примере показано, как это сделать с помощью списков:</span><span class="sxs-lookup"><span data-stu-id="560bc-111">The following example demonstrates how to do this with lists:</span></span>

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

<span data-ttu-id="560bc-112">Создание срезов массивы — так же, как Создание срезов списков:</span><span class="sxs-lookup"><span data-stu-id="560bc-112">Slicing arrays is just like slicing lists:</span></span>

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="560bc-113">Создание срезов многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="560bc-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="560bc-114">F#поддерживает многомерные массивы в F# основной библиотеки.</span><span class="sxs-lookup"><span data-stu-id="560bc-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="560bc-115">Как и одномерные массивы срезы многомерные массивы также можно использовать.</span><span class="sxs-lookup"><span data-stu-id="560bc-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="560bc-116">Тем не менее введение дополнительных измерений проходят различный синтаксис, благодаря чему можно использовать фрагменты из определенных строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="560bc-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="560bc-117">Следующие примеры демонстрируют, как выполнить срез двумерного массива:</span><span class="sxs-lookup"><span data-stu-id="560bc-117">The following examples demonstrate how to slice a 2D array:</span></span>

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twobyTwo
```

<span data-ttu-id="560bc-118">F# Основной библиотеки не определяет `GetSlice`3D массивов.</span><span class="sxs-lookup"><span data-stu-id="560bc-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="560bc-119">Если вы хотите разделить тех или другие массивы или более измерений, необходимо определить `GetSlice` элемент самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="560bc-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="560bc-120">Определение срезы для других структур данных</span><span class="sxs-lookup"><span data-stu-id="560bc-120">Defining slices for other data structures</span></span>

<span data-ttu-id="560bc-121">F# Библиотека ядра определяет фрагменты для ограниченного набора типов.</span><span class="sxs-lookup"><span data-stu-id="560bc-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="560bc-122">Если вы хотите определить срезы для типов данных, это можно сделать само определение типа или в расширение типа.</span><span class="sxs-lookup"><span data-stu-id="560bc-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="560bc-123">Например, вот как можно определить срезы для <xref:System.ArraySegment`1> класс, позволяющий для удобное управление данными:</span><span class="sxs-lookup"><span data-stu-id="560bc-123">For example, here's how you might define slices for the <xref:System.ArraySegment`1> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(?start, ?finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="560bc-124">Встраивание, чтобы избежать упаковки-преобразования, если это необходимо для использования</span><span class="sxs-lookup"><span data-stu-id="560bc-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="560bc-125">При определении срезы для типа, который является фактически структурой, мы рекомендуем вам `inline` `GetSlice` член.</span><span class="sxs-lookup"><span data-stu-id="560bc-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="560bc-126">F# Компилятор оптимизирует код, удаляя необязательные аргументы, как избежать выделений кучи, в результате создания срезов.</span><span class="sxs-lookup"><span data-stu-id="560bc-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="560bc-127">Это критически важно для среза конструкции, такие как <xref:System.Span`1> , не может быть выделяться в куче.</span><span class="sxs-lookup"><span data-stu-id="560bc-127">This is critically important for slicing constructs such as <xref:System.Span`1> that cannot be be allocated on the heap.</span></span>

```fsharp
open System

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a><span data-ttu-id="560bc-128">См. также</span><span class="sxs-lookup"><span data-stu-id="560bc-128">See also</span></span>

- [<span data-ttu-id="560bc-129">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="560bc-129">Indexed properties</span></span>](members/indexed-properties.md)