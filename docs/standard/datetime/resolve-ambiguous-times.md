---
title: Практическое руководство. Разрешение проблемы неоднозначности времени
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e98d5d8240492ca30da2825b72277d7a35f97f6
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106780"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="908e8-102">Практическое руководство. Разрешение проблемы неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="908e8-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="908e8-103">Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="908e8-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="908e8-104">Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время.</span><span class="sxs-lookup"><span data-stu-id="908e8-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="908e8-105">При обработке неоднозначного времени можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="908e8-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="908e8-106">Сделать предположение о том, насколько время соответствует времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="908e8-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="908e8-107">Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="908e8-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

- <span data-ttu-id="908e8-108">Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="908e8-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="908e8-109">В этом разделе показано, как устранить неоднозначное время, предполагая, что оно представляет стандартное время часового пояса.</span><span class="sxs-lookup"><span data-stu-id="908e8-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="908e8-110">Сопоставление неоднозначного времени стандартному времени часового пояса</span><span class="sxs-lookup"><span data-stu-id="908e8-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="908e8-111">Вызовите <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> метод, чтобы определить, является ли время неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="908e8-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="908e8-112">Если время неоднозначно, вычтите время из <xref:System.TimeSpan> объекта, возвращенного <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойством часового пояса.</span><span class="sxs-lookup"><span data-stu-id="908e8-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="908e8-113">`Shared` <xref:System.DateTime.SpecifyKind%2A> <xref:System.DateTime.Kind%2A> Вызовите метод <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>(в Visual Basic .NET), чтобы задать свойству значения даты и времени в формате UTC значение. `static`</span><span class="sxs-lookup"><span data-stu-id="908e8-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="908e8-114">Пример</span><span class="sxs-lookup"><span data-stu-id="908e8-114">Example</span></span>

<span data-ttu-id="908e8-115">В следующем примере показано, как преобразовать неоднозначное время в формат UTC, предполагая, что он представляет стандартное время местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="908e8-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="908e8-116">Пример состоит из метода с именем `ResolveAmbiguousTime` , который определяет, является <xref:System.DateTime> ли передаваемое ему значение неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="908e8-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="908e8-117">Если значение неоднозначно, метод возвращает <xref:System.DateTime> значение, представляющее соответствующее время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="908e8-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="908e8-118">Метод обрабатывает это преобразование, вычитая значение <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойства местного часового пояса из местного времени.</span><span class="sxs-lookup"><span data-stu-id="908e8-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="908e8-119">Как правило, неоднозначное время обрабатывается путем <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> вызова метода для получения <xref:System.TimeSpan> массива объектов, содержащих неоднозначное смещение времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="908e8-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="908e8-120">Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="908e8-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="908e8-121"><xref:System.TimeZoneInfo.BaseUtcOffset%2A> Свойство возвращает смещение между временем UTC и стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="908e8-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="908e8-122">В этом примере все ссылки на местный часовой пояс выполняются через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство; местный часовой пояс никогда не назначается объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="908e8-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="908e8-123">Это рекомендуемый подход, поскольку вызов <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метода делает недействительными все объекты, которым назначен местный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="908e8-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="908e8-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="908e8-124">Compiling the code</span></span>

<span data-ttu-id="908e8-125">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="908e8-125">This example requires:</span></span>

- <span data-ttu-id="908e8-126">, Что `using` пространство имен должно быть импортировано с помощью оператора C# (требуется в коде). <xref:System></span><span class="sxs-lookup"><span data-stu-id="908e8-126">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="908e8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="908e8-127">See also</span></span>

- [<span data-ttu-id="908e8-128">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="908e8-128">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="908e8-129">Практическое руководство. Разрешить пользователям решать неоднозначные времена</span><span class="sxs-lookup"><span data-stu-id="908e8-129">How to: Let users resolve ambiguous times</span></span>](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
