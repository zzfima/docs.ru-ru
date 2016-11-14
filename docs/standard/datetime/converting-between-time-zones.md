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
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 051a4891336470e79bda9d7b9bb1be4e2c9187b8

---

# <a name="converting-times-between-time-zones"></a>Преобразование времени из одного часового пояса в другой

Обработка различий между часовыми поясами становится все более важной для всех приложений, которые работают с датами и временем. При работе приложения нельзя предполагать, что все значения времени могут быть выражены по местному времени, которое доступно из структуры [System.DateTime](xref:System.DateTime). Например, веб-страница, которая отображает текущее время в восточной части США, будет содержать недостоверные сведения для пользователей в восточной Азии. В этом разделе объясняется, как преобразовать время из одного часового пояса в другой, а также как преобразовать значения [System.DateTimeOffset](xref:System.DateTimeOffset) с ограниченной поддержкой часовых поясов.

## <a name="converting-to-coordinated-universal-time"></a>Преобразование во время в формате UTC

Время в формате UTC — это высокоточный, атомарный стандарт времени. Часовые пояса выражаются как положительные или отрицательные смещения относительно времени в формате UTC. Таким образом, время в формате UTC предоставляет тип времени, свободного от часовых поясов, или нейтрального времени часового пояса. Использование времени в формате UTC рекомендовано, когда важна совместимость даты и времени между компьютерами. Преобразование отдельных часовых поясов во время в формате UTC упрощает сравнение времен.

> [!NOTE]
> Можно сериализовать структуру [DateTimeOffset](xref:System.DateTimeOffset) для однозначного представления одного момента времени. Поскольку объекты [DateTimeOffset](xref:System.DateTimeOffset) хранят значение даты и времени вместе с его смещением относительно времени в формате UTC, то они всегда представляют определенный момент времени по отношению ко времени UTC.

Самым простым способом преобразования времени в формате UTC является вызов `static` (`Shared` в Visual Basic) метода [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx). 

> [!IMPORTANT]
> Метод `TimeZoneInfo.ConvertTimeToUtc(DateTime)` сейчас недоступен в .NET Core. 

Точное преобразование, выполненное этим методом, зависит от значения свойства [Kind](xref:System.DateTime.Kind) параметра `DateTime`, как показано в следующей таблице.

Свойство [DateTime.Kind](xref:System.DateTimeKind) | Преобразование
---------------------------------------------------------------------------------------------- | ----------
[DateTimeKind.Local](xref:System.DateTimeKind.Local) | Преобразует местное время во время в формате UTC.
[DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) | Предполагает, что параметр `DateTime` является местным временем и преобразовывает местное время в UTC.
[DateTimeKind.Utc](xref:System.DateTimeKind.Utc) | Возвращает неизмененный параметр `DateTime`.

Следующий код преобразовывает текущее местное время во время в формате UTC и выводит результат на консоль.

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
>Метод [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) не обязательно возвращает результаты, которые совпадают с результатами методов [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) и [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime). Если местный часовой пояс на локальной системе содержит несколько правил коррекции, то метод [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) применяет соответствующее правило к конкретным дате и времени. Два других метода всегда применяют последнее правило коррекции.

Если значение даты и времени не представляет местное время или время в формате UTC, то метод [ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) скорее всего вернет ошибочный результат. Однако можно использовать метод [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) для преобразования даты и времени из заданного часового пояса. (Дополнительные сведения о получении объекта TimeZoneInfo, который представляет часовой пояс назначения, см. в статье [Поиск часового пояса, заданного в локальной системе](finding-the-time-zones-on-local-system.md).) В следующем коде используется метод [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) для преобразования восточного стандартного времени в UTC.

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

Обратите внимание, что этот метод создает исключение [ArgumentException](xref:System.ArgumentException), если свойство [Kind](xref:System.DateTimeKind) объекта [DateTime](xref:System.DateTime) не совпадает с часовым поясом. Несоответствие возникает, если свойство "Kind" задано как [DateTimeKind.Local](xref:System.DateTimeKind.Local), а объект [TimeZoneInfo](xref:System.TimeZoneInfo) не представляет местный часовой пояс, или если свойство "Kind" задано как [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), а объект [TimeZoneInfo](xref:System.TimeZoneInfo) не равен [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).

Все эти методы принимают значения [DateTime](xref:System.DateTime) в качестве параметров и возвращают значение [DateTime](xref:System.DateTime). Для значений [DateTimeOffset](xref:System.DateTimeOffset) в структуре [DateTimeOffset](xref:System.DateTimeOffset) используется метод экземпляра [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime), который преобразует дату и время текущего экземпляра в UTC. В следующем примере вызывается метод [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) для преобразования местного времени и нескольких других значений времени во время в формате UTC.

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

## <a name="converting-utc-to-a-designated-time-zone"></a>Преобразование времени в формате UTC в заданный часовой пояс

