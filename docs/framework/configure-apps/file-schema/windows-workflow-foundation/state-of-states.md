---
title: '&lt;state&gt; &lt;states&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0985c9ea84cc29b1cb8883411d3b9b1e52de97b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltstategt-of-ltstatesgt"></a><span data-ttu-id="69aca-102">&lt;state&gt; &lt;states&gt;</span><span class="sxs-lookup"><span data-stu-id="69aca-102">&lt;state&gt; of &lt;states&gt;</span></span>
<span data-ttu-id="69aca-103">Элемент конфигурации, содержащий состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="69aca-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="69aca-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="69aca-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="69aca-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="69aca-105">\<system.serviceModel></span></span>  
<span data-ttu-id="69aca-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="69aca-106">\<tracking></span></span>  
<span data-ttu-id="69aca-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="69aca-107">\<trackingProfile></span></span>  
<span data-ttu-id="69aca-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="69aca-108">\<workflow></span></span>  
<span data-ttu-id="69aca-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="69aca-109">\<activityStateQueries></span></span>  
<span data-ttu-id="69aca-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="69aca-110">\<activityStateQuery></span></span>  
<span data-ttu-id="69aca-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="69aca-111">\<states></span></span>  
<span data-ttu-id="69aca-112">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="69aca-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69aca-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69aca-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69aca-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="69aca-114">Attributes and Elements</span></span>  
 <span data-ttu-id="69aca-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="69aca-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69aca-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69aca-116">Attributes</span></span>  
  
|<span data-ttu-id="69aca-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="69aca-117">Attribute</span></span>|<span data-ttu-id="69aca-118">Описание</span><span class="sxs-lookup"><span data-stu-id="69aca-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69aca-119">имя</span><span class="sxs-lookup"><span data-stu-id="69aca-119">name</span></span>|<span data-ttu-id="69aca-120">Строка, содержащая состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="69aca-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69aca-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="69aca-121">Child Elements</span></span>  
 <span data-ttu-id="69aca-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="69aca-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69aca-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="69aca-123">Parent Elements</span></span>  
  
|<span data-ttu-id="69aca-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="69aca-124">Element</span></span>|<span data-ttu-id="69aca-125">Описание</span><span class="sxs-lookup"><span data-stu-id="69aca-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69aca-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="69aca-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="69aca-127">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="69aca-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69aca-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="69aca-128">Remarks</span></span>  
 <span data-ttu-id="69aca-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="69aca-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="69aca-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="69aca-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="69aca-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="69aca-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="69aca-132">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="69aca-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69aca-133">См. также</span><span class="sxs-lookup"><span data-stu-id="69aca-133">See Also</span></span>  
 <span data-ttu-id="69aca-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="69aca-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="69aca-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="69aca-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="69aca-136">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="69aca-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="69aca-137">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="69aca-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
