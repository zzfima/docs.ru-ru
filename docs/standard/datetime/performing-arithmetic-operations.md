---
title: "Выполнение арифметических операций с датами и временем"
description: "Выполнение арифметических операций с датами и временем"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 589ac5ec-8365-4a0d-bc38-72183718110c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b872cc4c2b799ddafc9df263795d860754d1ec17
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="performing-arithmetic-operations-with-dates-and-times"></a><span data-ttu-id="1f886-104">Выполнение арифметических операций с датами и временем</span><span class="sxs-lookup"><span data-stu-id="1f886-104">Performing arithmetic operations with dates and times</span></span>

<span data-ttu-id="1f886-105">Несмотря на то, что структуры [System.DateTime](xref:System.DateTime) и [System.DateTimeOffset](xref:System.DateTimeOffset) предоставляют члены, выполняющие арифметические действия над их значениями, результаты арифметических операций очень различаются.</span><span class="sxs-lookup"><span data-stu-id="1f886-105">Although both the [System.DateTime](xref:System.DateTime) and the [System.DateTimeOffset](xref:System.DateTimeOffset) structures provide members that perform arithmetic operations on their values, the results of arithmetic operations are very different.</span></span> <span data-ttu-id="1f886-106">В данном разделе эти различия описываются в контексте различных уровней представленности сведений о часовом поясе во временных данных, а также рассматриваются способы выполнения операций над датами и временем с полным учетом сведений о часовых поясах.</span><span class="sxs-lookup"><span data-stu-id="1f886-106">This article examines those differences, relates them to degrees of time zone awareness in date and time data, and discusses how to perform fully time zone aware operations using date and time data.</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a><span data-ttu-id="1f886-107">Сравнения и арифметические операции со значениями даты и времени</span><span class="sxs-lookup"><span data-stu-id="1f886-107">Comparisons and Arithmetic Operations with DateTime Values</span></span>

<span data-ttu-id="1f886-108">В значениях [System.DateTime](xref:System.DateTime) присутствуют ограниченные сведения о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="1f886-108">[System.DateTime](xref:System.DateTime) values possess a limited degree of time zone awareness.</span></span> <span data-ttu-id="1f886-109">Свойство [DateTime.Kind](xref:System.DateTime.Kind) позволяет присваивать значению даты и времени значение [System.DateTimeKind](xref:System.DateTimeKind), чтобы указать, представляет ли оно местное время, время в формате UTC или время в неопределенном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="1f886-109">The [DateTime.Kind](xref:System.DateTime.Kind) property allows a [System.DateTimeKind](xref:System.DateTimeKind) value to be assigned to the date and time to indicate whether it represents local time, Coordinated Universal Time (UTC), or the time in an unspecified time zone.</span></span> <span data-ttu-id="1f886-110">Тем не менее, эти ограниченные сведения о часовом поясе игнорируются при сравнении или выполнении арифметических операций со значениями [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="1f886-110">However, this limited time zone information is ignored when comparing or performing date and time arithmetic on [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="1f886-111">Это демонстрируется в следующем примере, где текущее местное время сравнивается с текущим временем в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="1f886-111">The following example, which compares the current local time with the current UTC time, illustrates this.</span></span>

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateManipulation
{
   public static void Main()
   {
      DateTime localTime = DateTime.Now;
      DateTime utcTime = DateTime.UtcNow;

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", 
                        localTime.Kind.ToString(), 
                        utcTime.Kind.ToString(), 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The {0} time is {1} the {2} time.", 
                        localTime.Kind.ToString(), 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)), 
                        utcTime.Kind.ToString());  
   }
}
// If run in the U.S. Pacific Standard Time zone, the example displays 
// the following output to the console:
//    Difference between Local and Utc time: -7:0 hours
//    The Local time is EarlierThan the Utc time.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateManipulation
   Public Sub Main()
      Dim localTime As Date = Date.Now
      Dim utcTime As Date = Date.UtcNow

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", _
                        localTime.Kind.ToString(), _
                        utcTime.Kind.ToString(), _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The {0} time is {1} the {2} time.", _
                        localTime.Kind.ToString(), _ 
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)), _
                        utcTime.Kind.ToString())  
      ' If run in the U.S. Pacific Standard Time zone, the example displays 
      ' the following output to the console:
      '    Difference between Local and Utc time: -7:0 hours
      '    The Local time is EarlierThan the Utc time.                                                    
   End Sub
