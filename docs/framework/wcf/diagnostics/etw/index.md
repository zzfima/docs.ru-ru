---
title: Аналитическое отслеживание ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: a0e3e3d27283e588b161e2209c5a682558d18f79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="analytic-tracing-with-etw"></a>Аналитическое отслеживание ETW
Windows Communication Foundation (WCF) аналитическая трассировка обеспечивает отслеживание диагностической информации во время выполнения [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] службы. Аналитические трассировки [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] представляют собой события, возникающие в ключевых точках стека [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] и позволяющие отлаживать службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] в рабочей среде. Аналитическая трассировка [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] службы будет оказывать минимальное влияние на производительность рабочего сервера, на котором размещена [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] службы, как эти события эффективно передаются в сеанс событий трассировки для Windows (ETW).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения об аналитическом отслеживании](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Описывает принципы работы аналитической трассировки [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] в [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Динамическое включение аналитического отслеживания](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Описывает, как динамически включить и отключить трассировку с помощью ETW.  
  
 [Настройка отслеживания потока сообщений](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Описывает процесс настройки трассировки потока сообщений.  
  
 [Ссылка на событие аналитического отслеживания](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Содержит таблицу идентификаторов событий с уровнями событий, сообщениями событий и ключевыми словами.  
  
## <a name="see-also"></a>См. также  
 [Службы WCF и трассировка событий для Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [Отслеживание событий в системе трассировки событий Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
