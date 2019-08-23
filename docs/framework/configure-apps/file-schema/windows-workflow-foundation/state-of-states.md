---
title: <state> из <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 7c7326b2fd5ae39ca4c0f39fac05444802fa3d49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947498"
---
# <a name="state-of-states"></a><span data-ttu-id="d2e84-102">\<состояние > \<состояний ></span><span class="sxs-lookup"><span data-stu-id="d2e84-102">\<state> of \<states></span></span>
<span data-ttu-id="d2e84-103">Элемент конфигурации, содержащий состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d2e84-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="d2e84-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d2e84-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="d2e84-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="d2e84-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d2e84-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="d2e84-106">\<tracking></span></span>  
<span data-ttu-id="d2e84-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d2e84-107">\<trackingProfile></span></span>  
<span data-ttu-id="d2e84-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d2e84-108">\<workflow></span></span>  
<span data-ttu-id="d2e84-109">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="d2e84-109">\<activityStateQueries></span></span>  
<span data-ttu-id="d2e84-110">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="d2e84-110">\<activityStateQuery></span></span>  
<span data-ttu-id="d2e84-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="d2e84-111">\<states></span></span>  
<span data-ttu-id="d2e84-112">\<> состояния</span><span class="sxs-lookup"><span data-stu-id="d2e84-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e84-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2e84-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2e84-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d2e84-114">Attributes and Elements</span></span>  
 <span data-ttu-id="d2e84-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d2e84-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2e84-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d2e84-116">Attributes</span></span>  
  
|<span data-ttu-id="d2e84-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d2e84-117">Attribute</span></span>|<span data-ttu-id="d2e84-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d2e84-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2e84-119">имя</span><span class="sxs-lookup"><span data-stu-id="d2e84-119">name</span></span>|<span data-ttu-id="d2e84-120">Строка, содержащая состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d2e84-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2e84-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d2e84-121">Child Elements</span></span>  
 <span data-ttu-id="d2e84-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="d2e84-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2e84-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d2e84-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d2e84-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="d2e84-124">Element</span></span>|<span data-ttu-id="d2e84-125">Описание</span><span class="sxs-lookup"><span data-stu-id="d2e84-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2e84-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="d2e84-126">\<states></span></span>](states-of-activitystatequery.md)|<span data-ttu-id="d2e84-127">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d2e84-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2e84-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="d2e84-128">Remarks</span></span>  
 <span data-ttu-id="d2e84-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d2e84-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="d2e84-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="d2e84-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="d2e84-131">Можно использовать [ \<аргументы >](arguments.md), [ \<состояния >](states.md) и [ \<состояния >](states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="d2e84-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="d2e84-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="d2e84-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="d2e84-133">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="d2e84-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2e84-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d2e84-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d2e84-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d2e84-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d2e84-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="d2e84-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