End Module
```

<span data-ttu-id="1f886-112">Метод [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) показывает, что местное время предшествует (или меньше) времени в формате UTC, а операция вычитания свидетельствует о том, что разница между временем в формате UTC и местным временем для систем в тихоокеанском стандартном часовом поясе США составляет семь часов.</span><span class="sxs-lookup"><span data-stu-id="1f886-112">The [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) method reports that the local time is earlier than (or less than) the UTC time, and the subtraction operation indicates that the difference between UTC and the local time for a system in the U.S. Pacific Standard Time zone is seven hours.</span></span> <span data-ttu-id="1f886-113">Тем не менее, поскольку эти значения дают различные представления одного и того же момента времени, в данном случае очевидно, что причина этого различия целиком кроется в смещении местного часового пояса относительно времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="1f886-113">But because these two values provide different representations of a single point in time, it is clear in this case that this time interval is completely attributable to the local time zone's offset from UTC.</span></span> 

<span data-ttu-id="1f886-114">В общем случае свойство [DateTimeKind](xref:System.DateTimeKind) не влияет на результаты, возвращаемые методами сравнения и арифметическими операциями (как показывает результат сравнения двух идентичных моментов времени) с [DateTime](xref:System.DateTime), хотя оно может повлиять на интерпретацию этих результатов.</span><span class="sxs-lookup"><span data-stu-id="1f886-114">More generally, the [DateTimeKind](xref:System.DateTimeKind) property does not affect the results returned by [DateTime](xref:System.DateTime) comparison and arithmetic methods (as the comparison of two identical points in time indicates), although it can affect the interpretation of those results.</span></span> <span data-ttu-id="1f886-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="1f886-115">For example:</span></span>

* <span data-ttu-id="1f886-116">Результат любой арифметической операции над парой значений даты и времени, свойства [DateTimeKind](xref:System.DateTimeKind) которых имеют значение [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), отражает фактический интервал времени между этими двумя значениями.</span><span class="sxs-lookup"><span data-stu-id="1f886-116">The result of any arithmetic operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) reflects the actual time interval between the two values.</span></span> <span data-ttu-id="1f886-117">Аналогичным образом результат сравнения двух таких значений даты и времени будет точно отражать соотношение между временами.</span><span class="sxs-lookup"><span data-stu-id="1f886-117">Similarly, the comparison of two such date and time values accurately reflects the relationship between times.</span></span>

* <span data-ttu-id="1f886-118">Результат любой арифметической операции или операции сравнения над двумя значениями даты и времени, свойства [DateTimeKind](xref:System.DateTimeKind) которых имеют значение [DateTimeKind.Local](xref:System.DateTimeKind.Local), или над двумя значениями даты и времени с различными значениями свойства [DateTimeKind](xref:System.DateTimeKind) будет отражать временную разницу между этими значениями.</span><span class="sxs-lookup"><span data-stu-id="1f886-118">The result of any arithmetic or comparison operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Local](xref:System.DateTimeKind.Local) or on two date and time values with different [DateTimeKind](xref:System.DateTimeKind) property values reflects the difference in clock time between the two values.</span></span> 

* <span data-ttu-id="1f886-119">Арифметические операции или операции сравнения, выполняемые над местными значениями даты и времени, не учитывают допустимость или недопустимость конкретных значений; не учитывают они и какие-либо правила коррекции, необходимые при переводе местного часового пояса на зимнее или летнее время.</span><span class="sxs-lookup"><span data-stu-id="1f886-119">Arithmetic or comparison operations on local date and time values do not consider whether a particular value is ambiguous or invalid, nor do they take account of the effect of any adjustment rules that result from the local time zone's transition to or from daylight saving time.</span></span>

* <span data-ttu-id="1f886-120">В результат любой операции, сравнивающей или вычисляющей разницу между временем в формате UTC и местным временем, входит временной интервал, равный смещению местного часового пояса относительно времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="1f886-120">Any operation that compares or calculates the difference between UTC and a local time includes a time interval equal to the local time zone's offset from UTC in the result.</span></span> 

* <span data-ttu-id="1f886-121">Любая операция, которая сравнивает или вычисляет разницу между неуказанным временем и временем в формате UTC или местным временем, соответствует простому времени.</span><span class="sxs-lookup"><span data-stu-id="1f886-121">Any operation that compares or calculates the difference between an unspecified time and either UTC or the local time reflects simple clock time.</span></span> <span data-ttu-id="1f886-122">Различия между часовыми поясами не учитываются, и в результате не отражено применение правил коррекции часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="1f886-122">Time zone differences are not considered, and the result does not reflect the application of time zone adjustment rules.</span></span> 

* <span data-ttu-id="1f886-123">Любая операция, которая сравнивает или вычисляет разницу между двумя неуказанными значениями времени, может включать неизвестный интервал, который отражает временную разницу между двумя различными часовыми поясами.</span><span class="sxs-lookup"><span data-stu-id="1f886-123">Any operation that compares or calculates the difference between two unspecified times may include an unknown interval that reflects the difference between the time in two different time zones.</span></span>

<span data-ttu-id="1f886-124">Существует множество сценариев, в которых различие часовых поясов не влияет на вычисления с датами и временем</span><span class="sxs-lookup"><span data-stu-id="1f886-124">There are many scenarios in which time zone differences do not affect date and time calculations or in which the context of the date and time data defines the meaning of comparison or arithmetic operations.</span></span> <span data-ttu-id="1f886-125">(обзор некоторых из них см. в разделе [Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](choosing-between-datetime.md)), или же контекст данных даты и времени определяет суть операций сравнения или арифметических операций.</span><span class="sxs-lookup"><span data-stu-id="1f886-125">For a discussion of some of these, see [Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md).</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a><span data-ttu-id="1f886-126">Сравнения и арифметические операции со значениями DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1f886-126">Comparisons and Arithmetic Operations with DateTimeOffset Values</span></span>

<span data-ttu-id="1f886-127">Значение [System.DateTimeOffset](xref:System.DateTimeOffset) содержит не только дату и время, но также и смещение, которое однозначно задает его соотношение с временем в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="1f886-127">A [System.DateTimeOffset](xref:System.DateTimeOffset) value includes not only a date and time, but also an offset that unambiguously defines that date and time relative to UTC.</span></span> <span data-ttu-id="1f886-128">Это дает возможность определить равенство несколько иначе, чем для значений [System.DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="1f886-128">This makes it possible to define equality somewhat differently than for [System.DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="1f886-129">Если значения [DateTime](xref:System.DateTime) считаются равными в случае, когда они имеют одинаковое значение даты и времени, то значения [DateTimeOffset](xref:System.DateTimeOffset) считаются равными тогда, когда они ссылаются на один момент времени.</span><span class="sxs-lookup"><span data-stu-id="1f886-129">Whereas [DateTime](xref:System.DateTime) values are equal if they have the same date and time value, [DateTimeOffset](xref:System.DateTimeOffset) values are equal if they both refer to the same point in time.</span></span> <span data-ttu-id="1f886-130">Это делает значение [DateTimeOffset](xref:System.DateTimeOffset) более точным и менее контекстно-зависимым при использовании в сравнении и в большинстве арифметических операций, которые определяют интервал между двумя значениями даты и времени.</span><span class="sxs-lookup"><span data-stu-id="1f886-130">This makes a [DateTimeOffset](xref:System.DateTimeOffset) value more accurate and less in need of interpretation when used in comparisons and in most arithmetic operations that determine the interval between two dates and times.</span></span> <span data-ttu-id="1f886-131">Различия в поведении [DateTimeOffset](xref:System.DateTimeOffset) демонстрирует следующий пример, который является аналогом предыдущего примера, в котором сравнивались значения DateTime для местного времени и времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="1f886-131">The following example, which is the [DateTimeOffset](xref:System.DateTimeOffset) equivalent to the previous example that compared local and UTC DateTime values, illustrates this difference in behavior.</span></span>

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateTimeOffsetManipulation
{
   public static void Main()
   {
      DateTimeOffset localTime = DateTimeOffset.Now;
      DateTimeOffset utcTime = DateTimeOffset.UtcNow;

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours", 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The local time is {0} UTC.", 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)));  
   }
}
// Regardless of the local time zone, the example displays 
// the following output to the console:
//    Difference between local time and UTC: 0:00 hours.
//    The local time is TheSameAs UTC.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateTimeOffsetManipulation
   Public Sub Main()
      Dim localTime As DateTimeOffset = DateTimeOffset.Now
      Dim utcTime As DateTimeOffset = DateTimeOffset.UtcNow

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours.", _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The local time is {0} UTC.", _
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)))  
   End Sub
End Module
' Regardless of the local time zone, the example displays 
' the following output to the console:
'    Difference between local time and UTC: 0:00 hours.
'    The local time is TheSameAs UTC.
'          Console.WriteLine(e.GetType().Name)
```

