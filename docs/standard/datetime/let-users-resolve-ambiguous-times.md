---
title: Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf97f1a08c6df13ce639466fc07472926c63987f
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106620"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="3c6c1-102">Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="3c6c1-102">How to: Let users resolve ambiguous times</span></span>

<span data-ttu-id="3c6c1-103">Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="3c6c1-104">Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="3c6c1-105">При обработке неоднозначного времени можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3c6c1-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="3c6c1-106">Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-106">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

- <span data-ttu-id="3c6c1-107">Сделать предположение о том, насколько время соответствует времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="3c6c1-108">Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="3c6c1-109">В этом разделе показано, как разрешить пользователю устранить неоднозначное время.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-109">This topic shows how to let a user resolve an ambiguous time.</span></span>

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="3c6c1-110">Предоставление пользователю возможности разрешать неоднозначность времени</span><span class="sxs-lookup"><span data-stu-id="3c6c1-110">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="3c6c1-111">Получите значение даты и времени, введенное пользователем.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-111">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="3c6c1-112">Вызовите <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> метод, чтобы определить, является ли время неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="3c6c1-113">Если время неоднозначно, вызовите <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> метод, чтобы получить <xref:System.TimeSpan> массив объектов.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-113">If the time is ambiguous, call the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects.</span></span> <span data-ttu-id="3c6c1-114">Каждый элемент массива содержит смещение в формате UTC, которое может сопоставляться с неоднозначным временем.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-114">Each element in the array contains a UTC offset that the ambiguous time can map to.</span></span>

4. <span data-ttu-id="3c6c1-115">Предоставьте пользователю возможность выбрать нужное смещение.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-115">Let the user select the desired offset.</span></span>

5. <span data-ttu-id="3c6c1-116">Получите дату и время в формате UTC путем вычитания выбранного пользователем смещения из локального времени.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

6. <span data-ttu-id="3c6c1-117">`Shared` <xref:System.DateTime.SpecifyKind%2A> <xref:System.DateTime.Kind%2A> Вызовите метод <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>(в Visual Basic .NET), чтобы задать свойству значения даты и времени в формате UTC значение. `static`</span><span class="sxs-lookup"><span data-stu-id="3c6c1-117">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="3c6c1-118">Пример</span><span class="sxs-lookup"><span data-stu-id="3c6c1-118">Example</span></span>

<span data-ttu-id="3c6c1-119">В следующем примере пользователю предлагается ввести значение даты и времени и, если оно неоднозначно, выбрать время в формате UTC, которому сопоставлено неоднозначное время.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span>

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

<span data-ttu-id="3c6c1-120">В ядре примера кода используется массив <xref:System.TimeSpan> объектов для указания возможных смещений неоднозначного времени от времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-120">The core of the example code uses an array of <xref:System.TimeSpan> objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="3c6c1-121">Однако эти смещения скорее всего не будут иметь значения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-121">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="3c6c1-122">Для уточнения значений этих смещений в коде также учитывается, представляет ли смещение стандартное время местного часового пояса или его летнее время.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-122">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="3c6c1-123">Код определяет, какое время является стандартным и какое время является летним, сравнивая смещение со значением <xref:System.TimeZoneInfo.BaseUtcOffset%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-123">The code determines which time is standard and which time is daylight by comparing the offset with the value of the <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span> <span data-ttu-id="3c6c1-124">Это свойство указывает разницу между временем UTC и стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-124">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="3c6c1-125">В этом примере все ссылки на местный часовой пояс выполняются через <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> свойство; местный часовой пояс никогда не назначается объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-125">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="3c6c1-126">Это рекомендуемый подход, поскольку вызов <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> метода делает недействительными все объекты, которым назначен местный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="3c6c1-126">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="3c6c1-127">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3c6c1-127">Compiling the code</span></span>

<span data-ttu-id="3c6c1-128">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="3c6c1-128">This example requires:</span></span>

- <span data-ttu-id="3c6c1-129">, Что `using` пространство имен должно быть импортировано с помощью оператора C# (требуется в коде). <xref:System></span><span class="sxs-lookup"><span data-stu-id="3c6c1-129">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c6c1-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3c6c1-130">See also</span></span>

- [<span data-ttu-id="3c6c1-131">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="3c6c1-131">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="3c6c1-132">Практическое руководство. Устранить неоднозначные времена</span><span class="sxs-lookup"><span data-stu-id="3c6c1-132">How to: Resolve ambiguous times</span></span>](../../../docs/standard/datetime/resolve-ambiguous-times.md)
