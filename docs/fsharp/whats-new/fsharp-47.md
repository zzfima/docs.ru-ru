---
title: Новые возможности в F# 4,7- F# Guide
description: Ознакомьтесь с обзором новых функций, доступных в F# 4,7.
ms.date: 11/27/2019
ms.openlocfilehash: 203b258466cb9f1f50215ecf8884e92e7e86416b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644124"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="db6d4-103">Новые возможности в F# 4,7</span><span class="sxs-lookup"><span data-stu-id="db6d4-103">What's new in F# 4.7</span></span>

<span data-ttu-id="db6d4-104">F#4,7 добавляет несколько улучшений в F# язык.</span><span class="sxs-lookup"><span data-stu-id="db6d4-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="db6d4-105">Начало работы</span><span class="sxs-lookup"><span data-stu-id="db6d4-105">Get started</span></span>

<span data-ttu-id="db6d4-106">F#4,7 доступна во всех дистрибутивах .NET Core и средствах Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="db6d4-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="db6d4-107">Дополнительные сведения см. в статье Приступая к [работе с F# ](../get-started/index.md) .</span><span class="sxs-lookup"><span data-stu-id="db6d4-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="db6d4-108">Версия языка</span><span class="sxs-lookup"><span data-stu-id="db6d4-108">Language version</span></span>

<span data-ttu-id="db6d4-109">Компилятор F# 4,7 вводит возможность установки действующей языковой версии с помощью свойства в файле проекта:</span><span class="sxs-lookup"><span data-stu-id="db6d4-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="db6d4-110">Для него можно задать значения `4.6`, `4.7`, `latest`и `preview`.</span><span class="sxs-lookup"><span data-stu-id="db6d4-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="db6d4-111">Значение по умолчанию: `latest`.</span><span class="sxs-lookup"><span data-stu-id="db6d4-111">The default is `latest`.</span></span>

<span data-ttu-id="db6d4-112">Если задать для него значение `preview`, компилятор будет активировать все F# функции предварительной версии, реализованные в компиляторе.</span><span class="sxs-lookup"><span data-stu-id="db6d4-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="db6d4-113">Неявные yield</span><span class="sxs-lookup"><span data-stu-id="db6d4-113">Implicit yields</span></span>

<span data-ttu-id="db6d4-114">Больше не нужно применять ключевое слово `yield` в массивах, списках, последовательностям или вычислительных выражениях, где тип может быть определен.</span><span class="sxs-lookup"><span data-stu-id="db6d4-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="db6d4-115">В следующем примере оба выражения требовали `yield` инструкции для каждой записи до F# 4,7:</span><span class="sxs-lookup"><span data-stu-id="db6d4-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

```fsharp
let s = seq { 1; 2; 3; 4; 5 }

let daysOfWeek includeWeekend =
    [ 
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then 
            "Saturday"
            "Sunday"
    ] 
```

<span data-ttu-id="db6d4-116">Если вводится одно ключевое слово `yield`, к нему также должен быть применен `yield`.</span><span class="sxs-lookup"><span data-stu-id="db6d4-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="db6d4-117">Неявные yield не активируются при использовании в выражении, которое также использует `yield!` для преобразования последовательности в неявное значение.</span><span class="sxs-lookup"><span data-stu-id="db6d4-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="db6d4-118">В таких случаях необходимо продолжать использовать `yield` в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="db6d4-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="db6d4-119">Идентификаторы с подстановочными знаками</span><span class="sxs-lookup"><span data-stu-id="db6d4-119">Wildcard identifiers</span></span>

<span data-ttu-id="db6d4-120">В F# коде, включающем классы, самоидентификатор должен всегда быть явным в объявлениях членов.</span><span class="sxs-lookup"><span data-stu-id="db6d4-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="db6d4-121">Но в случаях, когда сам идентификатор никогда не используется, он традиционно использовался для обозначения безименных идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="db6d4-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="db6d4-122">Теперь можно использовать один символ подчеркивания:</span><span class="sxs-lookup"><span data-stu-id="db6d4-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="db6d4-123">Это также относится к циклам `for`:</span><span class="sxs-lookup"><span data-stu-id="db6d4-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="db6d4-124">Ограничения отступов</span><span class="sxs-lookup"><span data-stu-id="db6d4-124">Indentation relaxations</span></span>

<span data-ttu-id="db6d4-125">До F# 4,7 требования к отступам для первичного конструктора и аргументов статических членов требовали чрезмерного отступа.</span><span class="sxs-lookup"><span data-stu-id="db6d4-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="db6d4-126">Теперь для них требуется только одна область отступов:</span><span class="sxs-lookup"><span data-stu-id="db6d4-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
