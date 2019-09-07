---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 11e301de1ab3dbd4c97f236bfd07c5de4a632272
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398578"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="38404-101">\<Воркфловинстанцекуериес ></span><span class="sxs-lookup"><span data-stu-id="38404-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="38404-102">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="38404-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="38404-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="38404-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="38404-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="38404-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="38404-105">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="38404-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="38404-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="38404-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="38404-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="38404-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="38404-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="38404-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="38404-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Воркфловинстанцекуериес >**</span><span class="sxs-lookup"><span data-stu-id="38404-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38404-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38404-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38404-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="38404-111">Attributes and Elements</span></span>  

<span data-ttu-id="38404-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="38404-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38404-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="38404-113">Attributes</span></span>  

<span data-ttu-id="38404-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="38404-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="38404-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="38404-115">Child Elements</span></span>  
  
|<span data-ttu-id="38404-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="38404-116">Element</span></span>|<span data-ttu-id="38404-117">Описание</span><span class="sxs-lookup"><span data-stu-id="38404-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38404-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="38404-118">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="38404-119">Запрос, используемый для отслеживания изменений жизненного цикла экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="38404-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38404-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="38404-120">Parent Elements</span></span>  
  
|<span data-ttu-id="38404-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="38404-121">Element</span></span>|<span data-ttu-id="38404-122">Описание</span><span class="sxs-lookup"><span data-stu-id="38404-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38404-123">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="38404-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="38404-124">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="38404-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38404-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="38404-125">Remarks</span></span>  

<span data-ttu-id="38404-126">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="38404-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="38404-127">Пример</span><span class="sxs-lookup"><span data-stu-id="38404-127">Example</span></span>  

<span data-ttu-id="38404-128">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="38404-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="38404-129">См. также</span><span class="sxs-lookup"><span data-stu-id="38404-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="38404-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="38404-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="38404-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="38404-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
