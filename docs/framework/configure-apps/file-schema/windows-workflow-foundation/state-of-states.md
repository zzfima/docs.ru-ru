---
title: <state> из <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 657814eb120878cdc71cd7603d0499ff65ca50e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271438"
---
# <a name="state-of-states"></a><span data-ttu-id="2dac7-102">\<Состояние > из \<состояний ></span><span class="sxs-lookup"><span data-stu-id="2dac7-102">\<state> of \<states></span></span>
<span data-ttu-id="2dac7-103">Элемент конфигурации, содержащий состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2dac7-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="2dac7-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2dac7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="2dac7-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2dac7-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2dac7-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="2dac7-106">\<tracking></span></span>  
<span data-ttu-id="2dac7-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2dac7-107">\<trackingProfile></span></span>  
<span data-ttu-id="2dac7-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="2dac7-108">\<workflow></span></span>  
<span data-ttu-id="2dac7-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="2dac7-109">\<activityStateQueries></span></span>  
<span data-ttu-id="2dac7-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="2dac7-110">\<activityStateQuery></span></span>  
<span data-ttu-id="2dac7-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="2dac7-111">\<states></span></span>  
<span data-ttu-id="2dac7-112">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="2dac7-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dac7-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2dac7-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2dac7-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2dac7-114">Attributes and Elements</span></span>  
 <span data-ttu-id="2dac7-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2dac7-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2dac7-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2dac7-116">Attributes</span></span>  
  
|<span data-ttu-id="2dac7-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2dac7-117">Attribute</span></span>|<span data-ttu-id="2dac7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="2dac7-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2dac7-119">имя</span><span class="sxs-lookup"><span data-stu-id="2dac7-119">name</span></span>|<span data-ttu-id="2dac7-120">Строка, содержащая состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2dac7-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2dac7-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2dac7-121">Child Elements</span></span>  
 <span data-ttu-id="2dac7-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2dac7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2dac7-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2dac7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2dac7-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="2dac7-124">Element</span></span>|<span data-ttu-id="2dac7-125">Описание</span><span class="sxs-lookup"><span data-stu-id="2dac7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2dac7-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="2dac7-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="2dac7-127">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2dac7-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dac7-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="2dac7-128">Remarks</span></span>  
 <span data-ttu-id="2dac7-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2dac7-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="2dac7-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="2dac7-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="2dac7-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="2dac7-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="2dac7-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="2dac7-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="2dac7-133">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="2dac7-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2dac7-134">См. также</span><span class="sxs-lookup"><span data-stu-id="2dac7-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2dac7-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2dac7-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2dac7-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2dac7-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
