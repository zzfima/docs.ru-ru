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
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 99ec9d8c433025bbc5122fe3ea364fe84f33a1f8

---

# <a name="converting-between-datetime-and-datetimeoffset"></a>Взаимное преобразование структур DateTime и DateTimeOffset

Хотя структура [System.DateTimeOffset](xref:System.DateTimeOffset) обеспечивает лучшую поддержку часовых поясов, чем структура [System.DateTime](xref:System.DateTime), параметры [DateTime](xref:System.DateTime) чаще используются в вызовах методов. Таким образом, возможность преобразования значений [DateTimeOffset](xref:System.DateTimeOffset) в значения [DateTime](xref:System.DateTime) и наоборот играет особенно важную роль. В этом разделе показано, как выполнять эти преобразования таким образом, чтобы сохранять как можно больше сведений о часовом поясе.

> [!NOTE]
> Типы [DateTime](xref:System.DateTime) и [DateTimeOffset](xref:System.DateTimeOffset) имеют некоторые ограничения при представлении времени в часовых поясах. Благодаря свойству [Kind](xref:System.DateTime.Kind) объект [DateTime](xref:System.DateTime) может автоматически устанавливать только время в формате UTC и время в местном часовом поясе системы. [DateTimeOffset](xref:System.DateTimeOffset) автоматически устанавливает смещение времени от времени UTC, но не устанавливает фактический часовой пояс, к которому относится это смещение. Дополнительные сведения о значениях времени и поддержке часовых поясов см. в разделе [Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo](choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Преобразование DateTime в DateTimeOffset

Структура [DateTimeOffset](xref:System.DateTimeOffset) предоставляет два равнозначных способа выполнения преобразования [DateTime](xref:System.DateTime) в [DateTimeOffset](xref:System.DateTimeOffset), которые подходят для большинства преобразований:

* Конструктор [DateTimeOffset](xref:System.DateTimeOffset), который создает новый объект [DateTimeOffset](xref:System.DateTimeOffset) на основе значения [DateTime](xref:System.DateTime).

* Оператор неявного преобразования, позволяющий назначить значение [DateTime](xref:System.DateTime) объекту [DateTimeOffset](xref:System.DateTimeOffset).

Для времени UTC и местных значений [DateTime](xref:System.DateTime) свойство [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) результирующего значения [DateTimeOffset](xref:System.DateTimeOffset) точно отражает время UTC или смещение местного часового пояса. Например, следующий код преобразует время UTC в эквивалентное значение [DateTimeOffset](xref:System.DateTimeOffset). 

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

В этом случае смещение переменной `utcTime2` равняется 00:00. Аналогичным образом следующий код преобразует местное время в эквивалентное значение [DateTimeOffset](xref:System.DateTimeOffset).

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

Однако для значений [DateTime](xref:System.DateTime), свойство [Kind](xref:System.DateTime.Kind) которых имеет значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), эти два метода преобразования возвращают значение [DateTimeOffset](xref:System.DateTimeOffset), смещением которого является смещение этого часового пояса. Это показано в приведенном ниже примере, который выполняется в тихоокеанском стандартном часовом поясе США.

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

Если значение [DateTime](xref:System.DateTime) отражает дату и время в часовом поясе, отличном от местного часового пояса или от UTC, то можно преобразовать его в значение [DateTimeOffset](xref:System.DateTimeOffset) и сохранить сведения о его часовом поясе, вызвав перегруженный конструктор [DateTimeOffset](xref:System.DateTimeOffset). Например, в следующем примере создается экземпляр [DateTimeOffset](xref:System.DateTimeOffset), который отражает центральное стандартное время.

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

Вторым параметром в этом перегруженном конструкторе является объект [System.TimeSpan](xref:System.TimeSpan), представляющий смещение времени от UTC, который должен быть извлечен посредством вызова метода [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo) соответствующего часового пояса. Единственным параметром данного метода является значение [DateTime](xref:System.DateTime), представляющее дату и время, которые требуется преобразовать. Если часовой пояс поддерживает переход на летнее время, то этот параметр позволяет методу определять соответствующее смещение для конкретных даты и времени.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Преобразование DateTimeOffset в DateTime

Свойство [DateTime](xref:System.DateTime) чаще всего используется для выполнения преобразования [DateTimeOffset](xref:System.DateTimeOffset) в [DateTime](xref:System.DateTime). Тем не менее, оно возвращает значение [DateTime](xref:System.DateTime), свойством [Kind](xref:System.DateTime.Kind) которого является [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), как показано в следующем примере. 

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

Это означает, что все сведения о связи значения [DateTimeOffset](xref:System.DateTimeOffset) с UTC будут потеряны при преобразовании, когда используется свойство [DateTime](xref:System.DateTime). Это влияет на значения [DateTimeOffset](xref:System.DateTimeOffset), которые соответствуют времени UTC или локальному времени системы, так как структура [DateTime](xref:System.DateTime) отражает только эти два часовых пояса в свойстве [Kind](xref:System.DateTime.Kind).

