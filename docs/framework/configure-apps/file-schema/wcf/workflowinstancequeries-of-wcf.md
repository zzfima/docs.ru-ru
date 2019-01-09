---
title: '&lt;workflowInstanceQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: e3ad1139781c54cc1ca4e2d2b264f3f375b49108
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145566"
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="83ddf-102">&lt;workflowInstanceQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="83ddf-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>

<span data-ttu-id="83ddf-103">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="83ddf-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="83ddf-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="83ddf-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="83ddf-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="83ddf-105">\<system.serviceModel></span></span>  
<span data-ttu-id="83ddf-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="83ddf-106">\<tracking></span></span>  
<span data-ttu-id="83ddf-107">\<профили ></span><span class="sxs-lookup"><span data-stu-id="83ddf-107">\<profiles></span></span>  
<span data-ttu-id="83ddf-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="83ddf-108">\<trackingProfile></span></span>  
<span data-ttu-id="83ddf-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="83ddf-109">\<workflow></span></span>  
<span data-ttu-id="83ddf-110">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="83ddf-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ddf-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83ddf-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83ddf-112">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="83ddf-112">Attributes and elements</span></span>

<span data-ttu-id="83ddf-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="83ddf-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83ddf-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="83ddf-114">Attributes</span></span>  

<span data-ttu-id="83ddf-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="83ddf-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="83ddf-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="83ddf-116">Child elements</span></span>  
  
|<span data-ttu-id="83ddf-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="83ddf-117">Element</span></span>|<span data-ttu-id="83ddf-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="83ddf-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83ddf-119">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="83ddf-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="83ddf-120">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="83ddf-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83ddf-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="83ddf-121">Parent elements</span></span>  
  
|<span data-ttu-id="83ddf-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="83ddf-122">Element</span></span>|<span data-ttu-id="83ddf-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="83ddf-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83ddf-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="83ddf-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="83ddf-125">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) свойство.</span><span class="sxs-lookup"><span data-stu-id="83ddf-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83ddf-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="83ddf-126">Remarks</span></span>

<span data-ttu-id="83ddf-127">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="83ddf-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="83ddf-128">Пример</span><span class="sxs-lookup"><span data-stu-id="83ddf-128">Example</span></span>  

<span data-ttu-id="83ddf-129">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="83ddf-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="83ddf-130">См. также</span><span class="sxs-lookup"><span data-stu-id="83ddf-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="83ddf-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="83ddf-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="83ddf-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="83ddf-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
