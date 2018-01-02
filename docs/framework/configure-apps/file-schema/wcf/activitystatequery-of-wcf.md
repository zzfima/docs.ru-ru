---
title: '&lt;activityStateQuery&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de042732e7957fa6ea8c22d03ff6892ee1e912f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivitystatequerygt-of-wcf"></a><span data-ttu-id="191c4-102">&lt;activityStateQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="191c4-102">&lt;activityStateQuery&gt; of WCF</span></span>
<span data-ttu-id="191c4-103">Представляет запрос, используемый для трассировки изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="191c4-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="191c4-104">Например можно хранить список каждый раз завершение действия «Send E-Mail» внутри экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="191c4-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="191c4-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="191c4-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="191c4-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="191c4-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="191c4-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="191c4-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="191c4-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="191c4-108">\<system.serviceModel></span></span>  
<span data-ttu-id="191c4-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="191c4-109">\<tracking></span></span>  
<span data-ttu-id="191c4-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="191c4-110">\<trackingProfile></span></span>  
<span data-ttu-id="191c4-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="191c4-111">\<workflow></span></span>  
<span data-ttu-id="191c4-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="191c4-112">\<activityStateQueries></span></span>  
<span data-ttu-id="191c4-113">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="191c4-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="191c4-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="191c4-114">Syntax</span></span>  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="191c4-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="191c4-115">Attributes and Elements</span></span>  
 <span data-ttu-id="191c4-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="191c4-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="191c4-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="191c4-117">Attributes</span></span>  
  
|<span data-ttu-id="191c4-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="191c4-118">Attribute</span></span>|<span data-ttu-id="191c4-119">Описание</span><span class="sxs-lookup"><span data-stu-id="191c4-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="191c4-120">activityName</span><span class="sxs-lookup"><span data-stu-id="191c4-120">activityName</span></span>|<span data-ttu-id="191c4-121">Строка, указывающая имя действия, по которому будут фильтроваться экземпляры <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="191c4-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="191c4-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="191c4-122">Child Elements</span></span>  
  
|<span data-ttu-id="191c4-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="191c4-123">Element</span></span>|<span data-ttu-id="191c4-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="191c4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="191c4-125">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="191c4-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="191c4-126">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="191c4-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="191c4-127">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="191c4-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="191c4-128">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="191c4-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="191c4-129">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="191c4-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="191c4-130">Коллекция переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="191c4-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="191c4-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="191c4-131">Parent Elements</span></span>  
  
|<span data-ttu-id="191c4-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="191c4-132">Element</span></span>|<span data-ttu-id="191c4-133">Описание:</span><span class="sxs-lookup"><span data-stu-id="191c4-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="191c4-134">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="191c4-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="191c4-135">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="191c4-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="191c4-136">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="191c4-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="191c4-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="191c4-137">Remarks</span></span>  
 <span data-ttu-id="191c4-138">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="191c4-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="191c4-139">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="191c4-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="191c4-140">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="191c4-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="191c4-141">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="191c4-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="191c4-142">См. также</span><span class="sxs-lookup"><span data-stu-id="191c4-142">See Also</span></span>  
 <span data-ttu-id="191c4-143"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement></span><span class="sxs-lookup"><span data-stu-id="191c4-143"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement></span></span>    
 <span data-ttu-id="191c4-144"><xref:System.Activities.Tracking.ActivityStateQuery></span><span class="sxs-lookup"><span data-stu-id="191c4-144"><xref:System.Activities.Tracking.ActivityStateQuery></span></span>     
 [<span data-ttu-id="191c4-145">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="191c4-145">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="191c4-146">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="191c4-146">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
