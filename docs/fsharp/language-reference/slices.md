---
title: Срезы (F#)
description: Узнайте, как использовать срезы для существующих F# типов данных и как определять собственные срезы для других типов данных.
ms.date: 01/22/2019
ms.openlocfilehash: cbff1b055ea99ef708f9db191be49275e630ee90
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72798903"
---
# <a name="slices"></a><span data-ttu-id="bbe53-103">Срезы</span><span class="sxs-lookup"><span data-stu-id="bbe53-103">Slices</span></span>

<span data-ttu-id="bbe53-104">В F#срез является подмножеством типа данных.</span><span class="sxs-lookup"><span data-stu-id="bbe53-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="bbe53-105">Чтобы иметь возможность взять срез из типа данных, тип данных должен либо определить `GetSlice` метод, либо [расширение типа](type-extensions.md) , которое находится в области.</span><span class="sxs-lookup"><span data-stu-id="bbe53-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="bbe53-106">В этой статье объясняется, как выполнять срезы F# из существующих типов и как определять собственные.</span><span class="sxs-lookup"><span data-stu-id="bbe53-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="bbe53-107">Срезы похожи на [индексаторы](./members/indexed-properties.md), но вместо получения одного значения из базовой структуры данных они получают несколько.</span><span class="sxs-lookup"><span data-stu-id="bbe53-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="bbe53-108">F#в настоящее время имеет встроенную поддержку для срезов строк, списков, массивов и двумерных массивов.</span><span class="sxs-lookup"><span data-stu-id="bbe53-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="bbe53-109">Базовые срезы с F# списками и массивами</span><span class="sxs-lookup"><span data-stu-id="bbe53-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="bbe53-110">Наиболее распространенными типами данных, которые являются срезами F# , являются списки и массивы.</span><span class="sxs-lookup"><span data-stu-id="bbe53-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="bbe53-111">В следующем примере показано, как это сделать с помощью списков.</span><span class="sxs-lookup"><span data-stu-id="bbe53-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="bbe53-112">Массивы срезов так же, как и списки срезов:</span><span class="sxs-lookup"><span data-stu-id="bbe53-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="bbe53-113">Многомерные массивы с срезами</span><span class="sxs-lookup"><span data-stu-id="bbe53-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="bbe53-114">F#поддерживает многомерные массивы в F# основной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="bbe53-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="bbe53-115">Как и в случае с одномерным массивами, можно также использовать срезы многомерных массивов.</span><span class="sxs-lookup"><span data-stu-id="bbe53-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="bbe53-116">Однако введение дополнительных измерений требует немного другого синтаксиса, чтобы можно было создавать срезы конкретных строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="bbe53-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="bbe53-117">В следующих примерах показано, как выполнить срез 2D-массива:</span><span class="sxs-lookup"><span data-stu-id="bbe53-117">The following examples demonstrate how to slice a 2D array:</span></span>

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
printfn "%A" twoByTwo
```

<span data-ttu-id="bbe53-118">F# Базовая библиотека не определяет`GetSlice`для трехмерных массивов.</span><span class="sxs-lookup"><span data-stu-id="bbe53-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="bbe53-119">Если вы хотите выполнить срез этих или других массивов большего размера, необходимо вручную определить элемент `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="bbe53-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="bbe53-120">Определение срезов для других структур данных</span><span class="sxs-lookup"><span data-stu-id="bbe53-120">Defining slices for other data structures</span></span>

<span data-ttu-id="bbe53-121">F# Основная библиотека определяет срезы для ограниченного набора типов.</span><span class="sxs-lookup"><span data-stu-id="bbe53-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="bbe53-122">Если вы хотите определить срезы для большего числа типов данных, это можно сделать либо в самом определении типа, либо в расширении типа.</span><span class="sxs-lookup"><span data-stu-id="bbe53-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="bbe53-123">Например, ниже показано, как можно определить срезы для класса <xref:System.ArraySegment%601>, чтобы обеспечить удобную обработку данных:</span><span class="sxs-lookup"><span data-stu-id="bbe53-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="bbe53-124">Используйте встраивание, чтобы избежать упаковки-преобразования в случае необходимости</span><span class="sxs-lookup"><span data-stu-id="bbe53-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="bbe53-125">При определении срезов для типа, который фактически является структурой, рекомендуется `inline` элемент `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="bbe53-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="bbe53-126">F# Компилятор оптимизирует необязательные аргументы, избегая выделения кучи в результате среза.</span><span class="sxs-lookup"><span data-stu-id="bbe53-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="bbe53-127">Это критически важно для конструкций среза, таких как <xref:System.Span%601>, которые не могут быть выделены в куче.</span><span class="sxs-lookup"><span data-stu-id="bbe53-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bbe53-128">См. также</span><span class="sxs-lookup"><span data-stu-id="bbe53-128">See also</span></span>

- [<span data-ttu-id="bbe53-129">Индексированные свойства</span><span class="sxs-lookup"><span data-stu-id="bbe53-129">Indexed properties</span></span>](./members/indexed-properties.md)
