---
title: "Как: разрешение проблемы неоднозначности времени"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 251f1914b131c5deed194ad7f3fb068c1d9b27c5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="9e8d6-102">Как: разрешение проблемы неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="9e8d6-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="9e8d6-103">Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="9e8d6-104">Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="9e8d6-105">При обработке неоднозначного времени можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9e8d6-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="9e8d6-106">Сделать предположение о том, насколько время соответствует времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="9e8d6-107">Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="9e8d6-108">Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="9e8d6-109">В этом разделе показано, как устранить неоднозначное время, предполагая, что он представляет зимнего времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="9e8d6-110">Сопоставление неоднозначного времени стандартному времени часового пояса</span><span class="sxs-lookup"><span data-stu-id="9e8d6-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="9e8d6-111">Вызовите <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> метод, чтобы определить, является ли время неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="9e8d6-112">Если время является неоднозначным, вычитать время из <xref:System.TimeSpan> объект, возвращаемый часового пояса <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="9e8d6-113">Вызовите `static` (`Shared` в Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> метод, чтобы задать UTC значения даты и времени <xref:System.DateTime.Kind%2A> свойства <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="9e8d6-114">Пример</span><span class="sxs-lookup"><span data-stu-id="9e8d6-114">Example</span></span>

<span data-ttu-id="9e8d6-115">Следующий пример показывает, как преобразовать неоднозначное время в формат UTC, предполагая, что он представляет зимнего времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="9e8d6-116">Пример состоит из метода с именем `ResolveAmbiguousTime` , определяющее, является ли <xref:System.DateTime> переданное значение является неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="9e8d6-117">Если значение является неоднозначным, метод возвращает <xref:System.DateTime> значение, представляющее собой соответствующее время UTC.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="9e8d6-118">Метод обрабатывает это преобразование путем вычитания значения местного часового пояса <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойство из местного времени.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="9e8d6-119">Как правило, неоднозначное время обрабатывается вызовом <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> метод для извлечения массива <xref:System.TimeSpan> объектов, содержащих неоднозначное время (UTC) возможные смещения.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="9e8d6-120">Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="9e8d6-121"><xref:System.TimeZoneInfo.BaseUtcOffset%2A> Свойство Возвращает смещение между временем UTC и зимнего времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="9e8d6-122">В этом примере все ссылки на местный часовой пояс выполняются через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство; местное время, зоны никогда не назначается переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="9e8d6-123">Это рекомендуется, поскольку вызов <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метод делает недействительными все объекты, которые назначены местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="9e8d6-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9e8d6-124">Compiling the code</span></span>

<span data-ttu-id="9e8d6-125">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="9e8d6-125">This example requires:</span></span>

* <span data-ttu-id="9e8d6-126">Чтобы ссылка на System.Core.dll была добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="9e8d6-126">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="9e8d6-127">Что <xref:System> импортировать пространство имен с `using` инструкции (обязательно в коде C#).</span><span class="sxs-lookup"><span data-stu-id="9e8d6-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e8d6-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9e8d6-128">See also</span></span>

<span data-ttu-id="9e8d6-129">[Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)
[как: разрешить пользователям разрешение проблемы неоднозначности времени](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span><span class="sxs-lookup"><span data-stu-id="9e8d6-129">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span></span>