Чтобы сохранить как можно больше сведений о часовом поясе при преобразовании [DateTimeOffset](xref:System.DateTimeOffset) в значение [DateTime](xref:System.DateTime), можно использовать свойства [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) и [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime). 

## <a name="converting-a-utc-time"></a>Преобразование времени UTC

Чтобы указать, что преобразуемое значение [DateTime](xref:System.DateTime) является временем UTC, можно получить значение свойства [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime). Оно отличается от свойства [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) двумя особенностями:

* Оно возвращает значение [DateTime](xref:System.DateTime), свойством [Kind](xref:System.DateTime.Kind) которого является [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).

* Если значение свойства [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) не равно [TimeSpan.Zero](xref:System.TimeSpan.Zero), то оно преобразуется во время UTC.

> [!NOTE]
> Если для приложения необходимо, чтобы преобразованные значения [DateTime](xref:System.DateTime) однозначно идентифицировали единственный момент времени, то следует использовать свойство [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) для обработки всех преобразований из [DateTimeOffset](xref:System.DateTimeOffset) в [DateTime](xref:System.DateTime).

Следующий код использует свойство [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) для преобразования значения [DateTimeOffset](xref:System.DateTimeOffset), смещение которого равно [TimeSpan.Zero](xref:System.TimeSpan.Zero), в значение [DateTime](xref:System.DateTime).

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

Следующий код использует свойство "UtcDateTime" для преобразования часового пояса и преобразования типов значения [DateTimeOffset](xref:System.DateTimeOffset).

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

## <a name="converting-a-local-time"></a>Преобразование локального времени

Чтобы указать, что значение [DateTimeOffset](xref:System.DateTimeOffset) представляет локальное время, можно передать значение [DateTime](xref:System.DateTime), возвращенное свойством [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) в static метода [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)). Этот метод возвращает дату и время, переданные ему в качестве первого параметра, но устанавливает для свойства [Kind](xref:System.DateTime.Kind) значение, указанное ему в качестве второго параметра. В следующем коде используется метод [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) при преобразовании значения [DateTimeOffset](xref:System.DateTimeOffset), смещение которого соответствует смещению местного часового пояса.

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

Также можно использовать свойство [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) для преобразования значения [DateTimeOffset](xref:System.DateTimeOffset) в локальное значение [DateTime](xref:System.DateTime). Свойством [Kind](xref:System.DateTime.Kind) возвращаемого значения [DateTime](xref:System.DateTime) является [DateTimeKind.Local](xref:System.DateTimeKind.Local). В следующем коде используется свойство [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) при преобразовании значения [DateTimeOffset](xref:System.DateTimeOffset), смещение которого соответствует смещению местного часового пояса.

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

При извлечении значения [DateTime](xref:System.DateTime) с помощью свойства [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) метод доступа `get` свойства сначала преобразует значение [DateTimeOffset](xref:System.DateTimeOffset) в UTC, а затем преобразует его в локальное время посредством вызова метода [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset). Это означает, что вы можете получить значение свойства [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) для выполнения преобразования в момент выполнения преобразования типов. Это также означает, что при выполнении преобразования применяются правила коррекции местного часового пояса. Следующий код иллюстрирует использование свойства [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) для выполнения преобразования и типа, и часового пояса.

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

## <a name="a-general-purpose-conversion-method"></a>Метод преобразования общего назначения

В следующем примере определяется метод с именем `ConvertFromDateTimeOffset`, который преобразует значения [DateTimeOffset](xref:System.DateTimeOffset) в значения [DateTime](xref:System.DateTime). В зависимости от смещения, он определяет, является ли значение [DateTimeOffset](xref:System.DateTimeOffset) временем UTC, локальным временем или другим временем, и соответствующим образом определяет свойство [Kind](xref:System.DateTime.Kind) возвращаемого значения даты и времени. 

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

В следующем примере вызывается метод `ConvertFromDateTimeOffset` для преобразования значений [DateTimeOffset](xref:System.DateTimeOffset), представляющих время UTC, местное время и время центрального стандартного часового пояса США.

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

Обратите внимание, что этот код делает два предположения, которые в зависимости от применения и источника значений даты и времени могут оказаться недопустимыми:

* Предполагается, что значение даты и времени, смещение которого равно [TimeSpan.Zero](xref:System.TimeSpan.Zero), представляет время UTC. На самом деле UTC не является временем в определенном часовом поясе, но оно является временем, по отношению к которому стандартизованы времена часовых поясов в мире. Часовые пояса также могут иметь смещение [Zero](xref:System.TimeSpan.Zero).

* Предполагается, что значение даты и времени, смещение для которого равно смещению местного часового пояса, представляет местный часовой пояс. Поскольку значения даты и времени не связаны со своими исходными часовыми поясами, то это может не выполняться. Значение даты и времени может быть создано в другом часовом поясе с тем же самым смещением.

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](index.md)







<!--HONumber=Nov16_HO3-->


