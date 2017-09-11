---
title: "Преобразование времени из одного часового пояса в другой"
description: "Преобразование времени из одного часового пояса в другой"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bf8f74e6-e7f2-4c2a-a04c-57db0e28dd36
ms.translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 051a4891336470e79bda9d7b9bb1be4e2c9187b8
ms.contentlocale: ru-ru
ms.lasthandoff: 11/05/2016

---

# <a name="converting-times-between-time-zones"></a><span data-ttu-id="30e7c-104">Преобразование времени из одного часового пояса в другой</span><span class="sxs-lookup"><span data-stu-id="30e7c-104">Converting times between time zones</span></span>

<span data-ttu-id="30e7c-105">Обработка различий между часовыми поясами становится все более важной для всех приложений, которые работают с датами и временем.</span><span class="sxs-lookup"><span data-stu-id="30e7c-105">It is becoming increasingly important for any application that works with dates and times to handle differences between time zones.</span></span> <span data-ttu-id="30e7c-106">При работе приложения нельзя предполагать, что все значения времени могут быть выражены по местному времени, которое доступно из структуры [System.DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="30e7c-106">An application can no longer assume that all times can be expressed in the local time, which is the time available from the [System.DateTime](xref:System.DateTime) structure.</span></span> <span data-ttu-id="30e7c-107">Например, веб-страница, которая отображает текущее время в восточной части США, будет содержать недостоверные сведения для пользователей в восточной Азии.</span><span class="sxs-lookup"><span data-stu-id="30e7c-107">For example, a Web page that displays the current time in the eastern part of the United States will lack credibility to a customer in eastern Asia.</span></span> <span data-ttu-id="30e7c-108">В этом разделе объясняется, как преобразовать время из одного часового пояса в другой, а также как преобразовать значения [System.DateTimeOffset](xref:System.DateTimeOffset) с ограниченной поддержкой часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="30e7c-108">This topic explains how to convert times from one time zone to another, as well as how to convert [System.DateTimeOffset](xref:System.DateTimeOffset) values that have limited time zone awareness.</span></span>

## <a name="converting-to-coordinated-universal-time"></a><span data-ttu-id="30e7c-109">Преобразование во время в формате UTC</span><span class="sxs-lookup"><span data-stu-id="30e7c-109">Converting to Coordinated Universal Time</span></span>

<span data-ttu-id="30e7c-110">Время в формате UTC — это высокоточный, атомарный стандарт времени.</span><span class="sxs-lookup"><span data-stu-id="30e7c-110">Coordinated Universal Time (UTC) is a high-precision, atomic time standard.</span></span> <span data-ttu-id="30e7c-111">Часовые пояса выражаются как положительные или отрицательные смещения относительно времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="30e7c-111">The world’s time zones are expressed as positive or negative offsets from UTC.</span></span> <span data-ttu-id="30e7c-112">Таким образом, время в формате UTC предоставляет тип времени, свободного от часовых поясов, или нейтрального времени часового пояса.</span><span class="sxs-lookup"><span data-stu-id="30e7c-112">Thus, UTC provides a kind of time-zone free or time-zone neutral time.</span></span> <span data-ttu-id="30e7c-113">Использование времени в формате UTC рекомендовано, когда важна совместимость даты и времени между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="30e7c-113">The use of UTC time is recommended when a date and time's portability across computers is important.</span></span> <span data-ttu-id="30e7c-114">Преобразование отдельных часовых поясов во время в формате UTC упрощает сравнение времен.</span><span class="sxs-lookup"><span data-stu-id="30e7c-114">Converting individual time zones to UTC makes time comparisons easy.</span></span>

> [!NOTE]
> <span data-ttu-id="30e7c-115">Можно сериализовать структуру [DateTimeOffset](xref:System.DateTimeOffset) для однозначного представления одного момента времени.</span><span class="sxs-lookup"><span data-stu-id="30e7c-115">You can also serialize a [DateTimeOffset](xref:System.DateTimeOffset) structure to unambiguously represent a single point in time.</span></span> <span data-ttu-id="30e7c-116">Поскольку объекты [DateTimeOffset](xref:System.DateTimeOffset) хранят значение даты и времени вместе с его смещением относительно времени в формате UTC, то они всегда представляют определенный момент времени по отношению ко времени UTC.</span><span class="sxs-lookup"><span data-stu-id="30e7c-116">Because [DateTimeOffset](xref:System.DateTimeOffset) objects store a date and time value along with its offset from UTC, they always represent a particular point in time in relationship to UTC.</span></span>

<span data-ttu-id="30e7c-117">Самым простым способом преобразования времени в формате UTC является вызов `static` (`Shared` в Visual Basic) метода [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="30e7c-117">The easiest way to convert a time to UTC is to call the `static` (`Shared` in Visual Basic) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="30e7c-118">Метод `TimeZoneInfo.ConvertTimeToUtc(DateTime)` сейчас недоступен в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="30e7c-118">The `TimeZoneInfo.ConvertTimeToUtc(DateTime)` method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="30e7c-119">Точное преобразование, выполненное этим методом, зависит от значения свойства [Kind](xref:System.DateTime.Kind) параметра `DateTime`, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="30e7c-119">The exact conversion performed by the method depends on the value of the `DateTime` parameter's [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="30e7c-120">Свойство [DateTime.Kind](xref:System.DateTimeKind)</span><span class="sxs-lookup"><span data-stu-id="30e7c-120">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="30e7c-121">Преобразование</span><span class="sxs-lookup"><span data-stu-id="30e7c-121">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="30e7c-122">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="30e7c-122">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="30e7c-123">Преобразует местное время во время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="30e7c-123">Converts local time to UTC.</span></span>
[<span data-ttu-id="30e7c-124">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="30e7c-124">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="30e7c-125">Предполагает, что параметр `DateTime` является местным временем и преобразовывает местное время в UTC.</span><span class="sxs-lookup"><span data-stu-id="30e7c-125">Assumes the `DateTime` parameter is local time and converts local time to UTC.</span></span>
[<span data-ttu-id="30e7c-126">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="30e7c-126">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="30e7c-127">Возвращает неизмененный параметр `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="30e7c-127">Returns the `DateTime` parameter unchanged.</span></span>

<span data-ttu-id="30e7c-128">Следующий код преобразовывает текущее местное время во время в формате UTC и выводит результат на консоль.</span><span class="sxs-lookup"><span data-stu-id="30e7c-128">The following code converts the current local time to UTC and displays the result to the console.</span></span>

```csharp
DateTime dateNow = DateTime.Now;
Console.WriteLine("The date and time are {0} UTC.", 
                   TimeZoneInfo.ConvertTimeToUtc(dateNow));
```

```vb
Dim dateNow As Date = Date.Now      
Console.WriteLine("The date and time are {0} UTC.", _
                  TimeZoneInfo.ConvertTimeToUtc(dateNow))
```

> [!NOTE]
><span data-ttu-id="30e7c-129">Метод [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) не обязательно возвращает результаты, которые совпадают с результатами методов [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) и [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime).</span><span class="sxs-lookup"><span data-stu-id="30e7c-129">The [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method does not necessarily produce results that are identical to the [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) and [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) methods.</span></span> <span data-ttu-id="30e7c-130">Если местный часовой пояс на локальной системе содержит несколько правил коррекции, то метод [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) применяет соответствующее правило к конкретным дате и времени.</span><span class="sxs-lookup"><span data-stu-id="30e7c-130">If the host system's local time zone includes multiple adjustment rules, [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) applies the appropriate rule to a particular date and time.</span></span> <span data-ttu-id="30e7c-131">Два других метода всегда применяют последнее правило коррекции.</span><span class="sxs-lookup"><span data-stu-id="30e7c-131">The other two methods always apply the latest adjustment rule.</span></span>

<span data-ttu-id="30e7c-132">Если значение даты и времени не представляет местное время или время в формате UTC, то метод [ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) скорее всего вернет ошибочный результат.</span><span class="sxs-lookup"><span data-stu-id="30e7c-132">If the date and time value does not represent either the local time or UTC, the [ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) method will likely return an erroneous result.</span></span> <span data-ttu-id="30e7c-133">Однако можно использовать метод [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) для преобразования даты и времени из заданного часового пояса.</span><span class="sxs-lookup"><span data-stu-id="30e7c-133">However, you can use the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method to convert the date and time from a specified time zone.</span></span> <span data-ttu-id="30e7c-134">(Дополнительные сведения о получении объекта TimeZoneInfo, который представляет часовой пояс назначения, см. в статье [Поиск часового пояса, заданного в локальной системе](finding-the-time-zones-on-local-system.md).)</span><span class="sxs-lookup"><span data-stu-id="30e7c-134">(For details on retrieving a TimeZoneInfo object that represents the destination time zone, see [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md).</span></span> <span data-ttu-id="30e7c-135">В следующем коде используется метод [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) для преобразования восточного стандартного времени в UTC.</span><span class="sxs-lookup"><span data-stu-id="30e7c-135">The following code uses the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method to convert Eastern Standard Time to UTC.</span></span>

```csharp
DateTime easternTime = new DateTime(2007, 01, 02, 12, 16, 00);
string easternZoneId = "Eastern Standard Time";
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId);
   Console.WriteLine("The date and time are {0} UTC.", 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to find the {0} zone in the registry.", 
                     easternZoneId);
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", 
                     easternZoneId);
}
```

```vb
Dim easternTime As New Date(2007, 01, 02, 12, 16, 00)
Dim easternZoneId As String = "Eastern Standard Time"
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId)
   Console.WriteLine("The date and time are {0} UTC.", _ 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to find the {0} zone in the registry.", _
                     easternZoneId)
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", _ 
                     easternZoneId)
