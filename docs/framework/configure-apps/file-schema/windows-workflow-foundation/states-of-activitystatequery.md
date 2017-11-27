---
title: '&lt;states&gt; &lt;activityStateQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4ee98263f43d9557d0ee81484ff8550f0e927ca6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltstatesgt-of-ltactivitystatequerygt"></a><span data-ttu-id="c9ba2-102">&lt;states&gt; &lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="c9ba2-102">&lt;states&gt; of &lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="c9ba2-103">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="c9ba2-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c9ba2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="c9ba2-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c9ba2-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c9ba2-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="c9ba2-106">\<tracking></span></span>  
<span data-ttu-id="c9ba2-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c9ba2-107">\<trackingProfile></span></span>  
<span data-ttu-id="c9ba2-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="c9ba2-108">\<workflow></span></span>  
<span data-ttu-id="c9ba2-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="c9ba2-109">\<activityStateQueries></span></span>  
<span data-ttu-id="c9ba2-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="c9ba2-110">\<activityStateQuery></span></span>  
<span data-ttu-id="c9ba2-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="c9ba2-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9ba2-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9ba2-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9ba2-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c9ba2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c9ba2-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9ba2-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9ba2-115">Attributes</span></span>  
 <span data-ttu-id="c9ba2-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9ba2-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9ba2-117">Child Elements</span></span>  
  
|<span data-ttu-id="c9ba2-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9ba2-118">Element</span></span>|<span data-ttu-id="c9ba2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c9ba2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9ba2-120">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="c9ba2-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="c9ba2-121">Элемент конфигурации, содержащий состояния подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9ba2-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c9ba2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c9ba2-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9ba2-123">Element</span></span>|<span data-ttu-id="c9ba2-124">Описание</span><span class="sxs-lookup"><span data-stu-id="c9ba2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9ba2-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="c9ba2-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="c9ba2-126">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c9ba2-127">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9ba2-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9ba2-128">Remarks</span></span>  
 <span data-ttu-id="c9ba2-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="c9ba2-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="c9ba2-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="c9ba2-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="c9ba2-132">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="c9ba2-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9ba2-133">См. также</span><span class="sxs-lookup"><span data-stu-id="c9ba2-133">See Also</span></span>  
 <span data-ttu-id="c9ba2-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c9ba2-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>      
 <span data-ttu-id="c9ba2-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c9ba2-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="c9ba2-136">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c9ba2-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="c9ba2-137">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="c9ba2-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
