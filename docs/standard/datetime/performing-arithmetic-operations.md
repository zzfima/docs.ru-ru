---
title: "Выполнение арифметических операций с датами и временем"
description: "Выполнение арифметических операций с датами и временем"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 589ac5ec-8365-4a0d-bc38-72183718110c
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 64fbb3b25d5959ac1dd781d2076775560d926e1a

---

# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Выполнение арифметических операций с датами и временем

Несмотря на то, что структуры [System.DateTime](xref:System.DateTime) и [System.DateTimeOffset](xref:System.DateTimeOffset) предоставляют члены, выполняющие арифметические действия над их значениями, результаты арифметических операций очень различаются. В данном разделе эти различия описываются в контексте различных уровней представленности сведений о часовом поясе во временных данных, а также рассматриваются способы выполнения операций над датами и временем с полным учетом сведений о часовых поясах.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Сравнения и арифметические операции со значениями даты и времени

В значениях [System.DateTime](xref:System.DateTime) присутствуют ограниченные сведения о часовом поясе. Свойство [DateTime.Kind](xref:System.DateTime.Kind) позволяет присваивать значению даты и времени значение [System.DateTimeKind](xref:System.DateTimeKind), чтобы указать, представляет ли оно местное время, время в формате UTC или время в неопределенном часовом поясе. Тем не менее, эти ограниченные сведения о часовом поясе игнорируются при сравнении или выполнении арифметических операций со значениями [DateTime](xref:System.DateTime). Это демонстрируется в следующем примере, где текущее местное время сравнивается с текущим временем в формате UTC.

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

Метод [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) показывает, что местное время предшествует (или меньше) времени в формате UTC, а операция вычитания свидетельствует о том, что разница между временем в формате UTC и местным временем для систем в тихоокеанском стандартном часовом поясе США составляет семь часов. Тем не менее, поскольку эти значения дают различные представления одного и того же момента времени, в данном случае очевидно, что причина этого различия целиком кроется в смещении местного часового пояса относительно времени в формате UTC. 

В общем случае свойство [DateTimeKind](xref:System.DateTimeKind) не влияет на результаты, возвращаемые методами сравнения и арифметическими операциями (как показывает результат сравнения двух идентичных моментов времени) с [DateTime](xref:System.DateTime), хотя оно может повлиять на интерпретацию этих результатов. Пример:

* Результат любой арифметической операции над парой значений даты и времени, свойства [DateTimeKind](xref:System.DateTimeKind) которых имеют значение [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), отражает фактический интервал времени между этими двумя значениями. Аналогичным образом результат сравнения двух таких значений даты и времени будет точно отражать соотношение между временами.

* Результат любой арифметической операции или операции сравнения над двумя значениями даты и времени, свойства [DateTimeKind](xref:System.DateTimeKind) которых имеют значение [DateTimeKind.Local](xref:System.DateTimeKind.Local), или над двумя значениями даты и времени с различными значениями свойства [DateTimeKind](xref:System.DateTimeKind) будет отражать временную разницу между этими значениями. 

* Арифметические операции или операции сравнения, выполняемые над местными значениями даты и времени, не учитывают допустимость или недопустимость конкретных значений; не учитывают они и какие-либо правила коррекции, необходимые при переводе местного часового пояса на зимнее или летнее время.

* В результат любой операции, сравнивающей или вычисляющей разницу между временем в формате UTC и местным временем, входит временной интервал, равный смещению местного часового пояса относительно времени в формате UTC. 

* Любая операция, которая сравнивает или вычисляет разницу между неуказанным временем и временем в формате UTC или местным временем, соответствует простому времени. Различия между часовыми поясами не учитываются, и в результате не отражено применение правил коррекции часовых поясов. 

* Любая операция, которая сравнивает или вычисляет разницу между двумя неуказанными значениями времени, может включать неизвестный интервал, который отражает временную разницу между двумя различными часовыми поясами.

