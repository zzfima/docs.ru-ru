---
title: <workflowInstanceQueries>WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: feae65a75f9f0b2b1b398f3f9e80ac4c8d971dcc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915299"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="e71ba-102">\<Воркфловинстанцекуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="e71ba-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="e71ba-103">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="e71ba-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="e71ba-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="e71ba-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e71ba-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="e71ba-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e71ba-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="e71ba-106">\<tracking></span></span>  
<span data-ttu-id="e71ba-107">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="e71ba-107">\<profiles></span></span>  
<span data-ttu-id="e71ba-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e71ba-108">\<trackingProfile></span></span>  
<span data-ttu-id="e71ba-109">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e71ba-109">\<workflow></span></span>  
<span data-ttu-id="e71ba-110">\<Воркфловинстанцекуериес ></span><span class="sxs-lookup"><span data-stu-id="e71ba-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e71ba-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e71ba-111">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e71ba-112">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="e71ba-112">Attributes and elements</span></span>

<span data-ttu-id="e71ba-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e71ba-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e71ba-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e71ba-114">Attributes</span></span>  

<span data-ttu-id="e71ba-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="e71ba-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e71ba-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e71ba-116">Child elements</span></span>  
  
|<span data-ttu-id="e71ba-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="e71ba-117">Element</span></span>|<span data-ttu-id="e71ba-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e71ba-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e71ba-119">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="e71ba-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="e71ba-120">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e71ba-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e71ba-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e71ba-121">Parent elements</span></span>  
  
|<span data-ttu-id="e71ba-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="e71ba-122">Element</span></span>|<span data-ttu-id="e71ba-123">Описание</span><span class="sxs-lookup"><span data-stu-id="e71ba-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e71ba-124">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e71ba-124">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="e71ba-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством [ActivityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) .</span><span class="sxs-lookup"><span data-stu-id="e71ba-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e71ba-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e71ba-126">Remarks</span></span>

<span data-ttu-id="e71ba-127">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="e71ba-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="e71ba-128">Пример</span><span class="sxs-lookup"><span data-stu-id="e71ba-128">Example</span></span>  

<span data-ttu-id="e71ba-129">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="e71ba-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="e71ba-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e71ba-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e71ba-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e71ba-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e71ba-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="e71ba-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
