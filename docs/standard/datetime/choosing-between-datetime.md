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
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: aeb1928be32584ee4b6acf7c9a4f4330daedc590
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="choosing-between-datetime-datetimeoffset-timespan-and-timezoneinfo"></a><span data-ttu-id="5901f-104">Выбор между типами DateTime, DateTimeOffset, TimeSpan и TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="5901f-104">Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>

<span data-ttu-id="5901f-105">Приложения .NET, использующие сведения о дате и времени, очень разнообразны и могут применять эти сведения различными способами.</span><span class="sxs-lookup"><span data-stu-id="5901f-105">.NET applications that use date and time information are very diverse and can use that information in several ways.</span></span> <span data-ttu-id="5901f-106">Чаще всего сведения о дате и времени используются в следующих целях:</span><span class="sxs-lookup"><span data-stu-id="5901f-106">The more common uses of date and time information include one or more of the following:</span></span>

* <span data-ttu-id="5901f-107">для представления только даты; сведения о времени не имеют значения;</span><span class="sxs-lookup"><span data-stu-id="5901f-107">To reflect a date only, so that time information is not important.</span></span>

* <span data-ttu-id="5901f-108">для представления только времени; сведения о дате не имеют значения;</span><span class="sxs-lookup"><span data-stu-id="5901f-108">To reflect a time only, so that date information is not important.</span></span>

* <span data-ttu-id="5901f-109">для представления абстрактных даты и времени, не привязанных к определенному времени и месту (например, большинство магазинов международных сетей открываются по рабочим дням в 9:00);</span><span class="sxs-lookup"><span data-stu-id="5901f-109">To reflect an abstract date and time that is not tied to a specific time and place (for example, most stores in an international chain open on weekdays at 9:00 A.M.).</span></span>

* <span data-ttu-id="5901f-110">для получения сведений о дате и времени из источников вне приложения .NET, в которых они, как правило, хранятся в простом типе данных;</span><span class="sxs-lookup"><span data-stu-id="5901f-110">To retrieve date and time information from sources outside of the .NET application, typically where date and time information is stored in a simple data type.</span></span>

* <span data-ttu-id="5901f-111">для однозначной идентификации конкретного момента времени:</span><span class="sxs-lookup"><span data-stu-id="5901f-111">To uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="5901f-112">некоторые приложения требуют, чтобы дата и время были однозначными только в основной системе; другие требуют, чтобы они были однозначным в разных системах (то есть дату, сериализованную в одной системе, можно достоверно десериализовать и использовать в другой системе в любой точке мира);</span><span class="sxs-lookup"><span data-stu-id="5901f-112">Some applications require that a date and time be unambiguous only on the host system; others require that it be unambiguous across systems (that is, a date serialized on one system can be meaningfully deserialized and used on another system anywhere in the world).</span></span> 

* <span data-ttu-id="5901f-113">для сохранения нескольких связанных значений времени (например, местного времени запрашивающей системы и серверного времени получения веб-запроса);</span><span class="sxs-lookup"><span data-stu-id="5901f-113">To preserve multiple related times (such as the requestor's local time and the server's time of receipt for a Web request).</span></span>

* <span data-ttu-id="5901f-114">для выполнения арифметических операций с датой и временем, возможно, с результатом, однозначно определяющим момент времени.</span><span class="sxs-lookup"><span data-stu-id="5901f-114">To perform date and time arithmetic, possibly with a result that uniquely and unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="5901f-115">Платформа .NET включает типы [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan) и [System.TimeZoneInfo](xref:System.TimeZoneInfo), которые можно использовать для создания приложений, работающих с датами и временем.</span><span class="sxs-lookup"><span data-stu-id="5901f-115">.NET includes the [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan), and [System.TimeZoneInfo](xref:System.TimeZoneInfo) types, all of which can be used to build applications that work with dates and times.</span></span> 

