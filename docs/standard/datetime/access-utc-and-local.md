---
title: "Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов"
description: "Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 13454d47-d957-421b-9ecd-940058b8835e
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: fcc48e40cdad25c6142dbc3a86513b816378fa4b
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов

Класс [System.TimeZoneInfo](xref:System.TimeZoneInfo) имеет свойства `Utc` и `Local`, обеспечивающие доступ к предопределенным объектам часовых поясов. В этом разделе рассматривается порядок работы с объектами `TimeZoneInfo`, возвращаемыми этими свойствами.

## <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Получение объекта TimeZoneInfo времени UTC

1. Для получения времени в формате UTC следует использовать статическое (**static**, **Shared** в языке Visual Basic) свойство [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc).

2. Вместо того чтобы сохранять возвращаемый этим свойством объект [TimeZoneInfo](xref:System.TimeZoneInfo) в объектной переменной, следует работать со временем в формате UTC с помощью свойства [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc).


## <a name="to-access-the-local-time-zone"></a>Получение местного часового пояса

1. Для получения часового пояса локальной системы следует использовать статическое (**static**, **Shared** в языке Visual Basic) свойство [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).

2. Вместо того чтобы сохранять возвращаемый этим свойством объект [TimeZoneInfo](xref:System.TimeZoneInfo) в объектной переменной, следует работать с местным часовым поясом с помощью свойства [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).

## <a name="example"></a>Пример

В следующем коде свойства [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) и [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.

```csharp
// Create Eastern Standard Time value and TimeZoneInfo object      
DateTime estTime = new DateTime(2007, 1, 1, 00, 00, 00);
string timeZoneName = "Eastern Standard Time";
try
{
   TimeZoneInfo est = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName);

   // Convert EST to local time
   DateTime localTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local);
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", 
           estTime, 
           est, 
           localTime, 
           TimeZoneInfo.Local.IsDaylightSavingTime(localTime) ?
                     TimeZoneInfo.Local.DaylightName : 
                     TimeZoneInfo.Local.StandardName);

   // Convert EST to UTC
   DateTime utcTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc);
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", 
           estTime, 
           est, 
           utcTime, 
           TimeZoneInfo.Utc.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The {0} zone cannot be found in the registry.", 
                     timeZoneName);
}
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The registry contains invalid data for the {0} zone.", 
                     timeZoneName);
}
```

```vb
' Create Eastern Standard Time value and TimeZoneInfo object      
Dim estTime As Date = #01/01/2007 00:00:00#
Dim timeZoneName As String = "Eastern Standard Time"
Try
   Dim est As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName)

   ' Convert EST to local time
   Dim localTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local)
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", _
           estTime, _
           est, _
           localTime, _
           IIf(TimeZoneInfo.Local.IsDaylightSavingTime(localTime), _
               TimeZoneInfo.Local.DaylightName, _
               TimeZoneInfo.Local.StandardName))

   ' Convert EST to UTC
   Dim utcTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc)
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", _
           estTime, _
           est, _
           utcTime, _
           TimeZoneInfo.Utc.StandardName)
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The {0} zone cannot be found in the registry.", _
                     timeZoneName)
Catch e As InvalidTimeZoneException
   Console.WriteLine("The registry contains invalid data for the {0} zone.", _
                     timeZoneName)
End Try
```

Вместо того чтобы сохранять местный часовой пояс в объектной переменной [TimeZoneInfo](xref:System.TimeZoneInfo), работать с местным часовым поясом всегда следует через свойство [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local). Подобным образом, вместо того чтобы сохранять часовой пояс UTC в объектной переменной [TimeZoneInfo](xref:System.TimeZoneInfo), работать со временем в формате UTC всегда следует с помощью свойства [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc). Это исключает присвоение объектной переменной [TimeZoneInfo](xref:System.TimeZoneInfo) недопустимого значения при вызове внешнего метода.


## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](index.md)

[Поиск часового пояса, заданного в локальной системе](finding-the-time-zones-on-local-system.md)

