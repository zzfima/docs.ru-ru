---
title: "Взаимное преобразование структур DateTime и DateTimeOffset"
description: "Взаимное преобразование структур DateTime и DateTimeOffset"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: fab3af5b-5d0f-4384-a40a-1b5d99b30dd1
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 2ba70e9ea39148d040bdb46d5e00ea50dcbb8980
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="converting-between-datetime-and-datetimeoffset"></a><span data-ttu-id="45d21-104">Взаимное преобразование структур DateTime и DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="45d21-104">Converting between DateTime and DateTimeOffset</span></span>

<span data-ttu-id="45d21-105">Хотя структура [System.DateTimeOffset](xref:System.DateTimeOffset) обеспечивает лучшую поддержку часовых поясов, чем структура [System.DateTime](xref:System.DateTime), параметры [DateTime](xref:System.DateTime) чаще используются в вызовах методов.</span><span class="sxs-lookup"><span data-stu-id="45d21-105">Although the [System.DateTimeOffset](xref:System.DateTimeOffset) structure provides a greater degree of time zone awareness than the [System.DateTime](xref:System.DateTime) structure, [DateTime](xref:System.DateTime) parameters are used more commonly in method calls.</span></span> <span data-ttu-id="45d21-106">Таким образом, возможность преобразования значений [DateTimeOffset](xref:System.DateTimeOffset) в значения [DateTime](xref:System.DateTime) и наоборот играет особенно важную роль.</span><span class="sxs-lookup"><span data-stu-id="45d21-106">Because of this, the ability to convert [DateTimeOffset](xref:System.DateTimeOffset) values to [DateTime](xref:System.DateTime) values and vice versa is particularly important.</span></span> <span data-ttu-id="45d21-107">В этом разделе показано, как выполнять эти преобразования таким образом, чтобы сохранять как можно больше сведений о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="45d21-107">This article shows how to perform these conversions in a way that preserves as much time zone information as possible.</span></span>