> [!NOTE]
> <span data-ttu-id="5901f-116">В этом разделе не рассматривается четвертый тип, `TimeZone`, так как его функциональность практически полностью включена в класс [System.TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="5901f-116">This topic does not discuss the older `TimeZone` type, because its functionality is almost entirely incorporated in the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class.</span></span> <span data-ttu-id="5901f-117">Везде, где это возможно, разработчикам следует использовать класс [System.TimeZoneInfo](xref:System.TimeZoneInfo) вместо класса `TimeZone`.</span><span class="sxs-lookup"><span data-stu-id="5901f-117">Whenever possible, developers should use the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class instead of the `TimeZone` class.</span></span>


## <a name="the-datetime-structure"></a><span data-ttu-id="5901f-118">Структура DateTime</span><span class="sxs-lookup"><span data-stu-id="5901f-118">The DateTime structure</span></span>

<span data-ttu-id="5901f-119">Значение [System.DateTime](xref:System.DateTime) определяет конкретные дату и время.</span><span class="sxs-lookup"><span data-stu-id="5901f-119">A [System.DateTime](xref:System.DateTime) value defines a particular date and time.</span></span> <span data-ttu-id="5901f-120">Оно включает свойство [Kind](xref:System.DateTime.Kind), которое предоставляет ограниченные сведения о часовом поясе, которому принадлежат эти дата и время.</span><span class="sxs-lookup"><span data-stu-id="5901f-120">It includes a [Kind](xref:System.DateTime.Kind) property that provides limited information about the time zone to which that date and time belongs.</span></span> <span data-ttu-id="5901f-121">Значение [DateTimeKind](xref:System.DateTimeKind), возвращаемое свойством [Kind](xref:System.DateTime.Kind), указывает, представляет ли значение [DateTime](xref:System.DateTime) местное время ([DateTimeKind.Local](xref:System.DateTimeKind.Local)), время в формате UTC ([DateTimeKind.Utc](xref:System.DateTimeKind.Utc)) или неопределенное время ([DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)).</span><span class="sxs-lookup"><span data-stu-id="5901f-121">The [DateTimeKind](xref:System.DateTimeKind) value returned by the [Kind](xref:System.DateTime.Kind) property indicates whether the [DateTime](xref:System.DateTime) value represents the local time [DateTimeKind.Local](xref:System.DateTimeKind.Local)), Coordinated Universal Time (UTC) [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), or an unspecified time [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span>

<span data-ttu-id="5901f-122">Структура [DateTime](xref:System.DateTime) подходит для приложений, которые:</span><span class="sxs-lookup"><span data-stu-id="5901f-122">The [DateTime](xref:System.DateTime) structure is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="5901f-123">работают только с датами;</span><span class="sxs-lookup"><span data-stu-id="5901f-123">Work with dates only.</span></span>

* <span data-ttu-id="5901f-124">работают только со временем;</span><span class="sxs-lookup"><span data-stu-id="5901f-124">Work with times only.</span></span>

* <span data-ttu-id="5901f-125">работают с абстрактными датами и временем;</span><span class="sxs-lookup"><span data-stu-id="5901f-125">Work with abstract dates and times.</span></span>

* <span data-ttu-id="5901f-126">работают с датами и временем, для которых отсутствуют сведения о часовом поясе;</span><span class="sxs-lookup"><span data-stu-id="5901f-126">Work with dates and times for which time zone information is missing.</span></span> 

* <span data-ttu-id="5901f-127">работают только с датами и временем в формате UTC;</span><span class="sxs-lookup"><span data-stu-id="5901f-127">Work with UTC dates and times only.</span></span> 

* <span data-ttu-id="5901f-128">получают информацию о дате и времени из источников вне платформы .NET Framework, таких как базы данных SQL</span><span class="sxs-lookup"><span data-stu-id="5901f-128">Retrieve date and time information from sources outside the .NET Framework, such as SQL databases.</span></span> <span data-ttu-id="5901f-129">(как правило, информация о дате и времени хранится в этих источниках в простом формате, который совместим со структурой [DateTime](xref:System.DateTime));</span><span class="sxs-lookup"><span data-stu-id="5901f-129">Typically, these sources store date and time information in a simple format that is compatible with the [DateTime](xref:System.DateTime) structure.</span></span>

* <span data-ttu-id="5901f-130">выполняют арифметические операции с датой и временем, но учитывают только общие результаты.</span><span class="sxs-lookup"><span data-stu-id="5901f-130">Perform date and time arithmetic, but are concerned with general results.</span></span> <span data-ttu-id="5901f-131">Например, в операции сложения, которая добавляет шесть месяцев к определенным дате и времени, часто не важно, корректируется ли результат с учетом перехода на летнее время.</span><span class="sxs-lookup"><span data-stu-id="5901f-131">For example, in an addition operation that adds six months to a particular date and time, it is often not important whether the result is adjusted for daylight saving time.</span></span>

<span data-ttu-id="5901f-132">Кроме случая, когда определенное значение [DateTime](xref:System.DateTime) представляет время в формате UTC, значение даты и времени часто является неоднозначным или ограниченным в плане возможности переноса.</span><span class="sxs-lookup"><span data-stu-id="5901f-132">Unless a particular [DateTime](xref:System.DateTime) value represents UTC, that date and time value is often ambiguous or limited in its portability.</span></span> <span data-ttu-id="5901f-133">Например, если значение [DateTime](xref:System.DateTime) представляет местное время, оно является переносимым внутри местного часового пояса (то есть если значение десериализуется в другой системе в том же часовом поясе, оно по-прежнему однозначно определяет конкретный момент времени).</span><span class="sxs-lookup"><span data-stu-id="5901f-133">For example, if a [DateTime](xref:System.DateTime) value represents the local time, it is portable within that local time zone (that is, if the value is deserialized on another system in the same time zone, that value still unambiguously identifies a single point in time).</span></span> <span data-ttu-id="5901f-134">За пределами местного часового пояса значение [DateTime](xref:System.DateTime) может иметь несколько интерпретаций.</span><span class="sxs-lookup"><span data-stu-id="5901f-134">Outside the local time zone, that [DateTime](xref:System.DateTime) value can have multiple interpretations.</span></span> <span data-ttu-id="5901f-135">Если свойство [Kind](xref:System.DateTime.Kind) имеет значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), то значение даты и времени становится еще менее переносимым: в этом случае оно неоднозначно даже в том же часовом поясе и, возможно, даже на том же компьютере, на котором оно было впервые сериализовано.</span><span class="sxs-lookup"><span data-stu-id="5901f-135">If the value's [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), it is even less portable: it is now ambiguous within the same time zone and possibly even on the same system on which it was first serialized.</span></span> <span data-ttu-id="5901f-136">Значение [DateTime](xref:System.DateTime) однозначно идентифицирует момент времени независимо от времени системы или часового пояса, в котором оно используется, только если это значение представляет время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="5901f-136">Only if a [DateTime](xref:System.DateTime) value represents UTC does that value unambiguously identify a single point in time regardless of the system or time zone in which the value is used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5901f-137">При сохранении или совместном использовании данных [DateTime](xref:System.DateTime) следует использовать формат UTC, а для свойства [Kind](xref:System.DateTime.Kind) значения [DateTime](xref:System.DateTime) должно быть задано значение [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span><span class="sxs-lookup"><span data-stu-id="5901f-137">When saving or sharing [DateTime](xref:System.DateTime) data, UTC should be used and the [DateTime](xref:System.DateTime) value's [Kind](xref:System.DateTime.Kind) property should be set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="the-datetimeoffset-structure"></a><span data-ttu-id="5901f-138">Структура DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5901f-138">The DateTimeOffset structure</span></span>

