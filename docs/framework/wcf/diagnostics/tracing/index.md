---
title: "Трассировка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e0a291e3ca277bc58f69b8016c523b383b3cece8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="tracing"></a><span data-ttu-id="ffc91-102">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ffc91-102">Tracing</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="ffc91-103"> предоставляет данные инструментирования приложений и диагностические данные для мониторинга и анализа сбоев.</span><span class="sxs-lookup"><span data-stu-id="ffc91-103"> provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="ffc91-104">Трассировку можно использовать вместо отладчика для понимания того, как ведет себя приложение или почему оно дает сбои.</span><span class="sxs-lookup"><span data-stu-id="ffc91-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="ffc91-105">Можно также устанавливать корреляцию между сбоями и обработкой, выполняемой различными компонентами, для сквозного анализа работы приложения.</span><span class="sxs-lookup"><span data-stu-id="ffc91-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="ffc91-106"> выдает следующие данные для диагностической трассировки:</span><span class="sxs-lookup"><span data-stu-id="ffc91-106"> outputs the following data for diagnostic tracing:</span></span>  
  
-   <span data-ttu-id="ffc91-107">Трассировки основных этапов процесса по всем компонентам приложений, таких как вызовы операций, исключения кода, предупреждения и прочие значительные события обработки.</span><span class="sxs-lookup"><span data-stu-id="ffc91-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
-   <span data-ttu-id="ffc91-108">События ошибок Windows при сбоях возможности трассировки.</span><span class="sxs-lookup"><span data-stu-id="ffc91-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ffc91-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="ffc91-109">In This Section</span></span>  
 [<span data-ttu-id="ffc91-110">Настройка трассировки</span><span class="sxs-lookup"><span data-stu-id="ffc91-110">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
 <span data-ttu-id="ffc91-111">В этом разделе описывается, как настраивать трассировку на разных уровнях в соответствии с конкретными потребностями.</span><span class="sxs-lookup"><span data-stu-id="ffc91-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="ffc91-112">End-to-End трассировки</span><span class="sxs-lookup"><span data-stu-id="ffc91-112">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)  
  
 <span data-ttu-id="ffc91-113">В этом разделе описывается использование распространения и трассировки действий для сквозной корреляции, полезной при отладке.</span><span class="sxs-lookup"><span data-stu-id="ffc91-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="ffc91-114">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ffc91-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="ffc91-115">В этом разделе описывается использование трассировки для отладки приложения.</span><span class="sxs-lookup"><span data-stu-id="ffc91-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="ffc91-116">Вопросы безопасности и полезные советы при трассировке</span><span class="sxs-lookup"><span data-stu-id="ffc91-116">Security Concerns and Useful Tips for Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="ffc91-117">В этом разделе описываются способы защиты конфиденциальных сведений от раскрытия, а также приводятся полезные советы по использованию WebHost.</span><span class="sxs-lookup"><span data-stu-id="ffc91-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="ffc91-118">Справочные сведения о трассировке</span><span class="sxs-lookup"><span data-stu-id="ffc91-118">Traces Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/traces-reference.md)  
  
 <span data-ttu-id="ffc91-119">В этом разделе приводится список всех трассировок, формируемых [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffc91-119">This topic lists all the traces generated by [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc91-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ffc91-120">See Also</span></span>  
 [<span data-ttu-id="ffc91-121">Средство просмотра трассировки служб (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="ffc91-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
