---
title: 'Практическое: предоставление пользователям возможности разрешения неоднозначности времени'
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91e80f44934092007f6f842f0694789d49321446
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863555"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="cebad-102">Практическое: предоставление пользователям возможности разрешения неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="cebad-102">How to: Let users resolve ambiguous times</span></span>

<span data-ttu-id="cebad-103">Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="cebad-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="cebad-104">Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время.</span><span class="sxs-lookup"><span data-stu-id="cebad-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="cebad-105">При обработке неоднозначного времени можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="cebad-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="cebad-106">Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="cebad-106">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="cebad-107">Сделать предположение о том, насколько время соответствует времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="cebad-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="cebad-108">Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="cebad-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="cebad-109">В этом разделе показано, как предоставление пользователю возможности разрешать неоднозначность времени.</span><span class="sxs-lookup"><span data-stu-id="cebad-109">This topic shows how to let a user resolve an ambiguous time.</span></span>

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="cebad-110">Предоставление пользователю возможности разрешать неоднозначность времени</span><span class="sxs-lookup"><span data-stu-id="cebad-110">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="cebad-111">Получите значение даты и времени, введенное пользователем.</span><span class="sxs-lookup"><span data-stu-id="cebad-111">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="cebad-112">Вызовите <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> метод, чтобы определить, является ли время неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="cebad-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="cebad-113">Если время является неоднозначным, вызовите <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> метод для извлечения массива <xref:System.TimeSpan> объектов.</span><span class="sxs-lookup"><span data-stu-id="cebad-113">If the time is ambiguous, call the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects.</span></span> <span data-ttu-id="cebad-114">Каждый элемент массива содержит смещения от UTC, можно сопоставить неоднозначное время.</span><span class="sxs-lookup"><span data-stu-id="cebad-114">Each element in the array contains a UTC offset that the ambiguous time can map to.</span></span>

4. <span data-ttu-id="cebad-115">Предоставьте пользователю возможность выбрать нужное смещение.</span><span class="sxs-lookup"><span data-stu-id="cebad-115">Let the user select the desired offset.</span></span>

5. <span data-ttu-id="cebad-116">Получите дату и время в формате UTC путем вычитания выбранного пользователем смещения из локального времени.</span><span class="sxs-lookup"><span data-stu-id="cebad-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

6. <span data-ttu-id="cebad-117">Вызовите `static` (`Shared` в Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> метод для установки даты и времени значение в формате UTC <xref:System.DateTime.Kind%2A> свойства <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cebad-117">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="cebad-118">Пример</span><span class="sxs-lookup"><span data-stu-id="cebad-118">Example</span></span>

<span data-ttu-id="cebad-119">В следующем примере пользователю предлагается ввести значение даты и времени и, если оно неоднозначно, выбрать время в формате UTC, которому сопоставлено неоднозначное время.</span><span class="sxs-lookup"><span data-stu-id="cebad-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span>

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

<span data-ttu-id="cebad-120">В главной части примера используется массив <xref:System.TimeSpan> объекты для указания возможных смещений неоднозначного времени относительно времени UTC.</span><span class="sxs-lookup"><span data-stu-id="cebad-120">The core of the example code uses an array of <xref:System.TimeSpan> objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="cebad-121">Однако эти смещения скорее всего не будут иметь значения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="cebad-121">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="cebad-122">Для уточнения значений этих смещений в коде также учитывается, представляет ли смещение стандартное время местного часового пояса или его летнее время.</span><span class="sxs-lookup"><span data-stu-id="cebad-122">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="cebad-123">Код определяет, какое время является стандартным и какое время является переход на летнее, сравнивая смещение со значением <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="cebad-123">The code determines which time is standard and which time is daylight by comparing the offset with the value of the <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span> <span data-ttu-id="cebad-124">Это свойство указывает разницу между временем UTC и стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="cebad-124">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="cebad-125">В этом примере все ссылки на местный часовой пояс выполняются через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство; в местный часовой пояс никогда не назначается переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="cebad-125">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="cebad-126">Это рекомендуется, поскольку вызов <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метод не делает недействительными все объекты, которые назначены местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="cebad-126">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="cebad-127">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="cebad-127">Compiling the code</span></span>

<span data-ttu-id="cebad-128">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="cebad-128">This example requires:</span></span>

* <span data-ttu-id="cebad-129">Чтобы добавить в проект ссылку на библиотеку System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="cebad-129">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="cebad-130">Что <xref:System> импорт пространства имен с помощью `using` инструкции (обязательно в коде C#).</span><span class="sxs-lookup"><span data-stu-id="cebad-130">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="cebad-131">См. также</span><span class="sxs-lookup"><span data-stu-id="cebad-131">See also</span></span>

* [<span data-ttu-id="cebad-132">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="cebad-132">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
* [<span data-ttu-id="cebad-133">Практическое руководство. Разрешение проблемы неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="cebad-133">How to: Resolve ambiguous times</span></span>](../../../docs/standard/datetime/resolve-ambiguous-times.md)
