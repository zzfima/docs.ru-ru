---
title: '&lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: bef9ddcee2e373f4588d6aed06b7c51e4c6ed4b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662053"
---
# <a name="ltworkflowinstancequerygt"></a><span data-ttu-id="da5e3-102">&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="da5e3-102">&lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="da5e3-103">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="da5e3-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="da5e3-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="da5e3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="da5e3-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="da5e3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="da5e3-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="da5e3-106">\<tracking></span></span>  
<span data-ttu-id="da5e3-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="da5e3-107">\<trackingProfile></span></span>  
<span data-ttu-id="da5e3-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="da5e3-108">\<workflow></span></span>  
<span data-ttu-id="da5e3-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="da5e3-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="da5e3-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="da5e3-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da5e3-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da5e3-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da5e3-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="da5e3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="da5e3-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="da5e3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da5e3-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da5e3-114">Attributes</span></span>  
 <span data-ttu-id="da5e3-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="da5e3-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da5e3-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da5e3-116">Child Elements</span></span>  
  
|<span data-ttu-id="da5e3-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="da5e3-117">Element</span></span>|<span data-ttu-id="da5e3-118">Описание</span><span class="sxs-lookup"><span data-stu-id="da5e3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da5e3-119">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="da5e3-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="da5e3-120">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="da5e3-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da5e3-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="da5e3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="da5e3-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="da5e3-122">Element</span></span>|<span data-ttu-id="da5e3-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="da5e3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da5e3-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="da5e3-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="da5e3-125">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="da5e3-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da5e3-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="da5e3-126">Remarks</span></span>  
 <span data-ttu-id="da5e3-127">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="da5e3-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="da5e3-128">Пример</span><span class="sxs-lookup"><span data-stu-id="da5e3-128">Example</span></span>  
 <span data-ttu-id="da5e3-129">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="da5e3-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="da5e3-130">См. также</span><span class="sxs-lookup"><span data-stu-id="da5e3-130">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="da5e3-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="da5e3-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="da5e3-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="da5e3-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
