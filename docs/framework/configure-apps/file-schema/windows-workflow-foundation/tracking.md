---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 28d73bb74c4a49052589040adc26194b1300668c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397606"
---
# <a name="tracking"></a><span data-ttu-id="18c68-101">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="18c68-101">\<tracking></span></span>
<span data-ttu-id="18c68-102">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="18c68-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="18c68-103">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе Отслеживание рабочего процесса [и трассировка](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания рабочего процесса](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="18c68-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="18c68-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="18c68-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="18c68-105">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="18c68-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="18c68-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Отслеживание >**</span><span class="sxs-lookup"><span data-stu-id="18c68-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c68-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18c68-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18c68-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18c68-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18c68-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18c68-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18c68-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18c68-110">Attributes</span></span>  
 <span data-ttu-id="18c68-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="18c68-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="18c68-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18c68-112">Child Elements</span></span>  
  
|<span data-ttu-id="18c68-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="18c68-113">Element</span></span>|<span data-ttu-id="18c68-114">Описание</span><span class="sxs-lookup"><span data-stu-id="18c68-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18c68-115">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="18c68-115">\<participants></span></span>](participants.md)|<span data-ttu-id="18c68-116">Коллекция элементов конфигурации, определяющих участников, которые подписываются на отслеживание записей.</span><span class="sxs-lookup"><span data-stu-id="18c68-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="18c68-117">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="18c68-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="18c68-118">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="18c68-118">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="18c68-119">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="18c68-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18c68-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18c68-120">Parent Elements</span></span>  
  
|<span data-ttu-id="18c68-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="18c68-121">Element</span></span>|<span data-ttu-id="18c68-122">Описание</span><span class="sxs-lookup"><span data-stu-id="18c68-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18c68-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="18c68-123">system.ServiceModel</span></span>|<span data-ttu-id="18c68-124">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="18c68-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18c68-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="18c68-125">Remarks</span></span>  
 <span data-ttu-id="18c68-126">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="18c68-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="18c68-127">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="18c68-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="18c68-128">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="18c68-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="18c68-129">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="18c68-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="18c68-130">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="18c68-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="18c68-131">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="18c68-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c68-132">См. также</span><span class="sxs-lookup"><span data-stu-id="18c68-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="18c68-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="18c68-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
