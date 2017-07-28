---
title: "Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов | Microsoft Docs"
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
  - "доступ к локальному часовому поясу"
  - "предопределенные часовые пояса"
  - "часовые пояса [платформа .NET Framework], локальные"
  - "часовые пояса [платформа .NET Framework], извлечение"
  - "часовые пояса [платформа .NET Framework], время в формате UTC"
  - "время в формате UTC, предопределенный"
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Доступ к предварительно определенным объектам UTC и объектам местных часовых поясов
Класс <xref:System.TimeZoneInfo> имеет свойства <xref:System.TimeZoneInfo.Utc%2A> и <xref:System.TimeZoneInfo.Local%2A>, обеспечивающие доступ к предопределенным объектам часовых поясов.  В этом разделе рассматривается порядок работы с объектами <xref:System.TimeZoneInfo>, возвращаемыми этими свойствами.  
  
### Получение объекта TimeZoneInfo времени UTC  
  
1.  Для получения времени в формате UTC следует использовать статическое \(`static`, `Shared` в языке Visual Basic\) свойство <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName>.  
  
2.  Вместо того чтобы сохранять возвращаемый этим свойством объект <xref:System.TimeZoneInfo> в объектной переменной, следует работать со временем в формате UTC с помощью свойства <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName>.  
  
### Получение местного часового пояса  
  
1.  Для получения часового пояса локальной системы следует использовать статическое \(`static`, `Shared` в языке Visual Basic\) свойство <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>.  
  
2.  Вместо того чтобы сохранять возвращаемый этим свойством объект <xref:System.TimeZoneInfo> в объектной переменной, следует работать с местным часовым поясом с помощью свойства <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>.  
  
## Пример  
 В следующем коде свойства <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> и <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName> используются для преобразования времени из восточного стандартного часового пояса США и Канады, а также для вывода названия часового пояса на консоль.  
  
 [!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
 [!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]  
  
 Вместо того чтобы сохранять местный часовой пояс в объектной переменной <xref:System.TimeZoneInfo>, работать с местным часовым поясом всегда следует через свойство <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>.  Подобным образом, вместо того чтобы сохранять часовой пояс UTC в объектной переменной <xref:System.TimeZoneInfo>, работать со временем в формате UTC всегда следует с помощью свойства <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName>.  Это исключает присвоение объектной переменной <xref:System.TimeZoneInfo> недопустимого значения при вызове метода <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName>.  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Чтобы ссылка на System.Core.dll была добавлена в проект.  
  
-   Чтобы пространство имен <xref:System> было импортировано с помощью оператора `using` \(обязательно в коде C\#\).  
  
## См. также  
 [Даты, время и часовые пояса](../../../docs/standard/datetime/index.md)   
 [Поиск часового пояса, заданного в локальной системе](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)   
 [Практическое руководство. Создание экземпляра объекта TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)