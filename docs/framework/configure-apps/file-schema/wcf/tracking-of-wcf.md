---
title: <tracking>WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: e8f74d635299a965b754536234e6be28e4e7a104
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399422"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="c299d-102">\<Отслеживание > WCF</span><span class="sxs-lookup"><span data-stu-id="c299d-102">\<tracking> of WCF</span></span>
<span data-ttu-id="c299d-103">Представляет раздел конфигурации для определения настроек отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c299d-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="c299d-104">Дополнительные сведения об отслеживании рабочих процессов и его конфигурации см. в разделе Отслеживание рабочего процесса [и трассировка](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) и [Настройка отслеживания рабочего процесса](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="c299d-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="c299d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c299d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c299d-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c299d-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c299d-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<Отслеживание >**</span><span class="sxs-lookup"><span data-stu-id="c299d-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c299d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c299d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c299d-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c299d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c299d-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c299d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c299d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c299d-111">Attributes</span></span>  
 <span data-ttu-id="c299d-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="c299d-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c299d-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c299d-113">Child Elements</span></span>  
  
|<span data-ttu-id="c299d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="c299d-114">Element</span></span>|<span data-ttu-id="c299d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c299d-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c299d-116">\<Участники ></span><span class="sxs-lookup"><span data-stu-id="c299d-116">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="c299d-117">Коллекция элементов конфигурации, определяющих участников, которые подписываются на отслеживание записей.</span><span class="sxs-lookup"><span data-stu-id="c299d-117">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="c299d-118">Участники содержат логику обработки полезных данных из записей отслеживания (например, они могут записать данные в файл).</span><span class="sxs-lookup"><span data-stu-id="c299d-118">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="c299d-119">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c299d-119">\<trackingProfile></span></span>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="c299d-120">Профиль отслеживания для фильтрации записей отслеживания, выдаваемых экземпляром рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c299d-120">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c299d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c299d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c299d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="c299d-122">Element</span></span>|<span data-ttu-id="c299d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c299d-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c299d-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c299d-124">system.ServiceModel</span></span>|<span data-ttu-id="c299d-125">Корневой элемент всех элементов конфигурации рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c299d-125">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c299d-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="c299d-126">Remarks</span></span>  
 <span data-ttu-id="c299d-127">Отслеживание позволяет исследовать выполнение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c299d-127">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="c299d-128">Инфраструктура отслеживания рабочего процесса инструментирует процесс таким образом, что выдаются записи, отражающие ключевые события выполнения.</span><span class="sxs-lookup"><span data-stu-id="c299d-128">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="c299d-129">Например, записи отслеживания создаются при запуске и завершении экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c299d-129">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="c299d-130">Отслеживание также позволяет извлекать важные бизнес-данные, связанные с переменными рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c299d-130">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="c299d-131">Например, если рабочий процесс представляет собой систему обработки заказов, то вместе с записью отслеживания можно извлечь идентификатор заказа.</span><span class="sxs-lookup"><span data-stu-id="c299d-131">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="c299d-132">В общем, функции отслеживания WF обеспечивают диагностику и анализ исполнения рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="c299d-132">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c299d-133">См. также</span><span class="sxs-lookup"><span data-stu-id="c299d-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="c299d-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c299d-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
