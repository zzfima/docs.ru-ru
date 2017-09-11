---
title: "Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем"
description: "Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 26870cdc-1709-4978-831b-ff2a2f24856f
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a86471972d42adcbc412cc8eeb300410ca8a9c42
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="bab01-104">Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем</span><span class="sxs-lookup"><span data-stu-id="bab01-104">How to: use time zones in date and time arithmetic</span></span>

<span data-ttu-id="bab01-105">Обычно при выполнении арифметических действий над датами и временем с помощью значений [System.DateTimeOffset](xref:System.DateTimeOffset) правила коррекции часовых поясов не учитываются в результате.</span><span class="sxs-lookup"><span data-stu-id="bab01-105">Ordinarily, when you perform date and time arithmetic using [System.DateTimeOffset](xref:System.DateTimeOffset) values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="bab01-106">Это верно даже в том случае, когда часовой пояс даты и времени четко определен.</span><span class="sxs-lookup"><span data-stu-id="bab01-106">This is true even when the time zone of the date and time value is clearly identifiable.</span></span> <span data-ttu-id="bab01-107">В этом разделе описывается порядок выполнения арифметических операций над значениями даты и времени, относящимися к определенному часовому поясу.</span><span class="sxs-lookup"><span data-stu-id="bab01-107">This article shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="bab01-108">Результаты арифметических операций при этом будут учитывать правила коррекции часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="bab01-108">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

## <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="bab01-109">Применение правил коррекции в вычислениях с датами и временем</span><span class="sxs-lookup"><span data-stu-id="bab01-109">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="bab01-110">Необходимо каким-либо способом тесно связать значения даты и времени с соответствующим часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="bab01-110">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="bab01-111">К примеру, можно объявить структуру, которая будет содержать значение даты и времени вместе с данными о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="bab01-111">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="bab01-112">В следующем примере для связывания значения [DateTimeOffset](xref:System.DateTimeOffset) с соответствующим ему часовым поясом используется именно этот подход.</span><span class="sxs-lookup"><span data-stu-id="bab01-112">The following example uses this approach to link a [DateTimeOffset](xref:System.DateTimeOffset) value with its time zone.</span></span>

    ```csharp
    // Define a structure for DateTime values for internal use only
    internal struct TimeWithTimeZone
    {
    TimeZoneInfo TimeZone;
    DateTimeOffset Time;
    }
    ```

    ```vb
    ' Define a structure for DateTime values for internal use only
    Friend Structure TimeWithTimeZone
       Dim TimeZone As TimeZoneInfo
       Dim Time As Date
    End Structure
    ```
    
2. <span data-ttu-id="bab01-113">Значение времени необходимо преобразовать во время в формате UTC с помощью вызова метода [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)).</span><span class="sxs-lookup"><span data-stu-id="bab01-113">Convert a time to Coordinated Universal Time (UTC) by calling the [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span>

3. <span data-ttu-id="bab01-114">Далее следует выполнить необходимые арифметические действия над временем UTC.</span><span class="sxs-lookup"><span data-stu-id="bab01-114">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="bab01-115">Время из формата UTC необходимо преобразовать в часовой пояс, соответствующий исходному времени, с помощью метода [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)).</span><span class="sxs-lookup"><span data-stu-id="bab01-115">Convert the time from UTC to the original time's associated time zone by calling the [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span> 

## <a name="example"></a><span data-ttu-id="bab01-116">Пример</span><span class="sxs-lookup"><span data-stu-id="bab01-116">Example</span></span>

<span data-ttu-id="bab01-117">В следующем примере к 9 марта 2008 г., 1:30</span><span class="sxs-lookup"><span data-stu-id="bab01-117">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="bab01-118">центрального стандартного времени прибавляется два часа и тридцать минут.</span><span class="sxs-lookup"><span data-stu-id="bab01-118">Central Standard Time.</span></span> <span data-ttu-id="bab01-119">Переход на летнее время в этом часовом поясе происходит на 30 минут позже, в 2:00</span><span class="sxs-lookup"><span data-stu-id="bab01-119">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="bab01-120">9 марта, 2008 г.</span><span class="sxs-lookup"><span data-stu-id="bab01-120">on March 9, 2008.</span></span> <span data-ttu-id="bab01-121">Поскольку в этом примере выполнены четыре шага, описанные в предыдущем разделе, он правильно возвращает итоговое время, равное 5:00</span><span class="sxs-lookup"><span data-stu-id="bab01-121">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="bab01-122">9 марта, 2008 г.</span><span class="sxs-lookup"><span data-stu-id="bab01-122">on March 9, 2008.</span></span> 

