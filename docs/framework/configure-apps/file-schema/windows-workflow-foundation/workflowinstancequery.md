---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 68e44584858e55c136bc3c3dc5f1fb333485fa17
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397515"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="710bd-101">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="710bd-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="710bd-102">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="710bd-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="710bd-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="710bd-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="710bd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="710bd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="710bd-105">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="710bd-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="710bd-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="710bd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="710bd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="710bd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="710bd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="710bd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="710bd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Воркфловинстанцекуериес >** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="710bd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="710bd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowInstanceQuery >**</span><span class="sxs-lookup"><span data-stu-id="710bd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="710bd-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="710bd-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="710bd-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="710bd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="710bd-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="710bd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="710bd-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="710bd-114">Attributes</span></span>  
 <span data-ttu-id="710bd-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="710bd-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="710bd-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="710bd-116">Child Elements</span></span>  
  
|<span data-ttu-id="710bd-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="710bd-117">Element</span></span>|<span data-ttu-id="710bd-118">Описание</span><span class="sxs-lookup"><span data-stu-id="710bd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="710bd-119">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="710bd-119">\<states></span></span>](states.md)|<span data-ttu-id="710bd-120">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="710bd-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="710bd-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="710bd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="710bd-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="710bd-122">Element</span></span>|<span data-ttu-id="710bd-123">Описание</span><span class="sxs-lookup"><span data-stu-id="710bd-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="710bd-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="710bd-124">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="710bd-125">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="710bd-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="710bd-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="710bd-126">Remarks</span></span>  
 <span data-ttu-id="710bd-127">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="710bd-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="710bd-128">Пример</span><span class="sxs-lookup"><span data-stu-id="710bd-128">Example</span></span>  
 <span data-ttu-id="710bd-129">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="710bd-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="710bd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="710bd-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="710bd-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="710bd-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="710bd-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="710bd-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
