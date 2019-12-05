---
title: Параметры значений
description: Сведения о типе F# параметра value, который является структурной версией типа параметра.
ms.date: 12/04/2019
ms.openlocfilehash: 0e9882ab4acdf2757705ef6022516d3572d87ef2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837120"
---
# <a name="value-options"></a><span data-ttu-id="7c0d5-103">Параметры значений</span><span class="sxs-lookup"><span data-stu-id="7c0d5-103">Value Options</span></span>

<span data-ttu-id="7c0d5-104">Тип параметра значения в используется F# в следующих двух обстоятельствах:</span><span class="sxs-lookup"><span data-stu-id="7c0d5-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="7c0d5-105">Сценарий подходит для [ F# параметра](options.md).</span><span class="sxs-lookup"><span data-stu-id="7c0d5-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="7c0d5-106">Использование структуры обеспечивает выигрыш в производительности в вашем сценарии.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="7c0d5-107">Не все сценарии с учетом производительности являются "решенными" с помощью структур.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="7c0d5-108">При использовании вместо ссылочных типов необходимо учитывать дополнительные затраты на копирование.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="7c0d5-109">Однако крупные F# программы часто создают множество необязательных типов, которые проходят через критические пути. в таких случаях структуры часто могут повысить общую производительность в течение всего времени существования программы.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="7c0d5-110">Определение</span><span class="sxs-lookup"><span data-stu-id="7c0d5-110">Definition</span></span>

<span data-ttu-id="7c0d5-111">Параметр значения определен как [размеченное объединение структуры](discriminated-unions.md#struct-discriminated-unions) , похожее на тип параметра ссылки.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="7c0d5-112">Его определение можно рассматривать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7c0d5-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="7c0d5-113">Параметр value соответствует структурному равенству и сравнению.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="7c0d5-114">Основное отличие состоит в том, что имя, имя типа и имена вариантов, как и названия регистров, указывают, что это тип значения.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="7c0d5-115">Использование параметров значения</span><span class="sxs-lookup"><span data-stu-id="7c0d5-115">Using Value Options</span></span>

<span data-ttu-id="7c0d5-116">Параметры значения используются так же, как и [Параметры](options.md).</span><span class="sxs-lookup"><span data-stu-id="7c0d5-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="7c0d5-117">`ValueSome` используется для указания на присутствие значения, а `ValueNone` используется, если отсутствует значение:</span><span class="sxs-lookup"><span data-stu-id="7c0d5-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

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

<span data-ttu-id="7c0d5-118">Как и в случае с [параметрами](options.md), соглашение об именовании для функции, возвращающей `ValueOption`, имеет префикс `try`.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="7c0d5-119">Свойства и методы параметра value</span><span class="sxs-lookup"><span data-stu-id="7c0d5-119">Value Option properties and methods</span></span>

<span data-ttu-id="7c0d5-120">В настоящее время имеется одно свойство параметров значения: `Value`.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="7c0d5-121">Если при вызове этого свойства значение не указано, вызывается <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="7c0d5-122">Функции параметров значений</span><span class="sxs-lookup"><span data-stu-id="7c0d5-122">Value Option functions</span></span>

<span data-ttu-id="7c0d5-123">Модуль `ValueOption` в FSharp. Core содержит эквивалентные функции для модуля `Option`.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-123">The `ValueOption` module in FSharp.Core contains equivalent functionality to the `Option` module.</span></span> <span data-ttu-id="7c0d5-124">Существует несколько отличий в имени, например `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="7c0d5-124">There are a few differences in name, such as `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

<span data-ttu-id="7c0d5-125">Это действует так же, как `defaultArg` в модуле `Option`, но работает вместо параметра значения.</span><span class="sxs-lookup"><span data-stu-id="7c0d5-125">This acts just like `defaultArg` in the `Option` module, but operates on a Value Option instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c0d5-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c0d5-126">See also</span></span>

- [<span data-ttu-id="7c0d5-127">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c0d5-127">Options</span></span>](options.md)
