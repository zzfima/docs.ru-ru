---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 747660df58604dd9384abefccb51ea665f97e2e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139676"
---
# <a name="trackingprofile"></a><span data-ttu-id="54b11-101">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="54b11-101">\<trackingProfile></span></span>
<span data-ttu-id="54b11-102">Представляет раздел конфигурации для создания подписки на записи в участнике отслеживания отслеживания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="54b11-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="54b11-103">Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, формируемые во время выполнения при изменении состояния экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="54b11-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="54b11-104">Запросы, заданные в разделе профиля отслеживания, определяют виды событий, возвращаемых подпиской.</span><span class="sxs-lookup"><span data-stu-id="54b11-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="54b11-105">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации, см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="54b11-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="54b11-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="54b11-106">\<system.serviceModel></span></span>  
<span data-ttu-id="54b11-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="54b11-107">\<tracking></span></span>  
<span data-ttu-id="54b11-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="54b11-108">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b11-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54b11-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54b11-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="54b11-110">Attributes and Elements</span></span>  
 <span data-ttu-id="54b11-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="54b11-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54b11-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="54b11-112">Attributes</span></span>  
  
|<span data-ttu-id="54b11-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="54b11-113">Attribute</span></span>|<span data-ttu-id="54b11-114">Описание</span><span class="sxs-lookup"><span data-stu-id="54b11-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54b11-115">имя</span><span class="sxs-lookup"><span data-stu-id="54b11-115">name</span></span>|<span data-ttu-id="54b11-116">Строка, задающая имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="54b11-116">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54b11-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="54b11-117">Child Elements</span></span>  
  
|<span data-ttu-id="54b11-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="54b11-118">Element</span></span>|<span data-ttu-id="54b11-119">Описание</span><span class="sxs-lookup"><span data-stu-id="54b11-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54b11-120">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="54b11-120">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="54b11-121">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="54b11-121">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54b11-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="54b11-122">Parent Elements</span></span>  
  
|<span data-ttu-id="54b11-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="54b11-123">Element</span></span>|<span data-ttu-id="54b11-124">Описание</span><span class="sxs-lookup"><span data-stu-id="54b11-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54b11-125">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="54b11-125">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="54b11-126">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="54b11-126">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54b11-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="54b11-127">Remarks</span></span>  
 <span data-ttu-id="54b11-128">Профиль отслеживания содержит запросы отслеживания, которые позволяют участнику подписываться на события рабочего потока, создаваемые при изменении состояния экземпляра рабочего процесса в ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="54b11-128">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="54b11-129">Исходя из потребностей, можно написать профиль с низкой детализацией, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="54b11-129">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="54b11-130">И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для последующего воспроизведения всего потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="54b11-130">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="54b11-131">Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="54b11-131">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="54b11-132">Существует множество типов запросов, которые позволяют подписаться на различные классы <xref:System.Activities.Tracking.TrackingRecord> объектов.</span><span class="sxs-lookup"><span data-stu-id="54b11-132">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="54b11-133">Полный список запросов, см. в разделе [ \<участников >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) и [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="54b11-133">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="54b11-134">В следующем примере показано профиль отслеживания в файле конфигурации, который позволяет участнику отслеживания подписаться на `Started` и `Completed` событий рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="54b11-134">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54b11-135">См. также</span><span class="sxs-lookup"><span data-stu-id="54b11-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="54b11-136">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="54b11-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="54b11-137">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="54b11-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
