---
title: '&lt;workflowInstanceQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: a165d6f55afbbf1489a7355d4207a74ac1f003ef
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="fa923-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="fa923-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="fa923-103">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="fa923-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="fa923-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="fa923-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="fa923-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="fa923-105">\<system.serviceModel></span></span>  
<span data-ttu-id="fa923-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="fa923-106">\<tracking></span></span>  
<span data-ttu-id="fa923-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="fa923-107">\<trackingProfile></span></span>  
<span data-ttu-id="fa923-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="fa923-108">\<workflow></span></span>  
<span data-ttu-id="fa923-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="fa923-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa923-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa923-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa923-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fa923-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fa923-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fa923-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa923-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fa923-113">Attributes</span></span>  
 <span data-ttu-id="fa923-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fa923-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa923-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fa923-115">Child Elements</span></span>  
  
|<span data-ttu-id="fa923-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa923-116">Element</span></span>|<span data-ttu-id="fa923-117">Описание</span><span class="sxs-lookup"><span data-stu-id="fa923-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa923-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="fa923-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="fa923-119">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fa923-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa923-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fa923-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fa923-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa923-121">Element</span></span>|<span data-ttu-id="fa923-122">Описание</span><span class="sxs-lookup"><span data-stu-id="fa923-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa923-123">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="fa923-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="fa923-124">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="fa923-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa923-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa923-125">Remarks</span></span>  
 <span data-ttu-id="fa923-126">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="fa923-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="fa923-127">Пример</span><span class="sxs-lookup"><span data-stu-id="fa923-127">Example</span></span>  
 <span data-ttu-id="fa923-128">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="fa923-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa923-129">См. также</span><span class="sxs-lookup"><span data-stu-id="fa923-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="fa923-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="fa923-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="fa923-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="fa923-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