<span data-ttu-id="1f886-132">В этом примере метод [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) показывает, что текущее местное время равно текущему времени в формате UTC, а вычитание значений [DateTimeOffset](xref:System.DateTimeOffset) показывает, что разница между двумя значениями времени равна [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span><span class="sxs-lookup"><span data-stu-id="1f886-132">In this example, the [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) method indicates that the current local time and the current UTC time are equal, and subtraction of [DateTimeOffset](xref:System.DateTimeOffset) values indicates that the difference between the two times is [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> 

<span data-ttu-id="1f886-133">Главным препятствием для использования значений [DateTimeOffset](xref:System.DateTimeOffset) в арифметике дат и времени является то, что значения [DateTimeOffset](xref:System.DateTimeOffset) отражают сведения о часовых поясах не полностью, хоть и содержат некоторую информацию о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="1f886-133">The chief limitation of using [DateTimeOffset](xref:System.DateTimeOffset) values in date and time arithmetic is that although [DateTimeOffset](xref:System.DateTimeOffset) values have some time zone awareness, they are not fully time zone aware.</span></span> <span data-ttu-id="1f886-134">Несмотря на то, что при первом присваивании значения переменной типа [DateTimeOffset](xref:System.DateTimeOffset) смещение [DateTimeOffset](xref:System.DateTimeOffset) соответствует смещению часового пояса относительно времени в формате UTC, впоследствии оно рассогласовывается с часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="1f886-134">Although the [DateTimeOffset](xref:System.DateTimeOffset) value's offset reflects a time zone's offset from UTC when a [DateTimeOffset](xref:System.DateTimeOffset) variable is first assigned a value, it becomes disassociated from the time zone thereafter.</span></span> <span data-ttu-id="1f886-135">Поскольку оно больше не связано напрямую с распознаваемым временем, правила коррекции часовых поясов больше не будут учитываться при сложении и вычитании интервалов даты и времени.</span><span class="sxs-lookup"><span data-stu-id="1f886-135">Because it is no longer directly associated with an identifiable time, the addition and subtraction of date and time intervals does not consider a time zone's adjustment rules.</span></span> 

<span data-ttu-id="1f886-136">Пример: переход на летнее время в зоне центрального стандартного времени США происходит в 2:00 утра</span><span class="sxs-lookup"><span data-stu-id="1f886-136">To illustrate, the transition to daylight saving time in the U.S. Central Standard Time zone occurs at 2:00 A.M.</span></span> <span data-ttu-id="1f886-137">9 марта, 2008 г.</span><span class="sxs-lookup"><span data-stu-id="1f886-137">on March 9, 2008.</span></span> <span data-ttu-id="1f886-138">Это означает, что при прибавлении двух с половиной часов к 1:30 утра 9 марта 2008 г.</span><span class="sxs-lookup"><span data-stu-id="1f886-138">This means that adding a two and a half hour interval to a Central Standard time of 1:30 A.M.</span></span> <span data-ttu-id="1f886-139">центрального стандартного времени США должно получиться 5:00 утра</span><span class="sxs-lookup"><span data-stu-id="1f886-139">on March 9, 2008, should produce a date and time of 5:00 A.M.</span></span> <span data-ttu-id="1f886-140">9 марта, 2008 г.</span><span class="sxs-lookup"><span data-stu-id="1f886-140">on March 9, 2008.</span></span> <span data-ttu-id="1f886-141">Однако, как показано в следующем примере, результатом сложения является 4:00 утра</span><span class="sxs-lookup"><span data-stu-id="1f886-141">However, as the following example shows, the result of the addition is 4:00 A.M.</span></span> <span data-ttu-id="1f886-142">9 марта, 2008 г.</span><span class="sxs-lookup"><span data-stu-id="1f886-142">on March 9, 2008.</span></span> <span data-ttu-id="1f886-143">Обратите внимание, что такой результат данной операции представляет правильный момент времени, хотя и не является временем в искомом часовом поясе (в результате не содержится ожидаемое смещение часового пояса).</span><span class="sxs-lookup"><span data-stu-id="1f886-143">Note that this result of this operation does represent the correct point in time, although it is not the time in the time zone in which we are interested (that is, it does not have the expected time zone offset).</span></span>

```csharp
using System;

public class IntervalArithmetic
{
   public static void Main()
   {
      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      const string tzName = "Central Standard Time";
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime));

         // Add two and a half hours      
         DateTimeOffset centralTime2 = centralTime1.Add(twoAndAHalfHours);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

```vb
Module IntervalArithmetic
   Public Sub Main()
      Dim generalTime As Date = #03/09/2008 1:30AM#
      Const tzName As String = "Central Standard Time"
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime))

         ' Add two and a half hours      
         Dim centralTime2 As DateTimeOffset = centralTime1.Add(twoAndAHalfHours)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

