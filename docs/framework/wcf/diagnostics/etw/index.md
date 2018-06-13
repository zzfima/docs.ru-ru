---
title: Аналитическое отслеживание ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 210418b8a8765a1fc59658e9df57c92ce087c95f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809268"
---
# <a name="analytic-tracing-with-etw"></a>Аналитическое отслеживание ETW
Windows Communication Foundation (WCF) аналитическая трассировка обеспечивает отслеживание диагностической информации во время выполнения службы WCF. События аналитического отслеживания WCF передаются в ключевых точках стека WCF и позволяющие отлаживать службы WCF в рабочей среде. Аналитическая трассировка служб WCF не влияли на производительность рабочего сервера, на котором размещена [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] службы WCF, как эти события эффективно передаются в сеанс событий трассировки для Windows (ETW).  
  
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
 [Службы WCF и трассировка событий для Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [Отслеживание событий в системе трассировки событий Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
