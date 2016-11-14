---
title: "Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем"
description: "Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 26870cdc-1709-4978-831b-ff2a2f24856f
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 735ae2f1d11ddf6b88b40c7b89083a45d1f07523

---

# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем

Обычно при выполнении арифметических действий над датами и временем с помощью значений [System.DateTimeOffset](xref:System.DateTimeOffset) правила коррекции часовых поясов не учитываются в результате. Это верно даже в том случае, когда часовой пояс даты и времени четко определен. В этом разделе описывается порядок выполнения арифметических операций над значениями даты и времени, относящимися к определенному часовому поясу. Результаты арифметических операций при этом будут учитывать правила коррекции часовых поясов.

## <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>Применение правил коррекции в вычислениях с датами и временем

1. Необходимо каким-либо способом тесно связать значения даты и времени с соответствующим часовым поясом. К примеру, можно объявить структуру, которая будет содержать значение даты и времени вместе с данными о часовом поясе. В следующем примере для связывания значения [DateTimeOffset](xref:System.DateTimeOffset) с соответствующим ему часовым поясом используется именно этот подход.

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
    
2. Значение времени необходимо преобразовать во время в формате UTC с помощью вызова метода [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)).

3. Далее следует выполнить необходимые арифметические действия над временем UTC.

4. Время из формата UTC необходимо преобразовать в часовой пояс, соответствующий исходному времени, с помощью метода [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)). 

## <a name="example"></a>Пример

В следующем примере к 9 марта 2008 г., 1:30 центрального стандартного времени прибавляется два часа и тридцать минут. Переход на летнее время в этом часовом поясе происходит на 30 минут позже, в 2:00 9 марта, 2008 г. Поскольку в этом примере выполнены четыре шага, описанные в предыдущем разделе, он правильно возвращает итоговое время, равное 5:00 9 марта, 2008 г. 

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

Обратите внимание, что в случае, если эта операция выполняется над значением [DateTimeOffset](xref:System.DateTimeOffset) без предварительного преобразования в формат UTC, то результат будет соответствовать правильному моменту времени, но его смещение не будет отражать этот факт по отношению к часовому поясу, к которому принадлежит это время. 

Значения [DateTimeOffset](xref:System.DateTimeOffset) не имеют связи с часовыми поясами, к которым они могут относиться. Для того чтобы арифметические действия с датами и временем выполнялись таким образом, что правила коррекции часовых поясов учитывались бы автоматически, сведения о часовом поясе, к которому относятся значения даты и времени, должны быть известны и непосредственно доступны. Это означает, что значения даты и времени должны быть тесно связаны с часовым поясом. Для того, чтобы этого добиться, существует целый ряд способов, некоторые из них перечислены ниже.

* Предположим, что все значения времени, используемые в приложении, принадлежат к определенному часовому поясу. Хотя этот подход вполне применим во многих случаях, его гибкость и, возможно, переносимость имеют ограничения.

* Следует определить тип, в котором значение даты и времени тесно связано с часовым поясом, включив эти данные в состав типа в качестве полей. Этот подход используется в примере кода — в нем определяется структура для хранения даты, времени и часового пояса в двух полях структуры.

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](index.md)

[Выполнение арифметических операций с датами и временем](performing-arithmetic-operations.md)



<!--HONumber=Nov16_HO1-->


