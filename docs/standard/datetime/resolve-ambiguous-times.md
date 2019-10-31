---
title: Руководство. разрешение неоднозначных времени
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 0b5b28c588237fb2f7f069aaef06f3f73d5268bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122253"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="f19ed-102">Руководство. разрешение неоднозначных времени</span><span class="sxs-lookup"><span data-stu-id="f19ed-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="f19ed-103">Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="f19ed-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="f19ed-104">Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время.</span><span class="sxs-lookup"><span data-stu-id="f19ed-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="f19ed-105">При обработке неоднозначного времени можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f19ed-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="f19ed-106">Сделать предположение о том, насколько время соответствует времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="f19ed-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="f19ed-107">Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="f19ed-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

- <span data-ttu-id="f19ed-108">Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="f19ed-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="f19ed-109">В этом разделе показано, как устранить неоднозначное время, предполагая, что оно представляет стандартное время часового пояса.</span><span class="sxs-lookup"><span data-stu-id="f19ed-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="f19ed-110">Сопоставление неоднозначного времени стандартному времени часового пояса</span><span class="sxs-lookup"><span data-stu-id="f19ed-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="f19ed-111">Вызовите метод <xref:System.TimeZoneInfo.IsAmbiguousTime%2A>, чтобы определить, является ли время неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="f19ed-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="f19ed-112">Если время неоднозначно, вычтите время из объекта <xref:System.TimeSpan>, возвращенного свойством <xref:System.TimeZoneInfo.BaseUtcOffset%2A> часового пояса.</span><span class="sxs-lookup"><span data-stu-id="f19ed-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="f19ed-113">Вызовите метод `static` (`Shared` в Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A>, чтобы задать для свойства <xref:System.DateTime.Kind%2A> значения даты и времени в формате UTC значение <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f19ed-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="f19ed-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f19ed-114">Example</span></span>

<span data-ttu-id="f19ed-115">В следующем примере показано, как преобразовать неоднозначное время в формат UTC, предполагая, что он представляет стандартное время местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="f19ed-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="f19ed-116">Пример состоит из метода с именем `ResolveAmbiguousTime`, определяющего, является ли передаваемое ему значение <xref:System.DateTime> неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="f19ed-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="f19ed-117">Если значение неоднозначно, метод возвращает <xref:System.DateTime> значение, представляющее соответствующее время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="f19ed-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="f19ed-118">Метод обрабатывает это преобразование, вычитая значение свойства <xref:System.TimeZoneInfo.BaseUtcOffset%2A> местного часового пояса из местного времени.</span><span class="sxs-lookup"><span data-stu-id="f19ed-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="f19ed-119">Как правило, неоднозначное время обрабатывается путем вызова метода <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> для получения массива объектов <xref:System.TimeSpan>, содержащих возможные смещения времени в формате UTC неоднозначности.</span><span class="sxs-lookup"><span data-stu-id="f19ed-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="f19ed-120">Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="f19ed-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="f19ed-121">Свойство <xref:System.TimeZoneInfo.BaseUtcOffset%2A> возвращает смещение между временем UTC и стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="f19ed-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="f19ed-122">В этом примере все ссылки на местный часовой пояс выполняются через свойство <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>. местный часовой пояс никогда не назначается объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="f19ed-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="f19ed-123">Это рекомендуемый подход, поскольку вызов метода <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> делает недействительными все объекты, которым назначен местный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="f19ed-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="f19ed-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f19ed-124">Compiling the code</span></span>

<span data-ttu-id="f19ed-125">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f19ed-125">This example requires:</span></span>

- <span data-ttu-id="f19ed-126">, Что <xref:System> пространство имен должно быть импортировано с помощью оператора `using` C# (требуется в коде).</span><span class="sxs-lookup"><span data-stu-id="f19ed-126">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="f19ed-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f19ed-127">See also</span></span>

- [<span data-ttu-id="f19ed-128">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="f19ed-128">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="f19ed-129">Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="f19ed-129">How to: Let users resolve ambiguous times</span></span>](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