> [!NOTE]
> <span data-ttu-id="45d21-108">Типы [DateTime](xref:System.DateTime) и [DateTimeOffset](xref:System.DateTimeOffset) имеют некоторые ограничения при представлении времени в часовых поясах.</span><span class="sxs-lookup"><span data-stu-id="45d21-108">Both the [DateTime](xref:System.DateTime) and the [DateTimeOffset](xref:System.DateTimeOffset) types have some limitations when representing times in time zones.</span></span> <span data-ttu-id="45d21-109">Благодаря свойству [Kind](xref:System.DateTime.Kind) объект [DateTime](xref:System.DateTime) может автоматически устанавливать только время в формате UTC и время в местном часовом поясе системы.</span><span class="sxs-lookup"><span data-stu-id="45d21-109">With its [Kind](xref:System.DateTime.Kind) property, [DateTime](xref:System.DateTime) is able to reflect only Coordinated Universal Time (UTC) and the system's local time zone.</span></span> <span data-ttu-id="45d21-110">[DateTimeOffset](xref:System.DateTimeOffset) автоматически устанавливает смещение времени от времени UTC, но не устанавливает фактический часовой пояс, к которому относится это смещение.</span><span class="sxs-lookup"><span data-stu-id="45d21-110">[DateTimeOffset](xref:System.DateTimeOffset) reflects a time's offset from UTC, but it does not reflect the actual time zone to which that offset belongs.</span></span> <span data-ttu-id="45d21-111">Дополнительные сведения о значениях времени и поддержке часовых поясов см. в разделе [Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](choosing-between-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="45d21-111">For details about time values and support for time zones, see [Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md).</span></span>

## <a name="conversions-from-datetime-to-datetimeoffset"></a><span data-ttu-id="45d21-112">Преобразование DateTime в DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="45d21-112">Conversions from DateTime to DateTimeOffset</span></span>

<span data-ttu-id="45d21-113">Структура [DateTimeOffset](xref:System.DateTimeOffset) предоставляет два равнозначных способа выполнения преобразования [DateTime](xref:System.DateTime) в [DateTimeOffset](xref:System.DateTimeOffset), которые подходят для большинства преобразований:</span><span class="sxs-lookup"><span data-stu-id="45d21-113">The [DateTimeOffset](xref:System.DateTimeOffset) structure provides two equivalent ways to perform [DateTime](xref:System.DateTime) to [DateTimeOffset](xref:System.DateTimeOffset) conversion that are suitable for most conversions:</span></span>

* <span data-ttu-id="45d21-114">Конструктор [DateTimeOffset](xref:System.DateTimeOffset), который создает новый объект [DateTimeOffset](xref:System.DateTimeOffset) на основе значения [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="45d21-114">The [DateTimeOffset(DateTime)](xref:System.DateTimeOffset) constructor, which creates a new [DateTimeOffset](xref:System.DateTimeOffset) object based on a [DateTime](xref:System.DateTime) value.</span></span>

* <span data-ttu-id="45d21-115">Оператор неявного преобразования, позволяющий назначить значение [DateTime](xref:System.DateTime) объекту [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="45d21-115">The implicit conversion operator, which allows you to assign a [DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) object.</span></span>

<span data-ttu-id="45d21-116">Для времени UTC и местных значений [DateTime](xref:System.DateTime) свойство [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) результирующего значения [DateTimeOffset](xref:System.DateTimeOffset) точно отражает время UTC или смещение местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="45d21-116">For UTC and local [DateTime](xref:System.DateTime) values, the [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) property of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value accurately reflects the UTC or local time zone offset.</span></span> <span data-ttu-id="45d21-117">Например, следующий код преобразует время UTC в эквивалентное значение [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="45d21-117">For example, the following code converts a UTC time to its equivalent [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> 

```csharp
DateTime utcTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
utcTime1 = DateTime.SpecifyKind(utcTime1, DateTimeKind.Utc);
DateTimeOffset utcTime2 = utcTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  utcTime1, 
                  utcTime1.Kind.ToString(), 
                  utcTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM +00:00
```

```vb
Dim utcTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, _
                                        DateTimeKind.Utc)
Dim utcTime2 As DateTimeOffset = utcTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  utcTime1, _
                  utcTime1.Kind.ToString(), _
                  utcTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM  +00:00
```

<span data-ttu-id="45d21-118">В этом случае смещение переменной `utcTime2` равняется 00:00.</span><span class="sxs-lookup"><span data-stu-id="45d21-118">In this case, the offset of the `utcTime2` variable is 00:00.</span></span> <span data-ttu-id="45d21-119">Аналогичным образом следующий код преобразует местное время в эквивалентное значение [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="45d21-119">Similarly, the following code converts a local time to its equivalent [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
DateTime localTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
localTime1 = DateTime.SpecifyKind(localTime1, DateTimeKind.Local);
DateTimeOffset localTime2 = localTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  localTime1, 
                  localTime1.Kind.ToString(), 
                  localTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim localTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, DateTimeKind.Local)
Dim localTime2 As DateTimeOffset = localTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  localTime1, _
                  localTime1.Kind.ToString(), _
                  localTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

<span data-ttu-id="45d21-120">Однако для значений [DateTime](xref:System.DateTime), свойство [Kind](xref:System.DateTime.Kind) которых имеет значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), эти два метода преобразования возвращают значение [DateTimeOffset](xref:System.DateTimeOffset), смещением которого является смещение этого часового пояса.</span><span class="sxs-lookup"><span data-stu-id="45d21-120">However, for [DateTime](xref:System.DateTime) values whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), these two conversion methods produce a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset is that of the local time zone.</span></span> <span data-ttu-id="45d21-121">Это показано в приведенном ниже примере, который выполняется в тихоокеанском стандартном часовом поясе США.</span><span class="sxs-lookup"><span data-stu-id="45d21-121">This is shown in the following example, which is run in the U.S. Pacific Standard Time zone.</span></span>

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);  // Kind is DateTimeKind.Unspecified
DateTimeOffset time2 = time1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  time1, 
                  time1.Kind.ToString(), 
                  time2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Dim time2 As DateTimeOffset = time1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  time1, _
                  time1.Kind.ToString(), _
                  time2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

<span data-ttu-id="45d21-122">Если значение [DateTime](xref:System.DateTime) отражает дату и время в часовом поясе, отличном от местного часового пояса или от UTC, то можно преобразовать его в значение [DateTimeOffset](xref:System.DateTimeOffset) и сохранить сведения о его часовом поясе, вызвав перегруженный конструктор [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="45d21-122">If the [DateTime](xref:System.DateTime) value reflects the date and time in something other than the local time zone or UTC, you can convert it to a [DateTimeOffset](xref:System.DateTimeOffset) value and preserve its time zone information by calling the overloaded [DateTimeOffset(DateTime, TimeSpan)](xref:System.DateTimeOffset) constructor.</span></span> <span data-ttu-id="45d21-123">Например, в следующем примере создается экземпляр [DateTimeOffset](xref:System.DateTimeOffset), который отражает центральное стандартное время.</span><span class="sxs-lookup"><span data-stu-id="45d21-123">For example, the following example instantiates a [DateTimeOffset](xref:System.DateTimeOffset) object that reflects Central Standard Time.</span></span>

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);     // Kind is DateTimeKind.Unspecified
try
{
   DateTimeOffset time2 = new DateTimeOffset(time1, 
                  TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)); 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", 
                     time1, 
                     time1.Kind.ToString(), 
                     time2);
}
// Handle exception if time zone is not defined in registry
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to identify target time zone for conversion.");
}
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Try
   Dim time2 As New DateTimeOffset(time1, _
                    TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)) 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", _
                     time1, _
                     time1.Kind.ToString(), _
                     time2)
