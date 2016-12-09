---
title: "Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo"
description: "Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2dd84ee8-9f0f-4054-9537-155857a460cd
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: f8a603bab32afd0b8e7d13c9c5755e3f14a9d2bd

---

# <a name="choosing-between-datetime-datetimeoffset-timespan-and-timezoneinfo"></a>Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo

Приложения .NET, использующие сведения о дате и времени, очень разнообразны и могут применять эти сведения различными способами. Чаще всего сведения о дате и времени используются в следующих целях:

* для представления только даты; сведения о времени не имеют значения;

* для представления только времени; сведения о дате не имеют значения;

* для представления абстрактных даты и времени, не привязанных к определенному времени и месту (например, большинство магазинов международных сетей открываются по рабочим дням в 9:00);

* для получения сведений о дате и времени из источников вне приложения .NET, в которых они, как правило, хранятся в простом типе данных;

* для однозначной идентификации конкретного момента времени: некоторые приложения требуют, чтобы дата и время были однозначными только в основной системе; другие требуют, чтобы они были однозначным в разных системах (то есть дату, сериализованную в одной системе, можно достоверно десериализовать и использовать в другой системе в любой точке мира); 

* для сохранения нескольких связанных значений времени (например, местного времени запрашивающей системы и серверного времени получения веб-запроса);

* для выполнения арифметических операций с датой и временем, возможно, с результатом, однозначно определяющим момент времени. 

Платформа .NET включает типы [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan) и [System.TimeZoneInfo](xref:System.TimeZoneInfo), которые можно использовать для создания приложений, работающих с датами и временем. 

> [!NOTE]
> В этом разделе не рассматривается четвертый тип, `TimeZone`, так как его функциональность практически полностью включена в класс [System.TimeZoneInfo](xref:System.TimeZoneInfo). Везде, где это возможно, разработчикам следует использовать класс [System.TimeZoneInfo](xref:System.TimeZoneInfo) вместо класса `TimeZone`.


## <a name="the-datetime-structure"></a>Структура DateTime

Значение [System.DateTime](xref:System.DateTime) определяет конкретные дату и время. Оно включает свойство [Kind](xref:System.DateTime.Kind), которое предоставляет ограниченные сведения о часовом поясе, которому принадлежат эти дата и время. Значение [DateTimeKind](xref:System.DateTimeKind), возвращаемое свойством [Kind](xref:System.DateTime.Kind), указывает, представляет ли значение [DateTime](xref:System.DateTime) местное время ([DateTimeKind.Local](xref:System.DateTimeKind.Local)), время в формате UTC ([DateTimeKind.Utc](xref:System.DateTimeKind.Utc)) или неопределенное время ([DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)).

Структура [DateTime](xref:System.DateTime) подходит для приложений, которые: 

* работают только с датами;

* работают только со временем;

* работают с абстрактными датами и временем;

* работают с датами и временем, для которых отсутствуют сведения о часовом поясе; 

* работают только с датами и временем в формате UTC; 

* получают информацию о дате и времени из источников вне платформы .NET Framework, таких как базы данных SQL (как правило, информация о дате и времени хранится в этих источниках в простом формате, который совместим со структурой [DateTime](xref:System.DateTime));

* выполняют арифметические операции с датой и временем, но учитывают только общие результаты. Например, в операции сложения, которая добавляет шесть месяцев к определенным дате и времени, часто не важно, корректируется ли результат с учетом перехода на летнее время.

Кроме случая, когда определенное значение [DateTime](xref:System.DateTime) представляет время в формате UTC, значение даты и времени часто является неоднозначным или ограниченным в плане возможности переноса. Например, если значение [DateTime](xref:System.DateTime) представляет местное время, оно является переносимым внутри местного часового пояса (то есть если значение десериализуется в другой системе в том же часовом поясе, оно по-прежнему однозначно определяет конкретный момент времени). За пределами местного часового пояса значение [DateTime](xref:System.DateTime) может иметь несколько интерпретаций. Если свойство [Kind](xref:System.DateTime.Kind) имеет значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), то значение даты и времени становится еще менее переносимым: в этом случае оно неоднозначно даже в том же часовом поясе и, возможно, даже на том же компьютере, на котором оно было впервые сериализовано. Значение [DateTime](xref:System.DateTime) однозначно идентифицирует момент времени независимо от времени системы или часового пояса, в котором оно используется, только если это значение представляет время в формате UTC.

