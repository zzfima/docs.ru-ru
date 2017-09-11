---
title: "Практическое руководство. Перечисление присутствующих на компьютере часовых поясов"
description: "Практическое руководство. Перечисление присутствующих на компьютере часовых поясов"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c5ae4a6c-1790-4355-b5b1-879aaf956129
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f30ba2a483ff7e5867417969946c2774175d5e3d
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="4f0d0-104">Практическое руководство. Перечисление присутствующих на компьютере часовых поясов</span><span class="sxs-lookup"><span data-stu-id="4f0d0-104">How to: enumerate time zones present on a computer</span></span>

<span data-ttu-id="4f0d0-105">Для успешной работы с указанным часовым поясом необходимо, чтобы сведения об этом часовом поясе были доступны в системе.</span><span class="sxs-lookup"><span data-stu-id="4f0d0-105">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="4f0d0-106">В операционных системах Windows, например, эти сведения хранятся в реестре.</span><span class="sxs-lookup"><span data-stu-id="4f0d0-106">For example, the Windows operating system stores this information in the registry.</span></span> <span data-ttu-id="4f0d0-107">Тем не менее, хотя общее число часовых поясов, которые существуют по всему миру, велико, реестр содержит сведения только о подмножестве из них.</span><span class="sxs-lookup"><span data-stu-id="4f0d0-107">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="4f0d0-108">Кроме того, реестр сам является динамической структурой, содержимое которой подвержено преднамеренным и случайным изменениям.</span><span class="sxs-lookup"><span data-stu-id="4f0d0-108">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="4f0d0-109">В итоге приложение не может всегда предполагать, что конкретный часовой пояс определен и доступен в системе.</span><span class="sxs-lookup"><span data-stu-id="4f0d0-109">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="4f0d0-110">Первым шагом для многих приложений, использующих данные о часовых поясах, является определение доступности требуемого часового пояса на локальном компьютере или предоставление пользователю списка часовых поясов для выбора.</span><span class="sxs-lookup"><span data-stu-id="4f0d0-110">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="4f0d0-111">Для этого необходимо, чтобы приложение перечислило часовые пояса, определенные в локальной системе.</span><span class="sxs-lookup"><span data-stu-id="4f0d0-111">This requires that an application enumerate the time zones defined on a local system.</span></span> 

## <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="4f0d0-112">Перечисление часовых поясов, присутствующих в локальной системе</span><span class="sxs-lookup"><span data-stu-id="4f0d0-112">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="4f0d0-113">Вызовите метод [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones).</span><span class="sxs-lookup"><span data-stu-id="4f0d0-113">Call the [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones) method.</span></span> <span data-ttu-id="4f0d0-114">Этот метод возвращает универсальную коллекцию [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) объектов [TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="4f0d0-114">The method returns a generic [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects.</span></span> <span data-ttu-id="4f0d0-115">Элементы коллекции сортируются по свойству [DisplayName](xref:System.TimeZoneInfo.DisplayName).</span><span class="sxs-lookup"><span data-stu-id="4f0d0-115">The entries in the collection are sorted by their [DisplayName](xref:System.TimeZoneInfo.DisplayName) property.</span></span> <span data-ttu-id="4f0d0-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="4f0d0-116">For example:</span></span>

    ```csharp
    ReadOnlyCollection<TimeZoneInfo> tzCollection;
    tzCollection = TimeZoneInfo.GetSystemTimeZones();
    ```

    ```vb
    Dim tzCollection As ReadOnlyCollection(Of TimeZoneInfo) = TimeZoneInfo.GetSystemTimeZones
    ```

2. <span data-ttu-id="4f0d0-117">Перечислите отдельные объекты [TimeZoneInfo](xref:System.TimeZoneInfo) в коллекции с помощью цикла `foreach` (в C#) или цикла `For Each…Next` (в Visual Basic) и выполните все необходимые действия с каждым объектом.</span><span class="sxs-lookup"><span data-stu-id="4f0d0-117">Enumerate the individual [TimeZoneInfo](xref:System.TimeZoneInfo) objects in the collection by using a `foreach` loop (in C#) or a `For Each…Next` loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="4f0d0-118">Например, следующий код перечисляет коллекцию [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) объектов [TimeZoneInfo](xref:System.TimeZoneInfo), возвращенную на шаге 1, и выводит на консоль список отображаемых имен всех часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="4f0d0-118">For example, the following code enumerates the [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

    ```csharp
    foreach (TimeZoneInfo timeZone in tzCollection)
    Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName);
    ```

    ```vb
    For Each timeZone As TimeZoneInfo In tzCollection
        Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName)
    Next
    ```

## <a name="see-also"></a><span data-ttu-id="4f0d0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4f0d0-119">See Also</span></span>

[<span data-ttu-id="4f0d0-120">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="4f0d0-120">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="4f0d0-121">Поиск часового пояса, заданного в локальной системе</span><span class="sxs-lookup"><span data-stu-id="4f0d0-121">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)


