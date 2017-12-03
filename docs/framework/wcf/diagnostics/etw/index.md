---
title: "Аналитическое отслеживание ETW"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42683acdfe2e63d59a13496b210f83fb97c02de7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="05d1f-102">Аналитическое отслеживание ETW</span><span class="sxs-lookup"><span data-stu-id="05d1f-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="05d1f-103">В [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] аналитическая трассировка обеспечивает отслеживание диагностической информации при запуске службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05d1f-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] analytic tracing offers a way to capture diagnostic information during the execution of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="05d1f-104">Аналитические трассировки [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] представляют собой события, возникающие в ключевых точках стека [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] и позволяющие отлаживать службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="05d1f-104">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing events are emitted at key points in the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack to allow troubleshooting of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services in a production environment.</span></span> <span data-ttu-id="05d1f-105">Аналитическая трассировка [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] службы будет оказывать минимальное влияние на производительность рабочего сервера, на котором размещена [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] службы, как эти события эффективно передаются в сеанс событий трассировки для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="05d1f-105">Analytic tracing for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05d1f-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="05d1f-106">In This Section</span></span>  
 [<span data-ttu-id="05d1f-107">Общие сведения об аналитическом отслеживании</span><span class="sxs-lookup"><span data-stu-id="05d1f-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="05d1f-108">Описывает принципы работы аналитической трассировки [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] в [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05d1f-108">Discusses how [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="05d1f-109">Динамическое включение аналитического отслеживания</span><span class="sxs-lookup"><span data-stu-id="05d1f-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="05d1f-110">Описывает, как динамически включить и отключить трассировку с помощью ETW.</span><span class="sxs-lookup"><span data-stu-id="05d1f-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="05d1f-111">Настройка отслеживания потока сообщений</span><span class="sxs-lookup"><span data-stu-id="05d1f-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="05d1f-112">Описывает процесс настройки трассировки потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="05d1f-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="05d1f-113">Ссылка на событие аналитического отслеживания</span><span class="sxs-lookup"><span data-stu-id="05d1f-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="05d1f-114">Содержит таблицу идентификаторов событий с уровнями событий, сообщениями событий и ключевыми словами.</span><span class="sxs-lookup"><span data-stu-id="05d1f-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d1f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="05d1f-115">See Also</span></span>  
 [<span data-ttu-id="05d1f-116">WCF Services and Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="05d1f-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="05d1f-117">Отслеживание событий в системе трассировки событий Windows</span><span class="sxs-lookup"><span data-stu-id="05d1f-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