> [!IMPORTANT]
> При сохранении или совместном использовании данных [DateTime](xref:System.DateTime) следует использовать формат UTC, а для свойства [Kind](xref:System.DateTime.Kind) значения [DateTime](xref:System.DateTime) должно быть задано значение [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).

## <a name="the-datetimeoffset-structure"></a>Структура DateTimeOffset

Структура [System.DateTimeOffset](xref:System.DateTimeOffset) представляет значение даты и времени, а также смещение, которое указывает, насколько это значение отличается от времени в формате UTC. Таким образом, значение всегда однозначно идентифицирует единственный момент времени. 

Тип [DateTimeOffset](xref:System.DateTimeOffset) включает все функциональные возможности типа [DateTime](xref:System.DateTime), а также сведения о часовом поясе. Это делает его подходящим для приложений, которые: 

* однозначно идентифицируют единственный момент времени; тип [DateTimeOffset](xref:System.DateTimeOffset) можно использовать для однозначного определения текущего момента времени, для ведения журнала времени транзакций, ведения журнала времени событий системы или приложений, а также для записи времени создания и изменения файлов; 

* выполняют общие арифметические операции с датами и временем;

* сохраняют несколько связанных значений времени, если они хранятся как два отдельных значения или два члена структуры.

> [!NOTE]
> Эти варианты использования значений [DateTimeOffset](xref:System.DateTimeOffset) более распространены, чем варианты использования значений [DateTime](xref:System.DateTime). Соответственно, [DateTimeOffset](xref:System.DateTimeOffset) следует рассматривать как тип даты и времени по умолчанию для разработки приложений.

Значение [DateTimeOffset](xref:System.DateTimeOffset) не привязано к определенному часовому поясу, но может быть создано из любого часового пояса. Чтобы проиллюстрировать это, в примере ниже перечисляются часовые пояса, к которым может принадлежать ряд значений [DateTimeOffset](xref:System.DateTimeOffset) (включая местное тихоокеанское время США).

```csharp
using System;
using System.Collections.ObjectModel;

public class TimeOffsets
{
   public static void Main()
   {
      DateTime thisDate = new DateTime(2007, 3, 10, 0, 0, 0);
      DateTime dstDate = new DateTime(2007, 6, 10, 0, 0, 0);
      DateTimeOffset thisTime;

      thisTime = new DateTimeOffset(dstDate, new TimeSpan(-7, 0, 0));
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(-6, 0, 0));  
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(+1, 0, 0));
      ShowPossibleTimeZones(thisTime);
   }

   private static void ShowPossibleTimeZones(DateTimeOffset offsetTime)
   {
      TimeSpan offset = offsetTime.Offset;
      ReadOnlyCollection<TimeZoneInfo> timeZones;

      Console.WriteLine("{0} could belong to the following time zones:", 
                        offsetTime.ToString());
      // Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones();     
      // Iterate time zones 
      foreach (TimeZoneInfo timeZone in timeZones)
      {
         // Compare offset with offset for that date in that time zone
         if (timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset))
            Console.WriteLine("   {0}", timeZone.DisplayName);
      }
      Console.WriteLine();
   } 
}
// This example displays the following output to the console:
//       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
//          (GMT-07:00) Arizona
//          (GMT-08:00) Pacific Time (US & Canada)
//          (GMT-08:00) Tijuana, Baja California
//       
//       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
//          (GMT-06:00) Central America
//          (GMT-06:00) Central Time (US & Canada)
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
//          (GMT-06:00) Saskatchewan
//       
//       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
//          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
//          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
//          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
//          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
//          (GMT+01:00) West Central Africa
```

