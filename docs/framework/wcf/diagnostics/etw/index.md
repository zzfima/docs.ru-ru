---
title: Аналитическое отслеживание ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: dd745730ca186b9489c547f790c546e95bf96372
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798088"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="0107c-102">Аналитическое отслеживание ETW</span><span class="sxs-lookup"><span data-stu-id="0107c-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="0107c-103">Аналитическая трассировка Windows Communication Foundation (WCF) предоставляет способ сбора диагностических сведений во время выполнения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="0107c-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="0107c-104">События аналитической трассировки WCF создаются в ключевых точках стека WCF, чтобы разрешить устранение неполадок служб WCF в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="0107c-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="0107c-105">Аналитическая трассировка служб WCF оказывает минимальное влияние на производительность сервера продукта, на котором размещены [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] службы WCF, так как эти события очень эффективны в сеансе трассировки событий для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="0107c-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0107c-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0107c-106">In This Section</span></span>  
 [<span data-ttu-id="0107c-107">Общие сведения об аналитическом отслеживании</span><span class="sxs-lookup"><span data-stu-id="0107c-107">Analytic Tracing Overview</span></span>](analytic-tracing-overview.md)  
 <span data-ttu-id="0107c-108">Описывает [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)], как работает аналитическая трассировка WCF.</span><span class="sxs-lookup"><span data-stu-id="0107c-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="0107c-109">Динамическое включение аналитического отслеживания</span><span class="sxs-lookup"><span data-stu-id="0107c-109">Dynamically Enabling Analytic Tracing</span></span>](dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="0107c-110">Описывает, как динамически включить и отключить трассировку с помощью ETW.</span><span class="sxs-lookup"><span data-stu-id="0107c-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="0107c-111">Настройка отслеживания потока сообщений</span><span class="sxs-lookup"><span data-stu-id="0107c-111">Configuring Message Flow Tracing</span></span>](configuring-message-flow-tracing.md)  
 <span data-ttu-id="0107c-112">Описывает процесс настройки трассировки потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="0107c-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="0107c-113">Ссылка на событие аналитического отслеживания</span><span class="sxs-lookup"><span data-stu-id="0107c-113">Analytic Trace Event Reference</span></span>](analytic-trace-event-reference.md)  
 <span data-ttu-id="0107c-114">Содержит таблицу идентификаторов событий с уровнями событий, сообщениями событий и ключевыми словами.</span><span class="sxs-lookup"><span data-stu-id="0107c-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0107c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0107c-115">See also</span></span>

- [<span data-ttu-id="0107c-116">Службы WCF и трассировка событий для Windows</span><span class="sxs-lookup"><span data-stu-id="0107c-116">WCF Services and Event Tracing for Windows</span></span>](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="0107c-117">Отслеживание событий в системе трассировки событий Windows</span><span class="sxs-lookup"><span data-stu-id="0107c-117">Tracking Events into Event Tracing in Windows</span></span>](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
