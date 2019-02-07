---
title: Параметры значения
description: Дополнительные сведения о F# значение параметра типа — версии структуры типа параметра.
ms.date: 02/06/2019
ms.openlocfilehash: e1036c83189c853b3704d94ca245e4818acc98c1
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828037"
---
# <a name="value-options"></a><span data-ttu-id="a9cd7-103">Параметры значения</span><span class="sxs-lookup"><span data-stu-id="a9cd7-103">Value Options</span></span>

<span data-ttu-id="a9cd7-104">Тип значения параметра в F# используется, если выполнено следующих двух случаях:</span><span class="sxs-lookup"><span data-stu-id="a9cd7-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="a9cd7-105">Сценарий подходит для [ F# параметр](options.md).</span><span class="sxs-lookup"><span data-stu-id="a9cd7-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="a9cd7-106">С помощью структуры обеспечивает повышение производительности в вашем сценарии.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="a9cd7-107">Не все сценарии быстродействие» разрешаются» с помощью структуры.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="a9cd7-108">Необходимо учитывать дополнительные издержки копирования при использовании их вместо ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="a9cd7-109">Однако большие F# программ часто создания экземпляра многие дополнительные типы, которые проходят через критических путей, и в таком случае структур часто приносит повышения общей производительности в течение времени существования программы.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="a9cd7-110">Определение</span><span class="sxs-lookup"><span data-stu-id="a9cd7-110">Definition</span></span>

<span data-ttu-id="a9cd7-111">Значение параметра определяется как [размеченные объединения](discriminated-unions.md#struct-discriminated-unions) подобный вариант в ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="a9cd7-112">Таким образом можно рассматривать его определения:</span><span class="sxs-lookup"><span data-stu-id="a9cd7-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="a9cd7-113">Значение параметра соответствует структурного равенства и сравнения.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="a9cd7-114">Основное различие является то, что скомпилированный имя, имя типа и регистра имен указать, что не типом значения.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="a9cd7-115">С помощью параметров значений</span><span class="sxs-lookup"><span data-stu-id="a9cd7-115">Using Value Options</span></span>

<span data-ttu-id="a9cd7-116">Параметры значения используются так же, как [параметры](options.md).</span><span class="sxs-lookup"><span data-stu-id="a9cd7-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="a9cd7-117">`ValueSome` Указывает, что значение будет присутствовать, и `ValueNone` используется, если значение отсутствует:</span><span class="sxs-lookup"><span data-stu-id="a9cd7-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

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

<span data-ttu-id="a9cd7-118">Как и в [параметры](options.md), соглашение об именовании для функции, которая возвращает `ValueOption` является перед ними `try`.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="a9cd7-119">Значение параметра свойства и методы</span><span class="sxs-lookup"><span data-stu-id="a9cd7-119">Value Option properties and methods</span></span>

<span data-ttu-id="a9cd7-120">В настоящее время есть одно свойство для возможных значений: `Value`.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="a9cd7-121"><xref:System.InvalidOperationException> Возникает, если значение не присутствует, при вызове этого свойства.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="a9cd7-122">Значение параметра функции</span><span class="sxs-lookup"><span data-stu-id="a9cd7-122">Value Option functions</span></span>

<span data-ttu-id="a9cd7-123">В данный момент одного связанного с модулем функции для параметров значение `defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="a9cd7-123">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

<span data-ttu-id="a9cd7-124">Как и в `defaultArg` функции `defaultValueArg` Возвращает базовое значение данного параметра значение, если он существует; в противном случае возвращает значение указанного по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-124">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="a9cd7-125">В настоящее время нет других функций связанного с модулем для возможных значений.</span><span class="sxs-lookup"><span data-stu-id="a9cd7-125">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9cd7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a9cd7-126">See also</span></span>

- [<span data-ttu-id="a9cd7-127">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9cd7-127">Options</span></span>](options.md)
