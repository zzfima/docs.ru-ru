---
title: '&lt;workflowInstanceQuery&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64b404fec3f3cd46912deede61bf08f8e962f1d7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="09a52-102">&lt;workflowInstanceQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="09a52-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>
<span data-ttu-id="09a52-103">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="09a52-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="09a52-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="09a52-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="09a52-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="09a52-105">\<system.serviceModel></span></span>  
<span data-ttu-id="09a52-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="09a52-106">\<tracking></span></span>  
<span data-ttu-id="09a52-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="09a52-107">\<trackingProfile></span></span>  
<span data-ttu-id="09a52-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="09a52-108">\<workflow></span></span>  
<span data-ttu-id="09a52-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="09a52-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="09a52-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="09a52-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09a52-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09a52-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09a52-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="09a52-112">Attributes and Elements</span></span>  
 <span data-ttu-id="09a52-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="09a52-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09a52-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09a52-114">Attributes</span></span>  
 <span data-ttu-id="09a52-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="09a52-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="09a52-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="09a52-116">Child Elements</span></span>  
  
|<span data-ttu-id="09a52-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="09a52-117">Element</span></span>|<span data-ttu-id="09a52-118">Описание</span><span class="sxs-lookup"><span data-stu-id="09a52-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09a52-119">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="09a52-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="09a52-120">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="09a52-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09a52-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="09a52-121">Parent Elements</span></span>  
  
|<span data-ttu-id="09a52-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="09a52-122">Element</span></span>|<span data-ttu-id="09a52-123">Описание</span><span class="sxs-lookup"><span data-stu-id="09a52-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09a52-124">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="09a52-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="09a52-125">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="09a52-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09a52-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="09a52-126">Remarks</span></span>  
 <span data-ttu-id="09a52-127">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="09a52-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="09a52-128">Пример</span><span class="sxs-lookup"><span data-stu-id="09a52-128">Example</span></span>  
 <span data-ttu-id="09a52-129">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="09a52-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="09a52-130">См. также</span><span class="sxs-lookup"><span data-stu-id="09a52-130">See Also</span></span>  
 <span data-ttu-id="09a52-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="09a52-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="09a52-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="09a52-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="09a52-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="09a52-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="09a52-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="09a52-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
