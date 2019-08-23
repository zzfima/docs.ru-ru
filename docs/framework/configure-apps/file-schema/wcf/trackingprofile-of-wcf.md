---
title: <trackingProfile>WCF
ms.date: 10/08/2018
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: 79326322eeed1f6b73729da675eb02fe6de670df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932354"
---
# <a name="trackingprofile-of-wcf"></a><span data-ttu-id="1f936-102">\<trackingProfile > WCF</span><span class="sxs-lookup"><span data-stu-id="1f936-102">\<trackingProfile> of WCF</span></span>
<span data-ttu-id="1f936-103">Представляет раздел конфигурации для создания подписки на записи отслеживания рабочих процессов в участнике отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1f936-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="1f936-104">Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, формируемые во время выполнения при изменении состояния экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1f936-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="1f936-105">Запросы, заданные в разделе профиля отслеживания, определяют виды событий, возвращаемых подпиской.</span><span class="sxs-lookup"><span data-stu-id="1f936-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="1f936-106">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Track Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1f936-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="1f936-107">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="1f936-107">\<system.serviceModel></span></span>  
<span data-ttu-id="1f936-108">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="1f936-108">\<tracking></span></span>  
<span data-ttu-id="1f936-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1f936-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f936-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f936-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String" />
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String">
              <arguments>
                <argument name="String" />
              </arguments>
              <states>
                <state name="String" />
              </states>
              <variables>
                <variable name="String" />
              </variables>
            </activityStateQuery>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestedQueries>
            <cancelRequestedQuery activityName="String"
                                  childActivityName="String" />
          </cancelRequestedQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String" />
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery faultSourceActivityName="String"
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <stateMachineStateQueries>
            <stateMachineStateQuery activityName="String" />
          </stateMachineStateQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f936-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1f936-111">Attributes and Elements</span></span>  

<span data-ttu-id="1f936-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1f936-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f936-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1f936-113">Attributes</span></span>  
  
|<span data-ttu-id="1f936-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1f936-114">Attribute</span></span>|<span data-ttu-id="1f936-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1f936-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f936-116">имя</span><span class="sxs-lookup"><span data-stu-id="1f936-116">name</span></span>|<span data-ttu-id="1f936-117">Строка, задающая имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1f936-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f936-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1f936-118">Child Elements</span></span>  
  
|<span data-ttu-id="1f936-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="1f936-119">Element</span></span>|<span data-ttu-id="1f936-120">Описание</span><span class="sxs-lookup"><span data-stu-id="1f936-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f936-121">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="1f936-121">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="1f936-122">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1f936-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f936-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1f936-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1f936-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="1f936-124">Element</span></span>|<span data-ttu-id="1f936-125">Описание</span><span class="sxs-lookup"><span data-stu-id="1f936-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f936-126">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="1f936-126">\<tracking></span></span>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="1f936-127">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1f936-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f936-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f936-128">Remarks</span></span>  
 <span data-ttu-id="1f936-129">Профиль отслеживания содержит запросы отслеживания, которые позволяют участнику подписываться на события рабочего потока, создаваемые при изменении состояния экземпляра рабочего процесса в ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="1f936-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="1f936-130">Исходя из потребностей, можно написать профиль с низкой детализацией, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="1f936-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="1f936-131">И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для последующего воспроизведения всего потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="1f936-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="1f936-132">Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1f936-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="1f936-133">Существует несколько типов запросов, которые позволяют подписываться на разные классы <xref:System.Activities.Tracking.TrackingRecord> объектов.</span><span class="sxs-lookup"><span data-stu-id="1f936-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="1f936-134">Полный список запросов см. в разделе [ \<Участники >](../windows-workflow-foundation/participants.md) и [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1f936-134">For a complete list of queries, see [\<participants>](../windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="1f936-135">В следующем примере показан профиль отслеживания в файле конфигурации, который позволяет участнику отслеживания подписываться `Started` на события рабочего процесса и. `Completed`</span><span class="sxs-lookup"><span data-stu-id="1f936-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="Sample Tracking Profile">
        <workflow activityDefinitionId="*">
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="Started" />
                <state name="Completed" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="1f936-136">См. также</span><span class="sxs-lookup"><span data-stu-id="1f936-136">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="1f936-137">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1f936-137">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1f936-138">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="1f936-138">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
