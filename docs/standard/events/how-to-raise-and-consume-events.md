---
title: "Практическое руководство. Вызов и прием событий | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "события [платформа .NET Framework], возникновение"
  - "события [платформа .NET Framework], примеры"
  - "создание событий"
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Вызов и прием событий
В примерах этого раздела показано, как работать с событиями.  Сюда входят примеры делегата <xref:System.EventHandler>, делегата <xref:System.EventHandler%601> и пользовательского делегата, чтобы проиллюстрировать события как c данными, так и без.  
  
 В примерах используются понятия, описанные в статье [События](../../../docs/standard/events/index.md).  
  
## Пример  
 В первом примере показано, как вызывать и получать событие, которое не содержит данные.  Он содержит класс `Counter` с именем события `ThresholdReached`.  Это событие возникает, когда значение счетчика больше либо равно порогового значения.  Делегат <xref:System.EventHandler> связан с событием, потому что данные события не предоставляются.  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## Пример  
 В следующем примере показано, вызывать и получать событие, которое предоставляет данные.  Делегат <xref:System.EventHandler%601> связан с событием и предоставляется экземпляр объекта данных пользовательского события.  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## Пример  
 В следующем примере показано объявление делегата для события.  Делегат назван `ThresholdReachedEventHandler`.  \(Это всего лишь пример.  Как правило, нет необходимости объявлять делегат для события, поскольку можно использовать или <xref:System.EventHandler> или делегат <xref:System.EventHandler%601>.  Объявлять делегат необходимо только в редких случаях, например, делая класс доступным коду прежних версий, который не может использовать универсальные шаблоны.  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## См. также  
 [События](../../../docs/standard/events/index.md)