## <a name="arithmetic-operations-with-times-in-time-zones"></a><span data-ttu-id="1f886-144">Арифметические операции со временем в часовых поясах</span><span class="sxs-lookup"><span data-stu-id="1f886-144">Arithmetic Operations with Times in Time Zones</span></span>

<span data-ttu-id="1f886-145">В классе [System.TimeZoneInfo](xref:System.TimeZoneInfo) отсутствуют методы, которые бы автоматически применяли правила коррекции при выполнении арифметических действий с датами и временем.</span><span class="sxs-lookup"><span data-stu-id="1f886-145">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not provide any methods that automatically apply adjustment rules when you perform date and time arithmetic.</span></span> <span data-ttu-id="1f886-146">Тем не менее, этого можно добиться, преобразовав время в часовом поясе во время в формате UTC, выполнив арифметическую операцию и преобразовав время UTC обратно во время в часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="1f886-146">However, you can do this by converting the time in a time zone to UTC, performing the arithmetic operation, and then converting from UTC back to the time in the time zone.</span></span> <span data-ttu-id="1f886-147">Дополнительные сведения см. в разделе [Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем](use-time-zones-in-arithmetic.md).</span><span class="sxs-lookup"><span data-stu-id="1f886-147">For details, see [How to: Use Time Zones in Date and Time Arithmetic](use-time-zones-in-arithmetic.md).</span></span>

