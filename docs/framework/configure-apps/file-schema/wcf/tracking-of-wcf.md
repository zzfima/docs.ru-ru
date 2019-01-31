---
title: <tracking> для WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: ddaf6f7871b4d10961b615f74d1ed49dd76d379a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268253"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="794ed-102">\<Отслеживание > из WCF</span><span class="sxs-lookup"><span data-stu-id="794ed-102">\<tracking> of WCF</span></span>
<span data-ttu-id="794ed-103">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="794ed-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="794ed-104">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации, см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания для рабочего процесса](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="794ed-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
 <span data-ttu-id="794ed-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="794ed-105">\<system.serviceModel></span></span>  
<span data-ttu-id="794ed-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="794ed-106">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="794ed-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="794ed-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
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
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="794ed-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="794ed-108">Attributes and Elements</span></span>  
 <span data-ttu-id="794ed-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="794ed-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="794ed-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="794ed-110">Attributes</span></span>  
 <span data-ttu-id="794ed-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="794ed-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="794ed-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="794ed-112">Child Elements</span></span>  
  
|<span data-ttu-id="794ed-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="794ed-113">Element</span></span>|<span data-ttu-id="794ed-114">Описание</span><span class="sxs-lookup"><span data-stu-id="794ed-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="794ed-115">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="794ed-115">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="794ed-116">Коллекция элементов конфигурации, которые определяют участников, подписки на записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="794ed-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="794ed-117">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="794ed-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="794ed-118">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="794ed-118">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="794ed-119">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="794ed-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="794ed-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="794ed-120">Parent Elements</span></span>  
  
|<span data-ttu-id="794ed-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="794ed-121">Element</span></span>|<span data-ttu-id="794ed-122">Описание</span><span class="sxs-lookup"><span data-stu-id="794ed-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="794ed-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="794ed-123">system.ServiceModel</span></span>|<span data-ttu-id="794ed-124">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="794ed-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="794ed-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="794ed-125">Remarks</span></span>  
 <span data-ttu-id="794ed-126">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="794ed-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="794ed-127">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="794ed-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="794ed-128">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="794ed-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="794ed-129">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="794ed-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="794ed-130">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="794ed-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="794ed-131">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="794ed-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="794ed-132">См. также</span><span class="sxs-lookup"><span data-stu-id="794ed-132">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="794ed-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="794ed-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
