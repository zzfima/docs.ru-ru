---
title: "Сквозная трассировка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c3f5c9f80bbf124440952e35049969c7cfa4f19c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="ae5e4-102">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="ae5e4-102">End-to-End Tracing</span></span>
<span data-ttu-id="ae5e4-103">Сквозная (e2e) трассировка позволяет разработчикам следить за выполнением кода в инфраструктуре [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] при исследовании причин сбоя в ветви кода, а также для получения подробной трассировки для планирования загрузки и анализа производительности характеристик производительности.</span><span class="sxs-lookup"><span data-stu-id="ae5e4-103">End to End (e2e) Tracing allows developers to follow the execution of code in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="ae5e4-104"> обеспечивает три механизма корреляции, помогающие в диагностике причин ошибки: действия, перенаправления и распространение.</span><span class="sxs-lookup"><span data-stu-id="ae5e4-104"> provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="ae5e4-105">В разделе [сценарии трассировки конца в конец](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) список сценарии трассировки начала до конца и их соответствующего действия и трассировки конструктора.</span><span class="sxs-lookup"><span data-stu-id="ae5e4-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae5e4-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="ae5e4-106">In This Section</span></span>  
 <span data-ttu-id="ae5e4-107">[Действие](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md): описываются трассировки действий в [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] модели трассировки.</span><span class="sxs-lookup"><span data-stu-id="ae5e4-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model.</span></span>  
  
 <span data-ttu-id="ae5e4-108">[Передача](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md): описывается перенаправление в [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] трассировка модели и использование перенаправления для корреляции действий внутри конечных точек.</span><span class="sxs-lookup"><span data-stu-id="ae5e4-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="ae5e4-109">[Распространение](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md): описывается распространение действий в [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] трассировка модели и использование распространения для корреляции действий между конечными точками.</span><span class="sxs-lookup"><span data-stu-id="ae5e4-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="ae5e4-110">Сводка типов трассировок</span><span class="sxs-lookup"><span data-stu-id="ae5e4-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="ae5e4-111">Краткий обзор всех типов трассировок действий</span><span class="sxs-lookup"><span data-stu-id="ae5e4-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae5e4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ae5e4-112">See Also</span></span>  
 [<span data-ttu-id="ae5e4-113">Настройка трассировки</span><span class="sxs-lookup"><span data-stu-id="ae5e4-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="ae5e4-114">Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="ae5e4-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="ae5e4-115">Сценарии трассировки конца в конец</span><span class="sxs-lookup"><span data-stu-id="ae5e4-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="ae5e4-116">Средство просмотра трассировки служб (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="ae5e4-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
