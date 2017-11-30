---
title: '&lt;workflowInstanceQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e7ed855dc49c4e6639734dcc6a9bc1db7ae53d01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancequerygt"></a><span data-ttu-id="e1b91-102">&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="e1b91-102">&lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="e1b91-103">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="e1b91-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="e1b91-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e1b91-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e1b91-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e1b91-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e1b91-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="e1b91-106">\<tracking></span></span>  
<span data-ttu-id="e1b91-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e1b91-107">\<trackingProfile></span></span>  
<span data-ttu-id="e1b91-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="e1b91-108">\<workflow></span></span>  
<span data-ttu-id="e1b91-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="e1b91-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="e1b91-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="e1b91-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b91-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1b91-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1b91-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1b91-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e1b91-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1b91-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1b91-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1b91-114">Attributes</span></span>  
 <span data-ttu-id="e1b91-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e1b91-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e1b91-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1b91-116">Child Elements</span></span>  
  
|<span data-ttu-id="e1b91-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1b91-117">Element</span></span>|<span data-ttu-id="e1b91-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e1b91-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1b91-119">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="e1b91-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="e1b91-120">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e1b91-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1b91-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1b91-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e1b91-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1b91-122">Element</span></span>|<span data-ttu-id="e1b91-123">Описание</span><span class="sxs-lookup"><span data-stu-id="e1b91-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1b91-124">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="e1b91-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="e1b91-125">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="e1b91-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1b91-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1b91-126">Remarks</span></span>  
 <span data-ttu-id="e1b91-127">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="e1b91-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="e1b91-128">Пример</span><span class="sxs-lookup"><span data-stu-id="e1b91-128">Example</span></span>  
 <span data-ttu-id="e1b91-129">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="e1b91-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1b91-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e1b91-130">See Also</span></span>  
 <span data-ttu-id="e1b91-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e1b91-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="e1b91-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e1b91-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="e1b91-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e1b91-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e1b91-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="e1b91-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
