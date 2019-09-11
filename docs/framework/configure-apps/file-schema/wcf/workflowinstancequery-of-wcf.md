---
title: <workflowInstanceQuery>WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: eaf0cd204265aac7c1421e3de0c33963e6bbb7a1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854739"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="80ed9-102">\<workflowInstanceQuery > WCF</span><span class="sxs-lookup"><span data-stu-id="80ed9-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="80ed9-103">Представляет запрос, отслеживающий изменения жизненного цикла экземпляра рабочего процесса, например начавшиеся и завершенные события.</span><span class="sxs-lookup"><span data-stu-id="80ed9-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="80ed9-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="80ed9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="80ed9-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="80ed9-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="80ed9-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="80ed9-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="80ed9-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="80ed9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="80ed9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="80ed9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="80ed9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="80ed9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="80ed9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="80ed9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="80ed9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Воркфловинстанцекуериес >** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="80ed9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="80ed9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowInstanceQuery >**</span><span class="sxs-lookup"><span data-stu-id="80ed9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ed9-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80ed9-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80ed9-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="80ed9-114">Attributes and elements</span></span>  

<span data-ttu-id="80ed9-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="80ed9-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80ed9-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="80ed9-116">Attributes</span></span>  

<span data-ttu-id="80ed9-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="80ed9-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80ed9-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="80ed9-118">Child elements</span></span>  
  
|<span data-ttu-id="80ed9-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="80ed9-119">Element</span></span>|<span data-ttu-id="80ed9-120">Описание</span><span class="sxs-lookup"><span data-stu-id="80ed9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80ed9-121">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="80ed9-121">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="80ed9-122">Коллекция состояний, на которые установлена подписка, из отслеживаемого экземпляра рабочего процесса в момент создания записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="80ed9-122">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80ed9-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="80ed9-123">Parent elements</span></span>  
  
|<span data-ttu-id="80ed9-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="80ed9-124">Element</span></span>|<span data-ttu-id="80ed9-125">Описание</span><span class="sxs-lookup"><span data-stu-id="80ed9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80ed9-126">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="80ed9-126">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="80ed9-127">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="80ed9-127">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80ed9-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="80ed9-128">Remarks</span></span>  

<span data-ttu-id="80ed9-129">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="80ed9-129">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="80ed9-130">Пример</span><span class="sxs-lookup"><span data-stu-id="80ed9-130">Example</span></span>  

<span data-ttu-id="80ed9-131">При использовании следующей конфигурации устанавливается подписка на записи отслеживания рабочего процесса на уровне экземпляра для состояния экземпляра `Started` при помощи данного запроса.</span><span class="sxs-lookup"><span data-stu-id="80ed9-131">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="80ed9-132">См. также</span><span class="sxs-lookup"><span data-stu-id="80ed9-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="80ed9-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="80ed9-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="80ed9-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="80ed9-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
