---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: f0a3c3a27b40000432b40b7008f81251fe771ca2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913145"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="f54cc-101">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="f54cc-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="f54cc-102">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="f54cc-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="f54cc-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="f54cc-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f54cc-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="f54cc-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f54cc-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f54cc-105">\<tracking></span></span>  
<span data-ttu-id="f54cc-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f54cc-106">\<trackingProfile></span></span>  
<span data-ttu-id="f54cc-107">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="f54cc-107">\<workflow></span></span>  
<span data-ttu-id="f54cc-108">\<Воркфловинстанцекуериес ></span><span class="sxs-lookup"><span data-stu-id="f54cc-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="f54cc-109">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="f54cc-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f54cc-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f54cc-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f54cc-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f54cc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f54cc-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f54cc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f54cc-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f54cc-113">Attributes</span></span>  
 <span data-ttu-id="f54cc-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="f54cc-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f54cc-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f54cc-115">Child Elements</span></span>  
  
|<span data-ttu-id="f54cc-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="f54cc-116">Element</span></span>|<span data-ttu-id="f54cc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f54cc-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f54cc-118">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="f54cc-118">\<states></span></span>](states.md)|<span data-ttu-id="f54cc-119">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f54cc-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f54cc-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f54cc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f54cc-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="f54cc-121">Element</span></span>|<span data-ttu-id="f54cc-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f54cc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f54cc-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="f54cc-123">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="f54cc-124">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="f54cc-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f54cc-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="f54cc-125">Remarks</span></span>  
 <span data-ttu-id="f54cc-126">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="f54cc-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="f54cc-127">Пример</span><span class="sxs-lookup"><span data-stu-id="f54cc-127">Example</span></span>  
 <span data-ttu-id="f54cc-128">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="f54cc-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f54cc-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f54cc-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f54cc-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f54cc-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f54cc-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f54cc-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
