---
title: <trackingProfile>WCF
ms.date: 10/08/2018
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: c5df03d63653e658a23a36e8943c06f156d2ae00
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854938"
---
# <a name="trackingprofile-of-wcf"></a><span data-ttu-id="4cc51-102">\<trackingProfile > WCF</span><span class="sxs-lookup"><span data-stu-id="4cc51-102">\<trackingProfile> of WCF</span></span>
<span data-ttu-id="4cc51-103">Представляет раздел конфигурации для создания подписки на записи отслеживания рабочих процессов в участнике отслеживания.</span><span class="sxs-lookup"><span data-stu-id="4cc51-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="4cc51-104">Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, формируемые во время выполнения при изменении состояния экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4cc51-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="4cc51-105">Запросы, заданные в разделе профиля отслеживания, определяют виды событий, возвращаемых подпиской.</span><span class="sxs-lookup"><span data-stu-id="4cc51-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
<span data-ttu-id="4cc51-106">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Track Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4cc51-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="4cc51-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4cc51-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4cc51-108">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4cc51-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4cc51-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4cc51-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="4cc51-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="4cc51-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="4cc51-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<trackingProfile >**</span><span class="sxs-lookup"><span data-stu-id="4cc51-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trackingProfile>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc51-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4cc51-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4cc51-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4cc51-113">Attributes and Elements</span></span>  

<span data-ttu-id="4cc51-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4cc51-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4cc51-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4cc51-115">Attributes</span></span>  
  
|<span data-ttu-id="4cc51-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4cc51-116">Attribute</span></span>|<span data-ttu-id="4cc51-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4cc51-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4cc51-118">имя</span><span class="sxs-lookup"><span data-stu-id="4cc51-118">name</span></span>|<span data-ttu-id="4cc51-119">Строка, задающая имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="4cc51-119">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4cc51-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4cc51-120">Child Elements</span></span>  
  
|<span data-ttu-id="4cc51-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="4cc51-121">Element</span></span>|<span data-ttu-id="4cc51-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4cc51-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4cc51-123">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="4cc51-123">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="4cc51-124">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4cc51-124">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4cc51-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4cc51-125">Parent Elements</span></span>  
  
|<span data-ttu-id="4cc51-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="4cc51-126">Element</span></span>|<span data-ttu-id="4cc51-127">Описание</span><span class="sxs-lookup"><span data-stu-id="4cc51-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4cc51-128">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="4cc51-128">\<tracking></span></span>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="4cc51-129">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4cc51-129">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cc51-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="4cc51-130">Remarks</span></span>  
 <span data-ttu-id="4cc51-131">Профиль отслеживания содержит запросы отслеживания, которые позволяют участнику подписываться на события рабочего потока, создаваемые при изменении состояния экземпляра рабочего процесса в ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="4cc51-131">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="4cc51-132">Исходя из потребностей, можно написать профиль с низкой детализацией, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="4cc51-132">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="4cc51-133">И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для последующего воспроизведения всего потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="4cc51-133">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="4cc51-134">Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="4cc51-134">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="4cc51-135">Существует несколько типов запросов, которые позволяют подписываться на разные классы <xref:System.Activities.Tracking.TrackingRecord> объектов.</span><span class="sxs-lookup"><span data-stu-id="4cc51-135">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="4cc51-136">Полный список запросов см. в разделе [ \<Участники >](../windows-workflow-foundation/participants.md) и [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4cc51-136">For a complete list of queries, see [\<participants>](../windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="4cc51-137">В следующем примере показан профиль отслеживания в файле конфигурации, который позволяет участнику отслеживания подписываться `Started` на события рабочего процесса и. `Completed`</span><span class="sxs-lookup"><span data-stu-id="4cc51-137">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4cc51-138">См. также</span><span class="sxs-lookup"><span data-stu-id="4cc51-138">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="4cc51-139">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="4cc51-139">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4cc51-140">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="4cc51-140">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
