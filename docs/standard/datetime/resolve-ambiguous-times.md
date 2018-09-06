---
title: 'Практическое: разрешение проблемы неоднозначности времени'
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
ms.openlocfilehash: eb09b1f087e0a0f726d32d85e06cfb2a9ec741a8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863138"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="6bc11-102">Практическое: разрешение проблемы неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="6bc11-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="6bc11-103">Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="6bc11-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="6bc11-104">Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время.</span><span class="sxs-lookup"><span data-stu-id="6bc11-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="6bc11-105">При обработке неоднозначного времени можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="6bc11-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="6bc11-106">Сделать предположение о том, насколько время соответствует времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="6bc11-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="6bc11-107">Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="6bc11-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="6bc11-108">Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="6bc11-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="6bc11-109">В этом разделе показано, как устранить неоднозначное время, предполагая, что он представляет стандартное время часового пояса.</span><span class="sxs-lookup"><span data-stu-id="6bc11-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="6bc11-110">Сопоставление неоднозначного времени стандартному времени часового пояса</span><span class="sxs-lookup"><span data-stu-id="6bc11-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="6bc11-111">Вызовите <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> метод, чтобы определить, является ли время неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="6bc11-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="6bc11-112">Если время является неоднозначным, вычитайте время из <xref:System.TimeSpan> объект, возвращаемый в часовом поясе <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="6bc11-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="6bc11-113">Вызовите `static` (`Shared` в Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> метод для установки даты и времени значение в формате UTC <xref:System.DateTime.Kind%2A> свойства <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6bc11-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="6bc11-114">Пример</span><span class="sxs-lookup"><span data-stu-id="6bc11-114">Example</span></span>

<span data-ttu-id="6bc11-115">Следующий пример иллюстрирует, как преобразовать неоднозначное время в формат UTC, предполагая, что он представляет местного часового пояса (зима).</span><span class="sxs-lookup"><span data-stu-id="6bc11-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="6bc11-116">Пример состоит из метода с именем `ResolveAmbiguousTime` , определяет ли <xref:System.DateTime> переданное значение является неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="6bc11-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="6bc11-117">Если значение является неоднозначным, метод возвращает <xref:System.DateTime> значение, представляющее собой соответствующее время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="6bc11-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="6bc11-118">Метод обрабатывает это преобразование путем вычитания значения местного часового пояса <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойство из локального времени.</span><span class="sxs-lookup"><span data-stu-id="6bc11-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="6bc11-119">Как правило, неоднозначное время обрабатывается вызовом <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> метод для извлечения массива <xref:System.TimeSpan> offsets объектов, содержащих возможные неоднозначное время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="6bc11-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="6bc11-120">Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="6bc11-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="6bc11-121"><xref:System.TimeZoneInfo.BaseUtcOffset%2A> Возвращает смещение между временем UTC и временем стандартного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="6bc11-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="6bc11-122">В этом примере все ссылки на местный часовой пояс выполняются через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство; в местный часовой пояс никогда не назначается переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="6bc11-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="6bc11-123">Это рекомендуется, поскольку вызов <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метод не делает недействительными все объекты, которые назначены местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="6bc11-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="6bc11-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6bc11-124">Compiling the code</span></span>

<span data-ttu-id="6bc11-125">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="6bc11-125">This example requires:</span></span>

* <span data-ttu-id="6bc11-126">Чтобы добавить в проект ссылку на библиотеку System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="6bc11-126">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="6bc11-127">Что <xref:System> импорт пространства имен с помощью `using` инструкции (обязательно в коде C#).</span><span class="sxs-lookup"><span data-stu-id="6bc11-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="6bc11-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6bc11-128">See also</span></span>

* [<span data-ttu-id="6bc11-129">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="6bc11-129">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
* [<span data-ttu-id="6bc11-130">Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="6bc11-130">How to: Let users resolve ambiguous times</span></span>](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
