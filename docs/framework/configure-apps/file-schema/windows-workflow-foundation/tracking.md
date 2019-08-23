---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 79230c65d8eb8c15cef5dce73698448ca7b1e003
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947315"
---
# <a name="tracking"></a><span data-ttu-id="f99a5-101">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f99a5-101">\<tracking></span></span>
<span data-ttu-id="f99a5-102">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f99a5-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="f99a5-103">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе Отслеживание рабочего процесса [и трассировка](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания рабочего процесса](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f99a5-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="f99a5-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="f99a5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f99a5-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f99a5-105">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f99a5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f99a5-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f99a5-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f99a5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f99a5-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f99a5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f99a5-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f99a5-109">Attributes</span></span>  
 <span data-ttu-id="f99a5-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="f99a5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f99a5-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f99a5-111">Child Elements</span></span>  
  
|<span data-ttu-id="f99a5-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="f99a5-112">Element</span></span>|<span data-ttu-id="f99a5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f99a5-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f99a5-114">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="f99a5-114">\<participants></span></span>](participants.md)|<span data-ttu-id="f99a5-115">Коллекция элементов конфигурации, определяющих участников, которые подписываются на отслеживание записей.</span><span class="sxs-lookup"><span data-stu-id="f99a5-115">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="f99a5-116">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="f99a5-116">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="f99a5-117">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f99a5-117">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="f99a5-118">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f99a5-118">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f99a5-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f99a5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f99a5-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="f99a5-120">Element</span></span>|<span data-ttu-id="f99a5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f99a5-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f99a5-122">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f99a5-122">system.ServiceModel</span></span>|<span data-ttu-id="f99a5-123">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f99a5-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f99a5-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="f99a5-124">Remarks</span></span>  
 <span data-ttu-id="f99a5-125">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f99a5-125">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="f99a5-126">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="f99a5-126">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="f99a5-127">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f99a5-127">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="f99a5-128">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f99a5-128">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="f99a5-129">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="f99a5-129">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="f99a5-130">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="f99a5-130">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f99a5-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f99a5-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="f99a5-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f99a5-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
