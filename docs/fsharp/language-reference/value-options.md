---
title: 'Параметры значения (F #)'
description: 'Дополнительные сведения о типе параметра значения F #, — версии структуры типа параметра.'
ms.date: 06/16/2018
ms.openlocfilehash: 5647ef61725401b10a6045b14eef11f5b041e3e9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43747504"
---
# <a name="value-options"></a><span data-ttu-id="51a7e-103">Параметры значения</span><span class="sxs-lookup"><span data-stu-id="51a7e-103">Value Options</span></span>

<span data-ttu-id="51a7e-104">Тип значения параметра в F # используется при проведении следующих двух случаях:</span><span class="sxs-lookup"><span data-stu-id="51a7e-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="51a7e-105">Сценарий подходит для [F # параметр](options.md).</span><span class="sxs-lookup"><span data-stu-id="51a7e-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="51a7e-106">С помощью структуры обеспечивает повышение производительности в вашем сценарии.</span><span class="sxs-lookup"><span data-stu-id="51a7e-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="51a7e-107">Не все сценарии быстродействие» разрешаются» с помощью структуры.</span><span class="sxs-lookup"><span data-stu-id="51a7e-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="51a7e-108">Необходимо учитывать дополнительные издержки копирования при использовании их вместо ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="51a7e-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="51a7e-109">Тем не менее больших программах F # обычно установить многие дополнительные типы, которые проходят через критических путей, так как структуры, иногда могут выдавать улучшить общую производительность в течение времени существования программы.</span><span class="sxs-lookup"><span data-stu-id="51a7e-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, because structs can sometimes yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="51a7e-110">Определение</span><span class="sxs-lookup"><span data-stu-id="51a7e-110">Definition</span></span>

<span data-ttu-id="51a7e-111">Значение параметра определяется как [размеченные объединения](discriminated-unions.md#struct-discriminated-unions) , похож на ссылочный тип параметра:</span><span class="sxs-lookup"><span data-stu-id="51a7e-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpValueOption`1")>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone: 'T voption
    | ValueSome: 'T -> 'T voption

    member Value : 'T

and 'T voption = ValueOption<'T>
```

<span data-ttu-id="51a7e-112">Значение параметра соответствует структурного равенства и сравнения.</span><span class="sxs-lookup"><span data-stu-id="51a7e-112">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="51a7e-113">Основное различие является то, что скомпилированный имя, имя типа и регистра имен указать, что не типом значения.</span><span class="sxs-lookup"><span data-stu-id="51a7e-113">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="51a7e-114">С помощью параметров значений</span><span class="sxs-lookup"><span data-stu-id="51a7e-114">Using Value Options</span></span>

<span data-ttu-id="51a7e-115">Параметры значения используются так же, как [параметры](options.md).</span><span class="sxs-lookup"><span data-stu-id="51a7e-115">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="51a7e-116">`ValueSome` Указывает, что значение будет присутствовать, и `ValueNone` используется, если значение отсутствует:</span><span class="sxs-lookup"><span data-stu-id="51a7e-116">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

<span data-ttu-id="51a7e-117">Как и в [параметры](options.md), соглашение об именовании для функции, которая возвращает `ValueOption` является перед ними `try`.</span><span class="sxs-lookup"><span data-stu-id="51a7e-117">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="51a7e-118">Значение параметра свойства и методы</span><span class="sxs-lookup"><span data-stu-id="51a7e-118">Value Option properties and methods</span></span>

<span data-ttu-id="51a7e-119">В настоящее время есть одно свойство для возможных значений: `Value`.</span><span class="sxs-lookup"><span data-stu-id="51a7e-119">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="51a7e-120"><xref:System.InvalidOperationException> Возникает, если значение не присутствует, при вызове этого свойства.</span><span class="sxs-lookup"><span data-stu-id="51a7e-120">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="51a7e-121">Значение параметра функции</span><span class="sxs-lookup"><span data-stu-id="51a7e-121">Value Option functions</span></span>

<span data-ttu-id="51a7e-122">В данный момент одного связанного с модулем функции для параметров значение `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="51a7e-122">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

<span data-ttu-id="51a7e-123">Как и в `defaultArg` функции `defaultValueArg` Возвращает базовое значение данного параметра значение, если он существует; в противном случае возвращает значение указанного по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51a7e-123">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="51a7e-124">В настоящее время нет других функций связанного с модулем для возможных значений.</span><span class="sxs-lookup"><span data-stu-id="51a7e-124">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="51a7e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="51a7e-125">See also</span></span>

- [<span data-ttu-id="51a7e-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="51a7e-126">Options</span></span>](options.md)