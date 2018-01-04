---
title: "Использование трассировки для устранения неполадок приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7676b9bb-cbd1-41fd-9a93-cc615af6e2d0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb46ad5fe95405c78baf3173a982969e0e7092fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-tracing-to-troubleshoot-your-application"></a><span data-ttu-id="5a8a0-102">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="5a8a0-102">Using Tracing to Troubleshoot Your Application</span></span>
<span data-ttu-id="5a8a0-103">Содержит разделы, посвященные использованию трассировки для устранения неполадок приложений.</span><span class="sxs-lookup"><span data-stu-id="5a8a0-103">This section contains various topics that describe how you can use tracing to troubleshoot your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a8a0-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5a8a0-104">In This Section</span></span>  
 [<span data-ttu-id="5a8a0-105">Рекомендуемые параметры для трассировки и ведения журналов сообщений</span><span class="sxs-lookup"><span data-stu-id="5a8a0-105">Recommended Settings for Tracing and Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md)  
 <span data-ttu-id="5a8a0-106">Описание рекомендуемых настроек рабочей среды и среды отладки.</span><span class="sxs-lookup"><span data-stu-id="5a8a0-106">Describes suggested settings for production and debugging environments.</span></span>  
  
 [<span data-ttu-id="5a8a0-107">Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="5a8a0-107">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 <span data-ttu-id="5a8a0-108">Описание использования средства просмотра трассировки службы для просмотра, определения взаимосвязей и анализа данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="5a8a0-108">Describes how you can use the Service Trace Viewer tool to view, correlate and analyze trace data.</span></span>  
  
 [<span data-ttu-id="5a8a0-109">Значимые трассировки</span><span class="sxs-lookup"><span data-stu-id="5a8a0-109">Significant Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/significant-traces.md)  
 <span data-ttu-id="5a8a0-110">Список основных трассировок, создаваемых в [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a8a0-110">A list of major traces emitted by [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="5a8a0-111">Отладка в клиенте</span><span class="sxs-lookup"><span data-stu-id="5a8a0-111">Debugging on the Client</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/debugging-on-the-client.md)  
 <span data-ttu-id="5a8a0-112">Позволяет отлаживать приложение на клиентах.</span><span class="sxs-lookup"><span data-stu-id="5a8a0-112">Enables clients to debug your application.</span></span>  
  
 [<span data-ttu-id="5a8a0-113">Сценарии сквозной трассировки</span><span class="sxs-lookup"><span data-stu-id="5a8a0-113">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 <span data-ttu-id="5a8a0-114">Описание трассировок, используемых в сценариях E2E [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], например, в синхронных запросах-ответах wsHttp и асинхронных односторонних TCP-запросах.</span><span class="sxs-lookup"><span data-stu-id="5a8a0-114">Describes traces used for E2E [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] scenarios, for example, synchronous wsHttp request-replies, and asynchronous TCP one-way requests.</span></span>  
  
 [<span data-ttu-id="5a8a0-115">Создание трассировки пользовательского кода</span><span class="sxs-lookup"><span data-stu-id="5a8a0-115">Emitting User-Code Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)  
 <span data-ttu-id="5a8a0-116">Описание способа программной выдачи трассировок в пользовательском коде, что позволяет заранее создавать данные инструментирования для их последующего использования в диагностических целях совместно с трассировками WCF.</span><span class="sxs-lookup"><span data-stu-id="5a8a0-116">Describes how to emit traces programmatically in user code, so that you can proactively create instrumentation data to be used later for diagnostic purpose, and in correlation with WCF traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a8a0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5a8a0-117">See Also</span></span>  
 [<span data-ttu-id="5a8a0-118">Средство просмотра трассировки служб (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="5a8a0-118">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [<span data-ttu-id="5a8a0-119">Трассировка</span><span class="sxs-lookup"><span data-stu-id="5a8a0-119">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="5a8a0-120">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="5a8a0-120">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