<span data-ttu-id="5901f-139">Структура [System.DateTimeOffset](xref:System.DateTimeOffset) представляет значение даты и времени, а также смещение, которое указывает, насколько это значение отличается от времени в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="5901f-139">The [System.DateTimeOffset](xref:System.DateTimeOffset) structure represents a date and time value, together with an offset that indicates how much that value differs from UTC.</span></span> <span data-ttu-id="5901f-140">Таким образом, значение всегда однозначно идентифицирует единственный момент времени.</span><span class="sxs-lookup"><span data-stu-id="5901f-140">Thus, the value always unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="5901f-141">Тип [DateTimeOffset](xref:System.DateTimeOffset) включает все функциональные возможности типа [DateTime](xref:System.DateTime), а также сведения о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="5901f-141">The [DateTimeOffset](xref:System.DateTimeOffset) type includes all of the functionality of the [DateTime](xref:System.DateTime) type along with time zone awareness.</span></span> <span data-ttu-id="5901f-142">Это делает его подходящим для приложений, которые:</span><span class="sxs-lookup"><span data-stu-id="5901f-142">This makes it is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="5901f-143">однозначно идентифицируют единственный момент времени;</span><span class="sxs-lookup"><span data-stu-id="5901f-143">Uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="5901f-144">тип [DateTimeOffset](xref:System.DateTimeOffset) можно использовать для однозначного определения текущего момента времени, для ведения журнала времени транзакций, ведения журнала времени событий системы или приложений, а также для записи времени создания и изменения файлов;</span><span class="sxs-lookup"><span data-stu-id="5901f-144">The [DateTimeOffset](xref:System.DateTimeOffset) type can be used to unambiguously define the meaning of "now", to log transaction times, to log the times of system or application events, and to record file creation and modification times.</span></span> 