End Try    
```

<span data-ttu-id="30e7c-136">Обратите внимание, что этот метод создает исключение [ArgumentException](xref:System.ArgumentException), если свойство [Kind](xref:System.DateTimeKind) объекта [DateTime](xref:System.DateTime) не совпадает с часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="30e7c-136">Note that this method throws an [ArgumentException](xref:System.ArgumentException) if the [DateTime](xref:System.DateTime) object's [Kind](xref:System.DateTimeKind) property and the time zone are mismatched.</span></span> <span data-ttu-id="30e7c-137">Несоответствие возникает, если свойство "Kind" задано как [DateTimeKind.Local](xref:System.DateTimeKind.Local), а объект [TimeZoneInfo](xref:System.TimeZoneInfo) не представляет местный часовой пояс, или если свойство "Kind" задано как [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), а объект [TimeZoneInfo](xref:System.TimeZoneInfo) не равен [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span><span class="sxs-lookup"><span data-stu-id="30e7c-137">A mismatch occurs if the Kind property is [DateTimeKind.Local](xref:System.DateTimeKind.Local) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not represent the local time zone, or if the Kind property is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

<span data-ttu-id="30e7c-138">Все эти методы принимают значения [DateTime](xref:System.DateTime) в качестве параметров и возвращают значение [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="30e7c-138">All of these methods take [DateTime](xref:System.DateTime) values as parameters and return a [DateTime](xref:System.DateTime) value.</span></span> <span data-ttu-id="30e7c-139">Для значений [DateTimeOffset](xref:System.DateTimeOffset) в структуре [DateTimeOffset](xref:System.DateTimeOffset) используется метод экземпляра [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime), который преобразует дату и время текущего экземпляра в UTC.</span><span class="sxs-lookup"><span data-stu-id="30e7c-139">For [DateTimeOffset](xref:System.DateTimeOffset) values, the [DateTimeOffset](xref:System.DateTimeOffset) structure has a [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) instance method that converts the date and time of the current instance to UTC.</span></span> <span data-ttu-id="30e7c-140">В следующем примере вызывается метод [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) для преобразования местного времени и нескольких других значений времени во время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="30e7c-140">The following example calls the [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) method to convert a local time and several other times to Coordinated Universal Time (UTC).</span></span>

```csharp
DateTimeOffset localTime, otherTime, universalTime;