```vb
Imports System.Collections.ObjectModel

Module TimeOffsets
   Public Sub Main()
      Dim thisTime As DateTimeOffset 

      thisTime = New DateTimeOffset(#06/10/2007#, New TimeSpan(-7, 0, 0))
      ShowPossibleTimeZones(thisTime) 

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(-6, 0, 0))  
      ShowPossibleTimeZones(thisTime)

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(+1, 0, 0))
      ShowPossibleTimeZones(thisTime)
   End Sub

   Private Sub ShowPossibleTimeZones(offsetTime As DateTimeOffset)
      Dim offset As TimeSpan = offsetTime.Offset
      Dim timeZones As ReadOnlyCollection(Of TimeZoneInfo)

      Console.WriteLine("{0} could belong to the following time zones:", _
                        offsetTime.ToString())
      ' Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones()     
      ' Iterate time zones
      For Each timeZone As TimeZoneInfo In timeZones
         ' Compare offset with offset for that date in that time zone
         If timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset) Then
            Console.WriteLine("   {0}", timeZone.DisplayName)
         End If   
      Next
      Console.WriteLine()
   End Sub
End Module
' This example displays the following output to the console:
'       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
'          (GMT-07:00) Arizona
'          (GMT-08:00) Pacific Time (US & Canada)
'          (GMT-08:00) Tijuana, Baja California
'       
'       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
'          (GMT-06:00) Central America
'          (GMT-06:00) Central Time (US & Canada)
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
'          (GMT-06:00) Saskatchewan
'       
'       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
'          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
'          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
'          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
'          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
'          (GMT+01:00) West Central Africa
```

Выходные данные показывают, что все значения даты и времени в этом примере могут принадлежать по крайней мере трем разным часовым поясам. Значение [DateTimeOffset](xref:System.DateTimeOffset) 6/10/2007 показывает, что если значение даты и времени представляет летнее время, его смещение от времени UTC необязательно соответствует базовому смещению UTC исходного часового пояса или смещению от времени UTC, указанному в его отображаемом имени. Это означает, что, так как одно значение [DateTimeOffset](xref:System.DateTimeOffset) не является тесно связанным с его часовым поясом, оно не может отражать переход часового пояса с летнего на зимнее время и обратно. Это может быть особенно проблематичным, когда используются арифметические операции со значением [DateTimeOffset](xref:System.DateTimeOffset). Описание способов выполнения арифметических операций с датой и временем с учетом правил коррекции часового пояса см. в разделе [Выполнение арифметических операций с датами и временем](performing-arithmetic-operations.md).

## <a name="the-timespan-structure"></a>Структура TimeSpan

Структура [System.TimeSpan](xref:System.TimeSpan) представляет интервал времени. Ее обычно используют двумя способами: 

* для отражения интервала времени между двумя значениями даты и времени (например, при вычитании одного значения [DateTime](xref:System.DateTime) из другого возвращается значение [TimeSpan](xref:System.TimeSpan)); 

* для измерения прошедшего времени. Например, свойство [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) возвращает значение [TimeSpan](xref:System.TimeSpan), которое отражает интервал времени, прошедший с момента вызова одного из методов [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch), который начинает измерение прошедшего времени.

Значение [TimeSpan](xref:System.TimeSpan) также может использоваться для замены значения [DateTime](xref:System.DateTime), если это значение отражает время без указания времени суток. Этот вариант использования аналогичен свойствам [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) и [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay), которые возвращают значение [TimeSpan](xref:System.TimeSpan), представляющее время безотносительно к дате. Например, структуру [TimeSpan](xref:System.TimeSpan) можно использовать для представления ежедневного времени открытия или закрытия магазина или времени, в которое происходит любое регулярное событие.

В примере ниже определяется структура `StoreInfo`, которая включает объекты [TimeSpan](xref:System.TimeSpan), представляющие время закрытия и открытия магазина, а также объект [TimeZoneInfo](xref:System.TimeZoneInfo), представляющий часовой пояс магазина. Структура также включает два метода, `IsOpenNow` и `IsOpenAt`, указывающие, открыт ли магазин в то время, которое указал пользователь, предположительно находящийся в местном часовом поясе.  

```csharp
using System;

public struct StoreInfo
{
   public String store;
   public TimeZoneInfo tz;
   public TimeSpan open;
   public TimeSpan close;

   public bool IsOpenNow()
   {
      return IsOpenAt(DateTime.TimeOfDay);
   }

   public bool IsOpenAt(TimeSpan time)
   {
      TimeZoneInfo local = TimeZoneInfo.Local;
      TimeSpan offset = TimeZoneInfo.BaseUtcOffset;

      // Is the store in the same time zone?
      if (tz.Equals(local)) {
         return time >= open & time <= close;
      }
   }
}
```