' Handle exception if time zone is not defined in registry
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to identify target time zone for conversion.")
End Try
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

<span data-ttu-id="45d21-124">Вторым параметром в этом перегруженном конструкторе является объект [System.TimeSpan](xref:System.TimeSpan), представляющий смещение времени от UTC, который должен быть извлечен посредством вызова метода [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo) соответствующего часового пояса.</span><span class="sxs-lookup"><span data-stu-id="45d21-124">The second parameter to this constructor overload, a [System.TimeSpan](xref:System.TimeSpan) object that represents the time's offset from UTC, should be retrieved by calling the [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo) method of the time's corresponding time zone.</span></span> <span data-ttu-id="45d21-125">Единственным параметром данного метода является значение [DateTime](xref:System.DateTime), представляющее дату и время, которые требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="45d21-125">The method's single parameter is the [DateTime](xref:System.DateTime) value that represents the date and time to be converted.</span></span> <span data-ttu-id="45d21-126">Если часовой пояс поддерживает переход на летнее время, то этот параметр позволяет методу определять соответствующее смещение для конкретных даты и времени.</span><span class="sxs-lookup"><span data-stu-id="45d21-126">If the time zone supports daylight saving time, this parameter allows the method to determine the appropriate offset for that particular date and time.</span></span>

## <a name="conversions-from-datetimeoffset-to-datetime"></a><span data-ttu-id="45d21-127">Преобразование DateTimeOffset в DateTime</span><span class="sxs-lookup"><span data-stu-id="45d21-127">Conversions from DateTimeOffset to DateTime</span></span>

<span data-ttu-id="45d21-128">Свойство [DateTime](xref:System.DateTime) чаще всего используется для выполнения преобразования [DateTimeOffset](xref:System.DateTimeOffset) в [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="45d21-128">The [DateTime](xref:System.DateTime) property is most commonly used to perform [DateTimeOffset](xref:System.DateTimeOffset) to [DateTime](xref:System.DateTime) conversion.</span></span> <span data-ttu-id="45d21-129">Тем не менее, оно возвращает значение [DateTime](xref:System.DateTime), свойством [Kind](xref:System.DateTime.Kind) которого является [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="45d21-129">However, it returns a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), as the following example illustrates.</span></span> 

```csharp
DateTime baseTime = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset sourceTime;
DateTime targetTime;

// Convert UTC to DateTime value
sourceTime = new DateTimeOffset(baseTime, TimeSpan.Zero);
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert local time to DateTime value
sourceTime = new DateTimeOffset(baseTime, 
                                TimeZoneInfo.Local.GetUtcOffset(baseTime));
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert Central Standard Time to a DateTime value
try
{
   TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime);
   sourceTime = new DateTimeOffset(baseTime, offset);
   targetTime = sourceTime.DateTime;
   Console.WriteLine("{0} converts to {1} {2}", 
                     sourceTime, 
                     targetTime, 
                     targetTime.Kind.ToString());
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.");
} 
// This example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

```vb
Const baseTime As Date = #06/19/2008 7:00AM#
Dim sourceTime As DateTimeOffset
Dim targetTime As Date

' Convert UTC to DateTime value
sourceTime = New DateTimeOffset(baseTime, TimeSpan.Zero)
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert local time to DateTime value
sourceTime = New DateTimeOffset(baseTime, _
                                TimeZoneInfo.Local.GetUtcOffset(baseTime))
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert Central Standard Time to a DateTime value
Try
   Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime)
   sourceTime = New DateTimeOffset(baseTime, offset)
   targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.")