// Define local time in local time zone
localTime = new DateTimeOffset(new DateTime(2007, 6, 15, 12, 0, 0));
Console.WriteLine("Local time: {0}", localTime);
Console.WriteLine();

// Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero);
Console.WriteLine("Other time: {0}", otherTime);
Console.WriteLine("{0} = {1}: {2}", 
                  localTime, otherTime, 
                  localTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  localTime, otherTime, 
                  localTime.EqualsExact(otherTime));
Console.WriteLine();

// Convert other time to UTC
universalTime = localTime.ToUniversalTime(); 
Console.WriteLine("Universal time: {0}", universalTime);
Console.WriteLine("{0} = {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.EqualsExact(otherTime));
Console.WriteLine();
// The example produces the following output to the console:
//    Local time: 6/15/2007 12:00:00 PM -07:00
//    
//    Other time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
//    
//    Universal time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

```vb
Dim localTime, otherTime, universalTime As DateTimeOffset

' Define local time in local time zone
localTime = New DateTimeOffset(#6/15/2007 12:00:00PM#)
Console.WriteLine("Local time: {0}", localTime)
Console.WriteLine()

' Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero)
Console.WriteLine("Other time: {0}", otherTime)
Console.WriteLine("{0} = {1}: {2}", _
                  localTime, otherTime, _
                  localTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  localTime, otherTime, _
                  localTime.EqualsExact(otherTime))
Console.WriteLine()

' Convert other time to UTC
universalTime = localTime.ToUniversalTime() 
Console.WriteLine("Universal time: {0}", universalTime)
Console.WriteLine("{0} = {1}: {2}", _
                  otherTime, universalTime, _ 
                  universalTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  otherTime, universalTime, _
                  universalTime.EqualsExact(otherTime))
Console.WriteLine()
' The example produces the following output to the console:
'    Local time: 6/15/2007 12:00:00 PM -07:00
'    
'    Other time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
'    
'    Universal time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

## <a name="converting-utc-to-a-designated-time-zone"></a><span data-ttu-id="30e7c-141">Преобразование времени в формате UTC в заданный часовой пояс</span><span class="sxs-lookup"><span data-stu-id="30e7c-141">Converting UTC to a designated time zone</span></span>

<span data-ttu-id="30e7c-142">Чтобы преобразовать время в формате UTC в местное, см. информацию в разделе [Преобразование времени в формате UTC в местное время](#converting-utc-to-local-time).</span><span class="sxs-lookup"><span data-stu-id="30e7c-142">To convert UTC to local time, see the [Converting UTC to local time](#converting-utc-to-local-time) section that follows.</span></span> 

<span data-ttu-id="30e7c-143">Чтобы преобразовать время в формате UTC во время в любом часовом поясе, вызовите метод [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="30e7c-143">To convert UTC to the time in any time zone that you designate, call the [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="30e7c-144">В настоящее время метод "TimeZoneInfo.ConvertTimeFromUtc" недоступен в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="30e7c-144">The \`TimeZoneInfo.ConvertTimeFromUtc' method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="30e7c-145">Этот метод принимает два параметра:</span><span class="sxs-lookup"><span data-stu-id="30e7c-145">The method takes two parameters:</span></span>

* <span data-ttu-id="30e7c-146">Время в формате UTC, которое требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="30e7c-146">The UTC to convert.</span></span> <span data-ttu-id="30e7c-147">Оно должно быть значением [DateTime](xref:System.DateTime), свойству [Kind](xref:System.DateTime.Kind) которого присвоено значение [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) или значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span><span class="sxs-lookup"><span data-stu-id="30e7c-147">This must be a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) or [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> 

* <span data-ttu-id="30e7c-148">Часовой пояс, в который требуется преобразовать время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="30e7c-148">The time zone to convert the UTC to.</span></span> 

<span data-ttu-id="30e7c-149">Следующий код преобразует время в формате UTC в центральное стандартное время.</span><span class="sxs-lookup"><span data-stu-id="30e7c-149">The following code converts UTC to Central Standard Time.</span></span>

```csharp
DateTime timeUtc = DateTime.UtcNow;
try
{
   TimeZoneInfo cstZone = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time");
   DateTime cstTime = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone);
   Console.WriteLine("The date and time are {0} {1}.", 
                     cstTime, 
                     cstZone.IsDaylightSavingTime(cstTime) ?
                             cstZone.DaylightName : cstZone.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Central Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.");
}
```

```vb
Dim timeUtc As Date = Date.UtcNow
Try
   Dim cstZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time")
   Dim cstTime As Date = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone)
   Console.WriteLine("The date and time are {0} {1}.", _
                     cstTime, _
                     IIf(cstZone.IsDaylightSavingTime(cstTime), _
                         cstZone.DaylightName, cstZone.StandardName))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Central Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.")
