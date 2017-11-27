---
title: '&lt;workflowInstanceQueries&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6ca8104ba2470593e07e03a7fe0bc80c9cd2f6a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="f228e-102">&lt;workflowInstanceQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="f228e-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>
<span data-ttu-id="f228e-103">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="f228e-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="f228e-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f228e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="f228e-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f228e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f228e-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f228e-106">\<tracking></span></span>  
<span data-ttu-id="f228e-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f228e-107">\<trackingProfile></span></span>  
<span data-ttu-id="f228e-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="f228e-108">\<workflow></span></span>  
<span data-ttu-id="f228e-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="f228e-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f228e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f228e-110">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f228e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f228e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f228e-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f228e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f228e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f228e-113">Attributes</span></span>  
 <span data-ttu-id="f228e-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f228e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f228e-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f228e-115">Child Elements</span></span>  
  
|<span data-ttu-id="f228e-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="f228e-116">Element</span></span>|<span data-ttu-id="f228e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f228e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f228e-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="f228e-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="f228e-119">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f228e-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f228e-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f228e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f228e-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="f228e-121">Element</span></span>|<span data-ttu-id="f228e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f228e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f228e-123">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="f228e-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f228e-124">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного [activityDefinitionId](http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) свойство.</span><span class="sxs-lookup"><span data-stu-id="f228e-124">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f228e-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="f228e-125">Remarks</span></span>  
 <span data-ttu-id="f228e-126">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="f228e-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="f228e-127">Пример</span><span class="sxs-lookup"><span data-stu-id="f228e-127">Example</span></span>  
 <span data-ttu-id="f228e-128">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="f228e-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f228e-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f228e-129">See Also</span></span>  
 <span data-ttu-id="f228e-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f228e-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f228e-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f228e-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="f228e-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f228e-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f228e-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f228e-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
