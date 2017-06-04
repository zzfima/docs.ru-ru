---
title: "Практическое руководство. Создание экземпляра объекта TimeZoneInfo | Microsoft Docs"
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
  - "создание экземпляров объектов часовых поясов"
  - "объекты часовых поясов [платформа .NET Framework], создание экземпляра"
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание экземпляра объекта TimeZoneInfo
Наиболее распространенный способ создания экземпляра объекта <xref:System.TimeZoneInfo> — получение сведений о нем из реестра. В этом разделе описываются способы создания экземпляра объекта <xref:System.TimeZoneInfo> на основе локального системного реестра.  
  
### Создание экземпляра объекта TimeZoneInfo  
  
1.  Объявите объект <xref:System.TimeZoneInfo>.  
  
2.  Вызовите метод `static` \(`Shared` в Visual Basic\) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=fullName>.  
  
3.  Обработайте исключения, созданные этим методом, особенно <xref:System.TimeZoneNotFoundException>, создаваемое, если в реестре не определен часовой пояс.  
  
## Пример  
 Следующий код извлекает объект <xref:System.TimeZoneInfo>, который представляет часовой пояс восточного времени США, и отображает время в этом поясе, соответствующее местному времени.  
  
 [!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
 [!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]  
  
 Единственный параметр метода <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=fullName> — идентификатор часового пояса, который необходимо получить и который соответствует свойству <xref:System.TimeZoneInfo.Id%2A?displayProperty=fullName> объекта. Идентификатор часового пояса — это важнейшее поле, которое уникально идентифицирует часовой пояс. Несмотря на то что большинство ключей являются относительно короткими, идентификатор часового пояса относительно длинный. В большинстве случаев его значение соответствует свойству <xref:System.TimeZoneInfo.StandardName%2A> объекта <xref:System.TimeZoneInfo>, которое используется для предоставления имени стандартного времени часового пояса. Однако существуют исключения. Лучше всего гарантировать, что передается действительный идентификатор, путем перечисления доступных в системе часовых поясов и отслеживания присутствующих в них идентификаторов часовых поясов. Пример см. в разделе [Практическое руководство. Перечисление присутствующих на компьютере часовых поясов](../../../docs/standard/datetime/enumerate-time-zones.md). Раздел [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) также содержит список идентификаторов избранных часовых поясов.  
  
 Если часовой пояс найден, метод возвращает его объект <xref:System.TimeZoneInfo>.  Если часовой пояс не найден, метод создает <xref:System.TimeZoneNotFoundException>. Если часовой пояс найден, но его данные повреждены или неполны, метод создает <xref:System.InvalidTimeZoneException>.  
  
 Если приложение зависит от наличия часового пояса, необходимо сначала вызвать метод <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> для извлечения сведений о часовом поясе из реестра. Если вызов метода завершится сбоем, обработчик исключений должен создать новый экземпляр часового пояса или повторно создать его путем десериализации сериализованного объекта <xref:System.TimeZoneInfo>. Пример см. в разделе [Практическое руководство. Восстановление часовых поясов из внедренного ресурса](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
  
## См. также  
 [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)   
 [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)   
 [Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов](../../../docs/standard/datetime/access-utc-and-local.md)