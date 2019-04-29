---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: d6c23bb0b819b5f22367a93db0dec64787449664
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613486"
---
# <a name="workflow"></a><span data-ttu-id="dcf84-101">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="dcf84-101">\<workflow></span></span>
<span data-ttu-id="dcf84-102">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dcf84-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="dcf84-103">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации, см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dcf84-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="dcf84-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dcf84-104">\<system.serviceModel></span></span>  
<span data-ttu-id="dcf84-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="dcf84-105">\<tracking></span></span>  
<span data-ttu-id="dcf84-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dcf84-106">\<trackingProfile></span></span>  
<span data-ttu-id="dcf84-107">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="dcf84-107">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf84-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcf84-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcf84-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dcf84-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dcf84-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dcf84-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcf84-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dcf84-111">Attributes</span></span>  
  
|<span data-ttu-id="dcf84-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dcf84-112">Attribute</span></span>|<span data-ttu-id="dcf84-113">Описание</span><span class="sxs-lookup"><span data-stu-id="dcf84-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dcf84-114">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="dcf84-114">activityDefinitionId</span></span>|<span data-ttu-id="dcf84-115">Строка, указывающая идентификатор определения действия отслеживаемого рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dcf84-115">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dcf84-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dcf84-116">Child Elements</span></span>  
  
|<span data-ttu-id="dcf84-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="dcf84-117">Element</span></span>|<span data-ttu-id="dcf84-118">Описание</span><span class="sxs-lookup"><span data-stu-id="dcf84-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcf84-119">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="dcf84-119">\<activityScheduledQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledqueries.md)|<span data-ttu-id="dcf84-120">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="dcf84-120">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="dcf84-121">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="dcf84-121">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="dcf84-122">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="dcf84-122">\<activityStateQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequeries.md)|<span data-ttu-id="dcf84-123">Представляет коллекцию запросов, которые используются для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dcf84-123">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="dcf84-124">Например можно хранить список всякий раз по завершении действия «Send E-Mail» внутри рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dcf84-124">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="dcf84-125">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="dcf84-125">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="dcf84-126">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="dcf84-126">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="dcf84-127">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="dcf84-127">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="dcf84-128">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dcf84-128">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="dcf84-129">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="dcf84-129">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="dcf84-130">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="dcf84-130">\<cancelRequestedQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedqueries.md)|<span data-ttu-id="dcf84-131">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="dcf84-131">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="dcf84-132">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="dcf84-132">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="dcf84-133">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="dcf84-133">\<customTrackingQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingqueries.md)|<span data-ttu-id="dcf84-134">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="dcf84-134">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="dcf84-135">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="dcf84-135">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="dcf84-136">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="dcf84-136">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="dcf84-137">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="dcf84-137">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dcf84-138">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="dcf84-138">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="dcf84-139">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="dcf84-139">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="dcf84-140">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="dcf84-140">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="dcf84-141">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="dcf84-141">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="dcf84-142">Представляет коллекцию элементов конфигурации, которые отслеживают изменения жизненного цикла экземпляра рабочего процесса, например события «запущен» или «завершен».</span><span class="sxs-lookup"><span data-stu-id="dcf84-142">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dcf84-143">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dcf84-143">Parent Elements</span></span>  
  
|<span data-ttu-id="dcf84-144">Элемент</span><span class="sxs-lookup"><span data-stu-id="dcf84-144">Element</span></span>|<span data-ttu-id="dcf84-145">Описание:</span><span class="sxs-lookup"><span data-stu-id="dcf84-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcf84-146">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dcf84-146">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="dcf84-147">Представляет раздел конфигурации для создания подписки на записи в участнике отслеживания отслеживания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dcf84-147">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="dcf84-148">Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, формируемые во время выполнения при изменении состояния экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dcf84-148">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="dcf84-149">Запросы, заданные в разделе профиля отслеживания, определяют виды событий, возвращаемых подпиской.</span><span class="sxs-lookup"><span data-stu-id="dcf84-149">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcf84-150">Примечания</span><span class="sxs-lookup"><span data-stu-id="dcf84-150">Remarks</span></span>  
 <span data-ttu-id="dcf84-151">Профили отслеживания содержат запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в результате изменения состояния экземпляра рабочего процесса в ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="dcf84-151">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="dcf84-152">Этот элемент конфигурации определяет отслеживаемый экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dcf84-152">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="dcf84-153">Исходя из потребностей, можно написать профиль с низкой детализацией, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="dcf84-153">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="dcf84-154">И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для последующего воспроизведения всего потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="dcf84-154">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="dcf84-155">Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="dcf84-155">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="dcf84-156">Существует множество типов запросов, которые позволяют подписываться на различные классы записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="dcf84-156">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="dcf84-157">Полный список запросов, см. в статье в списке дочерних элементов в этом разделе и [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dcf84-157">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="dcf84-158">В следующем примере показано профиль отслеживания в файле конфигурации, который позволяет участнику отслеживания подписаться на `Started` и `Completed` событий рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dcf84-158">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dcf84-159">См. также</span><span class="sxs-lookup"><span data-stu-id="dcf84-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="dcf84-160">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="dcf84-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dcf84-161">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="dcf84-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
