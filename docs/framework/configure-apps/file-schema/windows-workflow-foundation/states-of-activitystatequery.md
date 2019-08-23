---
title: <states> из <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 50827577374859133e6c673e8850e145b4ccab73
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947432"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="ed3c3-102">\<состояния > \<активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="ed3c3-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="ed3c3-103">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="ed3c3-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ed3c3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ed3c3-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="ed3c3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ed3c3-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="ed3c3-106">\<tracking></span></span>  
<span data-ttu-id="ed3c3-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ed3c3-107">\<trackingProfile></span></span>  
<span data-ttu-id="ed3c3-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="ed3c3-108">\<workflow></span></span>  
<span data-ttu-id="ed3c3-109">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="ed3c3-109">\<activityStateQueries></span></span>  
<span data-ttu-id="ed3c3-110">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="ed3c3-110">\<activityStateQuery></span></span>  
<span data-ttu-id="ed3c3-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="ed3c3-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3c3-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed3c3-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed3c3-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ed3c3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ed3c3-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed3c3-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ed3c3-115">Attributes</span></span>  
 <span data-ttu-id="ed3c3-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ed3c3-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ed3c3-117">Child Elements</span></span>  
  
|<span data-ttu-id="ed3c3-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed3c3-118">Element</span></span>|<span data-ttu-id="ed3c3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ed3c3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed3c3-120">\<> состояния</span><span class="sxs-lookup"><span data-stu-id="ed3c3-120">\<state></span></span>](state-of-states.md)|<span data-ttu-id="ed3c3-121">Элемент конфигурации, содержащий состояния подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed3c3-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ed3c3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ed3c3-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed3c3-123">Element</span></span>|<span data-ttu-id="ed3c3-124">Описание</span><span class="sxs-lookup"><span data-stu-id="ed3c3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed3c3-125">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="ed3c3-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="ed3c3-126">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ed3c3-127">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed3c3-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed3c3-128">Remarks</span></span>  
 <span data-ttu-id="ed3c3-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ed3c3-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ed3c3-131">Можно использовать [ \<аргументы >](arguments.md), [ \<состояния >](states.md) и [ \<состояния >](states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="ed3c3-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="ed3c3-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ed3c3-133">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="ed3c3-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ed3c3-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ed3c3-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ed3c3-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ed3c3-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ed3c3-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ed3c3-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
