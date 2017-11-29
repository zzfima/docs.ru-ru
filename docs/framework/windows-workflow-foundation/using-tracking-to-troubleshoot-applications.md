---
title: "Использование отслеживания для устранения неполадок приложений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 02c6d346c6ebea27148c11f5f033f74dfb556e44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="b4d11-102">Использование отслеживания для устранения неполадок приложений</span><span class="sxs-lookup"><span data-stu-id="b4d11-102">Using Tracking to Troubleshoot Applications</span></span>
[!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="b4d11-103"> позволяет отслеживать данные, связанные с рабочим процессом, для последующей передачи подробных сведений в выполнение приложения [!INCLUDE[wf2](../../../includes/wf2-md.md)] или службы.</span><span class="sxs-lookup"><span data-stu-id="b4d11-103"> enables you to track workflow-related information to give details into the execution of a [!INCLUDE[wf2](../../../includes/wf2-md.md)] application or service.</span></span> <span data-ttu-id="b4d11-104">Узлы [!INCLUDE[wf2](../../../includes/wf2-md.md)] могут захватывать события рабочего процесса во время выполнения экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b4d11-104">[!INCLUDE[wf2](../../../includes/wf2-md.md)] hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="b4d11-105">Если в рабочем процессе возникают ошибки или исключения, можно использовать данные отслеживания [!INCLUDE[wf2](../../../includes/wf2-md.md)] для устранения неполадок обработки.</span><span class="sxs-lookup"><span data-stu-id="b4d11-105">If your workflow generates faults or exceptions, you can use the [!INCLUDE[wf2](../../../includes/wf2-md.md)] tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="b4d11-106">Устранение неполадок WF с помощью отслеживания WF</span><span class="sxs-lookup"><span data-stu-id="b4d11-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="b4d11-107">Для обнаружения ошибок при обработке действия [!INCLUDE[wf2](../../../includes/wf2-md.md)] можно включить отслеживание с профилем отслеживания, в ходе которого запрашиваются записи <xref:System.Activities.Tracking.ActivityStateRecord> с состоянием ошибки (Faulted).</span><span class="sxs-lookup"><span data-stu-id="b4d11-107">To detect faults within the processing of a [!INCLUDE[wf2](../../../includes/wf2-md.md)] activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="b4d11-108">Соответствующий запрос задан в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="b4d11-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="b4d11-109">Если ошибка передается и обрабатывается в обработчике ошибок (например, в действии <xref:System.Activities.Statements.TryCatch>), это можно обнаружить с помощью записи <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="b4d11-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="b4d11-110">Запись <xref:System.Activities.Tracking.FaultPropagationRecord> указывает исходное действие, вызвавшее ошибку, и имя обработчика ошибок.</span><span class="sxs-lookup"><span data-stu-id="b4d11-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="b4d11-111">Запись <xref:System.Activities.Tracking.FaultPropagationRecord> содержит сведения об ошибке в виде стека исключений для ошибки. Запрос на подписку на <xref:System.Activities.Tracking.FaultPropagationRecord> показан в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b4d11-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="b4d11-112">Если ошибка не обрабатывается в рабочем процессе, это создает необработанное исключение в экземпляре рабочего процесса, и работа экземпляра рабочего процесса прерывается.</span><span class="sxs-lookup"><span data-stu-id="b4d11-112">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="b4d11-113">Для получения сведений о необработанном исключении профиль отслеживания должен запросить запись экземпляра рабочего процесса с состоянием `state name="UnhandledException"`, как указано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b4d11-113">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="b4d11-114">Когда экземпляр рабочего процесса встречает необработанное исключение, создается объект <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>, если отслеживание [!INCLUDE[wf2](../../../includes/wf2-md.md)] включено.</span><span class="sxs-lookup"><span data-stu-id="b4d11-114">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if [!INCLUDE[wf2](../../../includes/wf2-md.md)] tracking has been enabled.</span></span>  
  
 <span data-ttu-id="b4d11-115">Эта запись отслеживания содержит сведения об ошибке в виде стека исключений.</span><span class="sxs-lookup"><span data-stu-id="b4d11-115">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="b4d11-116">Она содержит сведения об источнике ошибки (например, о действии), где произошел сбой, вызвавший необработанное исключение. Чтобы подписаться на события, связанные с ошибками, из [!INCLUDE[wf2](../../../includes/wf2-md.md)], включите отслеживание, добавив участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="b4d11-116">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a [!INCLUDE[wf2](../../../includes/wf2-md.md)], enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="b4d11-117">Настройте участника с профилем отслеживания, запрашивающим запись `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> и `WorkflowInstanceQuery (state="UnhandledException")`.</span><span class="sxs-lookup"><span data-stu-id="b4d11-117">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="b4d11-118">Если отслеживание включено с использованием участника отслеживания ETW, события ошибок создаются в сеансе ETW.</span><span class="sxs-lookup"><span data-stu-id="b4d11-118">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="b4d11-119">События можно просмотреть с помощью средства «Просмотр событий».</span><span class="sxs-lookup"><span data-stu-id="b4d11-119">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="b4d11-120">Это можно найти в узле **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения** в канале аналитики.</span><span class="sxs-lookup"><span data-stu-id="b4d11-120">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d11-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b4d11-121">See Also</span></span>  
 [<span data-ttu-id="b4d11-122">Наблюдение за Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="b4d11-122">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="b4d11-123">Мониторинг приложений с</span><span class="sxs-lookup"><span data-stu-id="b4d11-123">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
