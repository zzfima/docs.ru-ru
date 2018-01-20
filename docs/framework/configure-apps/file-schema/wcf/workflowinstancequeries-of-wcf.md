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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f02336dc35083009f601b3c4fb3568585a0beeef
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="f3950-102">&lt;workflowInstanceQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="f3950-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>
<span data-ttu-id="f3950-103">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="f3950-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="f3950-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f3950-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="f3950-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f3950-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f3950-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f3950-106">\<tracking></span></span>  
<span data-ttu-id="f3950-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f3950-107">\<trackingProfile></span></span>  
<span data-ttu-id="f3950-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f3950-108">\<workflow></span></span>  
<span data-ttu-id="f3950-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="f3950-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3950-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3950-110">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3950-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3950-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f3950-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3950-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3950-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3950-113">Attributes</span></span>  
 <span data-ttu-id="f3950-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f3950-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f3950-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3950-115">Child Elements</span></span>  
  
|<span data-ttu-id="f3950-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3950-116">Element</span></span>|<span data-ttu-id="f3950-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="f3950-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3950-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="f3950-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="f3950-119">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f3950-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f3950-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3950-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f3950-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3950-121">Element</span></span>|<span data-ttu-id="f3950-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="f3950-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3950-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f3950-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f3950-124">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного [activityDefinitionId](http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) свойство.</span><span class="sxs-lookup"><span data-stu-id="f3950-124">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3950-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3950-125">Remarks</span></span>  
 <span data-ttu-id="f3950-126">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="f3950-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="f3950-127">Пример</span><span class="sxs-lookup"><span data-stu-id="f3950-127">Example</span></span>  
 <span data-ttu-id="f3950-128">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="f3950-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3950-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f3950-129">See Also</span></span>  
 <span data-ttu-id="f3950-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f3950-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f3950-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f3950-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="f3950-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f3950-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f3950-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f3950-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
