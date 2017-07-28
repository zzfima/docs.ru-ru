---
title: "Преобразование времени из одного часового пояса в другой | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "преобразование времени"
  - "преобразование локального времени"
  - "часовые пояса [платформа .NET Framework], преобразования"
  - "времена [платформа .NET Framework], преобразование"
  - "время в формате UTC, преобразование"
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Преобразование времени из одного часового пояса в другой
Обработка различий между часовыми поясами становится все более важной для всех приложений, которые работают с датами и временем.  При работе приложения нельзя предполагать, что все значения времени могут быть выражены по местному времени, которое доступно из структуры <xref:System.DateTime>.  Например, веб\-страница, которая отображает текущее время в восточной части США, будет содержать недостоверные сведения для пользователей в восточной Азии.  В этом разделе объясняется, как преобразовать время из одного часового пояса в другой, а также как преобразовать значения <xref:System.DateTimeOffset> с ограниченной поддержкой часовых поясов.  
  
## Преобразование во время в формате UTC  
 Время в формате UTC — это высокоточный, атомарный стандарт времени.  Часовые пояса выражаются как положительные или отрицательные смещения относительно времени в формате UTC.  Таким образом, время в формате UTC предоставляет тип времени свободного от часовых поясов или нейтрального времени часового пояса.  Использование времени в формате UTC рекомендовано, когда важна совместимость даты и времени между компьютерами. \(Дополнительные сведения и рекомендации по использованию даты и времени содержатся в разделе [Рекомендации по использованию DateTime в платформе .NET Framework](http://go.microsoft.com/fwlink/?LinkId=92342).\) Преобразование отдельных часовых поясов во время в формате UTC упрощает сравнение времен.  
  
> [!NOTE]
>  Можно сериализовать структуру <xref:System.DateTimeOffset> для однозначного представления одного момента времени.  Поскольку объекты <xref:System.DateTimeOffset> хранят значение даты и времени вместе с его смещением относительно времени в формате UTC, то они всегда представляют определенный момент времени по отношению ко времени UTC.  
  
 Самым простым способом преобразования времени в формате UTC является вызов `static` \(`Shared` в Visual Basic\) метода <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName>.  Точное преобразование, выполненное этим методом, зависит от значения свойства <xref:System.DateTime.Kind%2A> параметра `dateTime`, как показано в следующей таблице.  
  
|Свойство DateTime.Kind|Преобразование|  
|----------------------------|--------------------|  
|<xref:System.DateTimeKind?displayProperty=fullName>|Преобразовывает местное время во время в формате UTC.|  
|<xref:System.DateTimeKind?displayProperty=fullName>|Предполагает, что параметр `dateTime` является местным временем и преобразовывает местное время в UTC.|  
|<xref:System.DateTimeKind?displayProperty=fullName>|Возвращает неизмененный параметр `dateTime`.|  
  
 Следующий код преобразовывает текущее местное время во время в формате UTC и выводит результат на консоль.  
  
 [!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
 [!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]  
  
> [!NOTE]
>  Метод <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName> не обязательно возвращает результаты, которые совпадают с результатами методов <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=fullName> и <xref:System.DateTime.ToUniversalTime%2A?displayProperty=fullName>.  Если местный часовой пояс на локальной системе содержит несколько правил коррекции, то метод <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName> применяет соответствующее правило к конкретным дате и времени.  Два других метода всегда применяют последнее правило коррекции.  
  
 Если значение даты и времени не представляет местное время или время в формате UTC, то метод <xref:System.DateTime.ToUniversalTime%2A> скорее всего вернет ошибочный результат.  Однако можно использовать метод <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=fullName> для преобразования даты и времени из заданного часового пояса. \(Дополнительные сведения о получении объекта <xref:System.TimeZoneInfo>, который представляет часовой пояс назначения, см. в разделе [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).\) В следующем коде используется метод <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=fullName> для преобразования восточного стандартного времени в UTC.  
  
 [!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
 [!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]  
  
 Обратите внимание, что этот метод создает исключение <xref:System.ArgumentException>, если свойство <xref:System.DateTime.Kind%2A> объекта <xref:System.DateTime> не совпадает с часовым поясом.  Несоответствие возникает, если свойство <xref:System.DateTime.Kind%2A> задано как <xref:System.DateTimeKind?displayProperty=fullName>, а объект <xref:System.TimeZoneInfo> не представляет местный часовой пояс, или если свойство <xref:System.DateTime.Kind%2A> задано как <xref:System.DateTimeKind?displayProperty=fullName>, а объект <xref:System.TimeZoneInfo> не равен <xref:System.DateTimeKind?displayProperty=fullName>.  
  
 Все эти методы принимают значения <xref:System.DateTime> в качестве параметров и возвращают значение <xref:System.DateTime>.  Для значений <xref:System.DateTimeOffset> в структуре <xref:System.DateTimeOffset> используется метод экземпляра <xref:System.DateTimeOffset.ToUniversalTime%2A>, который преобразует дату и время текущего экземпляра в UTC.  В следующем примере вызывается метод <xref:System.DateTimeOffset.ToUniversalTime%2A> для преобразования местного времени и нескольких других значений времени во время в формате UTC.  
  
 [!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
 [!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]  
  
## Преобразование времени в формате UTC в заданный часовой пояс  
 Чтобы преобразовать время UTC в местное время, см. следующий далее раздел "Преобразование времени UTC в местное время".  Чтобы преобразовать время в формате UTC во время в любом часовом поясе, вызовите метод <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>.  Этот метод принимает два параметра:  
  
-   Время в формате UTC, которое требуется преобразовать.  Оно должно быть значением <xref:System.DateTime>, свойству <xref:System.DateTime.Kind%2A> которого присвоено значение <xref:System.DateTimeKind?displayProperty=fullName> или значение <xref:System.DateTimeKind?displayProperty=fullName>.  
  
-   Часовой пояс, в который требуется преобразовать время в формате UTC.  
  
 Следующий код преобразует время в формате UTC в центральное стандартное время.  
  
 [!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
 [!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]  
  
## Преобразование UTC в местное время  
 Чтобы преобразовать время в формате UTC в местное время, вызовите метод <xref:System.DateTime.ToLocalTime%2A> объекта <xref:System.DateTime>, время которого требуется преобразовать.  Точное поведение метода зависит от значения свойства объекта <xref:System.DateTime.Kind%2A>, как показано в следующей таблице.  
  
|Свойство `DateTime.Kind`|Преобразование|  
|------------------------------|--------------------|  
|`DateTimeKind.Local`|Возвращает неизмененное значение <xref:System.DateTime>.|  
|`DateTimeKind.Unspecified`|Предполагает, что значение <xref:System.DateTime> является временем в формате UTC и преобразует UTC в местное время.|  
|`DateTimeKind.Utc`|Преобразует значение <xref:System.DateTime> в местное время.|  
  
 **Примечание** Метод <xref:System.TimeZone.ToLocalTime%2A?displayProperty=fullName> работает идентично методу `DateTime.ToLocalTime`.  Он принимает один параметр, являющийся значением даты и времени, которое требуется преобразовать.  
  
 Можно также преобразовать время любого часового пояса в местное время с помощью `static` \(`Shared` в Visual Basic\) метода <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=fullName>.  Этот метод рассматривается в следующем разделе.  
  
## Преобразование между любыми двумя часовыми поясами  
 Можно преобразовать время между любыми двумя часовыми поясами с помощью любого из следующих двух `static` \(`Shared` в Visual Basic\) методов класса <xref:System.TimeZoneInfo>:  
  
-   <xref:System.TimeZoneInfo.ConvertTime%2A>  
  
     Параметрами этого метода являются значение даты и времени, которое требуется преобразовать, объект `TimeZoneInfo`, представляющий часовой пояс значения даты и времени, и объект `TimeZoneInfo`, представляющий часовой пояс, к которому требуется преобразовать значение даты и времени.  
  
-   <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>  
  
     Параметрами этого метода являются значение даты и времени, которое требуется преобразовать, идентификатор часового пояса для значения даты и времени и идентификатор часового пояса, к которому требуется преобразовать значение даты и времени.  
  
 Для обоих методов требуется, чтобы свойство <xref:System.DateTime.Kind%2A> значения даты и времени, которое требуется преобразовать, соответствовало объекту <xref:System.TimeZoneInfo> или идентификатору часового пояса, представляющего его часовой пояс.  В противном случае возникает исключение <xref:System.ArgumentException>.  Например, если свойством `Kind` значения даты и времени является `DateTimeKind.Local`, то исключение возникнет в том случае, если объект `TimeZoneInfo`, который передан в качестве параметра метода, не равен `TimeZoneInfo.Local`.  Также исключение возникнет в том случае, если идентификатор, переданный в качестве параметра метода, не равен `TimeZoneInfo.Local.Id`.  
  
 В следующем примере используется метод <xref:System.TimeZoneInfo.ConvertTime%2A> для преобразования из гавайского стандартного времени в местное время.  
  
 [!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
 [!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]  
  
## Преобразование значений DateTimeOffset  
 Значения даты и времени, представленные объектами <xref:System.DateTimeOffset>, не соответствуют полностью часовым поясам, так как при создании этот объект не связан с часовым поясом.  Однако, во многих случаях приложению достаточно преобразовать дату и время на основе двух различных значений смещения относительно времени в формате UTC, а не на основе времени конкретных часовых поясов.  Чтобы выполнить это преобразование, можно вызвать метод <xref:System.DateTimeOffset.ToOffset%2A> текущего экземпляра.  Единственным параметром данного метода является смещение нового значения даты и времени, которое возвращает этот метод.  
  
 Например, если дата и время запроса пользователя к веб\-странице известны и сериализованы в виде строки в формате мм\/дд\/гггг чч:мм:сс zzzz, то следующий метод `ReturnTimeOnServer` преобразует это значение даты и времени в значение даты и времени на веб\-сервере.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
 [!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)]  
  
 Если методу передается строка "9\/1\/2007 5:32:07 \-05:00", которая представляет дату и время в часовом поясе, который раньше времени в формате UTC на пять часов, то он возвращает "9\/1\/2007 3:32:07 \-07:00" для сервера, который находится в США, в Тихоокеанской стандартной зоне времени.  
  
 Класс <xref:System.TimeZoneInfo> также содержит перегрузку метода <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName>, который выполняет преобразование часовых поясов со значениями <xref:System.DateTimeOffset>.  Параметрами данного метода являются значение <xref:System.DateTimeOffset> и ссылка на часовой пояс, к которому требуется преобразовать время.  Этот метод возвращает значение <xref:System.DateTimeOffset>.  Например, метод `ReturnTimeOnServer` в предыдущем примере может быть переписан для вызова метода <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]  
  
## См. также  
 <xref:System.TimeZoneInfo>   
 [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)   
 [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)