---
title: "Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов"
description: "Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 13454d47-d957-421b-9ecd-940058b8835e
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: fcc48e40cdad25c6142dbc3a86513b816378fa4b
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="4489b-104">Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов</span><span class="sxs-lookup"><span data-stu-id="4489b-104">How to: access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="4489b-105">Класс [System.TimeZoneInfo](xref:System.TimeZoneInfo) имеет свойства `Utc` и `Local`, обеспечивающие доступ к предопределенным объектам часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="4489b-105">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class provides two properties, `Utc` and `Local`, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="4489b-106">В этом разделе рассматривается порядок работы с объектами `TimeZoneInfo`, возвращаемыми этими свойствами.</span><span class="sxs-lookup"><span data-stu-id="4489b-106">This topic discusses how to access the `TimeZoneInfo` objects returned by those properties.</span></span>

## <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="4489b-107">Получение объекта TimeZoneInfo времени UTC</span><span class="sxs-lookup"><span data-stu-id="4489b-107">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="4489b-108">Для получения времени в формате UTC следует использовать статическое (**static**, **Shared** в языке Visual Basic) свойство [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc).</span><span class="sxs-lookup"><span data-stu-id="4489b-108">Use the **static** (**Shared** in Visual Basic) [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="4489b-109">Вместо того чтобы сохранять возвращаемый этим свойством объект [TimeZoneInfo](xref:System.TimeZoneInfo) в объектной переменной, следует работать со временем в формате UTC с помощью свойства [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc).</span><span class="sxs-lookup"><span data-stu-id="4489b-109">Rather than assigning the [TimeZoneInfo](xref:System.TimeZoneInfo) object returned by the property to an object variable, continue to access Coordinated Universal Time through the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property.</span></span>


## <a name="to-access-the-local-time-zone"></a><span data-ttu-id="4489b-110">Получение местного часового пояса</span><span class="sxs-lookup"><span data-stu-id="4489b-110">To access the local time zone</span></span>

1. <span data-ttu-id="4489b-111">Для получения часового пояса локальной системы следует использовать статическое (**static**, **Shared** в языке Visual Basic) свойство [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span><span class="sxs-lookup"><span data-stu-id="4489b-111">Use the **static** (**Shared** in Visual Basic) [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property to access the local system time zone.</span></span>

2. <span data-ttu-id="4489b-112">Вместо того чтобы сохранять возвращаемый этим свойством объект [TimeZoneInfo](xref:System.TimeZoneInfo) в объектной переменной, следует работать с местным часовым поясом с помощью свойства [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span><span class="sxs-lookup"><span data-stu-id="4489b-112">Rather than assigning the [TimeZoneInfo](xref:System.TimeZoneInfo) object returned by the property to an object variable, continue to access the local time zone through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property.</span></span>

## <a name="example"></a><span data-ttu-id="4489b-113">Пример</span><span class="sxs-lookup"><span data-stu-id="4489b-113">Example</span></span>

<span data-ttu-id="4489b-114">В следующем коде свойства [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) и [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.</span><span class="sxs-lookup"><span data-stu-id="4489b-114">The following code uses the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) and [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

```csharp
// Create Eastern Standard Time value and TimeZoneInfo object      
DateTime estTime = new DateTime(2007, 1, 1, 00, 00, 00);
string timeZoneName = "Eastern Standard Time";
try
{
   TimeZoneInfo est = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName);

   // Convert EST to local time
   DateTime localTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local);
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", 
           estTime, 
           est, 
           localTime, 
           TimeZoneInfo.Local.IsDaylightSavingTime(localTime) ?
                     TimeZoneInfo.Local.DaylightName : 
                     TimeZoneInfo.Local.StandardName);

   // Convert EST to UTC
   DateTime utcTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc);
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", 
           estTime, 
           est, 
           utcTime, 
           TimeZoneInfo.Utc.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The {0} zone cannot be found in the registry.", 
                     timeZoneName);
}
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The registry contains invalid data for the {0} zone.", 
                     timeZoneName);
}
```

```vb
' Create Eastern Standard Time value and TimeZoneInfo object      
Dim estTime As Date = #01/01/2007 00:00:00#
Dim timeZoneName As String = "Eastern Standard Time"
Try
   Dim est As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName)

   ' Convert EST to local time
   Dim localTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local)
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", _
           estTime, _
           est, _
           localTime, _
           IIf(TimeZoneInfo.Local.IsDaylightSavingTime(localTime), _
               TimeZoneInfo.Local.DaylightName, _
               TimeZoneInfo.Local.StandardName))

   ' Convert EST to UTC
   Dim utcTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc)
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", _
           estTime, _
           est, _
           utcTime, _
           TimeZoneInfo.Utc.StandardName)
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The {0} zone cannot be found in the registry.", _
                     timeZoneName)
Catch e As InvalidTimeZoneException
   Console.WriteLine("The registry contains invalid data for the {0} zone.", _
                     timeZoneName)
End Try
```

<span data-ttu-id="4489b-115">Вместо того чтобы сохранять местный часовой пояс в объектной переменной [TimeZoneInfo](xref:System.TimeZoneInfo), работать с местным часовым поясом всегда следует через свойство [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span><span class="sxs-lookup"><span data-stu-id="4489b-115">You should always access the local time zone through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property rather than assigning the local time zone to a [TimeZoneInfo](xref:System.TimeZoneInfo) object variable.</span></span> <span data-ttu-id="4489b-116">Подобным образом, вместо того чтобы сохранять часовой пояс UTC в объектной переменной [TimeZoneInfo](xref:System.TimeZoneInfo), работать со временем в формате UTC всегда следует с помощью свойства [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc).</span><span class="sxs-lookup"><span data-stu-id="4489b-116">Similarly, you should always access Coordinated Universal Time through the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property rather than assigning the UTC zone to a [TimeZoneInfo](xref:System.TimeZoneInfo) object variable.</span></span> <span data-ttu-id="4489b-117">Это исключает присвоение объектной переменной [TimeZoneInfo](xref:System.TimeZoneInfo) недопустимого значения при вызове внешнего метода.</span><span class="sxs-lookup"><span data-stu-id="4489b-117">This prevents the [TimeZoneInfo](xref:System.TimeZoneInfo) object variable from being invalidated by an external method.</span></span>


## <a name="see-also"></a><span data-ttu-id="4489b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4489b-118">See Also</span></span>

[<span data-ttu-id="4489b-119">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="4489b-119">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="4489b-120">Поиск часового пояса, заданного в локальной системе</span><span class="sxs-lookup"><span data-stu-id="4489b-120">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)

