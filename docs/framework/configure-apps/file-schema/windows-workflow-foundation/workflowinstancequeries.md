---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 6db5b2c821037b81f293daeed78cd4767ab48688
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55290034"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="0dd87-101">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="0dd87-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="0dd87-102">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="0dd87-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="0dd87-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0dd87-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0dd87-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0dd87-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0dd87-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="0dd87-105">\<tracking></span></span>  
<span data-ttu-id="0dd87-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0dd87-106">\<trackingProfile></span></span>  
<span data-ttu-id="0dd87-107">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="0dd87-107">\<workflow></span></span>  
<span data-ttu-id="0dd87-108">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="0dd87-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd87-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0dd87-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0dd87-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0dd87-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0dd87-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0dd87-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0dd87-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0dd87-112">Attributes</span></span>  
 <span data-ttu-id="0dd87-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0dd87-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0dd87-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0dd87-114">Child Elements</span></span>  
  
|<span data-ttu-id="0dd87-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="0dd87-115">Element</span></span>|<span data-ttu-id="0dd87-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="0dd87-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0dd87-117">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="0dd87-117">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="0dd87-118">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0dd87-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0dd87-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0dd87-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0dd87-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="0dd87-120">Element</span></span>|<span data-ttu-id="0dd87-121">Описание</span><span class="sxs-lookup"><span data-stu-id="0dd87-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0dd87-122">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="0dd87-122">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="0dd87-123">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="0dd87-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0dd87-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0dd87-124">Remarks</span></span>  
 <span data-ttu-id="0dd87-125">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="0dd87-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="0dd87-126">Пример</span><span class="sxs-lookup"><span data-stu-id="0dd87-126">Example</span></span>  
 <span data-ttu-id="0dd87-127">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="0dd87-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0dd87-128">См. также</span><span class="sxs-lookup"><span data-stu-id="0dd87-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0dd87-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0dd87-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0dd87-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="0dd87-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