End Try 
' This example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

<span data-ttu-id="45d21-130">Это означает, что все сведения о связи значения [DateTimeOffset](xref:System.DateTimeOffset) с UTC будут потеряны при преобразовании, когда используется свойство [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="45d21-130">This means that any information about the [DateTimeOffset](xref:System.DateTimeOffset) value's relationship to UTC is lost by the conversion when the [DateTime](xref:System.DateTime) property is used.</span></span> <span data-ttu-id="45d21-131">Это влияет на значения [DateTimeOffset](xref:System.DateTimeOffset), которые соответствуют времени UTC или локальному времени системы, так как структура [DateTime](xref:System.DateTime) отражает только эти два часовых пояса в свойстве [Kind](xref:System.DateTime.Kind).</span><span class="sxs-lookup"><span data-stu-id="45d21-131">This affects [DateTimeOffset](xref:System.DateTimeOffset) values that correspond to UTC time or to the system's local time because the [DateTime](xref:System.DateTime) structure reflects only those two time zones in its [Kind](xref:System.DateTime.Kind) property.</span></span>

<span data-ttu-id="45d21-132">Чтобы сохранить как можно больше сведений о часовом поясе при преобразовании [DateTimeOffset](xref:System.DateTimeOffset) в значение [DateTime](xref:System.DateTime), можно использовать свойства [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) и [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime).</span><span class="sxs-lookup"><span data-stu-id="45d21-132">To preserve as much time zone information as possible when converting a [DateTimeOffset](xref:System.DateTimeOffset) to a [DateTime](xref:System.DateTime) value, you can use the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) and [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) properties.</span></span> 

## <a name="converting-a-utc-time"></a><span data-ttu-id="45d21-133">Преобразование времени UTC</span><span class="sxs-lookup"><span data-stu-id="45d21-133">Converting a UTC Time</span></span>

<span data-ttu-id="45d21-134">Чтобы указать, что преобразуемое значение [DateTime](xref:System.DateTime) является временем UTC, можно получить значение свойства [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime).</span><span class="sxs-lookup"><span data-stu-id="45d21-134">To indicate that a converted [DateTime](xref:System.DateTime) value is the UTC time, you can retrieve the value of the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property.</span></span> <span data-ttu-id="45d21-135">Оно отличается от свойства [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) двумя особенностями:</span><span class="sxs-lookup"><span data-stu-id="45d21-135">It differs from the [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) property in two ways:</span></span>

