---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 31490c7425572909cc30fe4237af9309754b68e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072249"
---
# <a name="tracking"></a><span data-ttu-id="8d9be-101">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="8d9be-101">\<tracking></span></span>
<span data-ttu-id="8d9be-102">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8d9be-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="8d9be-103">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации, см. в разделе [отслеживание и трассировка рабочих процессов](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания для рабочего процесса](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8d9be-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="8d9be-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8d9be-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8d9be-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="8d9be-105">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d9be-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d9be-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d9be-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8d9be-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8d9be-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8d9be-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d9be-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d9be-109">Attributes</span></span>  
 <span data-ttu-id="8d9be-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8d9be-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8d9be-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d9be-111">Child Elements</span></span>  
  
|<span data-ttu-id="8d9be-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d9be-112">Element</span></span>|<span data-ttu-id="8d9be-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8d9be-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d9be-114">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="8d9be-114">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="8d9be-115">Коллекция элементов конфигурации, которые определяют участников, подписки на записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="8d9be-115">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="8d9be-116">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="8d9be-116">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="8d9be-117">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8d9be-117">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="8d9be-118">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8d9be-118">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d9be-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d9be-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8d9be-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d9be-120">Element</span></span>|<span data-ttu-id="8d9be-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8d9be-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d9be-122">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8d9be-122">system.ServiceModel</span></span>|<span data-ttu-id="8d9be-123">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8d9be-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d9be-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d9be-124">Remarks</span></span>  
 <span data-ttu-id="8d9be-125">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8d9be-125">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="8d9be-126">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="8d9be-126">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="8d9be-127">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8d9be-127">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="8d9be-128">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8d9be-128">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="8d9be-129">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="8d9be-129">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="8d9be-130">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="8d9be-130">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d9be-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8d9be-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="8d9be-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8d9be-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