* <span data-ttu-id="5901f-145">выполняют общие арифметические операции с датами и временем;</span><span class="sxs-lookup"><span data-stu-id="5901f-145">Perform general date and time arithmetic.</span></span>

* <span data-ttu-id="5901f-146">сохраняют несколько связанных значений времени, если они хранятся как два отдельных значения или два члена структуры.</span><span class="sxs-lookup"><span data-stu-id="5901f-146">Preserve multiple related times, as long as those times are stored as two separate values or as two members of a structure.</span></span>

> [!NOTE]
> <span data-ttu-id="5901f-147">Эти варианты использования значений [DateTimeOffset](xref:System.DateTimeOffset) более распространены, чем варианты использования значений [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="5901f-147">These uses for [DateTimeOffset](xref:System.DateTimeOffset) values are much more common than those for [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="5901f-148">Соответственно, [DateTimeOffset](xref:System.DateTimeOffset) следует рассматривать как тип даты и времени по умолчанию для разработки приложений.</span><span class="sxs-lookup"><span data-stu-id="5901f-148">As a result, [DateTimeOffset](xref:System.DateTimeOffset) should be considered the default date and time type for application development.</span></span>

<span data-ttu-id="5901f-149">Значение [DateTimeOffset](xref:System.DateTimeOffset) не привязано к определенному часовому поясу, но может быть создано из любого часового пояса.</span><span class="sxs-lookup"><span data-stu-id="5901f-149">A [DateTimeOffset](xref:System.DateTimeOffset) value is not tied to a particular time zone, but can originate from any of a variety of time zones.</span></span> <span data-ttu-id="5901f-150">Чтобы проиллюстрировать это, в примере ниже перечисляются часовые пояса, к которым может принадлежать ряд значений [DateTimeOffset](xref:System.DateTimeOffset) (включая местное тихоокеанское время США).</span><span class="sxs-lookup"><span data-stu-id="5901f-150">To illustrate this, the following example lists the time zones to which a number of [DateTimeOffset](xref:System.DateTimeOffset) values (including a local Pacific Standard Time) can belong.</span></span>

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

<span data-ttu-id="5901f-151">Выходные данные показывают, что все значения даты и времени в этом примере могут принадлежать по крайней мере трем разным часовым поясам.</span><span class="sxs-lookup"><span data-stu-id="5901f-151">The output shows that each date and time value in this example can belong to at least three different time zones.</span></span> <span data-ttu-id="5901f-152">Значение [DateTimeOffset](xref:System.DateTimeOffset) 6/10/2007 показывает, что если значение даты и времени представляет летнее время, его смещение от времени UTC необязательно соответствует базовому смещению UTC исходного часового пояса или смещению от времени UTC, указанному в его отображаемом имени.</span><span class="sxs-lookup"><span data-stu-id="5901f-152">The [DateTimeOffset](xref:System.DateTimeOffset) value of 6/10/2007 shows that if a date and time value represents a daylight saving time, its offset from UTC does not even necessarily correspond to the originating time zone's base UTC offset or to the offset from UTC found in its display name.</span></span> <span data-ttu-id="5901f-153">Это означает, что, так как одно значение [DateTimeOffset](xref:System.DateTimeOffset) не является тесно связанным с его часовым поясом, оно не может отражать переход часового пояса с летнего на зимнее время и обратно.</span><span class="sxs-lookup"><span data-stu-id="5901f-153">This means that, because a single [DateTimeOffset](xref:System.DateTimeOffset)  value is not tightly coupled with its time zone, it cannot reflect a time zone's transition to and from daylight saving time.</span></span> <span data-ttu-id="5901f-154">Это может быть особенно проблематичным, когда используются арифметические операции со значением [DateTimeOffset](xref:System.DateTimeOffset).</span><span class="sxs-lookup"><span data-stu-id="5901f-154">This can be particularly problematic when date and time arithmetic is used to manipulate a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="5901f-155">Описание способов выполнения арифметических операций с датой и временем с учетом правил коррекции часового пояса см. в разделе [Выполнение арифметических операций с датами и временем](performing-arithmetic-operations.md).</span><span class="sxs-lookup"><span data-stu-id="5901f-155">For a discussion of how to perform date and time arithmetic in a way that takes account of a time zone's adjustment rules, see [Performing arithmetic operations with dates and times](performing-arithmetic-operations.md).</span></span>

## <a name="the-timespan-structure"></a><span data-ttu-id="5901f-156">Структура TimeSpan</span><span class="sxs-lookup"><span data-stu-id="5901f-156">The TimeSpan structure</span></span>

<span data-ttu-id="5901f-157">Структура [System.TimeSpan](xref:System.TimeSpan) представляет интервал времени.</span><span class="sxs-lookup"><span data-stu-id="5901f-157">The [System.TimeSpan](xref:System.TimeSpan) structure represents a time interval.</span></span> <span data-ttu-id="5901f-158">Ее обычно используют двумя способами:</span><span class="sxs-lookup"><span data-stu-id="5901f-158">Its two typical uses are:</span></span> 

* <span data-ttu-id="5901f-159">для отражения интервала времени между двумя значениями даты и времени</span><span class="sxs-lookup"><span data-stu-id="5901f-159">Reflecting the time interval between two date and time values.</span></span> <span data-ttu-id="5901f-160">(например, при вычитании одного значения [DateTime](xref:System.DateTime) из другого возвращается значение [TimeSpan](xref:System.TimeSpan));</span><span class="sxs-lookup"><span data-stu-id="5901f-160">For example, subtracting one [DateTime](xref:System.DateTime) value from another returns a [TimeSpan](xref:System.TimeSpan) value.</span></span> 

* <span data-ttu-id="5901f-161">для измерения прошедшего времени.</span><span class="sxs-lookup"><span data-stu-id="5901f-161">Measuring elapsed time.</span></span> <span data-ttu-id="5901f-162">Например, свойство [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) возвращает значение [TimeSpan](xref:System.TimeSpan), которое отражает интервал времени, прошедший с момента вызова одного из методов [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch), который начинает измерение прошедшего времени.</span><span class="sxs-lookup"><span data-stu-id="5901f-162">For example, the [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) property returns a [TimeSpan](xref:System.TimeSpan) value that reflects the time interval that has elapsed since the call to one of the [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) methods that begins to measure elapsed time.</span></span>

<span data-ttu-id="5901f-163">Значение [TimeSpan](xref:System.TimeSpan) также может использоваться для замены значения [DateTime](xref:System.DateTime), если это значение отражает время без указания времени суток.</span><span class="sxs-lookup"><span data-stu-id="5901f-163">A [TimeSpan](xref:System.TimeSpan) value can also be used as a replacement for a [DateTime](xref:System.DateTime) value when that value reflects a time without reference to a particular time of day.</span></span> <span data-ttu-id="5901f-164">Этот вариант использования аналогичен свойствам [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) и [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay), которые возвращают значение [TimeSpan](xref:System.TimeSpan), представляющее время безотносительно к дате.</span><span class="sxs-lookup"><span data-stu-id="5901f-164">This usage is similar to the [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) and [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay) properties, which return a [TimeSpan](xref:System.TimeSpan) value that represents the time without reference to a date.</span></span> <span data-ttu-id="5901f-165">Например, структуру [TimeSpan](xref:System.TimeSpan) можно использовать для представления ежедневного времени открытия или закрытия магазина или времени, в которое происходит любое регулярное событие.</span><span class="sxs-lookup"><span data-stu-id="5901f-165">For example, the [TimeSpan](xref:System.TimeSpan) structure can be used to reflect a store's daily opening or closing time, or it can be used to represent the time at which any regular event occurs.</span></span>

<span data-ttu-id="5901f-166">В примере ниже определяется структура `StoreInfo`, которая включает объекты [TimeSpan](xref:System.TimeSpan), представляющие время закрытия и открытия магазина, а также объект [TimeZoneInfo](xref:System.TimeZoneInfo), представляющий часовой пояс магазина.</span><span class="sxs-lookup"><span data-stu-id="5901f-166">The following example defines a `StoreInfo` structure that includes [TimeSpan](xref:System.TimeSpan) objects for store opening and closing times, as well as a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the store's time zone.</span></span> <span data-ttu-id="5901f-167">Структура также включает два метода, `IsOpenNow` и `IsOpenAt`, указывающие, открыт ли магазин в то время, которое указал пользователь, предположительно находящийся в местном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="5901f-167">The structure also includes two methods, `IsOpenNow` and `IsOpenAt`, that indicates whether the store is open at a time specified by the user, who is assumed to be in the local time zone.</span></span>  

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

<span data-ttu-id="5901f-168">Затем клиентский код может использовать структуру `StoreInfo`, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="5901f-168">The `StoreInfo` structure can then be used by client code like the following.</span></span> 

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

## <a name="the-timezoneinfo-class"></a><span data-ttu-id="5901f-169">Класс TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="5901f-169">The TimeZoneInfo class</span></span>

<span data-ttu-id="5901f-170">Класс [System.TimeZoneInfo](xref:System.TimeZoneInfo) представляет все часовые пояса земли и обеспечивает преобразование любого значения даты и времени из одного часового пояса в его эквивалент в другом часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="5901f-170">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class represents any of the earth's time zones, and enables the conversion of any date and time in one time zone to its equivalent in another time zone.</span></span> <span data-ttu-id="5901f-171">Класс [TimeZoneInfo](xref:System.TimeZoneInfo) позволяет работать со значениями даты и времени, обеспечивая однозначную идентификацию единственного момента времени с помощью любого значения даты и времени.</span><span class="sxs-lookup"><span data-stu-id="5901f-171">The [TimeZoneInfo](xref:System.TimeZoneInfo) class makes it possible to work with dates and times so that any date and time value unambiguously identifies a single point in time.</span></span>

<span data-ttu-id="5901f-172">В некоторых случаях использование всех преимуществ класса [TimeZoneInfo](xref:System.TimeZoneInfo) может потребовать дальнейших усилий по разработке.</span><span class="sxs-lookup"><span data-stu-id="5901f-172">In some cases, taking full advantage of the [TimeZoneInfo](xref:System.TimeZoneInfo) class may require further development work.</span></span> <span data-ttu-id="5901f-173">Значения даты и времени не связаны тесно с часовыми поясами, к которым они относятся.</span><span class="sxs-lookup"><span data-stu-id="5901f-173">Date and time values are not tightly coupled with the time zones to which they belong.</span></span> <span data-ttu-id="5901f-174">Соответственно, если приложение не предоставляет некоторый механизм для связывания даты и времени с соответствующим часовым поясом, определенное значение даты и времени может легко утратить связь с часовым поясом.</span><span class="sxs-lookup"><span data-stu-id="5901f-174">As a result, unless your application provides some mechanism for linking a date and time with its associated time zone, it is easy for a particular date and time value to become disassociated from its time zone.</span></span> <span data-ttu-id="5901f-175">Одним из способов связывания этой информации является определение класса или структуры, содержащих значение даты и времени и связанный с ним часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="5901f-175">One method of linking this information is to define a class or structure that contains both the date and time value and its associated time zone object.</span></span>

<span data-ttu-id="5901f-176">Использование преимуществ поддержки часовых поясов в .NET возможно только в том случае, если часовой пояс, к которому относится значение даты и времени, известен при создании экземпляра объекта даты и времени.</span><span class="sxs-lookup"><span data-stu-id="5901f-176">Taking advantage of time zone support in .NET is possible only if the time zone to which a date and time value belongs is known when that date and time object is instantiated.</span></span> <span data-ttu-id="5901f-177">Как правило, это условие не выполняется, особенно в сетевых или веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="5901f-177">This is often not the case, particularly in Web or network applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="5901f-178">См. также</span><span class="sxs-lookup"><span data-stu-id="5901f-178">See Also</span></span>

[<span data-ttu-id="5901f-179">Даты, время и часовые пояса</span><span class="sxs-lookup"><span data-stu-id="5901f-179">Dates, times, and time zones</span></span>](index.md)
