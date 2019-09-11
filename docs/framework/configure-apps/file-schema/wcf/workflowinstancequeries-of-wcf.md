---
title: <workflowInstanceQueries>WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854770"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="a8476-102">\<Воркфловинстанцекуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="a8476-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="a8476-103">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="a8476-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="a8476-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="a8476-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a8476-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8476-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a8476-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a8476-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a8476-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a8476-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="a8476-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="a8476-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="a8476-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a8476-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="a8476-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a8476-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="a8476-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Воркфловинстанцекуериес >**</span><span class="sxs-lookup"><span data-stu-id="a8476-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8476-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8476-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8476-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8476-113">Attributes and elements</span></span>

<span data-ttu-id="a8476-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a8476-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8476-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8476-115">Attributes</span></span>  

<span data-ttu-id="a8476-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="a8476-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8476-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8476-117">Child elements</span></span>  
  
|<span data-ttu-id="a8476-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8476-118">Element</span></span>|<span data-ttu-id="a8476-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a8476-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8476-120">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="a8476-120">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="a8476-121">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a8476-121">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8476-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8476-122">Parent elements</span></span>  
  
|<span data-ttu-id="a8476-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8476-123">Element</span></span>|<span data-ttu-id="a8476-124">Описание</span><span class="sxs-lookup"><span data-stu-id="a8476-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8476-125">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a8476-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="a8476-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством [ActivityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) .</span><span class="sxs-lookup"><span data-stu-id="a8476-126">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8476-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8476-127">Remarks</span></span>

<span data-ttu-id="a8476-128">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="a8476-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="a8476-129">Пример</span><span class="sxs-lookup"><span data-stu-id="a8476-129">Example</span></span>  

<span data-ttu-id="a8476-130">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="a8476-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="a8476-131">См. также</span><span class="sxs-lookup"><span data-stu-id="a8476-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a8476-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a8476-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a8476-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a8476-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
