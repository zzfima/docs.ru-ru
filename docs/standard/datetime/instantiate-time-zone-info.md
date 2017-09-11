---
title: "Практическое руководство. Создание экземпляра объекта TimeZoneInfo"
description: "Практическое руководство. Создание экземпляра объекта TimeZoneInfo"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bff137e5-d550-44c3-b460-b3f2dabd4035
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f2584d446c92d2df2f6d74533ef07fe96888d36a
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="2ec2f-104">Практическое руководство. Создание экземпляра объекта TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="2ec2f-104">How to: instantiate a TimeZoneInfo object</span></span>

<span data-ttu-id="2ec2f-105">Наиболее распространенный способ создания экземпляра объекта [TimeZoneInfo](xref:System.TimeZoneInfo) — получение сведений о нем из реестра.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-105">The most common way to instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object is to retrieve information about it from the operating system.</span></span> <span data-ttu-id="2ec2f-106">В этом разделе описываются способы создания экземпляра объекта [TimeZoneInfo](xref:System.TimeZoneInfo) на основе локального системного реестра.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-106">This topic discusses how to instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object from the local system.</span></span>

## <a name="to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="2ec2f-107">Создание экземпляра объекта TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="2ec2f-107">To instantiate a TimeZoneInfo Object</span></span>

1. <span data-ttu-id="2ec2f-108">Объявите объект [TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="2ec2f-108">Declare a [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span>

2. <span data-ttu-id="2ec2f-109">Вызовите метод static `static` (`Shared` в Visual Basic) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)).</span><span class="sxs-lookup"><span data-stu-id="2ec2f-109">Call the `static` (`Shared` in Visual Basic) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) method.</span></span>

3. <span data-ttu-id="2ec2f-110">Обработайте исключения, созданные этим методом.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-110">Handle any exceptions thrown by the method.</span></span>

## <a name="example"></a><span data-ttu-id="2ec2f-111">Пример</span><span class="sxs-lookup"><span data-stu-id="2ec2f-111">Example</span></span>

<span data-ttu-id="2ec2f-112">Следующий код извлекает объект [TimeZoneInfo](xref:System.TimeZoneInfo), который представляет часовой пояс восточного времени США, и отображает время в этом поясе, соответствующее местному времени.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-112">The following code retrieves a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the Eastern Standard Time zone and displays the Eastern Standard time that corresponds to the local time.</span></span>

```csharp
DateTime timeNow = DateTime.Now;
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
   DateTime easternTimeNow = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, 
                                                   easternZone);
   Console.WriteLine("{0} {1} corresponds to {2} {3}.",
                     timeNow, 
                     TimeZoneInfo.Local.IsDaylightSavingTime(timeNow) ?
                               TimeZoneInfo.Local.DaylightName : 
                               TimeZoneInfo.Local.StandardName,
                     easternTimeNow, 
                     easternZone.IsDaylightSavingTime(easternTimeNow) ?
                                 easternZone.DaylightName : 
                                 easternZone.StandardName);
}
// Handle exception
//
// As an alternative to simply displaying an error message, an alternate Eastern
// Standard Time TimeZoneInfo object could be instantiated here either by restoring
// it from a serialized string or by providing the necessary data to the
// CreateCustomTimeZone method.
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.");
}
catch (SecurityException)
{
   Console.WriteLine("The application lacks permission to read time zone information from the registry.");
}
catch (OutOfMemoryException)
{
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.");
}
// If we weren't passing FindSystemTimeZoneById a literal string, we also 
// would handle an ArgumentNullException.
```

```vb
Dim timeNow As Date = Date.Now
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
   Dim easternTimeNow As Date = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, easternZone)
   Console.WriteLine("{0} {1} corresponds to {2} {3}.", _
                     timeNow, _
                     IIf(TimeZoneInfo.Local.IsDaylightSavingTime(timeNow), _
                         TimeZoneInfo.Local.DaylightName, TimeZoneInfo.Local.StandardName), _
                     easternTimeNow, _
                     IIf(easternZone.IsDaylightSavingTime(easternTimeNow), _
                         easternZone.DaylightName, easternZone.StandardName))
' Handle exception
'
' As an alternative to simply displaying an error message, an alternate Eastern
' Standard Time TimeZoneInfo object could be instantiated here either by restoring
' it from a serialized string or by providing the necessary data to the
' CreateCustomTimeZone method.
Catch e As InvalidTimeZoneException
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.")   
Catch e As SecurityException
   Console.WriteLine("The application lacks permission to read time zone information from the registry.")
Catch e As OutOfMemoryException
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.")
' If we weren't passing FindSystemTimeZoneById a literal string, we also 
' would handle an ArgumentNullException.
End
``` 

<span data-ttu-id="2ec2f-113">Единственный параметр метода [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) — идентификатор часового пояса, который необходимо получить и который соответствует свойству [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) объекта.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-113">The [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) method's single parameter is the identifier of the time zone that you want to retrieve, which corresponds to the object's [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) property.</span></span> <span data-ttu-id="2ec2f-114">Идентификатор часового пояса — это важнейшее поле, которое уникально идентифицирует часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-114">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="2ec2f-115">Несмотря на то что большинство ключей являются относительно короткими, идентификатор часового пояса относительно длинный.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-115">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="2ec2f-116">В большинстве случаев его значение соответствует свойству [StandardName](xref:System.TimeZoneInfo.StandardName) объекта [TimeZoneInfo](xref:System.TimeZoneInfo), которое используется для предоставления имени стандартного времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-116">In most cases, its value corresponds to the [StandardName](xref:System.TimeZoneInfo.StandardName) property of a [TimeZoneInfo](xref:System.TimeZoneInfo) object, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="2ec2f-117">Однако существуют исключения.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-117">However, there are exceptions.</span></span> <span data-ttu-id="2ec2f-118">Лучше всего гарантировать, что передается действительный идентификатор, путем перечисления доступных в системе часовых поясов и отслеживания присутствующих в них идентификаторов часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-118">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note the identifiers of the time zones present on them.</span></span> <span data-ttu-id="2ec2f-119">Пример см. в разделе [Практическое руководство. Перечисление присутствующих на компьютере часовых поясов](enumerate-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="2ec2f-119">For an illustration, see [How to: enumerate time zones present on a computer](enumerate-time-zones.md).</span></span> <span data-ttu-id="2ec2f-120">В разделе [Поиск часового пояса, заданного в локальной системе](finding-the-time-zones-on-local-system.md) также представлен список выбранных идентификаторов часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="2ec2f-120">The [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md) topic also contains a list of selected time zone identifiers.</span></span>

<span data-ttu-id="2ec2f-121">Если часовой пояс найден, метод возвращает его объект [TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="2ec2f-121">If the time zone is found, the method returns its [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span> <span data-ttu-id="2ec2f-122">Если часовой пояс найден, но его данные повреждены или неполны, метод создает исключение [InvalidTimeZoneException](xref:System.InvalidTimeZoneException).</span><span class="sxs-lookup"><span data-stu-id="2ec2f-122">If the time zone is found but its data is corrupted or incomplete, the method throws an [InvalidTimeZoneException](xref:System.InvalidTimeZoneException).</span></span> 

## <a name="see-also"></a><span data-ttu-id="2ec2f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2ec2f-123">See Also</span></span>

[<span data-ttu-id="2ec2f-124">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="2ec2f-124">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="2ec2f-125">Поиск часового пояса, заданного в локальной системе</span><span class="sxs-lookup"><span data-stu-id="2ec2f-125">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)
