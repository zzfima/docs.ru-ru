---
title: '&lt;activityStateQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 8f9f30cf16e18eec6f076a41474a1935feeb3460
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757623"
---
# <a name="ltactivitystatequerygt"></a><span data-ttu-id="2105b-102">&lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="2105b-102">&lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="2105b-103">Представляет запрос, используемый для трассировки изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2105b-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="2105b-104">Например можно хранить список каждый раз завершение действия «Send E-Mail» внутри экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2105b-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="2105b-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="2105b-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="2105b-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="2105b-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="2105b-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2105b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="2105b-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="2105b-108">\<system.serviceModel></span></span>  
<span data-ttu-id="2105b-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="2105b-109">\<tracking></span></span>  
<span data-ttu-id="2105b-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2105b-110">\<trackingProfile></span></span>  
<span data-ttu-id="2105b-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="2105b-111">\<workflow></span></span>  
<span data-ttu-id="2105b-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="2105b-112">\<activityStateQueries></span></span>  
<span data-ttu-id="2105b-113">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="2105b-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2105b-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2105b-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2105b-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2105b-115">Attributes and Elements</span></span>  
 <span data-ttu-id="2105b-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2105b-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2105b-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2105b-117">Attributes</span></span>  
  
|<span data-ttu-id="2105b-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2105b-118">Attribute</span></span>|<span data-ttu-id="2105b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2105b-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2105b-120">activityName</span><span class="sxs-lookup"><span data-stu-id="2105b-120">activityName</span></span>|<span data-ttu-id="2105b-121">Строка, указывающая имя действия, по которому будут фильтроваться экземпляры <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="2105b-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2105b-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2105b-122">Child Elements</span></span>  
  
|<span data-ttu-id="2105b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="2105b-123">Element</span></span>|<span data-ttu-id="2105b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="2105b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2105b-125">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="2105b-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="2105b-126">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="2105b-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="2105b-127">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="2105b-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2105b-128">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2105b-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="2105b-129">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="2105b-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2105b-130">Коллекция переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="2105b-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2105b-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2105b-131">Parent Elements</span></span>  
  
|<span data-ttu-id="2105b-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="2105b-132">Element</span></span>|<span data-ttu-id="2105b-133">Описание</span><span class="sxs-lookup"><span data-stu-id="2105b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2105b-134">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="2105b-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="2105b-135">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="2105b-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="2105b-136">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="2105b-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2105b-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="2105b-137">Remarks</span></span>  
 <span data-ttu-id="2105b-138">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2105b-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="2105b-139">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="2105b-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="2105b-140">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2105b-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="2105b-141">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="2105b-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2105b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="2105b-142">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="2105b-143">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2105b-143">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2105b-144">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2105b-144">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
