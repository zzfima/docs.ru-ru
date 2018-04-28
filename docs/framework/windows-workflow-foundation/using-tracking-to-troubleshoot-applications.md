---
title: Использование отслеживания для устранения неполадок приложений
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: adc9a159b8887b0198cf19891f73fdee2a48437b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="738d5-102">Использование отслеживания для устранения неполадок приложений</span><span class="sxs-lookup"><span data-stu-id="738d5-102">Using Tracking to Troubleshoot Applications</span></span>
<span data-ttu-id="738d5-103">Windows Workflow Foundation (WF) позволяет отслеживать сведения о рабочем процессе для предоставления сведений в выполнение Windows Workflow Foundation приложения или службы.</span><span class="sxs-lookup"><span data-stu-id="738d5-103">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="738d5-104">Узлы Windows Workflow Foundation, могут захватывать события рабочего процесса во время выполнения экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="738d5-104">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="738d5-105">Если рабочий процесс приводит к возникновению ошибки или исключения, можно использовать данные отслеживания для устранения неполадок обработки Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="738d5-105">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="738d5-106">Устранение неполадок WF с помощью отслеживания WF</span><span class="sxs-lookup"><span data-stu-id="738d5-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="738d5-107">Для обнаружения ошибок при обработке действия Windows Workflow Foundation, можно включить отслеживание с профилем отслеживания, который запрашивает <xref:System.Activities.Tracking.ActivityStateRecord> в состоянии Faulted.</span><span class="sxs-lookup"><span data-stu-id="738d5-107">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="738d5-108">Соответствующий запрос задан в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="738d5-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="738d5-109">Если ошибка передается и обрабатывается в обработчике ошибок (например, в действии <xref:System.Activities.Statements.TryCatch>), это можно обнаружить с помощью записи <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="738d5-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="738d5-110">Запись <xref:System.Activities.Tracking.FaultPropagationRecord> указывает исходное действие, вызвавшее ошибку, и имя обработчика ошибок.</span><span class="sxs-lookup"><span data-stu-id="738d5-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="738d5-111">Запись <xref:System.Activities.Tracking.FaultPropagationRecord> содержит сведения об ошибке в виде стека исключений для ошибки. Запрос на подписку на <xref:System.Activities.Tracking.FaultPropagationRecord> показан в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="738d5-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="738d5-112">Если ошибка не обрабатывается в рабочем процессе, это создает необработанное исключение в экземпляре рабочего процесса, и работа экземпляра рабочего процесса прерывается.</span><span class="sxs-lookup"><span data-stu-id="738d5-112">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="738d5-113">Для получения сведений о необработанном исключении профиль отслеживания должен запросить запись экземпляра рабочего процесса с состоянием `state name="UnhandledException"`, как указано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="738d5-113">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="738d5-114">Когда экземпляр рабочего процесса обнаруживается необработанное исключение, <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> объект создается в том случае, если включено отслеживание Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="738d5-114">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="738d5-115">Эта запись отслеживания содержит сведения об ошибке в виде стека исключений.</span><span class="sxs-lookup"><span data-stu-id="738d5-115">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="738d5-116">Она содержит сведения об источнике ошибки (например, действие), произошел сбой, вызвавший необработанное исключение. Чтобы подписаться на события ошибок с Windows Workflow Foundation, включите отслеживание путем добавления участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="738d5-116">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="738d5-117">Настройте участника с профилем отслеживания, запрашивающим запись `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> и `WorkflowInstanceQuery (state="UnhandledException")`.</span><span class="sxs-lookup"><span data-stu-id="738d5-117">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="738d5-118">Если отслеживание включено с использованием участника отслеживания ETW, события ошибок создаются в сеансе ETW.</span><span class="sxs-lookup"><span data-stu-id="738d5-118">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="738d5-119">События можно просмотреть с помощью средства «Просмотр событий».</span><span class="sxs-lookup"><span data-stu-id="738d5-119">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="738d5-120">Это можно найти в узле **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения** в канале аналитики.</span><span class="sxs-lookup"><span data-stu-id="738d5-120">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738d5-121">См. также</span><span class="sxs-lookup"><span data-stu-id="738d5-121">See Also</span></span>  
 [<span data-ttu-id="738d5-122">Наблюдение за Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="738d5-122">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="738d5-123">Мониторинг приложений с</span><span class="sxs-lookup"><span data-stu-id="738d5-123">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
