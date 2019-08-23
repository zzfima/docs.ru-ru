---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: 89f9d0e7c57f6e66b9fdffd148d9dcae5a189fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947238"
---
# <a name="workflow"></a><span data-ttu-id="f01e0-101">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="f01e0-101">\<workflow></span></span>
<span data-ttu-id="f01e0-102">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f01e0-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="f01e0-103">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Track Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f01e0-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f01e0-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="f01e0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f01e0-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f01e0-105">\<tracking></span></span>  
<span data-ttu-id="f01e0-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f01e0-106">\<trackingProfile></span></span>  
<span data-ttu-id="f01e0-107">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="f01e0-107">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f01e0-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f01e0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f01e0-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f01e0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f01e0-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f01e0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f01e0-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f01e0-111">Attributes</span></span>  
  
|<span data-ttu-id="f01e0-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f01e0-112">Attribute</span></span>|<span data-ttu-id="f01e0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f01e0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f01e0-114">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="f01e0-114">activityDefinitionId</span></span>|<span data-ttu-id="f01e0-115">Строка, указывающая идентификатор определения действия отслеживаемого рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f01e0-115">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f01e0-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f01e0-116">Child Elements</span></span>  
  
|<span data-ttu-id="f01e0-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="f01e0-117">Element</span></span>|<span data-ttu-id="f01e0-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f01e0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f01e0-119">\<Активитисчедуледкуериес ></span><span class="sxs-lookup"><span data-stu-id="f01e0-119">\<activityScheduledQueries></span></span>](activityscheduledqueries.md)|<span data-ttu-id="f01e0-120">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="f01e0-120">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="f01e0-121">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="f01e0-121">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="f01e0-122">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="f01e0-122">\<activityStateQueries></span></span>](activitystatequeries.md)|<span data-ttu-id="f01e0-123">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f01e0-123">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="f01e0-124">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f01e0-124">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="f01e0-125">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="f01e0-125">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="f01e0-126">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="f01e0-126">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="f01e0-127">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="f01e0-127">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="f01e0-128">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f01e0-128">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="f01e0-129">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="f01e0-129">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="f01e0-130">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="f01e0-130">\<cancelRequestedQueries></span></span>](cancelrequestedqueries.md)|<span data-ttu-id="f01e0-131">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="f01e0-131">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f01e0-132">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="f01e0-132">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="f01e0-133">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="f01e0-133">\<customTrackingQueries></span></span>](customtrackingqueries.md)|<span data-ttu-id="f01e0-134">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f01e0-134">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f01e0-135">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f01e0-135">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="f01e0-136">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="f01e0-136">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="f01e0-137">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="f01e0-137">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f01e0-138">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="f01e0-138">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f01e0-139">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="f01e0-139">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f01e0-140">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="f01e0-140">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="f01e0-141">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="f01e0-141">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="f01e0-142">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="f01e0-142">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f01e0-143">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f01e0-143">Parent Elements</span></span>  
  
|<span data-ttu-id="f01e0-144">Элемент</span><span class="sxs-lookup"><span data-stu-id="f01e0-144">Element</span></span>|<span data-ttu-id="f01e0-145">Описание:</span><span class="sxs-lookup"><span data-stu-id="f01e0-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f01e0-146">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f01e0-146">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="f01e0-147">Представляет раздел конфигурации для создания подписки на записи отслеживания рабочих процессов в участнике отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f01e0-147">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="f01e0-148">Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, формируемые во время выполнения при изменении состояния экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f01e0-148">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="f01e0-149">Запросы, заданные в разделе профиля отслеживания, определяют виды событий, возвращаемых подпиской.</span><span class="sxs-lookup"><span data-stu-id="f01e0-149">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f01e0-150">Примечания</span><span class="sxs-lookup"><span data-stu-id="f01e0-150">Remarks</span></span>  
 <span data-ttu-id="f01e0-151">Профили отслеживания содержат запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в результате изменения состояния экземпляра рабочего процесса в ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="f01e0-151">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="f01e0-152">Этот элемент конфигурации определяет отслеживаемый экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f01e0-152">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="f01e0-153">Исходя из потребностей, можно написать профиль с низкой детализацией, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="f01e0-153">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="f01e0-154">И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для последующего воспроизведения всего потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="f01e0-154">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="f01e0-155">Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f01e0-155">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="f01e0-156">Существует несколько типов запросов, которые позволяют подписываться на различные классы отслеживаемых записей.</span><span class="sxs-lookup"><span data-stu-id="f01e0-156">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="f01e0-157">Полный список запросов см. в списке дочерних элементов этого раздела и [профилях отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f01e0-157">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="f01e0-158">В следующем примере показан профиль отслеживания в файле конфигурации, который позволяет участнику отслеживания подписываться `Started` на события рабочего процесса и. `Completed`</span><span class="sxs-lookup"><span data-stu-id="f01e0-158">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f01e0-159">См. также</span><span class="sxs-lookup"><span data-stu-id="f01e0-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="f01e0-160">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f01e0-160">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f01e0-161">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f01e0-161">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