Существует множество сценариев, в которых различие часовых поясов не влияет на вычисления с датами и временем (обзор некоторых из них см. в разделе [Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](choosing-between-datetime.md)), или же контекст данных даты и времени определяет суть операций сравнения или арифметических операций.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Сравнения и арифметические операции со значениями DateTimeOffset

Значение [System.DateTimeOffset](xref:System.DateTimeOffset) содержит не только дату и время, но также и смещение, которое однозначно задает его соотношение с временем в формате UTC. Это дает возможность определить равенство несколько иначе, чем для значений [System.DateTime](xref:System.DateTime). Если значения [DateTime](xref:System.DateTime) считаются равными в случае, когда они имеют одинаковое значение даты и времени, то значения [DateTimeOffset](xref:System.DateTimeOffset) считаются равными тогда, когда они ссылаются на один момент времени. Это делает значение [DateTimeOffset](xref:System.DateTimeOffset) более точным и менее контекстно-зависимым при использовании в сравнении и в большинстве арифметических операций, которые определяют интервал между двумя значениями даты и времени. Различия в поведении [DateTimeOffset](xref:System.DateTimeOffset) демонстрирует следующий пример, который является аналогом предыдущего примера, в котором сравнивались значения DateTime для местного времени и времени в формате UTC.

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

В этом примере метод [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) показывает, что текущее местное время равно текущему времени в формате UTC, а вычитание значений [DateTimeOffset](xref:System.DateTimeOffset) показывает, что разница между двумя значениями времени равна [TimeSpan.Zero](xref:System.TimeSpan.Zero). 

Главным препятствием для использования значений [DateTimeOffset](xref:System.DateTimeOffset) в арифметике дат и времени является то, что значения [DateTimeOffset](xref:System.DateTimeOffset) отражают сведения о часовых поясах не полностью, хоть и содержат некоторую информацию о часовом поясе. Несмотря на то, что при первом присваивании значения переменной типа [DateTimeOffset](xref:System.DateTimeOffset) смещение [DateTimeOffset](xref:System.DateTimeOffset) соответствует смещению часового пояса относительно времени в формате UTC, впоследствии оно рассогласовывается с часовым поясом. Поскольку оно больше не связано напрямую с распознаваемым временем, правила коррекции часовых поясов больше не будут учитываться при сложении и вычитании интервалов даты и времени. 

Пример: переход на летнее время в зоне центрального стандартного времени США происходит в 2:00 утра 9 марта, 2008 г. Это означает, что при прибавлении двух с половиной часов к 1:30 утра 9 марта 2008 г. центрального стандартного времени США должно получиться 5:00 утра 9 марта, 2008 г. Однако, как показано в следующем примере, результатом сложения является 4:00 утра 9 марта, 2008 г. Обратите внимание, что такой результат данной операции представляет правильный момент времени, хотя и не является временем в искомом часовом поясе (в результате не содержится ожидаемое смещение часового пояса).

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

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Арифметические операции со временем в часовых поясах

В классе [System.TimeZoneInfo](xref:System.TimeZoneInfo) отсутствуют методы, которые бы автоматически применяли правила коррекции при выполнении арифметических действий с датами и временем. Тем не менее, этого можно добиться, преобразовав время в часовом поясе во время в формате UTC, выполнив арифметическую операцию и преобразовав время UTC обратно во время в часовом поясе. Дополнительные сведения см. в разделе [Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем](use-time-zones-in-arithmetic.md).

Например, следующий код аналогичен предыдущему коду, в котором 2,5 часа добавлялись к 2:00 утра 9 марта, 2008 г. Тем не менее, поскольку в этом примере перед выполнением арифметических действий над датой и временем центральное стандартное время преобразуется во время в формате UTC, а затем результат преобразуется из времени UTC обратно в центральное стандартное время, полученное время соответствует переходу центрального стандартного часового пояса на летнее время.

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

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](index.md)

[Практическое руководство. Использование часовых поясов в арифметических операциях с датами и временем](use-time-zones-in-arithmetic.md)





<!--HONumber=Nov16_HO1-->


