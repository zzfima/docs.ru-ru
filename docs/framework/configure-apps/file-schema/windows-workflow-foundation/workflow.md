---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: 5205f9ab89297c0e55c3e5e0c03b9e3fef36963a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397570"
---
# <a name="workflow"></a><span data-ttu-id="81fef-101">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="81fef-101">\<workflow></span></span>
<span data-ttu-id="81fef-102">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="81fef-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="81fef-103">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Track Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="81fef-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="81fef-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="81fef-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="81fef-105">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="81fef-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="81fef-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="81fef-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="81fef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="81fef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="81fef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> рабочего процесса**</span><span class="sxs-lookup"><span data-stu-id="81fef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81fef-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81fef-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String" 
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String" 
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String" 
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81fef-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="81fef-110">Attributes and Elements</span></span>  
 <span data-ttu-id="81fef-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="81fef-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81fef-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="81fef-112">Attributes</span></span>  
  
|<span data-ttu-id="81fef-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="81fef-113">Attribute</span></span>|<span data-ttu-id="81fef-114">Описание</span><span class="sxs-lookup"><span data-stu-id="81fef-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81fef-115">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="81fef-115">activityDefinitionId</span></span>|<span data-ttu-id="81fef-116">Строка, указывающая идентификатор определения действия отслеживаемого рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="81fef-116">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81fef-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="81fef-117">Child Elements</span></span>  
  
|<span data-ttu-id="81fef-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="81fef-118">Element</span></span>|<span data-ttu-id="81fef-119">Описание</span><span class="sxs-lookup"><span data-stu-id="81fef-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81fef-120">\<Активитисчедуледкуериес ></span><span class="sxs-lookup"><span data-stu-id="81fef-120">\<activityScheduledQueries></span></span>](activityscheduledqueries.md)|<span data-ttu-id="81fef-121">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="81fef-121">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="81fef-122">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="81fef-122">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="81fef-123">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="81fef-123">\<activityStateQueries></span></span>](activitystatequeries.md)|<span data-ttu-id="81fef-124">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="81fef-124">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="81fef-125">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="81fef-125">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="81fef-126">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="81fef-126">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="81fef-127">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="81fef-127">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="81fef-128">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="81fef-128">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="81fef-129">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="81fef-129">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="81fef-130">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="81fef-130">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="81fef-131">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="81fef-131">\<cancelRequestedQueries></span></span>](cancelrequestedqueries.md)|<span data-ttu-id="81fef-132">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="81fef-132">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="81fef-133">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="81fef-133">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="81fef-134">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="81fef-134">\<customTrackingQueries></span></span>](customtrackingqueries.md)|<span data-ttu-id="81fef-135">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="81fef-135">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="81fef-136">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="81fef-136">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="81fef-137">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="81fef-137">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="81fef-138">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="81fef-138">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="81fef-139">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="81fef-139">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="81fef-140">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="81fef-140">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="81fef-141">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="81fef-141">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="81fef-142">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="81fef-142">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="81fef-143">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="81fef-143">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="81fef-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="81fef-144">Parent Elements</span></span>  
  
|<span data-ttu-id="81fef-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="81fef-145">Element</span></span>|<span data-ttu-id="81fef-146">Описание:</span><span class="sxs-lookup"><span data-stu-id="81fef-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81fef-147">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="81fef-147">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="81fef-148">Представляет раздел конфигурации для создания подписки на записи отслеживания рабочих процессов в участнике отслеживания.</span><span class="sxs-lookup"><span data-stu-id="81fef-148">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="81fef-149">Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, формируемые во время выполнения при изменении состояния экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="81fef-149">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="81fef-150">Запросы, заданные в разделе профиля отслеживания, определяют виды событий, возвращаемых подпиской.</span><span class="sxs-lookup"><span data-stu-id="81fef-150">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81fef-151">Примечания</span><span class="sxs-lookup"><span data-stu-id="81fef-151">Remarks</span></span>  
 <span data-ttu-id="81fef-152">Профили отслеживания содержат запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в результате изменения состояния экземпляра рабочего процесса в ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="81fef-152">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="81fef-153">Этот элемент конфигурации определяет отслеживаемый экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="81fef-153">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="81fef-154">Исходя из потребностей, можно написать профиль с низкой детализацией, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="81fef-154">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="81fef-155">И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для последующего воспроизведения всего потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="81fef-155">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="81fef-156">Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="81fef-156">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="81fef-157">Существует несколько типов запросов, которые позволяют подписываться на различные классы отслеживаемых записей.</span><span class="sxs-lookup"><span data-stu-id="81fef-157">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="81fef-158">Полный список запросов см. в списке дочерних элементов этого раздела и [профилях отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="81fef-158">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="81fef-159">В следующем примере показан профиль отслеживания в файле конфигурации, который позволяет участнику отслеживания подписываться `Started` на события рабочего процесса и. `Completed`</span><span class="sxs-lookup"><span data-stu-id="81fef-159">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81fef-160">См. также</span><span class="sxs-lookup"><span data-stu-id="81fef-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="81fef-161">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="81fef-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="81fef-162">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="81fef-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
