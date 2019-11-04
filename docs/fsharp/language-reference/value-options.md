---
title: Параметры значений
description: Сведения о типе F# параметра value, который является структурной версией типа параметра.
ms.date: 02/06/2019
ms.openlocfilehash: 4dc3f7217943345b7aaf1165fd648ab2e01bd727
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424021"
---
# <a name="value-options"></a><span data-ttu-id="fe609-103">Параметры значений</span><span class="sxs-lookup"><span data-stu-id="fe609-103">Value Options</span></span>

<span data-ttu-id="fe609-104">Тип параметра значения в используется F# в следующих двух обстоятельствах:</span><span class="sxs-lookup"><span data-stu-id="fe609-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="fe609-105">Сценарий подходит для [ F# параметра](options.md).</span><span class="sxs-lookup"><span data-stu-id="fe609-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="fe609-106">Использование структуры обеспечивает выигрыш в производительности в вашем сценарии.</span><span class="sxs-lookup"><span data-stu-id="fe609-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="fe609-107">Не все сценарии с учетом производительности являются "решенными" с помощью структур.</span><span class="sxs-lookup"><span data-stu-id="fe609-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="fe609-108">При использовании вместо ссылочных типов необходимо учитывать дополнительные затраты на копирование.</span><span class="sxs-lookup"><span data-stu-id="fe609-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="fe609-109">Однако крупные F# программы часто создают множество необязательных типов, которые проходят через критические пути. в таких случаях структуры часто могут повысить общую производительность в течение всего времени существования программы.</span><span class="sxs-lookup"><span data-stu-id="fe609-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="fe609-110">Определение</span><span class="sxs-lookup"><span data-stu-id="fe609-110">Definition</span></span>

<span data-ttu-id="fe609-111">Параметр значения определен как [размеченное объединение структуры](discriminated-unions.md#struct-discriminated-unions) , похожее на тип параметра ссылки.</span><span class="sxs-lookup"><span data-stu-id="fe609-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="fe609-112">Его определение можно рассматривать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fe609-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="fe609-113">Параметр value соответствует структурному равенству и сравнению.</span><span class="sxs-lookup"><span data-stu-id="fe609-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="fe609-114">Основное отличие состоит в том, что имя, имя типа и имена вариантов, как и названия регистров, указывают, что это тип значения.</span><span class="sxs-lookup"><span data-stu-id="fe609-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="fe609-115">Использование параметров значения</span><span class="sxs-lookup"><span data-stu-id="fe609-115">Using Value Options</span></span>

<span data-ttu-id="fe609-116">Параметры значения используются так же, как и [Параметры](options.md).</span><span class="sxs-lookup"><span data-stu-id="fe609-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="fe609-117">`ValueSome` используется для указания на присутствие значения, а `ValueNone` используется, если отсутствует значение:</span><span class="sxs-lookup"><span data-stu-id="fe609-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

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

<span data-ttu-id="fe609-118">Как и в случае с [параметрами](options.md), соглашение об именовании для функции, возвращающей `ValueOption`, имеет префикс `try`.</span><span class="sxs-lookup"><span data-stu-id="fe609-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="fe609-119">Свойства и методы параметра value</span><span class="sxs-lookup"><span data-stu-id="fe609-119">Value Option properties and methods</span></span>

<span data-ttu-id="fe609-120">В настоящее время имеется одно свойство параметров значения: `Value`.</span><span class="sxs-lookup"><span data-stu-id="fe609-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="fe609-121">Если при вызове этого свойства значение не указано, вызывается <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="fe609-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="fe609-122">Функции параметров значений</span><span class="sxs-lookup"><span data-stu-id="fe609-122">Value Option functions</span></span>

<span data-ttu-id="fe609-123">В настоящее время существует одна функция, привязанная к модулю, для параметров значения `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="fe609-123">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

<span data-ttu-id="fe609-124">Как и в случае с функцией `defaultArg`, `defaultValueArg` Возвращает базовое значение данного параметра значения, если оно существует; в противном случае возвращается указанное значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe609-124">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="fe609-125">В настоящее время нет других функций, привязанных к модулю, для параметров значения.</span><span class="sxs-lookup"><span data-stu-id="fe609-125">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe609-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fe609-126">See also</span></span>

- [<span data-ttu-id="fe609-127">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe609-127">Options</span></span>](options.md)
