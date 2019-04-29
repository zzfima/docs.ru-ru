---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 6fe02cfea91633da41c8ebc7d8a78dd005ad3f4a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613720"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="890c6-101">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="890c6-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="890c6-102">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="890c6-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="890c6-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="890c6-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="890c6-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="890c6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="890c6-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="890c6-105">\<tracking></span></span>  
<span data-ttu-id="890c6-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="890c6-106">\<trackingProfile></span></span>  
<span data-ttu-id="890c6-107">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="890c6-107">\<workflow></span></span>  
<span data-ttu-id="890c6-108">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="890c6-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="890c6-109">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="890c6-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="890c6-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="890c6-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="890c6-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="890c6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="890c6-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="890c6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="890c6-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="890c6-113">Attributes</span></span>  
 <span data-ttu-id="890c6-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="890c6-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="890c6-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="890c6-115">Child Elements</span></span>  
  
|<span data-ttu-id="890c6-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="890c6-116">Element</span></span>|<span data-ttu-id="890c6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="890c6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="890c6-118">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="890c6-118">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="890c6-119">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="890c6-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="890c6-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="890c6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="890c6-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="890c6-121">Element</span></span>|<span data-ttu-id="890c6-122">Описание</span><span class="sxs-lookup"><span data-stu-id="890c6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="890c6-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="890c6-123">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="890c6-124">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="890c6-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="890c6-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="890c6-125">Remarks</span></span>  
 <span data-ttu-id="890c6-126">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="890c6-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="890c6-127">Пример</span><span class="sxs-lookup"><span data-stu-id="890c6-127">Example</span></span>  
 <span data-ttu-id="890c6-128">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="890c6-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="890c6-129">См. также</span><span class="sxs-lookup"><span data-stu-id="890c6-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="890c6-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="890c6-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="890c6-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="890c6-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
