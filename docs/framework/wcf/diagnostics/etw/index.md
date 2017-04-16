---
title: "Analytic Tracing with ETW | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "diagnostics [WCF], analytic tracing"
  - "administration [WCF], analytic tracing"
  - "analytic tracing [WCF]"
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Analytic Tracing with ETW
В [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] аналитическая трассировка обеспечивает отслеживание диагностической информации при запуске службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].Аналитические трассировки [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] представляют собой события, возникающие в ключевых точках стека [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] и позволяющие отлаживать службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] в рабочей среде.Аналитическая трассировка служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] в минимальной степени влияет на производительность рабочего сервера, где размещены службы [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], поскольку эти события эффективно передаются в сеанс трассировки событий для Windows.  
  
## В этом подразделе  
 [Общие сведения об аналитическом отслеживании](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Описывает принципы работы аналитической трассировки в [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)][!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Динамическое включение аналитического отслеживания](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Описывает, как динамически включить и отключить трассировку с помощью ETW.  
  
 [Настройка отслеживания потока сообщений](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Описывает процесс настройки трассировки потока сообщений.  
  
 [Ссылка на событие аналитического отслеживания](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Содержит таблицу идентификаторов событий с уровнями событий, сообщениями событий и ключевыми словами.  
  
## См. также  
 [Службы WCF и средство отслеживания событий для Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)   
 [Отслеживание событий в системе трассировки событий Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)