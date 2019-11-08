---
title: Срезы (F#)
description: Узнайте, как использовать срезы для существующих F# типов данных и как определять собственные срезы для других типов данных.
ms.date: 01/22/2019
ms.openlocfilehash: 2f7b87cda87aad1fdac05b4e14b16f454f8c0461
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733372"
---
# <a name="slices"></a>Срезы

В F#срез является подмножеством типа данных. Чтобы иметь возможность взять срез из типа данных, тип данных должен либо определить `GetSlice` метод, либо [расширение типа](type-extensions.md) , которое находится в области. В этой статье объясняется, как выполнять срезы F# из существующих типов и как определять собственные.

Срезы похожи на [индексаторы](./members/indexed-properties.md), но вместо получения одного значения из базовой структуры данных они получают несколько.

F#в настоящее время имеет встроенную поддержку для срезов строк, списков, массивов и двумерных массивов.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>Базовые срезы с F# списками и массивами

Наиболее распространенными типами данных, которые являются срезами F# , являются списки и массивы. В следующем примере показано, как это сделать с помощью списков.

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

Массивы срезов так же, как и списки срезов:

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

## <a name="slicing-multidimensional-arrays"></a>Многомерные массивы с срезами

F#поддерживает многомерные массивы в F# основной библиотеке. Как и в случае с одномерным массивами, можно также использовать срезы многомерных массивов. Однако введение дополнительных измерений требует немного другого синтаксиса, чтобы можно было создавать срезы конкретных строк и столбцов.

В следующих примерах показано, как выполнить срез 2D-массива:

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

F# Базовая библиотека не определяет`GetSlice`для трехмерных массивов. Если вы хотите выполнить срез этих или других массивов большего размера, необходимо вручную определить элемент `GetSlice`.

## <a name="defining-slices-for-other-data-structures"></a>Определение срезов для других структур данных

F# Основная библиотека определяет срезы для ограниченного набора типов. Если вы хотите определить срезы для большего числа типов данных, это можно сделать либо в самом определении типа, либо в расширении типа.

Например, ниже показано, как можно определить срезы для класса <xref:System.ArraySegment%601>, чтобы обеспечить удобную обработку данных:

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>Используйте встраивание, чтобы избежать упаковки-преобразования в случае необходимости

При определении срезов для типа, который фактически является структурой, рекомендуется `inline` элемент `GetSlice`. F# Компилятор оптимизирует необязательные аргументы, избегая выделения кучи в результате среза. Это критически важно для конструкций среза, таких как <xref:System.Span%601>, которые не могут быть выделены в куче.

```fsharp
open System

type ReadOnlySpan<'T> with
    // Note the 'inline' in the member definition
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a>См. также

- [Индексированные свойства](./members/indexed-properties.md)
