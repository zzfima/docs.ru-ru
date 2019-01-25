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
# <a name="slices"></a>Срезы

В F#, срез представляет собой подмножество типом данных. Чтобы иметь возможность выполнить срез с типом данных, необходимо либо определить тип данных `GetSlice` метода или в [введите расширение](type-extensions.md) то есть в области. В этой статье объясняется, как воспользоваться фрагменты на основе существующего F# типы и как определять свои собственные.

Срезы, аналогичны [индексаторы](members/indexed-properties.md), но вместо одного значения из структуры данных, дают несколько сеансов.

F#в настоящее время имеет встроенную поддержку для среза строк, списки, массивы и двухмерные массивы.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>Основные срезов с F# списки и массивы

Наиболее распространенными типами данных, которые разделены являются F# списками и массивами. В следующем примере показано, как это сделать с помощью списков:

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

Создание срезов массивы — так же, как Создание срезов списков:

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

## <a name="slicing-multidimensional-arrays"></a>Создание срезов многомерные массивы

F#поддерживает многомерные массивы в F# основной библиотеки. Как и одномерные массивы срезы многомерные массивы также можно использовать. Тем не менее введение дополнительных измерений проходят различный синтаксис, благодаря чему можно использовать фрагменты из определенных строк и столбцов.

Следующие примеры демонстрируют, как выполнить срез двумерного массива:

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

F# Основной библиотеки не определяет `GetSlice`3D массивов. Если вы хотите разделить тех или другие массивы или более измерений, необходимо определить `GetSlice` элемент самостоятельно.

## <a name="defining-slices-for-other-data-structures"></a>Определение срезы для других структур данных

F# Библиотека ядра определяет фрагменты для ограниченного набора типов. Если вы хотите определить срезы для типов данных, это можно сделать само определение типа или в расширение типа.

Например, вот как можно определить срезы для <xref:System.ArraySegment`1> класс, позволяющий для удобное управление данными:

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>Встраивание, чтобы избежать упаковки-преобразования, если это необходимо для использования

При определении срезы для типа, который является фактически структурой, мы рекомендуем вам `inline` `GetSlice` член. F# Компилятор оптимизирует код, удаляя необязательные аргументы, как избежать выделений кучи, в результате создания срезов. Это критически важно для среза конструкции, такие как <xref:System.Span`1> , не может быть выделяться в куче.

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

## <a name="see-also"></a>См. также

- [Индексированные свойства](members/indexed-properties.md)