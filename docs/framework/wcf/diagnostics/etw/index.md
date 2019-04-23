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
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="e1710-102">Аналитическое отслеживание ETW</span><span class="sxs-lookup"><span data-stu-id="e1710-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="e1710-103">Windows Communication Foundation (WCF) аналитическая трассировка обеспечивает отслеживание диагностической информации во время выполнения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="e1710-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="e1710-104">События аналитического отслеживания WCF, передаваемые в ключевых точках стека WCF и позволяющие отлаживать службы WCF в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="e1710-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="e1710-105">Аналитическая трассировка для служб WCF будет оказывать минимальное влияние на производительность рабочего сервера, на котором размещена [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] службы WCF, как эти события эффективно передаются в сеанс Windows (Трассировка событий).</span><span class="sxs-lookup"><span data-stu-id="e1710-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1710-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e1710-106">In This Section</span></span>  
 [<span data-ttu-id="e1710-107">Общие сведения об аналитическом отслеживании</span><span class="sxs-lookup"><span data-stu-id="e1710-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="e1710-108">Содержит сведения о работе аналитическая трассировка WCF [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1710-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="e1710-109">Динамическое включение аналитического отслеживания</span><span class="sxs-lookup"><span data-stu-id="e1710-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="e1710-110">Описывает, как динамически включить и отключить трассировку с помощью ETW.</span><span class="sxs-lookup"><span data-stu-id="e1710-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="e1710-111">Настройка отслеживания потока сообщений</span><span class="sxs-lookup"><span data-stu-id="e1710-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="e1710-112">Описывает процесс настройки трассировки потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="e1710-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="e1710-113">Ссылка на событие аналитического отслеживания</span><span class="sxs-lookup"><span data-stu-id="e1710-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="e1710-114">Содержит таблицу идентификаторов событий с уровнями событий, сообщениями событий и ключевыми словами.</span><span class="sxs-lookup"><span data-stu-id="e1710-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1710-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e1710-115">See also</span></span>

- [<span data-ttu-id="e1710-116">Службы WCF и трассировка событий для Windows</span><span class="sxs-lookup"><span data-stu-id="e1710-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="e1710-117">Отслеживание событий в системе трассировки событий Windows</span><span class="sxs-lookup"><span data-stu-id="e1710-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
