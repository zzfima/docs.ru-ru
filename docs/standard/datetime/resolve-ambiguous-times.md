---
title: "Практическое руководство. Разрешение проблемы неоднозначности времени"
description: "Практическое руководство. Разрешение проблемы неоднозначности времени"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e86050c6-d16d-405e-8bba-7205945c9a81
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f4ab3b4bf3487e70be7e885e9b8a2281927eb30e
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="c579d-104">Практическое руководство. Разрешение проблемы неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="c579d-104">How to: resolve ambiguous times</span></span>

<span data-ttu-id="c579d-105">Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="c579d-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="c579d-106">Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время.</span><span class="sxs-lookup"><span data-stu-id="c579d-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="c579d-107">При обработке неоднозначного времени можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c579d-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="c579d-108">Сделать предположение о том, насколько время соответствует времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="c579d-108">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="c579d-109">Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="c579d-109">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="c579d-110">Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="c579d-110">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="c579d-111">В этом разделе показано, как устранить неоднозначное время, предполагая, что оно представляет собой стандартное время часового пояса.</span><span class="sxs-lookup"><span data-stu-id="c579d-111">This article shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

## <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="c579d-112">Сопоставление неоднозначного времени стандартному времени часового пояса</span><span class="sxs-lookup"><span data-stu-id="c579d-112">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="c579d-113">Вызовите метод [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) или [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)), чтобы определить, является ли время неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="c579d-113">Call the [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="c579d-114">Если время является неоднозначным, вычитайте время из объекта [TimeSpan](xref:System.TimeSpan), возвращаемого свойством часового пояса [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset).</span><span class="sxs-lookup"><span data-stu-id="c579d-114">If the time is ambiguous, subtract the time from the [TimeSpan](xref:System.TimeSpan) object returned by the time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span>

3. <span data-ttu-id="c579d-115">Вызовите метод `static` (`Shared` в Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)), чтобы задать значение даты и времени в формате UTC для свойства [Kind](xref:System.DateTime.Kind) равным [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span><span class="sxs-lookup"><span data-stu-id="c579d-115">Call the `static` (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="c579d-116">Пример</span><span class="sxs-lookup"><span data-stu-id="c579d-116">Example</span></span>

<span data-ttu-id="c579d-117">В следующем примере показано, как преобразовать неоднозначное время [DateTime](xref:System.DateTime) в формат UTC, предполагая, что оно представляет собой местное время часового пояса.</span><span class="sxs-lookup"><span data-stu-id="c579d-117">The following example illustrates how to convert an ambiguous [DateTime](xref:System.DateTime) to UTC by assuming that it represents the local time zone's standard time.</span></span> 

```csharp
private DateTime ResolveAmbiguousTime(DateTime ambiguousTime)
{
   // Time is not ambiguous
   if (! TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime))
   { 
      return ambiguousTime; 
   }
   // Time is ambiguous
   else
   {
      DateTime utcTime = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, 
                                              DateTimeKind.Utc);      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", 
                        ambiguousTime, utcTime, utcTime.Kind.ToString());
      return utcTime;            
   }   
}
```

```vb
Private Function ResolveAmbiguousTime(ambiguousTime As Date) As Date
   ' Time is not ambiguous
   If Not TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime) Then 
      Return TimeZoneInfo.ConvertTimeToUtc(ambiguousTime) 
   ' Time is ambiguous
   Else
      Dim utcTime As Date = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, DateTimeKind.Utc)      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", ambiguousTime, utcTime, utcTime.Kind.ToString())
      Return utcTime            
   End If   
End Function
```

<span data-ttu-id="c579d-118">Пример состоит из метода с именем `ResolveAmbiguousTime`, который определяет, является ли значение [DateTime](xref:System.DateTime), переданное в него, неоднозначным.</span><span class="sxs-lookup"><span data-stu-id="c579d-118">The example consists of a method named `ResolveAmbiguousTime` that determines whether the [DateTime](xref:System.DateTime) value passed to it is ambiguous.</span></span> <span data-ttu-id="c579d-119">Если значение является неоднозначным, то метод возвращает значение [DateTime](xref:System.DateTime), представляющее собой соответствующее время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="c579d-119">If the value is ambiguous, the method returns a [DateTime](xref:System.DateTime) value that represents the corresponding UTC time.</span></span> <span data-ttu-id="c579d-120">Метод обрабатывает это преобразование путем вычитания значения свойства [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) местного часового пояса из локального времени.</span><span class="sxs-lookup"><span data-stu-id="c579d-120">The method handles this conversion by subtracting the value of the local time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property from the local time.</span></span> 

<span data-ttu-id="c579d-121">Как правило, неоднозначное время обрабатывается вызовом метода [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) для извлечения массива объектов [TimeSpan](xref:System.TimeSpan), содержащих возможные смещения неоднозначного времени относительно UTC.</span><span class="sxs-lookup"><span data-stu-id="c579d-121">Ordinarily, an ambiguous time is handled by calling the [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) method to retrieve an array of [TimeSpan](xref:System.TimeSpan) objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="c579d-122">Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса.</span><span class="sxs-lookup"><span data-stu-id="c579d-122">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="c579d-123">Свойство [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) возвращает смещение между временем по UTC и временем стандартного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="c579d-123">The [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property returns the offset between UTC and a time zone's standard time.</span></span>

## <a name="see-also"></a><span data-ttu-id="c579d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c579d-124">See Also</span></span>

[<span data-ttu-id="c579d-125">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="c579d-125">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="c579d-126">Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени</span><span class="sxs-lookup"><span data-stu-id="c579d-126">How to: let users resolve ambiguous times</span></span>](let-users-resolve-ambiguous-times.md)


