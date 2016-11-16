---
title: "Практическое руководство. Разрешение проблемы неоднозначности времени"
description: "Практическое руководство. Разрешение проблемы неоднозначности времени"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e86050c6-d16d-405e-8bba-7205945c9a81
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: e4e62607fd1bd3b4cee3e23a5863e1ba9e25ab03

---

# <a name="how-to-resolve-ambiguous-times"></a>Практическое руководство. Разрешение проблемы неоднозначности времени

Неоднозначное время — это время, которое соответствует более чем одному значению времени в формате UTC. Это происходит, когда часы переводятся назад, как при переходе в одном часовом поясе с летнего времени на его стандартное время. При обработке неоднозначного времени можно выполнить одно из следующих действий:

* Сделать предположение о том, насколько время соответствует времени в формате UTC. Например, можно предположить, что неоднозначное время всегда выражается в стандартном времени часового пояса.

* Если неоднозначное время является элементом данных, введенных пользователем, то можно предложить пользователю устранить неоднозначность.

В этом разделе показано, как устранить неоднозначное время, предполагая, что оно представляет собой стандартное время часового пояса.

## <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Сопоставление неоднозначного времени стандартному времени часового пояса

1. Вызовите метод [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) или [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)), чтобы определить, является ли время неоднозначным.

2. Если время является неоднозначным, вычитайте время из объекта [TimeSpan](xref:System.TimeSpan), возвращаемого свойством часового пояса [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset).

3. Вызовите метод `static` (`Shared` в Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)), чтобы задать значение даты и времени в формате UTC для свойства [Kind](xref:System.DateTime.Kind) равным [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).

## <a name="example"></a>Пример

В следующем примере показано, как преобразовать неоднозначное время [DateTime](xref:System.DateTime) в формат UTC, предполагая, что оно представляет собой местное время часового пояса. 

```csharp
private DateTime ResolveAmbiguousTime(DateTime ambiguousTime)
{
   // Time is not ambiguous
   if (! TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime))
   { 
      return ambiguousTime; 
   }
   // Time is ambiguous
   else
   {
      DateTime utcTime = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, 
                                              DateTimeKind.Utc);      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", 
                        ambiguousTime, utcTime, utcTime.Kind.ToString());
      return utcTime;            
   }   
}
```

```vb
Private Function ResolveAmbiguousTime(ambiguousTime As Date) As Date
   ' Time is not ambiguous
   If Not TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime) Then 
      Return TimeZoneInfo.ConvertTimeToUtc(ambiguousTime) 
   ' Time is ambiguous
   Else
      Dim utcTime As Date = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, DateTimeKind.Utc)      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", ambiguousTime, utcTime, utcTime.Kind.ToString())
      Return utcTime            
   End If   
End Function
```

Пример состоит из метода с именем `ResolveAmbiguousTime`, который определяет, является ли значение [DateTime](xref:System.DateTime), переданное в него, неоднозначным. Если значение является неоднозначным, то метод возвращает значение [DateTime](xref:System.DateTime), представляющее собой соответствующее время в формате UTC. Метод обрабатывает это преобразование путем вычитания значения свойства [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) местного часового пояса из локального времени. 

Как правило, неоднозначное время обрабатывается вызовом метода [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) для извлечения массива объектов [TimeSpan](xref:System.TimeSpan), содержащих возможные смещения неоднозначного времени относительно UTC. Однако в этом примере происходит произвольное предположение, что неоднозначное время следует всегда сопоставлять со стандартным временем часового пояса. Свойство [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) возвращает смещение между временем по UTC и временем стандартного часового пояса.

## <a name="see-also"></a>См. также

[Даты, время и часовые пояса](index.md)

[Практическое руководство. Предоставление пользователям возможности разрешения неоднозначности времени](let-users-resolve-ambiguous-times.md)




<!--HONumber=Nov16_HO1-->


