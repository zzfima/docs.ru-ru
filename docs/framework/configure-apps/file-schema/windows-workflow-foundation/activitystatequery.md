---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 560df771b44fc8ba8d192657677bf0496283b539
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945428"
---
# <a name="activitystatequery"></a><span data-ttu-id="3bce2-101">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="3bce2-101">\<activityStateQuery></span></span>
<span data-ttu-id="3bce2-102">Представляет запрос, используемый для трассировки изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3bce2-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="3bce2-103">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3bce2-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="3bce2-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="3bce2-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="3bce2-105">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="3bce2-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="3bce2-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3bce2-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3bce2-107">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="3bce2-107">\<system.serviceModel></span></span>  
<span data-ttu-id="3bce2-108">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="3bce2-108">\<tracking></span></span>  
<span data-ttu-id="3bce2-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3bce2-109">\<trackingProfile></span></span>  
<span data-ttu-id="3bce2-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="3bce2-110">\<workflow></span></span>  
<span data-ttu-id="3bce2-111">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="3bce2-111">\<activityStateQueries></span></span>  
<span data-ttu-id="3bce2-112">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="3bce2-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bce2-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bce2-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
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
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bce2-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3bce2-114">Attributes and Elements</span></span>  
 <span data-ttu-id="3bce2-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3bce2-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bce2-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3bce2-116">Attributes</span></span>  
  
|<span data-ttu-id="3bce2-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3bce2-117">Attribute</span></span>|<span data-ttu-id="3bce2-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3bce2-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3bce2-119">activityName</span><span class="sxs-lookup"><span data-stu-id="3bce2-119">activityName</span></span>|<span data-ttu-id="3bce2-120">Строка, указывающая имя действия, по которому будут фильтроваться экземпляры <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="3bce2-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3bce2-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3bce2-121">Child Elements</span></span>  
  
|<span data-ttu-id="3bce2-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="3bce2-122">Element</span></span>|<span data-ttu-id="3bce2-123">Описание</span><span class="sxs-lookup"><span data-stu-id="3bce2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bce2-124">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="3bce2-124">\<arguments></span></span>](arguments.md)|<span data-ttu-id="3bce2-125">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="3bce2-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="3bce2-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="3bce2-126">\<states></span></span>](states.md)|<span data-ttu-id="3bce2-127">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="3bce2-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="3bce2-128">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="3bce2-128">\<states></span></span>](states.md)|<span data-ttu-id="3bce2-129">Коллекция переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="3bce2-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3bce2-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3bce2-130">Parent Elements</span></span>  
  
|<span data-ttu-id="3bce2-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="3bce2-131">Element</span></span>|<span data-ttu-id="3bce2-132">Описание</span><span class="sxs-lookup"><span data-stu-id="3bce2-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bce2-133">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="3bce2-133">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="3bce2-134">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="3bce2-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3bce2-135">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="3bce2-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bce2-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="3bce2-136">Remarks</span></span>  
 <span data-ttu-id="3bce2-137">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3bce2-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="3bce2-138">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="3bce2-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="3bce2-139">Можно использовать [ \<аргументы >](arguments.md), [ \<состояния >](states.md) и [ \<состояния >](states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="3bce2-139">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="3bce2-140">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="3bce2-140">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="3bce2-141">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="3bce2-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3bce2-142">См. также</span><span class="sxs-lookup"><span data-stu-id="3bce2-142">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3bce2-143">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3bce2-143">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3bce2-144">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="3bce2-144">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