```csharp
using System;

public struct TimeZoneTime
{
   public TimeZoneInfo TimeZone;
   public DateTimeOffset Time;

   public TimeZoneTime(TimeZoneInfo tz, DateTimeOffset time)
   {
      if (tz == null) 
         throw new ArgumentNullException("The time zone cannot be a null reference.");

      this.TimeZone = tz;
      this.Time = time;   
   }

   public TimeZoneTime AddTime(TimeSpan interval)
   {
      // Convert time to UTC
      DateTimeOffset utcTime = TimeZoneInfo.ConvertTime(this.Time, TimeZoneInfo.Utc);      
      // Add time interval to time
      utcTime = utcTime.Add(interval);
      // Convert time back to time in time zone
      return new TimeZoneTime(this.TimeZone, TimeZoneInfo.ConvertTime(utcTime, this.TimeZone));
   }
}

public class TimeArithmetic
{
   public const string tzName = "Central Standard Time";

   public static void Main()
   {
      try
      {
         TimeZoneTime cstTime1, cstTime2;

         TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
         DateTime time1 = new DateTime(2008, 3, 9, 1, 30, 0);          
         TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

         cstTime1 = new TimeZoneTime(cst, 
                        new DateTimeOffset(time1, cst.GetUtcOffset(time1)));
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours);
         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, 
                                                    twoAndAHalfHours.ToString(),  
                                                    cstTime2.Time);
      }
      catch
      {
         Console.WriteLine("Unable to find {0}.", tzName);
      }
   }
}
```

```vb
Public Structure TimeZoneTime
   Public TimeZone As TimeZoneInfo
   Public Time As Date

   Public Sub New(tz As TimeZoneInfo, time As Date)
      If tz Is Nothing Then _
         Throw New ArgumentNullException("The time zone cannot be a null reference.")

      Me.TimeZone = tz
      Me.Time = time
   End Sub

   Public Function AddTime(interval As TimeSpan) As TimeZoneTime
      ' Convert time to UTC
      Dim utcTime As DateTime = TimeZoneInfo.ConvertTimeToUtc(Me.Time, _
                                                              Me.TimeZone)      
      ' Add time interval to time
      utcTime = utcTime.Add(interval)
      ' Convert time back to time in time zone
      Return New TimeZoneTime(Me.TimeZone, TimeZoneInfo.ConvertTime(utcTime, _
                              TimeZoneInfo.Utc, Me.TimeZone))
   End Function
End Structure

Module TimeArithmetic
   Public Const tzName As String = "Central Standard Time"

   Public Sub Main()
      Try
         Dim cstTime1, cstTime2 As TimeZoneTime

         Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName)
         Dim time1 As Date = #03/09/2008 1:30AM#
         Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

         cstTime1 = New TimeZoneTime(cst, time1)
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours)

         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, _
                                                    twoAndAHalfHours.ToString(), _ 
                                                    cstTime2.Time)  
      Catch
         Console.WriteLine("Unable to find {0}.", tzName)
      End Try   
   End Sub   
End Module
```

<span data-ttu-id="bab01-123">Обратите внимание, что в случае, если эта операция выполняется над значением [DateTimeOffset](xref:System.DateTimeOffset) без предварительного преобразования в формат UTC, то результат будет соответствовать правильному моменту времени, но его смещение не будет отражать этот факт по отношению к часовому поясу, к которому принадлежит это время.</span><span class="sxs-lookup"><span data-stu-id="bab01-123">Note that if this addition is simply performed on the [DateTimeOffset](xref:System.DateTimeOffset) value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span> 

<span data-ttu-id="bab01-124">Значения [DateTimeOffset](xref:System.DateTimeOffset) не имеют связи с часовыми поясами, к которым они могут относиться.</span><span class="sxs-lookup"><span data-stu-id="bab01-124">[DateTimeOffset](xref:System.DateTimeOffset) values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="bab01-125">Для того чтобы арифметические действия с датами и временем выполнялись таким образом, что правила коррекции часовых поясов учитывались бы автоматически, сведения о часовом поясе, к которому относятся значения даты и времени, должны быть известны и непосредственно доступны.</span><span class="sxs-lookup"><span data-stu-id="bab01-125">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="bab01-126">Это означает, что значения даты и времени должны быть тесно связаны с часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="bab01-126">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="bab01-127">Для того, чтобы этого добиться, существует целый ряд способов, некоторые из них перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="bab01-127">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="bab01-128">Предположим, что все значения времени, используемые в приложении, принадлежат к определенному часовому поясу.</span><span class="sxs-lookup"><span data-stu-id="bab01-128">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="bab01-129">Хотя этот подход вполне применим во многих случаях, его гибкость и, возможно, переносимость имеют ограничения.</span><span class="sxs-lookup"><span data-stu-id="bab01-129">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="bab01-130">Следует определить тип, в котором значение даты и времени тесно связано с часовым поясом, включив эти данные в состав типа в качестве полей.</span><span class="sxs-lookup"><span data-stu-id="bab01-130">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="bab01-131">Этот подход используется в примере кода — в нем определяется структура для хранения даты, времени и часового пояса в двух полях структуры.</span><span class="sxs-lookup"><span data-stu-id="bab01-131">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="bab01-132">См. также</span><span class="sxs-lookup"><span data-stu-id="bab01-132">See Also</span></span>

[<span data-ttu-id="bab01-133">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="bab01-133">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="bab01-134">Выполнение арифметических операций с датами и временем</span><span class="sxs-lookup"><span data-stu-id="bab01-134">Performing arithmetic operations with dates and times</span></span>](performing-arithmetic-operations.md)

