---
title: Сквозная трассировка
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: fd2964b39c758e41620fb453ddd8f61a1aa550aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092144"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="cc090-102">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="cc090-102">End-to-End Tracing</span></span>
<span data-ttu-id="cc090-103">Сквозной (e2e) Трассировка позволяет разработчикам следить за выполнением кода в инфраструктуре Windows Communication Foundation (WCF) для изучения причин сбоя пути кода или для получения подробной трассировки для емкости планирования и анализа производительности.</span><span class="sxs-lookup"><span data-stu-id="cc090-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="cc090-104">Windows Communication Foundation (WCF) предоставляет три механизма корреляции, которые помогают диагностировать причину ошибки: действия, перенаправления и распространение.</span><span class="sxs-lookup"><span data-stu-id="cc090-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="cc090-105">См. в разделе [сценариев трассировки End-To-End](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) список сценариев трассировки end-to-end, соответствующих действий и трассировки конструктора.</span><span class="sxs-lookup"><span data-stu-id="cc090-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc090-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="cc090-106">In This Section</span></span>  
 <span data-ttu-id="cc090-107">[Действие](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Описание трассировок действий в модели трассировки Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cc090-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="cc090-108">[Передача](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Описание перенаправления в модели трассировки Windows Communication Foundation (WCF) и использования перенаправления для корреляции действий внутри конечных точек.</span><span class="sxs-lookup"><span data-stu-id="cc090-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="cc090-109">[Распространение](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Описание распространения действий в Windows Communication Foundation (WCF) модели трассировки и использования распространения для корреляции действий между конечными точками.</span><span class="sxs-lookup"><span data-stu-id="cc090-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="cc090-110">Сводка типов трассировок</span><span class="sxs-lookup"><span data-stu-id="cc090-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="cc090-111">Краткий обзор всех типов трассировок действий</span><span class="sxs-lookup"><span data-stu-id="cc090-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc090-112">См. также</span><span class="sxs-lookup"><span data-stu-id="cc090-112">See also</span></span>

- [<span data-ttu-id="cc090-113">Настройка трассировки</span><span class="sxs-lookup"><span data-stu-id="cc090-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [<span data-ttu-id="cc090-114">Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="cc090-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="cc090-115">Сценарии сквозной трассировки</span><span class="sxs-lookup"><span data-stu-id="cc090-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="cc090-116">Программа Service Trace Viewer (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="cc090-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
