---
title: <states> из <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 97664518f7c7c0078cef1c81035724a02c9857c0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257739"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="0bf86-102">\<состояния > из \<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="0bf86-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="0bf86-103">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="0bf86-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="0bf86-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0bf86-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0bf86-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0bf86-105">\<system.serviceModel></span></span>  
<span data-ttu-id="0bf86-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="0bf86-106">\<tracking></span></span>  
<span data-ttu-id="0bf86-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0bf86-107">\<trackingProfile></span></span>  
<span data-ttu-id="0bf86-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="0bf86-108">\<workflow></span></span>  
<span data-ttu-id="0bf86-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="0bf86-109">\<activityStateQueries></span></span>  
<span data-ttu-id="0bf86-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="0bf86-110">\<activityStateQuery></span></span>  
<span data-ttu-id="0bf86-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="0bf86-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bf86-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bf86-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bf86-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0bf86-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0bf86-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0bf86-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bf86-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0bf86-115">Attributes</span></span>  
 <span data-ttu-id="0bf86-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0bf86-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0bf86-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0bf86-117">Child Elements</span></span>  
  
|<span data-ttu-id="0bf86-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="0bf86-118">Element</span></span>|<span data-ttu-id="0bf86-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="0bf86-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bf86-120">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="0bf86-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="0bf86-121">Элемент конфигурации, содержащий состояния подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="0bf86-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0bf86-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0bf86-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0bf86-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="0bf86-123">Element</span></span>|<span data-ttu-id="0bf86-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="0bf86-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bf86-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="0bf86-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="0bf86-126">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="0bf86-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0bf86-127">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="0bf86-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bf86-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="0bf86-128">Remarks</span></span>  
 <span data-ttu-id="0bf86-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0bf86-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="0bf86-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="0bf86-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="0bf86-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="0bf86-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="0bf86-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="0bf86-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="0bf86-133">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="0bf86-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0bf86-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0bf86-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0bf86-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0bf86-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0bf86-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="0bf86-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
