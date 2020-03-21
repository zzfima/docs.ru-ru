---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 968cfa8e5402458afd6f13545ed999a472adf2e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151914"
---
# <a name="tracking"></a><span data-ttu-id="07e99-101">\<отслеживание></span><span class="sxs-lookup"><span data-stu-id="07e99-101">\<tracking></span></span>
<span data-ttu-id="07e99-102">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="07e99-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="07e99-103">Для получения дополнительной информации о отслеживании рабочего процесса и [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)его конфигурации [см.](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="07e99-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="07e99-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="07e99-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="07e99-105">&nbsp;&nbsp;[**\<Системы. СервисМодель>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="07e99-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="07e99-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<отслеживание>**</span><span class="sxs-lookup"><span data-stu-id="07e99-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07e99-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07e99-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07e99-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="07e99-108">Attributes and Elements</span></span>  
 <span data-ttu-id="07e99-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="07e99-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07e99-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="07e99-110">Attributes</span></span>  
 <span data-ttu-id="07e99-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="07e99-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07e99-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="07e99-112">Child Elements</span></span>  
  
|<span data-ttu-id="07e99-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="07e99-113">Element</span></span>|<span data-ttu-id="07e99-114">Описание</span><span class="sxs-lookup"><span data-stu-id="07e99-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07e99-115">\<участники></span><span class="sxs-lookup"><span data-stu-id="07e99-115">\<participants></span></span>](participants.md)|<span data-ttu-id="07e99-116">Коллекция элементов конфигурации, которые определяют участников, подписанных на записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="07e99-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="07e99-117">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="07e99-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="07e99-118">\<отслеживаниеПрофильная></span><span class="sxs-lookup"><span data-stu-id="07e99-118">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="07e99-119">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="07e99-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07e99-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="07e99-120">Parent Elements</span></span>  
  
|<span data-ttu-id="07e99-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="07e99-121">Element</span></span>|<span data-ttu-id="07e99-122">Описание</span><span class="sxs-lookup"><span data-stu-id="07e99-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="07e99-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="07e99-123">system.ServiceModel</span></span>|<span data-ttu-id="07e99-124">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="07e99-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07e99-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="07e99-125">Remarks</span></span>  
 <span data-ttu-id="07e99-126">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="07e99-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="07e99-127">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="07e99-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="07e99-128">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="07e99-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="07e99-129">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="07e99-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="07e99-130">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="07e99-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="07e99-131">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="07e99-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e99-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="07e99-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="07e99-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="07e99-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
