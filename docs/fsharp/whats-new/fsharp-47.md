---
title: Что нового в F- 4.7 - F' Руководство
description: Получить обзор новых функций, доступных в ФЗ 4.7.
ms.date: 11/27/2019
ms.openlocfilehash: 7a6e744a398719bcb55d168dd700459e0b122dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185879"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="98b4b-103">Что нового в ФЗ 4.7</span><span class="sxs-lookup"><span data-stu-id="98b4b-103">What's new in F# 4.7</span></span>

<span data-ttu-id="98b4b-104">ФЗ 4.7 добавляет несколько улучшений в язык F..</span><span class="sxs-lookup"><span data-stu-id="98b4b-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="98b4b-105">Начало работы</span><span class="sxs-lookup"><span data-stu-id="98b4b-105">Get started</span></span>

<span data-ttu-id="98b4b-106">ФЗ 4.7 доступен во всех дистрибутивах .NET Core и инструментарии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="98b4b-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="98b4b-107">[Начало работы с ФЗ,](../get-started/index.md) чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="98b4b-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="98b4b-108">Версия языка</span><span class="sxs-lookup"><span data-stu-id="98b4b-108">Language version</span></span>

<span data-ttu-id="98b4b-109">Компилятор F'4.7 вводит возможность настройки эффективной языковой версии через свойство в файле проекта:</span><span class="sxs-lookup"><span data-stu-id="98b4b-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="98b4b-110">Вы можете установить его `4.6` `4.7`на `latest`значения, и `preview`.</span><span class="sxs-lookup"><span data-stu-id="98b4b-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="98b4b-111">Значение по умолчанию — `latest`.</span><span class="sxs-lookup"><span data-stu-id="98b4b-111">The default is `latest`.</span></span>

<span data-ttu-id="98b4b-112">Если вы установите `preview`его, ваш компилятор активирует все функции предварительного просмотра F, которые реализованы в компиляторе.</span><span class="sxs-lookup"><span data-stu-id="98b4b-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="98b4b-113">Неявные урожаи</span><span class="sxs-lookup"><span data-stu-id="98b4b-113">Implicit yields</span></span>

<span data-ttu-id="98b4b-114">Вам больше не нужно `yield` применять ключевое слово в массивах, списках, последовательностях или выражениях вычислений, в которых можно сделать вывод о типе.</span><span class="sxs-lookup"><span data-stu-id="98b4b-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="98b4b-115">В следующем примере оба выражения `yield` требовали оператора для каждой записи до 4.7 F.7:</span><span class="sxs-lookup"><span data-stu-id="98b4b-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

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

<span data-ttu-id="98b4b-116">Если вы введете одно `yield` ключевое слово, каждый другой элемент должен также `yield` применяться к нему.</span><span class="sxs-lookup"><span data-stu-id="98b4b-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="98b4b-117">Неявные урожаи не активируются `yield!` при использовании в выражении, которое также использует для сглаживания последовательности.</span><span class="sxs-lookup"><span data-stu-id="98b4b-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="98b4b-118">Вы должны продолжать `yield` использовать сегодня в этих случаях.</span><span class="sxs-lookup"><span data-stu-id="98b4b-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="98b4b-119">Идентификаторы Wildcard</span><span class="sxs-lookup"><span data-stu-id="98b4b-119">Wildcard identifiers</span></span>

<span data-ttu-id="98b4b-120">В коде ФЗ, включающем классы, самоисждатель должен всегда быть явным в декларациях членов.</span><span class="sxs-lookup"><span data-stu-id="98b4b-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="98b4b-121">Но в тех случаях, когда самоижденитель никогда не используется, традиционно было условно использовать двойной показатель для обозначения безымянных самоиспоминовемых.</span><span class="sxs-lookup"><span data-stu-id="98b4b-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="98b4b-122">Теперь вы можете использовать один подчеркнуть:</span><span class="sxs-lookup"><span data-stu-id="98b4b-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="98b4b-123">Это также относится к `for` циклам:</span><span class="sxs-lookup"><span data-stu-id="98b4b-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="98b4b-124">Отклонения отступов</span><span class="sxs-lookup"><span data-stu-id="98b4b-124">Indentation relaxations</span></span>

<span data-ttu-id="98b4b-125">До 4,7 ФЗ требования к отступам для первичного конструктора и статических аргументов членов требовали чрезмерного отступа.</span><span class="sxs-lookup"><span data-stu-id="98b4b-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="98b4b-126">Теперь они требуют только одной области отступов:</span><span class="sxs-lookup"><span data-stu-id="98b4b-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