Чтобы преобразовать время в формате UTC в местное, см. информацию в разделе [Преобразование времени в формате UTC в местное время](#converting-utc-to-local-time). 

Чтобы преобразовать время в формате UTC во время в любом часовом поясе, вызовите метод [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx). 

> [!IMPORTANT]
> В настоящее время метод "TimeZoneInfo.ConvertTimeFromUtc" недоступен в .NET Core. 

Этот метод принимает два параметра:

* Время в формате UTC, которое требуется преобразовать. Оно должно быть значением [DateTime](xref:System.DateTime), свойству [Kind](xref:System.DateTime.Kind) которого присвоено значение [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) или значение [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified). 

* Часовой пояс, в который требуется преобразовать время в формате UTC. 

Следующий код преобразует время в формате UTC в центральное стандартное время.

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

## <a name="converting-utc-to-local-time"></a>Преобразование времени в формате UTC в местное время

Чтобы преобразовать время в формате UTC в местное время, вызовите метод [DateTime.ToLocalTime](xref:System.DateTime) объекта [DateTime](xref:System.DateTime), время которого требуется преобразовать. Точное поведение метода зависит от значения свойства объекта [Kind](xref:System.DateTime.Kind), как показано в следующей таблице.

Свойство [DateTime.Kind](xref:System.DateTimeKind) | Преобразование
---------------------------------------------------------------------------------------------- | ----------
[DateTimeKind.Local](xref:System.DateTimeKind.Local) | Возвращает неизмененное значение [DateTime](xref:System.DateTime).
[DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) | Предполагает, что значение [DateTime](xref:System.DateTime) является временем в формате UTC и преобразует UTC в местное время.
[DateTimeKind.Utc](xref:System.DateTimeKind.Utc) | Преобразует значение [DateTime](xref:System.DateTime) в местное время.

## <a name="converting-between-any-two-time-zones"></a>Преобразование между любыми двумя часовыми поясами

Можно преобразовать время между любыми двумя часовыми поясами с помощью static метода класса [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)). Параметрами этого метода являются значение [DateTime](xref:System.DateTime), которое требуется преобразовать, объект [TimeZoneInfo](xref:System.TimeZoneInfo), представляющий часовой пояс значения даты и времени, и объект [TimeZoneInfo](xref:System.TimeZoneInfo), представляющий часовой пояс, к которому требуется преобразовать значение даты и времени.

Для этого метода требуется, чтобы свойство [Kind](xref:System.DateTime.Kind) значения даты и времени, которое требуется преобразовать, соответствовало объекту [TimeZoneInfo](xref:System.TimeZoneInfo) или идентификатору часового пояса, представляющего его часовой пояс. В противном случае возникает исключение [ArgumentException](xref:System.ArgumentException). Например, если свойством [Kind](xref:System.DateTime.Kind) значения даты и времени является [DateTimeKind.Local](xref:System.DateTimeKind.Local), то исключение возникнет в том случае, если объект [TimeZoneInfo](xref:System.TimeZoneInfo), который передан в качестве параметра метода, не равен [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local). Также исключение возникнет в том случае, если идентификатор, переданный в качестве параметра метода, не равен [TimeZoneInfo.Local.Id](xref:System.TimeZoneInfo.Id).

В следующем примере используется метод [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) для преобразования из гавайского стандартного времени в местное время.

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

## <a name="converting-datetimeoffset-values"></a>Преобразование значений DateTimeOffset

Значения даты и времени, представленные объектами [System.DateTimeOffset](xref:System.DateTimeOffset), не соответствуют полностью часовым поясам, так как при создании этот объект не связан с часовым поясом. Однако во многих случаях приложению достаточно преобразовать дату и время на основе двух различных значений смещения относительно времени в формате UTC, а не на основе времени конкретных часовых поясов. Чтобы выполнить это преобразование, можно вызвать метод [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) текущего экземпляра. Единственным параметром данного метода является [TimeSpan](xref:System.TimeSpan), который представляет собой смещение нового значения даты и времени, которое возвращает этот метод.  

Например, если дата и время запроса пользователя к веб-странице известны и сериализованы в виде строки в формате мм/дд/гггг чч:мм:сс zzzz, то следующий метод `ReturnTimeOnServer` преобразует это значение даты и времени в значение даты и времени на веб-сервере.

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

Если методу передается строка "9/1/2007 5:32:07 -05:00", которая представляет дату и время в часовом поясе, который раньше пояса UTC на пять часов, он возвращает строку "9/1/2007 3:32:07 -07:00" для сервера, расположенного в тихоокеанском стандартном часовом поясе США.

Класс [TimeZoneInfo](xref:System.TimeZoneInfo) также содержит перегрузку метода [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)), который выполняет преобразование часовых поясов со значениями [System.DateTimeOffset](xref:System.DateTimeOffset). Параметрами данного метода являются значение [System.DateTimeOffset](xref:System.DateTimeOffset) и ссылка на часовой пояс, к которому требуется преобразовать время. Этот метод возвращает значение [System.DateTimeOffset](xref:System.DateTimeOffset). Например, метод `ReturnTimeOnServer` в предыдущем примере может быть переписан для вызова метода [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)).

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

## <a name="see-also"></a>См. также

[TimeZoneInfo](xref:System.TimeZoneInfo)

[Даты, время и часовые пояса](index.md)

[Поиск часового пояса, заданного в локальной системе](finding-the-time-zones-on-local-system.md)





<!--HONumber=Nov16_HO1-->