<span data-ttu-id="1f886-148">Например, следующий код аналогичен предыдущему коду, в котором 2,5 часа добавлялись к 2:00 утра</span><span class="sxs-lookup"><span data-stu-id="1f886-148">For example, the following code is similar to the previous code that added two-and-a-half hours to 2:00 A.M.</span></span> <span data-ttu-id="1f886-149">9 марта, 2008 г.</span><span class="sxs-lookup"><span data-stu-id="1f886-149">on March 9, 2008.</span></span> <span data-ttu-id="1f886-150">Тем не менее, поскольку в этом примере перед выполнением арифметических действий над датой и временем центральное стандартное время преобразуется во время в формате UTC, а затем результат преобразуется из времени UTC обратно в центральное стандартное время, полученное время соответствует переходу центрального стандартного часового пояса на летнее время.</span><span class="sxs-lookup"><span data-stu-id="1f886-150">However, because it converts a Central Standard time to UTC before it performs date and time arithmetic, and then converts the result from UTC back to Central Standard time, the resulting time reflects the Central Standard Time Zone's transition to daylight saving time.</span></span>

```csharp
using System;

public class TimeZoneAwareArithmetic
{
   public static void Main()
   {
      const string tzName = "Central Standard Time";

      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                                       cst.GetUtcOffset(generalTime));

         // Add two and a half hours
         DateTimeOffset utcTime = centralTime1.ToUniversalTime();
         utcTime += twoAndAHalfHours;

         DateTimeOffset centralTime2 = TimeZoneInfo.ConvertTime(utcTime, cst);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

```vb
Module TimeZoneAwareArithmetic
   Public Sub Main()
      Const tzName As String = "Central Standard Time"

      Dim generalTime As Date = #03/09/2008 1:30AM#
      Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName) 
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    cst.GetUtcOffset(generalTime))

         ' Add two and a half hours 
         Dim utcTime As DateTimeOffset = centralTime1.ToUniversalTime()
         utcTime += twoAndAHalfHours

         Dim centralTime2 As DateTimeOffset = TimeZoneInfo.ConvertTime(utcTime, cst)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

## <a name="see-also"></a><span data-ttu-id="1f886-151">См. также</span><span class="sxs-lookup"><span data-stu-id="1f886-151">See Also</span></span>

[<span data-ttu-id="1f886-152">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="1f886-152">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="1f886-153">Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем</span><span class="sxs-lookup"><span data-stu-id="1f886-153">How to: use time zones in date and time arithmetic</span></span>](use-time-zones-in-arithmetic.md)