* <span data-ttu-id="45d21-136">Оно возвращает значение [DateTime](xref:System.DateTime), свойством [Kind](xref:System.DateTime.Kind) которого является [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span><span class="sxs-lookup"><span data-stu-id="45d21-136">It returns a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

* <span data-ttu-id="45d21-137">Если значение свойства [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) не равно [TimeSpan.Zero](xref:System.TimeSpan.Zero), то оно преобразуется во время UTC.</span><span class="sxs-lookup"><span data-stu-id="45d21-137">If the [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) property value does not equal [TimeSpan.Zero](xref:System.TimeSpan.Zero), it converts the time to UTC.</span></span>

> [!NOTE]
> <span data-ttu-id="45d21-138">Если для приложения необходимо, чтобы преобразованные значения [DateTime](xref:System.DateTime) однозначно идентифицировали единственный момент времени, то следует использовать свойство [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) для обработки всех преобразований из [DateTimeOffset](xref:System.DateTimeOffset) в [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="45d21-138">If your application requires that converted [DateTime](xref:System.DateTime) values unambiguously identify a single point in time, you should consider using the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property to handle all [DateTimeOffset](xref:System.DateTimeOffset) to [DateTime](xref:System.DateTime) conversions.</span></span>

<span data-ttu-id="45d21-139">Следующий код использует свойство [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) для преобразования значения [DateTimeOffset](xref:System.DateTimeOffset), смещение которого равно [TimeSpan.Zero](xref:System.TimeSpan.Zero), в значение [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="45d21-139">The following code uses the [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property to convert a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset equals [TimeSpan.Zero](xref:System.TimeSpan.Zero) to a [DateTime](xref:System.DateTime) value.</span></span>

```csharp
DateTimeOffset utcTime1 = new DateTimeOffset(2008, 6, 19, 7, 0, 0, TimeSpan.Zero);
DateTime utcTime2 = utcTime1.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

```vb
Dim utcTime1 As New DateTimeOffset(#06/19/2008 7:00AM#, TimeSpan.Zero)
Dim utcTime2 As Date = utcTime1.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

<span data-ttu-id="45d21-140">Следующий код использует свойство "UtcDateTime" для преобразования часового пояса и преобразования типов значения [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="45d21-140">The following code uses the UtcDateTime property to perform both a time zone conversion and a type conversion on a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
DateTimeOffset originalTime = new DateTimeOffset(2008, 6, 19, 7, 0, 0, new TimeSpan(5, 0, 0));
DateTime utcTime = originalTime.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalTime, 
                  utcTime, 
                  utcTime.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

```vb
Dim originalTime As New DateTimeOffset(#6/19/2008 7:00AM#, _
                                       New TimeSpan(5, 0, 0))
Dim utcTime As Date = originalTime.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _ 
                  originalTime, _
                  utcTime, _
                  utcTime.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

## <a name="converting-a-local-time"></a><span data-ttu-id="45d21-141">Преобразование локального времени</span><span class="sxs-lookup"><span data-stu-id="45d21-141">Converting a Local Time</span></span>

<span data-ttu-id="45d21-142">Чтобы указать, что значение [DateTimeOffset](xref:System.DateTimeOffset) представляет локальное время, можно передать значение [DateTime](xref:System.DateTime), возвращенное свойством [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) в static метода [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)).</span><span class="sxs-lookup"><span data-stu-id="45d21-142">To indicate that a [DateTimeOffset](xref:System.DateTimeOffset) value represents the local time, you can pass the [DateTime](xref:System.DateTime) value returned by the [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) property to the static [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method.</span></span> <span data-ttu-id="45d21-143">Этот метод возвращает дату и время, переданные ему в качестве первого параметра, но устанавливает для свойства [Kind](xref:System.DateTime.Kind) значение, указанное ему в качестве второго параметра.</span><span class="sxs-lookup"><span data-stu-id="45d21-143">The method returns the date and time passed to it as its first parameter, but sets the [Kind](xref:System.DateTime.Kind) property to the value specified by its second parameter.</span></span> <span data-ttu-id="45d21-144">В следующем коде используется метод [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) при преобразовании значения [DateTimeOffset](xref:System.DateTimeOffset), смещение которого соответствует смещению местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="45d21-144">The following code uses the [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method when converting a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset corresponds to that of the local time zone.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset utcTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime utcTime2 = utcTime1.DateTime;
if (utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime))) 
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local);

Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim utcTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim utcTime2 As Date = utcTime1.DateTime
If utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime)) Then
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local)
End If   
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

<span data-ttu-id="45d21-145">Также можно использовать свойство [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) для преобразования значения [DateTimeOffset](xref:System.DateTimeOffset) в локальное значение [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="45d21-145">You can also use the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to convert a [DateTimeOffset](xref:System.DateTimeOffset) value to a local [DateTime](xref:System.DateTime) value.</span></span> <span data-ttu-id="45d21-146">Свойством [Kind](xref:System.DateTime.Kind) возвращаемого значения [DateTime](xref:System.DateTime) является [DateTimeKind.Local](xref:System.DateTimeKind.Local).</span><span class="sxs-lookup"><span data-stu-id="45d21-146">The [Kind](xref:System.DateTime.Kind) property of the returned [DateTime](xref:System.DateTime) value is [DateTimeKind.Local](xref:System.DateTimeKind.Local).</span></span> <span data-ttu-id="45d21-147">В следующем коде используется свойство [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) при преобразовании значения [DateTimeOffset](xref:System.DateTimeOffset), смещение которого соответствует смещению местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="45d21-147">The following code uses the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property when converting a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset corresponds to that of the local time zone.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset localTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime localTime2 = localTime1.LocalDateTime;

Console.WriteLine("{0} converted to {1} {2}", 
                  localTime1, 
                  localTime2, 
                  localTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim localTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim localTime2 As Date = localTime1.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime1, _
                  localTime2, _
                  localTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local 
```

<span data-ttu-id="45d21-148">При извлечении значения [DateTime](xref:System.DateTime) с помощью свойства [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) метод доступа `get` свойства сначала преобразует значение [DateTimeOffset](xref:System.DateTimeOffset) в UTC, а затем преобразует его в локальное время посредством вызова метода [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="45d21-148">When you retrieve a [DateTime](xref:System.DateTime) value using the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property, the property's `get` accessor first converts the [DateTimeOffset](xref:System.DateTimeOffset) value to UTC, then converts it to local time by calling the [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset) method.</span></span> <span data-ttu-id="45d21-149">Это означает, что вы можете получить значение свойства [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) для выполнения преобразования в момент выполнения преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="45d21-149">This means that you can retrieve a value from the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to perform a time zone conversion at the same time that you perform a type conversion.</span></span> <span data-ttu-id="45d21-150">Это также означает, что при выполнении преобразования применяются правила коррекции местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="45d21-150">It also means that the local time zone's adjustment rules are applied in performing the conversion.</span></span> <span data-ttu-id="45d21-151">Следующий код иллюстрирует использование свойства [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) для выполнения преобразования и типа, и часового пояса.</span><span class="sxs-lookup"><span data-stu-id="45d21-151">The following code illustrates the use of the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to perform both a type and a time zone conversion.</span></span>

```csharp
DateTimeOffset originalDate;
DateTime localDate;

// Convert time originating in a different time zone
originalDate = new DateTimeOffset(2008, 6, 18, 7, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// Convert time originating in a different time zone 
// so local time zone's adjustment rules are applied
originalDate = new DateTimeOffset(2007, 11, 4, 4, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
//       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

```vb
Dim originalDate As DateTimeOffset
Dim localDate As Date

' Convert time originating in a different time zone
originalDate = New DateTimeOffset(#06/19/2008 7:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' Convert time originating in a different time zone 
' so local time zone's adjustment rules are applied
originalDate = New DateTimeOffset(#11/04/2007 4:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
'       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

## <a name="a-general-purpose-conversion-method"></a><span data-ttu-id="45d21-152">Метод преобразования общего назначения</span><span class="sxs-lookup"><span data-stu-id="45d21-152">A General-Purpose Conversion Method</span></span>

<span data-ttu-id="45d21-153">В следующем примере определяется метод с именем `ConvertFromDateTimeOffset`, который преобразует значения [DateTimeOffset](xref:System.DateTimeOffset) в значения [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="45d21-153">The following example defines a method named `ConvertFromDateTimeOffset` that converts [DateTimeOffset](xref:System.DateTimeOffset) values to [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="45d21-154">В зависимости от смещения, он определяет, является ли значение [DateTimeOffset](xref:System.DateTimeOffset) временем UTC, локальным временем или другим временем, и соответствующим образом определяет свойство [Kind](xref:System.DateTime.Kind) возвращаемого значения даты и времени.</span><span class="sxs-lookup"><span data-stu-id="45d21-154">Based on its offset, it determines whether the [DateTimeOffset](xref:System.DateTimeOffset) value is a UTC time, a local time, or some other time, and defines the returned date and time value's [Kind](xref:System.DateTime.Kind) property accordingly.</span></span> 

```csharp
static DateTime ConvertFromDateTimeOffset(DateTimeOffset dateTime)
{
   if (dateTime.Offset.Equals(TimeSpan.Zero))
      return dateTime.UtcDateTime;
   else if (dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime)))
      return DateTime.SpecifyKind(dateTime.DateTime, DateTimeKind.Local);
   else
      return dateTime.DateTime;   
}
```

```vb
Function ConvertFromDateTimeOffset(dateTime As DateTimeOffset) As Date
   If dateTime.Offset.Equals(TimeSpan.Zero) Then
      Return dateTime.UtcDateTime
   ElseIf dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime))
      Return Date.SpecifyKind(dateTime.DateTime, DateTimeKind.Local)
   Else
      Return dateTime.DateTime   
   End If
```

<span data-ttu-id="45d21-155">В следующем примере вызывается метод `ConvertFromDateTimeOffset` для преобразования значений [DateTimeOffset](xref:System.DateTimeOffset), представляющих время UTC, местное время и время центрального стандартного часового пояса США.</span><span class="sxs-lookup"><span data-stu-id="45d21-155">The follow example calls the `ConvertFromDateTimeOffset` method to convert [DateTimeOffset](xref:System.DateTimeOffset) values that represent a UTC time, a local time, and a time in the U.S. Central Standard Time zone.</span></span>

```csharp
DateTime timeComponent = new DateTime(2008, 6, 19, 7, 0, 0);
DateTime returnedDate; 

// Convert UTC time
DateTimeOffset utcTime = new DateTimeOffset(timeComponent, TimeSpan.Zero);
returnedDate = ConvertFromDateTimeOffset(utcTime); 
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert local time
DateTimeOffset localTime = new DateTimeOffset(timeComponent, 
                           TimeZoneInfo.Local.GetUtcOffset(timeComponent)); 
returnedDate = ConvertFromDateTimeOffset(localTime);                                          
Console.WriteLine("{0} converted to {1} {2}", 
                  localTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert Central Standard Time
DateTimeOffset cstTime = new DateTimeOffset(timeComponent, 
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent));
returnedDate = ConvertFromDateTimeOffset(cstTime);
Console.WriteLine("{0} converted to {1} {2}", 
                  cstTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());
// The example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
//    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
//    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

```vb
Dim timeComponent As Date = #06/19/2008 7:00AM#
Dim returnedDate As Date 

' Convert UTC time
Dim utcTime As New DateTimeOffset(timeComponent, TimeSpan.Zero)
returnedDate = ConvertFromDateTimeOffset(utcTime) 
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert local time
Dim localTime As New DateTimeOffset(timeComponent, _
                                    TimeZoneInfo.Local.GetUtcOffset(timeComponent)) 
returnedDate = ConvertFromDateTimeOffset(localTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert Central Standard Time
Dim cstTime As New DateTimeOffset(timeComponent, _
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent))
returnedDate = ConvertFromDateTimeOffset(cstTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  cstTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())
' The example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
'    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
'    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

<span data-ttu-id="45d21-156">Обратите внимание, что этот код делает два предположения, которые в зависимости от применения и источника значений даты и времени могут оказаться недопустимыми:</span><span class="sxs-lookup"><span data-stu-id="45d21-156">Note that this code makes two assumptions that, depending on the application and the source of its date and time values, may not always be valid:</span></span>

* <span data-ttu-id="45d21-157">Предполагается, что значение даты и времени, смещение которого равно [TimeSpan.Zero](xref:System.TimeSpan.Zero), представляет время UTC.</span><span class="sxs-lookup"><span data-stu-id="45d21-157">It assumes that a date and time value whose offset is [TimeSpan.Zero](xref:System.TimeSpan.Zero) represents UTC.</span></span> <span data-ttu-id="45d21-158">На самом деле UTC не является временем в определенном часовом поясе, но оно является временем, по отношению к которому стандартизованы времена часовых поясов в мире.</span><span class="sxs-lookup"><span data-stu-id="45d21-158">In fact, UTC is not a time in a particular time zone, but the time in relation to which the times in the world's time zones are standardized.</span></span> <span data-ttu-id="45d21-159">Часовые пояса также могут иметь смещение [Zero](xref:System.TimeSpan.Zero).</span><span class="sxs-lookup"><span data-stu-id="45d21-159">Time zones can also have an offset of [Zero](xref:System.TimeSpan.Zero).</span></span>

* <span data-ttu-id="45d21-160">Предполагается, что значение даты и времени, смещение для которого равно смещению местного часового пояса, представляет местный часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="45d21-160">It assumes that a date and time whose offset equals that of the local time zone represents the local time zone.</span></span> <span data-ttu-id="45d21-161">Поскольку значения даты и времени не связаны со своими исходными часовыми поясами, то это может не выполняться. Значение даты и времени может быть создано в другом часовом поясе с тем же самым смещением.</span><span class="sxs-lookup"><span data-stu-id="45d21-161">Because date and time values are disassociated from their original time zone, this may not be the case; the date and time can have originated in another time zone with the same offset.</span></span>

## <a name="see-also"></a><span data-ttu-id="45d21-162">См. также</span><span class="sxs-lookup"><span data-stu-id="45d21-162">See Also</span></span>

[<span data-ttu-id="45d21-163">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="45d21-163">Dates, times, and time zones</span></span>](index.md)





