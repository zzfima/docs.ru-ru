---
title: "Создание экземпляра объекта DateTimeOffset"
description: "Создание экземпляра объекта DateTimeOffset"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 476fe67b-6be4-4435-88ab-ced37304f1d1
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 26be324eb5d58b94a71e89aba213f107cf8dfd1e
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="instantiating-a-datetimeoffset-object"></a><span data-ttu-id="43b69-104">Создание экземпляра объекта DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="43b69-104">Instantiating a DateTimeOffset object</span></span>

<span data-ttu-id="43b69-105">В структуре [System.DateTimeOffset](xref:System.DateTimeOffset) есть несколько способов создания новых значений [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-105">The [System.DateTimeOffset](xref:System.DateTimeOffset) structure offers a number of ways to create new [DateTimeOffset](xref:System.DateTimeOffset) values.</span></span> <span data-ttu-id="43b69-106">Многие из них непосредственно соответствуют методам создания новых значений класса [System.DateTime](xref:System.DateTime); отличающие их усовершенствования позволяют указывать смещение значения даты и времени относительно универсального синхронизированного времени (UTC).</span><span class="sxs-lookup"><span data-stu-id="43b69-106">Many of them correspond directly to the methods available for instantiating new [System.DateTime](xref:System.DateTime) values, with enhancements that allow you to specify the date and time value's offset from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="43b69-107">В частности, экземпляр значения [DateTimeOffset](xref:System.DateTimeOffset) можно создать следующими способами.</span><span class="sxs-lookup"><span data-stu-id="43b69-107">In particular, you can instantiate a [DateTimeOffset](xref:System.DateTimeOffset) value in the following ways:</span></span>

* <span data-ttu-id="43b69-108">Вызвав конструктор [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-108">By calling a [DateTimeOffset](xref:System.DateTimeOffset) constructor.</span></span>

* <span data-ttu-id="43b69-109">Неявным преобразованием в значение типа [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-109">By implicitly converting a value to [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

* <span data-ttu-id="43b69-110">Разбором строкового представления даты и времени.</span><span class="sxs-lookup"><span data-stu-id="43b69-110">By parsing the string representation of a date and time.</span></span>

## <a name="date-and-time-literals"></a><span data-ttu-id="43b69-111">Литералы даты и времени</span><span class="sxs-lookup"><span data-stu-id="43b69-111">Date and Time Literals</span></span>

<span data-ttu-id="43b69-112">Одним из наиболее распространенных способов создания экземпляров значений [DateTime](xref:System.DateTime) в языках, допускающих такую возможность, является представление даты и времени в виде жестко заданного литерала.</span><span class="sxs-lookup"><span data-stu-id="43b69-112">For languages that support it, one of the most common ways to instantiate a [DateTime](xref:System.DateTime) value is to provide the date and time as a hard-coded literal value.</span></span> <span data-ttu-id="43b69-113">Например, в следующем коде на языке Visual Basic создается объект [DateTime](xref:System.DateTime), значение которого соответствует 1 января 2008 г., 10:00.</span><span class="sxs-lookup"><span data-stu-id="43b69-113">For example, the following Visual Basic code creates a [DateTime](xref:System.DateTime) object whose value is January 1, 2008, at 10:00 AM.</span></span>

```vb
Dim literalDate1 As Date = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate1.ToString())
' Displays:
'              5/1/2008 8:06:32 AM
```

<span data-ttu-id="43b69-114">При использовании языков, поддерживающих литералы типа [DateTime](xref:System.DateTime), значения [DateTimeOffset](xref:System.DateTimeOffset) также могут инициализироваться с помощью литералов даты и времени.</span><span class="sxs-lookup"><span data-stu-id="43b69-114">[DateTimeOffset](xref:System.DateTimeOffset) values can also be initialized using date and time literals when using languages that support [DateTime](xref:System.DateTime) literals.</span></span> <span data-ttu-id="43b69-115">Например, в следующем коде на языке Visual Basic создается объект [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-115">For example, the following Visual Basic code creates a [DateTimeOffset](xref:System.DateTimeOffset) object.</span></span>

```vb
Dim literalDate As DateTimeOffset = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate.ToString())
' Displays:
'              5/1/2008 8:06:32 AM -07:00
```

<span data-ttu-id="43b69-116">По результату, выведенному на консоль, видно, что созданному таким способом значению [DateTimeOffset](xref:System.DateTimeOffset) присваивается смещение локального часового пояса.</span><span class="sxs-lookup"><span data-stu-id="43b69-116">As the console output shows, the [DateTimeOffset](xref:System.DateTimeOffset) value created in this way is assigned the offset of the local time zone.</span></span> <span data-ttu-id="43b69-117">Отсюда следует, что значение [DateTimeOffset](xref:System.DateTimeOffset), заданное с помощью знакового литерала, не будет определять один и тот же момент времени при выполнении кода на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="43b69-117">This means that a [DateTimeOffset](xref:System.DateTimeOffset) value assigned using a character literal does not identify a single point of time if the code is run on different computers.</span></span>

## <a name="datetimeoffset-constructors"></a><span data-ttu-id="43b69-118">Конструкторы DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="43b69-118">DateTimeOffset Constructors</span></span>

<span data-ttu-id="43b69-119">В классе [System.DateTimeOffset](xref:System.DateTimeOffset) определено пять конструкторов.</span><span class="sxs-lookup"><span data-stu-id="43b69-119">The [System.DateTimeOffset](xref:System.DateTimeOffset) type defines five constructors.</span></span> <span data-ttu-id="43b69-120">Три из них непосредственно соответствуют конструкторам [DateTime](xref:System.DateTime), отличаясь от них дополнительным параметром типа [System.TimeSpan](xref:System.TimeSpan), который задает смещение даты и времени относительно времени UTC.</span><span class="sxs-lookup"><span data-stu-id="43b69-120">Three of them correspond directly to [DateTime](xref:System.DateTime) constructors, with an additional parameter of type [System.TimeSpan](xref:System.TimeSpan) that defines the date and time's offset from UTC.</span></span> <span data-ttu-id="43b69-121">Они позволяют определить значение [DateTimeOffset](xref:System.DateTimeOffset) на основе значений отдельных компонентов даты и времени.</span><span class="sxs-lookup"><span data-stu-id="43b69-121">These allow you to define a [DateTimeOffset](xref:System.DateTimeOffset) value based on the value of its individual date and time components.</span></span> <span data-ttu-id="43b69-122">К примеру, в следующем коде эти четыре конструктора используются для создания объектов [DateTimeOffset](xref:System.DateTimeOffset) с одинаковыми значениями 01.07.2008, 12:05 +01:00.</span><span class="sxs-lookup"><span data-stu-id="43b69-122">For example, the following code uses these three constructors to instantiate [DateTimeOffset](xref:System.DateTimeOffset) objects with identical values of 7/1/2008 12:05 AM +01:00.</span></span>

```csharp
DateTimeOffset dateAndTime;

// Instantiate date and time using years, months, days, 
// hours, minutes, and seconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine(dateAndTime);
// Instantiate date and time using years, months, days,
// hours, minutes, seconds, and milliseconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), 
                             dateAndTime.ToString("zzz"));

// Instantiate date and time using number of ticks
// 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = new DateTimeOffset(633452259920000000, new TimeSpan(1, 0, 0));  
Console.WriteLine(dateAndTime);
// The example displays the following output to the console:
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
```

```vb
Dim dateAndTime As DateTimeOffset

' Instantiate date and time using years, months, days, 
' hours, minutes, and seconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine(dateAndTime)
' Instantiate date and time using years, months, days,
' hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using Persian calendar with years,
' months, days, hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(1387, 2, 12, 8, 6, 32, 545, New PersianCalendar, New TimeSpan(1, 0, 0))
' Note that the console output displays the date in the Gregorian
' calendar, not the Persian calendar. 
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using number of ticks
' 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = New DateTimeOffset(633452259920000000, New TimeSpan(1, 0, 0))  
Console.WriteLine(dateAndTime)
' The example displays the following output to the console:
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
```

<span data-ttu-id="43b69-123">Обратите внимание, что при инициализации значения объекта [DateTimeOffset](xref:System.DateTimeOffset) путем передачи в качестве одного из аргументов конструктора объекта [PersianCalendar](xref:System.Globalization.PersianCalendar) при последующем выводе значения на консоль дата выражается по григорианскому календарю, а не по иранскому.</span><span class="sxs-lookup"><span data-stu-id="43b69-123">Note that, when the value of the [DateTimeOffset](xref:System.DateTimeOffset) object instantiated using a [PersianCalendar](xref:System.Globalization.PersianCalendar) object as one of the arguments to its constructor is displayed to the console, it is expressed as a date in the Gregorian rather than the Persian calendar.</span></span> 

<span data-ttu-id="43b69-124">Два других конструктора создают объект [DateTimeOffset](xref:System.DateTimeOffset) по значению DateTime.</span><span class="sxs-lookup"><span data-stu-id="43b69-124">The other two constructors create a [DateTimeOffset](xref:System.DateTimeOffset) object from a DateTime value.</span></span> <span data-ttu-id="43b69-125">Единственный параметр первого из них — это значение [DateTime](xref:System.DateTime), преобразуемое в значение типа [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-125">The first of these has a single parameter, the [DateTime](xref:System.DateTime) value to convert to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="43b69-126">Смещение результирующего значения [DateTimeOffset](xref:System.DateTimeOffset) зависит от свойства [Kind](xref:System.DateTime.Kind) единственного параметра [DateTime](xref:System.DateTime) конструктора.</span><span class="sxs-lookup"><span data-stu-id="43b69-126">The offset of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value depends on the [Kind](xref:System.DateTime.Kind) property of the constructor's single [DateTime](xref:System.DateTime) parameter.</span></span> <span data-ttu-id="43b69-127">Если его значение равно [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), то смещение приравнивается к [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span><span class="sxs-lookup"><span data-stu-id="43b69-127">If its value is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the offset is set equal to [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="43b69-128">В противном случае его смещение приравнивается к смещению местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="43b69-128">Otherwise, its offset is set equal to that of the local time zone.</span></span> <span data-ttu-id="43b69-129">В следующем примере приведен пример использования этого конструктора для создания объектов [DateTimeOffset](xref:System.DateTimeOffset), представляющих UTC и местный часовой пояс:</span><span class="sxs-lookup"><span data-stu-id="43b69-129">The following example illustrates the use of this constructor to instantiate [DateTimeOffset](xref:System.DateTimeOffset) objects representing UTC and the local time zone:</span></span>

```csharp
// Declare date; Kind property is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time 
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the offset is TimeSpan.Zero.

// Instantiate a DateTimeOffset value from a UTC time with a zero offset
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a negative offset
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      targetTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM +00:00 failed.

// Instantiate a DateTimeOffset value from a local time
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local, 
// the offset is that of the local time zone.

// Instantiate a DateTimeOffset value from an unspecified time
targetTime = new DateTimeOffset(sourceDate);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Unspecified, 
// the offset is that of the local time zone.
```

```vb
' Declare date; Kind property is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time 
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc, 
' the offset is TimeSpan.Zero.


' Instantiate a DateTimeOffset value from a local time
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Local, 
' the offset is that of the local time zone.

' Instantiate a DateTimeOffset value from an unspecified time
targetTime = New DateTimeOffset(sourceDate)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Unspecified, 
' the offset is that of the local time zone.
```

> [!NOTE]
> <span data-ttu-id="43b69-130">Вызов перегрузки конструктора [DateTimeOffset](xref:System.DateTimeOffset), принимающей одиночный параметр [DateTime](xref:System.DateTime), эквивалентен выполнению неявного преобразования значения типа [DateTime](xref:System.DateTime) в значение типа [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-130">Calling the overload of the [DateTimeOffset](xref:System.DateTimeOffset) constructor that has a single [DateTime](xref:System.DateTime) parameter is equivalent to performing an implicit conversion of a [DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

<span data-ttu-id="43b69-131">Второй конструктор, создающий объект класса [DateTimeOffset](xref:System.DateTimeOffset) по значению [DateTime](xref:System.DateTime), имеет два параметра: преобразуемое значение [DateTime](xref:System.DateTime) и значение [TimeSpan](xref:System.TimeSpan), задающее смещение даты и времени относительно UTC.</span><span class="sxs-lookup"><span data-stu-id="43b69-131">The second constructor that creates a [DateTimeOffset](xref:System.DateTimeOffset) object from a [DateTime](xref:System.DateTime) value has two parameters: the [DateTime](xref:System.DateTime) value to convert, and a [TimeSpan](xref:System.TimeSpan) value representing the date and time's offset from UTC.</span></span> <span data-ttu-id="43b69-132">Это смещение должно соответствовать свойству [Kind](xref:System.DateTime.Kind) первого параметра конструктора — в противном случае будет создано исключение [System.ArgumentException](xref:System.ArgumentException).</span><span class="sxs-lookup"><span data-stu-id="43b69-132">This offset value must correspond to the [Kind](xref:System.DateTime.Kind) property of the constructor's first parameter or an [System.ArgumentException](xref:System.ArgumentException) is thrown.</span></span> <span data-ttu-id="43b69-133">Если свойство [Kind](xref:System.DateTime.Kind) первого параметра имеет значение [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), то значение второго параметра должно быть равно [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span><span class="sxs-lookup"><span data-stu-id="43b69-133">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the value of the second parameter must be [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="43b69-134">Если свойство [Kind](xref:System.DateTime.Kind) первого параметра имеет значение [DateTimeKind.Local](xref:System.DateTimeKind.Local), то значение второго параметра должно быть равно смещению локального часового пояса.</span><span class="sxs-lookup"><span data-stu-id="43b69-134">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Local](xref:System.DateTimeKind.Local), the value of the second parameter must be the offset of the local system's time zone.</span></span> <span data-ttu-id="43b69-135">Если свойство [Kind](xref:System.DateTime.Kind) первого параметра имеет значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), то смещение может иметь произвольное допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="43b69-135">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), the offset can be any valid value.</span></span> <span data-ttu-id="43b69-136">В следующем коде показано, как этот конструктор позволяет преобразовывать значения [DateTime](xref:System.DateTime) в значения [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-136">The following code illustrates calls to this constructor to convert [DateTime](xref:System.DateTime) to [DateTimeOffset](xref:System.DateTimeOffset) values.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time with a zero offset.
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc,  
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      utcTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value from a local time with 
// the offset of the local time zone
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime, 
                                TimeZoneInfo.Local.GetUtcOffset(localTime));
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local and the offset matches
// that of the local time zone, the call to the constructor succeeds.

// Instantiate a DateTimeOffset value from a local time with a zero offset.
try
{
   targetTime = new DateTimeOffset(localTime, TimeSpan.Zero);
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      localTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value with an arbitary time zone. 
string timeZoneName = "Central Standard Time";
TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). 
                         GetUtcOffset(sourceDate); 
targetTime = new DateTimeOffset(sourceDate, offset);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -05:00
```

```vb
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time with a zero offset.
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime, TimeSpan.Zero)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc,  
' the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
Try
   targetTime = New DateTimeOffset(utcTime, New TimeSpan(-2, 0, 0))
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      utcTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value from a local time with 
' the offset of the local time zone.
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime, _
                                TimeZoneInfo.Local.GetUtcOffset(localTime))
Console.WriteLine(targetTime)
' Because the Kind property is DateTimeKind.Local and the offset matches
' that of the local time zone, the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a local time with a zero offset.
Try
   targetTime = New DateTimeOffset(localTime, TimeSpan.Zero)
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      localTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value with an arbitary time zone. 
Dim timeZoneName As String = "Central Standard Time"
Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). _
                         GetUtcOffset(sourceDate) 
targetTime = New DateTimeOffset(sourceDate, offset)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -05:00
```

## <a name="implicit-type-conversion"></a><span data-ttu-id="43b69-137">Неявное преобразование типов</span><span class="sxs-lookup"><span data-stu-id="43b69-137">Implicit Type Conversion</span></span>
 
<span data-ttu-id="43b69-138">Тип [System.DateTimeOffset](xref:System.DateTimeOffset) поддерживает только одно неявное преобразование: из значения типа [System.DateTime](xref:System.DateTime) в значение типа [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-138">The [System.DateTimeOffset](xref:System.DateTimeOffset) type supports one implicit type conversion: from a [System.DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="43b69-139">(Неявное преобразование типов — это преобразование одного типа в другой, не требующее явного приведения, как в языке C#, или преобразования, как в языке Visual Basic, в ходе которого не теряются данные.)</span><span class="sxs-lookup"><span data-stu-id="43b69-139">(An implicit type conversion is a conversion from one type to another that does not require an explicit cast (in C#) or conversion (in Visual Basic) and that does not lose information.</span></span> <span data-ttu-id="43b69-140">Благодаря этому можно использовать код, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="43b69-140">It makes code like the following possible.</span></span>

```csharp
DateTimeOffset targetTime;

// The Kind property of sourceDate is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
targetTime = sourceDate;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM -07:00

// define a UTC time (Kind property is DateTimeKind.Utc)
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = utcTime;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM +00:00

// Define a local time (Kind property is DateTimeKind.Local)
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = localTime;
Console.WriteLine(targetTime);      
// Displays 5/1/2008 8:30:00 AM -07:00
```

```vb
Dim targetTime As DateTimeOffset

' The Kind property of sourceDate is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
targetTime = sourceDate
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM -07:00

' define a UTC time (Kind property is DateTimeKind.Utc)
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = utcTime
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM +00:00

' Define a local time (Kind property is DateTimeKind.Local)
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = localTime
Console.WriteLine(targetTime)      
' Displays 5/1/2008 8:30:00 AM -07:00
```

<span data-ttu-id="43b69-141">Смещение результирующего объекта [DateTimeOffset](xref:System.DateTimeOffset) зависит от значения свойства DateTime.Kind](xref:System.DateTime.Kind).</span><span class="sxs-lookup"><span data-stu-id="43b69-141">The offset of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value depends on the DateTime.Kind](xref:System.DateTime.Kind) property value.</span></span> <span data-ttu-id="43b69-142">Если его значение равно [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), то смещение приравнивается к [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span><span class="sxs-lookup"><span data-stu-id="43b69-142">If its value is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the offset is set equal to [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="43b69-143">Если его значение равно [DateTimeKind.Local](xref:System.DateTimeKind.Local) или [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), то смещение приравнивается к смещению местного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="43b69-143">If its value is either [DateTimeKind.Local](xref:System.DateTimeKind.Local) or [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), the offset is set equal to that of the local time zone.</span></span>

## <a name="parsing-the-string-representation-of-a-date-and-time"></a><span data-ttu-id="43b69-144">Разбор строкового представления даты и времен</span><span class="sxs-lookup"><span data-stu-id="43b69-144">Parsing the String Representation of a Date and Time</span></span>

<span data-ttu-id="43b69-145">В классе [System.DateTimeOffset](xref:System.DateTimeOffset) присутствует четыре метода, позволяющих преобразовывать строковое представление даты и времени в значение типа [DateTimeOffset](xref:System.DateTimeOffset):</span><span class="sxs-lookup"><span data-stu-id="43b69-145">The [System.DateTimeOffset](xref:System.DateTimeOffset) type supports four methods that allow you to convert the string representation of a date and time into a [DateTimeOffset](xref:System.DateTimeOffset) value:</span></span>

* <span data-ttu-id="43b69-146">Метод [Parse](xref:System.DateTimeOffset.Parse(System.String)), который пытается преобразовать строковое представление даты и времени в значение [DateTimeOffset](xref:System.DateTimeOffset) и создает исключение при сбое преобразования.</span><span class="sxs-lookup"><span data-stu-id="43b69-146">[Parse](xref:System.DateTimeOffset.Parse(System.String)), which tries to convert the string representation of a date and time to a [DateTimeOffset](xref:System.DateTimeOffset) value and throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="43b69-147">Метод [TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)), который предпринимает попытку преобразовать строковое представление даты и времени в значение [DateTimeOffset](xref:System.DateTimeOffset) и возвращает `false` при сбое преобразования.</span><span class="sxs-lookup"><span data-stu-id="43b69-147">[TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)), which tries to convert the string representation of a date and time to a [DateTimeOffset](xref:System.DateTimeOffset) value and returns `false` if the conversion fails.</span></span>

* <span data-ttu-id="43b69-148">Метод [ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)), который предпринимает попытку преобразовать строковое представление даты и времени в определенном формате в значение [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-148">[ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)), which tries to convert the string representation of a date and time in a specified format to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="43b69-149">Этот метод создает исключение при сбое преобразования.</span><span class="sxs-lookup"><span data-stu-id="43b69-149">The method throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="43b69-150">Метод [TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), который предпринимает попытку преобразовать строковое представление даты и времени в определенном формате в значение [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-150">[TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), which tries to convert the string representation of a date and time in a specified format to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="43b69-151">При сбое преобразования метод возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="43b69-151">The method returns `false` if the conversion fails.</span></span>

<span data-ttu-id="43b69-152">В следующем коде приведены примеры вызова каждого из этих четырех методов преобразования строк, формирующие значения типа [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="43b69-152">The following example illustrates calls to each of these four string conversion methods to instantiate a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
string timeString; 
DateTimeOffset targetTime;

timeString = "05/01/2008 8:30 AM +01:00";
try
{
   targetTime = DateTimeOffset.Parse(timeString);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "05/01/2008 8:30 AM";
if (DateTimeOffset.TryParse(timeString, out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);   

timeString = "Thursday, 01 May 2008 08:30";
try
{
   targetTime = DateTimeOffset.ParseExact(timeString, "f", 
                CultureInfo.InvariantCulture);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "Thursday, 01 May 2008 08:30 +02:00";
string formatString; 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern +
                " " +
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern +
                " zzz"; 
if (DateTimeOffset.TryParseExact(timeString, 
                                formatString, 
                                CultureInfo.InvariantCulture, 
                                DateTimeStyles.AllowLeadingWhite, 
                                out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);
// The example displays the following output to the console:
//    5/1/2008 8:30:00 AM +01:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM +02:00
```

```vb
Dim timeString As String 
Dim targetTime As DateTimeOffset

timeString = "05/01/2008 8:30 AM +01:00"
Try
   targetTime = DateTimeOffset.Parse(timeString)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "05/01/2008 8:30 AM"
If DateTimeOffset.TryParse(timeString, targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)   
End If

timeString = "Thursday, 01 May 2008 08:30"
Try
   targetTime = DateTimeOffset.ParseExact(timeString, "f", _
                CultureInfo.InvariantCulture)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "Thursday, 01 May 2008 08:30 +02:00"
Dim formatString As String 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern & _
                " " & _
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern & _
                " zzz" 
If DateTimeOffset.TryParseExact(timeString, _
                                formatString, _
                                CultureInfo.InvariantCulture, _
                                DateTimeStyles.AllowLeadingWhite, _
                                targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)
End If      
' The example displays the following output to the console:
'    5/1/2008 8:30:00 AM +01:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM +02:00
```

## <a name="see-also"></a><span data-ttu-id="43b69-153">См. также</span><span class="sxs-lookup"><span data-stu-id="43b69-153">See Also</span></span>

[<span data-ttu-id="43b69-154">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="43b69-154">Dates, times, and time zones</span></span>](index.md)


