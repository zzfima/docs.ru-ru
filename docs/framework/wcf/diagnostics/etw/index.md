---
title: Аналитическое отслеживание ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: cff13439995d8a90da15b7afa15723f21574e35e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193730"
---
# <a name="analytic-tracing-with-etw"></a>Аналитическое отслеживание ETW
Windows Communication Foundation (WCF) аналитическая трассировка обеспечивает отслеживание диагностической информации во время выполнения службы WCF. События аналитического отслеживания WCF, передаваемые в ключевых точках стека WCF и позволяющие отлаживать службы WCF в рабочей среде. Аналитическая трассировка для служб WCF будет оказывать минимальное влияние на производительность рабочего сервера, на котором размещена [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] службы WCF, как эти события эффективно передаются в сеанс Windows (Трассировка событий).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения об аналитическом отслеживании](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Содержит сведения о работе аналитическая трассировка WCF [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Динамическое включение аналитического отслеживания](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Описывает, как динамически включить и отключить трассировку с помощью ETW.  
  
 [Настройка отслеживания потока сообщений](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Описывает процесс настройки трассировки потока сообщений.  
  
 [Ссылка на событие аналитического отслеживания](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Содержит таблицу идентификаторов событий с уровнями событий, сообщениями событий и ключевыми словами.  
  
## <a name="see-also"></a>См. также

- [Службы WCF и трассировка событий для Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [Отслеживание событий в системе трассировки событий Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
