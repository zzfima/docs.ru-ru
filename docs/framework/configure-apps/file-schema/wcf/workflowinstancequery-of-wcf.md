---
title: '&lt;workflowInstanceQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 447564e46e5e74432802341d9f63adbb72667ab4
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123310"
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="9c7ef-102">&lt;workflowInstanceQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="9c7ef-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>

<span data-ttu-id="9c7ef-103">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="9c7ef-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="9c7ef-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9c7ef-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9c7ef-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9c7ef-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9c7ef-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="9c7ef-106">\<tracking></span></span>  
<span data-ttu-id="9c7ef-107">\<профили ></span><span class="sxs-lookup"><span data-stu-id="9c7ef-107">\<profiles></span></span>  
<span data-ttu-id="9c7ef-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9c7ef-108">\<trackingProfile></span></span>  
<span data-ttu-id="9c7ef-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="9c7ef-109">\<workflow></span></span>  
<span data-ttu-id="9c7ef-110">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="9c7ef-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="9c7ef-111">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="9c7ef-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c7ef-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c7ef-112">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9c7ef-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="9c7ef-113">Attributes and elements</span></span>  

<span data-ttu-id="9c7ef-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9c7ef-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c7ef-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9c7ef-115">Attributes</span></span>  

<span data-ttu-id="9c7ef-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9c7ef-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c7ef-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9c7ef-117">Child elements</span></span>  
  
|<span data-ttu-id="9c7ef-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="9c7ef-118">Element</span></span>|<span data-ttu-id="9c7ef-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9c7ef-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c7ef-120">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="9c7ef-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="9c7ef-121">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="9c7ef-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c7ef-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9c7ef-122">Parent elements</span></span>  
  
|<span data-ttu-id="9c7ef-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="9c7ef-123">Element</span></span>|<span data-ttu-id="9c7ef-124">Описание</span><span class="sxs-lookup"><span data-stu-id="9c7ef-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c7ef-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="9c7ef-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="9c7ef-126">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="9c7ef-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c7ef-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="9c7ef-127">Remarks</span></span>  

<span data-ttu-id="9c7ef-128">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="9c7ef-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="9c7ef-129">Пример</span><span class="sxs-lookup"><span data-stu-id="9c7ef-129">Example</span></span>  

<span data-ttu-id="9c7ef-130">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="9c7ef-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c7ef-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9c7ef-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9c7ef-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9c7ef-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9c7ef-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="9c7ef-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
