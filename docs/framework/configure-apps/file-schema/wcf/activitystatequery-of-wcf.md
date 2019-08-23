---
title: <activityStateQuery>WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: ce7505896b9c5bb605bb0f67d735cb324f4fd493
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926902"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="6046f-102">\<Активитистатекуери > WCF</span><span class="sxs-lookup"><span data-stu-id="6046f-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="6046f-103">Представляет запрос, используемый для трассировки изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6046f-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="6046f-104">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6046f-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="6046f-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="6046f-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="6046f-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="6046f-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="6046f-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6046f-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="6046f-108">\<> отслеживания > \<System. ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6046f-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="6046f-109">\<Профили > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6046f-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="6046f-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6046f-110">\<workflow></span></span>  
<span data-ttu-id="6046f-111">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="6046f-111">\<activityStateQueries></span></span>  
<span data-ttu-id="6046f-112">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="6046f-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6046f-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6046f-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6046f-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="6046f-114">Attributes and elements</span></span>  

<span data-ttu-id="6046f-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6046f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6046f-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6046f-116">Attributes</span></span>  
  
|<span data-ttu-id="6046f-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6046f-117">Attribute</span></span>|<span data-ttu-id="6046f-118">Описание</span><span class="sxs-lookup"><span data-stu-id="6046f-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6046f-119">activityName</span><span class="sxs-lookup"><span data-stu-id="6046f-119">activityName</span></span>|<span data-ttu-id="6046f-120">Строка, указывающая имя действия, по которому будут фильтроваться экземпляры <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="6046f-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6046f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6046f-121">Child elements</span></span>  
  
|<span data-ttu-id="6046f-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="6046f-122">Element</span></span>|<span data-ttu-id="6046f-123">Описание</span><span class="sxs-lookup"><span data-stu-id="6046f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6046f-124">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="6046f-124">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="6046f-125">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="6046f-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="6046f-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="6046f-126">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="6046f-127">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="6046f-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="6046f-128">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="6046f-128">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="6046f-129">Коллекция переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="6046f-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6046f-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6046f-130">Parent elements</span></span>  
  
|<span data-ttu-id="6046f-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="6046f-131">Element</span></span>|<span data-ttu-id="6046f-132">Описание</span><span class="sxs-lookup"><span data-stu-id="6046f-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6046f-133">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="6046f-133">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="6046f-134">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="6046f-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="6046f-135">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="6046f-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6046f-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="6046f-136">Remarks</span></span>

<span data-ttu-id="6046f-137">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6046f-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="6046f-138">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="6046f-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="6046f-139">Можно использовать [ \<аргументы >](../windows-workflow-foundation/arguments.md), [ \<состояния >](../windows-workflow-foundation/states.md) и [ \<состояния >](../windows-workflow-foundation/states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе. В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при выдаче записи `Closed` отслеживания действия.</span><span class="sxs-lookup"><span data-stu-id="6046f-139">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="6046f-140">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](../windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="6046f-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="6046f-141">См. также</span><span class="sxs-lookup"><span data-stu-id="6046f-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="6046f-142">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6046f-142">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6046f-143">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="6046f-143">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