```vb
Public Structure StoreInfo
   Dim store As String
   Dim tz As TimeZoneInfo
   Dim open As TimeSpan
   Dim close As TimeSpan

   Public Function IsOpenNow() As Boolean
      Return IsOpenAt(Date.Now.TimeOfDay)
   End Function

   Public Function IsOpenAt(time As TimeSpan) As Boolean
      Dim local As TimeZoneInfo = TimeZoneInfo.Local
      Dim offset As TimeSpan = TimeZoneInfo.Local.BaseUtcOffset

      ' Is the store in the same time zone?
      If tz.Equals(local) Then
         Return time >= open And time <= close
      Else
         Dim delta As TimeSpan = TimeSpan.Zero
         Dim storeDelta As TimeSpan = TimeSpan.Zero

         ' Is it daylight saving time in either time zone?
         If local.IsDaylightSavingTime(Date.Now.Date + time) Then
            delta = local.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         If tz.IsDaylightSavingTime(TimeZoneInfo.ConvertTime(Date.Now.Date + time, local, tz))
            storeDelta = tz.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         Dim comparisonTime As TimeSpan = time + (offset - tz.BaseUtcOffset).Negate() + (delta - storeDelta).Negate
         Return (comparisonTime >= open And comparisonTime <= close)
      End If
   End Function
End Structure
```

Затем клиентский код может использовать структуру `StoreInfo`, как показано ниже. 

```csharp
public class Example
{
   public static void Main()
   {
      // Instantiate a StoreInfo object.
      var store103 = new StoreInfo();
      store103.store = "Store #103";
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
      // Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0);
      // Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0);

      Console.WriteLine("Store is open now at {0}: {1}",
                        DateTime.TimeOfDay, store103.IsOpenNow());
      TimeSpan[] times = { new TimeSpan(8, 0, 0), new TimeSpan(21, 0, 0),
                           new TimeSpan(4, 59, 0), new TimeSpan(18, 31, 0) };
      foreach (var time in times)
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time));
   }
}
// The example displays the following output:
//       Store is open now at 15:29:01.6129911: True
//       Store is open at 08:00:00: True
//       Store is open at 21:00:00: False
//       Store is open at 04:59:00: False
//       Store is open at 18:31:00: False
```

```vb
Module Example
   Public Sub Main()
      ' Instantiate a StoreInfo object.
      Dim store103 As New StoreInfo()
      store103.store = "Store #103"
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
      ' Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0)
      ' Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0)

      Console.WriteLine("Store is open now at {0}: {1}",
                        Date.Now.TimeOfDay, store103.IsOpenNow())
      Dim times() As TimeSpan = { New TimeSpan(8, 0, 0),
                                  New TimeSpan(21, 0, 0),
                                  New TimeSpan(4, 59, 0),
                                  New TimeSpan(18, 31, 0) }
      For Each time In times
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time))
      Next
   End Sub
End Module
' The example displays the following output:
'       Store is open now at 15:29:01.6129911: True
'       Store is open at 08:00:00: True
'       Store is open at 21:00:00: False
'       Store is open at 04:59:00: False
'       Store is open at 18:31:00: False
```

## <a name="the-timezoneinfo-class"></a>Класс TimeZoneInfo

Класс [System.TimeZoneInfo](xref:System.TimeZoneInfo) представляет все часовые пояса земли и обеспечивает преобразование любого значения даты и времени из одного часового пояса в его эквивалент в другом часовом поясе. Класс [TimeZoneInfo](xref:System.TimeZoneInfo) позволяет работать со значениями даты и времени, обеспечивая однозначную идентификацию единственного момента времени с помощью любого значения даты и времени.

В некоторых случаях использование всех преимуществ класса [TimeZoneInfo](xref:System.TimeZoneInfo) может потребовать дальнейших усилий по разработке. Значения даты и времени не связаны тесно с часовыми поясами, к которым они относятся. Соответственно, если приложение не предоставляет некоторый механизм для связывания даты и времени с соответствующим часовым поясом, определенное значение даты и времени может легко утратить связь с часовым поясом. Одним из способов связывания этой информации является определение класса или структуры, содержащих значение даты и времени и связанный с ним часовой пояс.

Использование преимуществ поддержки часовых поясов в .NET возможно только в том случае, если часовой пояс, к которому относится значение даты и времени, известен при создании экземпляра объекта даты и времени. Как правило, это условие не выполняется, особенно в сетевых или веб-приложениях.

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](index.md)


<!--HONumber=Nov16_HO3-->


