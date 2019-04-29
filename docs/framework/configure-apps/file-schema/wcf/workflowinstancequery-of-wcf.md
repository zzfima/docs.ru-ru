---
title: <workflowInstanceQuery> для WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 726d4db3bad9f57663790e2bb4e081faba28f1ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672969"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="6e8ca-102">\<workflowInstanceQuery > из WCF</span><span class="sxs-lookup"><span data-stu-id="6e8ca-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="6e8ca-103">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="6e8ca-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="6e8ca-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6e8ca-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6e8ca-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6e8ca-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6e8ca-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="6e8ca-106">\<tracking></span></span>  
<span data-ttu-id="6e8ca-107">\<профили ></span><span class="sxs-lookup"><span data-stu-id="6e8ca-107">\<profiles></span></span>  
<span data-ttu-id="6e8ca-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6e8ca-108">\<trackingProfile></span></span>  
<span data-ttu-id="6e8ca-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="6e8ca-109">\<workflow></span></span>  
<span data-ttu-id="6e8ca-110">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="6e8ca-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="6e8ca-111">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="6e8ca-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e8ca-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e8ca-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e8ca-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="6e8ca-113">Attributes and elements</span></span>  

<span data-ttu-id="6e8ca-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6e8ca-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e8ca-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6e8ca-115">Attributes</span></span>  

<span data-ttu-id="6e8ca-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6e8ca-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6e8ca-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6e8ca-117">Child elements</span></span>  
  
|<span data-ttu-id="6e8ca-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="6e8ca-118">Element</span></span>|<span data-ttu-id="6e8ca-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6e8ca-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e8ca-120">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="6e8ca-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="6e8ca-121">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="6e8ca-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e8ca-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6e8ca-122">Parent elements</span></span>  
  
|<span data-ttu-id="6e8ca-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="6e8ca-123">Element</span></span>|<span data-ttu-id="6e8ca-124">Описание</span><span class="sxs-lookup"><span data-stu-id="6e8ca-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e8ca-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="6e8ca-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="6e8ca-126">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="6e8ca-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e8ca-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="6e8ca-127">Remarks</span></span>  

<span data-ttu-id="6e8ca-128">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="6e8ca-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="6e8ca-129">Пример</span><span class="sxs-lookup"><span data-stu-id="6e8ca-129">Example</span></span>  

<span data-ttu-id="6e8ca-130">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="6e8ca-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="6e8ca-131">См. также</span><span class="sxs-lookup"><span data-stu-id="6e8ca-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6e8ca-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6e8ca-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6e8ca-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="6e8ca-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