End Try
``` 

## <a name="converting-utc-to-local-time"></a><span data-ttu-id="30e7c-150">Преобразование времени в формате UTC в местное время</span><span class="sxs-lookup"><span data-stu-id="30e7c-150">Converting UTC to local time</span></span>

<span data-ttu-id="30e7c-151">Чтобы преобразовать время в формате UTC в местное время, вызовите метод [DateTime.ToLocalTime](xref:System.DateTime) объекта [DateTime](xref:System.DateTime), время которого требуется преобразовать.</span><span class="sxs-lookup"><span data-stu-id="30e7c-151">To convert UTC to local time, call the [DateTime.ToLocalTime](xref:System.DateTime) method of the [DateTime](xref:System.DateTime) object whose time you want to convert.</span></span> <span data-ttu-id="30e7c-152">Точное поведение метода зависит от значения свойства объекта [Kind](xref:System.DateTime.Kind), как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="30e7c-152">The exact behavior of the method depends on the value of the object’s [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="30e7c-153">Свойство [DateTime.Kind](xref:System.DateTimeKind)</span><span class="sxs-lookup"><span data-stu-id="30e7c-153">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="30e7c-154">Преобразование</span><span class="sxs-lookup"><span data-stu-id="30e7c-154">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="30e7c-155">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="30e7c-155">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="30e7c-156">Возвращает неизмененное значение [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="30e7c-156">Returns the [DateTime](xref:System.DateTime) value unchanged.</span></span>
[<span data-ttu-id="30e7c-157">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="30e7c-157">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="30e7c-158">Предполагает, что значение [DateTime](xref:System.DateTime) является временем в формате UTC и преобразует UTC в местное время.</span><span class="sxs-lookup"><span data-stu-id="30e7c-158">Assumes that the [DateTime](xref:System.DateTime) value is UTC and converts the UTC to local time.</span></span>
[<span data-ttu-id="30e7c-159">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="30e7c-159">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="30e7c-160">Преобразует значение [DateTime](xref:System.DateTime) в местное время.</span><span class="sxs-lookup"><span data-stu-id="30e7c-160">Converts the [DateTime](xref:System.DateTime) value to local time.</span></span>

## <a name="converting-between-any-two-time-zones"></a><span data-ttu-id="30e7c-161">Преобразование между любыми двумя часовыми поясами</span><span class="sxs-lookup"><span data-stu-id="30e7c-161">Converting between any two time zones</span></span>

<span data-ttu-id="30e7c-162">Можно преобразовать время между любыми двумя часовыми поясами с помощью static метода класса [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)).</span><span class="sxs-lookup"><span data-stu-id="30e7c-162">You can convert between any two time zones by using the static [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span> <span data-ttu-id="30e7c-163">Параметрами этого метода являются значение [DateTime](xref:System.DateTime), которое требуется преобразовать, объект [TimeZoneInfo](xref:System.TimeZoneInfo), представляющий часовой пояс значения даты и времени, и объект [TimeZoneInfo](xref:System.TimeZoneInfo), представляющий часовой пояс, к которому требуется преобразовать значение даты и времени.</span><span class="sxs-lookup"><span data-stu-id="30e7c-163">This method's parameters are the [DateTime](xref:System.DateTime) value to convert, a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone of the date and time value, and a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone to convert the date and time value to.</span></span>

<span data-ttu-id="30e7c-164">Для этого метода требуется, чтобы свойство [Kind](xref:System.DateTime.Kind) значения даты и времени, которое требуется преобразовать, соответствовало объекту [TimeZoneInfo](xref:System.TimeZoneInfo) или идентификатору часового пояса, представляющего его часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="30e7c-164">The method requires that the [Kind](xref:System.DateTime.Kind) property of the date and time value to convert and the [TimeZoneInfo](xref:System.TimeZoneInfo) object or time zone identifier that represents its time zone correspond to one another.</span></span> <span data-ttu-id="30e7c-165">В противном случае возникает исключение [ArgumentException](xref:System.ArgumentException).</span><span class="sxs-lookup"><span data-stu-id="30e7c-165">Otherwise, an [ArgumentException](xref:System.ArgumentException) is thrown.</span></span> <span data-ttu-id="30e7c-166">Например, если свойством [Kind](xref:System.DateTime.Kind) значения даты и времени является [DateTimeKind.Local](xref:System.DateTimeKind.Local), то исключение возникнет в том случае, если объект [TimeZoneInfo](xref:System.TimeZoneInfo), который передан в качестве параметра метода, не равен [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span><span class="sxs-lookup"><span data-stu-id="30e7c-166">For example, if the [Kind](xref:System.DateTime.Kind) property of the date and time value is [DateTimeKind.Local](xref:System.DateTimeKind.Local), an exception is thrown if the [TimeZoneInfo](xref:System.TimeZoneInfo) object passed as a parameter to the method is not equal to [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span></span> <span data-ttu-id="30e7c-167">Также исключение возникнет в том случае, если идентификатор, переданный в качестве параметра метода, не равен [TimeZoneInfo.Local.Id](xref:System.TimeZoneInfo.Id).</span><span class="sxs-lookup"><span data-stu-id="30e7c-167">An exception is also thrown if the identifier passed as a parameter to the method is not equal to [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id).</span></span>

<span data-ttu-id="30e7c-168">В следующем примере используется метод [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) для преобразования из гавайского стандартного времени в местное время.</span><span class="sxs-lookup"><span data-stu-id="30e7c-168">The following example uses the [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method to convert from Hawaiian Standard Time to local time.</span></span>

```csharp
DateTime hwTime = new DateTime(2007, 02, 01, 08, 00, 00);
try
{
   TimeZoneInfo hwZone = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time");
   Console.WriteLine("{0} {1} is {2} local time.", 
           hwTime, 
           hwZone.IsDaylightSavingTime(hwTime) ? hwZone.DaylightName : hwZone.StandardName, 
           TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Hawaiian STandard Time zone has been corrupted.");
}
```

```vb
Dim hwTime As Date = #2/01/2007 8:00:00 AM#
Try
   Dim hwZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time")
   Console.WriteLine("{0} {1} is {2} local time.", _
                     hwTime, _
                     IIf(hwZone.IsDaylightSavingTime(hwTime), hwZone.DaylightName, hwZone.StandardName), _
                     TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Hawaiian Standard Time zone has been corrupted.")
End Try
```

## <a name="converting-datetimeoffset-values"></a><span data-ttu-id="30e7c-169">Преобразование значений DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="30e7c-169">Converting DateTimeOffset values</span></span>

<span data-ttu-id="30e7c-170">Значения даты и времени, представленные объектами [System.DateTimeOffset](xref:System.DateTimeOffset), не соответствуют полностью часовым поясам, так как при создании этот объект не связан с часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="30e7c-170">Date and time values represented by [System.DateTimeOffset](xref:System.DateTimeOffset) objects are not fully time-zone aware because the object is disassociated from its time zone at the time it is instantiated.</span></span> <span data-ttu-id="30e7c-171">Однако во многих случаях приложению достаточно преобразовать дату и время на основе двух различных значений смещения относительно времени в формате UTC, а не на основе времени конкретных часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="30e7c-171">However, in many cases an application simply needs to convert a date and time based on two different offsets from UTC rather than on the time in particular time zones.</span></span> <span data-ttu-id="30e7c-172">Чтобы выполнить это преобразование, можно вызвать метод [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="30e7c-172">To perform this conversion, you can call the current instance's [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) method.</span></span> <span data-ttu-id="30e7c-173">Единственным параметром данного метода является [TimeSpan](xref:System.TimeSpan), который представляет собой смещение нового значения даты и времени, которое возвращает этот метод.</span><span class="sxs-lookup"><span data-stu-id="30e7c-173">The method's single parameter is [TimeSpan](xref:System.TimeSpan) representing the offset of the new date and time value that the method is to return.</span></span>  

<span data-ttu-id="30e7c-174">Например, если дата и время запроса пользователя к веб-странице известны и сериализованы в виде строки в формате мм/дд/гггг чч:мм:сс zzzz, то следующий метод `ReturnTimeOnServer` преобразует это значение даты и времени в значение даты и времени на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="30e7c-174">For example, if the date and time of a user request for a Web page is known and is serialized as a string in the format MM/dd/yyyy hh:mm:ss zzzz, the following `ReturnTimeOnServer` method converts this date and time value to the date and time on the Web server.</span></span>

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";
   TimeSpan serverOffset = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now);

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = clientTime.ToOffset(serverOffset);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"
   Dim serverOffset As TimeSpan = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now)

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = clientTime.ToOffset(serverOffset)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

<span data-ttu-id="30e7c-175">Если методу передается строка "9/1/2007 5:32:07 -05:00", которая представляет дату и время в часовом поясе, который раньше пояса UTC на пять часов, он возвращает строку "9/1/2007 3:32:07 -07:00" для сервера, расположенного в тихоокеанском стандартном часовом поясе США.</span><span class="sxs-lookup"><span data-stu-id="30e7c-175">If the method is passed the string "9/1/2007 5:32:07 -05:00", which represents the date and time in a time zone five hours earlier than UTC, it returns 9/1/2007 3:32:07 AM -07:00 for a server located in the U.S. Pacific Standard Time zone.</span></span>

<span data-ttu-id="30e7c-176">Класс [TimeZoneInfo](xref:System.TimeZoneInfo) также содержит перегрузку метода [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)), который выполняет преобразование часовых поясов со значениями [System.DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="30e7c-176">The [TimeZoneInfo](xref:System.TimeZoneInfo) class also includes an overloaded [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method that performs time zone conversions with [System.DateTimeOffset](xref:System.DateTimeOffset) values.</span></span> <span data-ttu-id="30e7c-177">Параметрами данного метода являются значение [System.DateTimeOffset](xref:System.DateTimeOffset) и ссылка на часовой пояс, к которому требуется преобразовать время.</span><span class="sxs-lookup"><span data-stu-id="30e7c-177">The method's parameters are a [System.DateTimeOffset](xref:System.DateTimeOffset) value and a reference to the time zone to which the time is to be converted.</span></span> <span data-ttu-id="30e7c-178">Этот метод возвращает значение [System.DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="30e7c-178">The method call returns a [System.DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="30e7c-179">Например, метод `ReturnTimeOnServer` в предыдущем примере может быть переписан для вызова метода [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)).</span><span class="sxs-lookup"><span data-stu-id="30e7c-179">For example, the `ReturnTimeOnServer` method in the previous example could be rewritten as follows to call the [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method.</span></span>

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, 
                                  CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = TimeZoneInfo.ConvertTime(clientTime, 
                                  TimeZoneInfo.Local);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = TimeZoneInfo.ConvertTime(clientTime, TimeZoneInfo.Local)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

## <a name="see-also"></a><span data-ttu-id="30e7c-180">См. также</span><span class="sxs-lookup"><span data-stu-id="30e7c-180">See also</span></span>

[<span data-ttu-id="30e7c-181">TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="30e7c-181">TimeZoneInfo</span></span>](xref:System.TimeZoneInfo)

[<span data-ttu-id="30e7c-182">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="30e7c-182">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="30e7c-183">Поиск часового пояса, заданного в локальной системе</span><span class="sxs-lookup"><span data-stu-id="30e7c-183">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)



