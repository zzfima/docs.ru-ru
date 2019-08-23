---
title: <workflowInstanceQuery>WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 7e15d7654aeafa5fa7b87922283d6520d5493242
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915227"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="18908-102">\<workflowInstanceQuery > WCF</span><span class="sxs-lookup"><span data-stu-id="18908-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="18908-103">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="18908-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="18908-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="18908-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="18908-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="18908-105">\<system.serviceModel></span></span>  
<span data-ttu-id="18908-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="18908-106">\<tracking></span></span>  
<span data-ttu-id="18908-107">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="18908-107">\<profiles></span></span>  
<span data-ttu-id="18908-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="18908-108">\<trackingProfile></span></span>  
<span data-ttu-id="18908-109">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="18908-109">\<workflow></span></span>  
<span data-ttu-id="18908-110">\<Воркфловинстанцекуериес ></span><span class="sxs-lookup"><span data-stu-id="18908-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="18908-111">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="18908-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18908-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18908-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18908-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="18908-113">Attributes and elements</span></span>  

<span data-ttu-id="18908-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18908-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18908-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18908-115">Attributes</span></span>  

<span data-ttu-id="18908-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="18908-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="18908-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18908-117">Child elements</span></span>  
  
|<span data-ttu-id="18908-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="18908-118">Element</span></span>|<span data-ttu-id="18908-119">Описание</span><span class="sxs-lookup"><span data-stu-id="18908-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18908-120">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="18908-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="18908-121">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="18908-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18908-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18908-122">Parent elements</span></span>  
  
|<span data-ttu-id="18908-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="18908-123">Element</span></span>|<span data-ttu-id="18908-124">Описание</span><span class="sxs-lookup"><span data-stu-id="18908-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18908-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="18908-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="18908-126">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="18908-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18908-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="18908-127">Remarks</span></span>  

<span data-ttu-id="18908-128">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="18908-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="18908-129">Пример</span><span class="sxs-lookup"><span data-stu-id="18908-129">Example</span></span>  

<span data-ttu-id="18908-130">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="18908-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="18908-131">См. также</span><span class="sxs-lookup"><span data-stu-id="18908-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="18908-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="18908-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="18908-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="18908-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
