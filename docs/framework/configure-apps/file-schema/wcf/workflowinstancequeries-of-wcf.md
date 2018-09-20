---
title: '&lt;workflowInstanceQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: dfa75a7e4729244ba5887e6666c0fdfe840e9faf
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46470757"
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="de7ae-102">&lt;workflowInstanceQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="de7ae-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>
<span data-ttu-id="de7ae-103">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="de7ae-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="de7ae-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="de7ae-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="de7ae-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="de7ae-105">\<system.serviceModel></span></span>  
<span data-ttu-id="de7ae-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="de7ae-106">\<tracking></span></span>  
<span data-ttu-id="de7ae-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="de7ae-107">\<trackingProfile></span></span>  
<span data-ttu-id="de7ae-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="de7ae-108">\<workflow></span></span>  
<span data-ttu-id="de7ae-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="de7ae-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de7ae-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de7ae-110">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de7ae-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="de7ae-111">Attributes and Elements</span></span>  
 <span data-ttu-id="de7ae-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="de7ae-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de7ae-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="de7ae-113">Attributes</span></span>  
 <span data-ttu-id="de7ae-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="de7ae-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="de7ae-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="de7ae-115">Child Elements</span></span>  
  
|<span data-ttu-id="de7ae-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="de7ae-116">Element</span></span>|<span data-ttu-id="de7ae-117">Описание</span><span class="sxs-lookup"><span data-stu-id="de7ae-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de7ae-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="de7ae-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="de7ae-119">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="de7ae-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de7ae-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="de7ae-120">Parent Elements</span></span>  
  
|<span data-ttu-id="de7ae-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="de7ae-121">Element</span></span>|<span data-ttu-id="de7ae-122">Описание</span><span class="sxs-lookup"><span data-stu-id="de7ae-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de7ae-123">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="de7ae-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="de7ae-124">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) свойство.</span><span class="sxs-lookup"><span data-stu-id="de7ae-124">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de7ae-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="de7ae-125">Remarks</span></span>  
 <span data-ttu-id="de7ae-126">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="de7ae-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="de7ae-127">Пример</span><span class="sxs-lookup"><span data-stu-id="de7ae-127">Example</span></span>  
 <span data-ttu-id="de7ae-128">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="de7ae-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de7ae-129">См. также</span><span class="sxs-lookup"><span data-stu-id="de7ae-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="de7ae-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="de7ae-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="de7ae-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="de7ae-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
