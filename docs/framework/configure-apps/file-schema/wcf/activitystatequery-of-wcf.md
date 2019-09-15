---
title: <activityStateQuery>WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 49c507424e813067e1dad9b08167d9661acef36f
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991216"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="8b2e0-102">\<Активитистатекуери > WCF</span><span class="sxs-lookup"><span data-stu-id="8b2e0-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="8b2e0-103">Представляет запрос, используемый для трассировки изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="8b2e0-104">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="8b2e0-105">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="8b2e0-106">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="8b2e0-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8b2e0-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="8b2e0-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8b2e0-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8b2e0-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8b2e0-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8b2e0-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8b2e0-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="8b2e0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="8b2e0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="8b2e0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8b2e0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="8b2e0-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8b2e0-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="8b2e0-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Активитистатекуериес >** ](activitystatequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="8b2e0-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)</span></span>\
<span data-ttu-id="8b2e0-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Активитистатекуери >**</span><span class="sxs-lookup"><span data-stu-id="8b2e0-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2e0-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b2e0-116">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b2e0-117">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="8b2e0-117">Attributes and elements</span></span>  

<span data-ttu-id="8b2e0-118">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-118">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b2e0-119">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8b2e0-119">Attributes</span></span>  
  
|<span data-ttu-id="8b2e0-120">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8b2e0-120">Attribute</span></span>|<span data-ttu-id="8b2e0-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8b2e0-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b2e0-122">activityName</span><span class="sxs-lookup"><span data-stu-id="8b2e0-122">activityName</span></span>|<span data-ttu-id="8b2e0-123">Строка, указывающая имя действия, по которому будут фильтроваться экземпляры <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-123">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b2e0-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8b2e0-124">Child elements</span></span>  
  
|<span data-ttu-id="8b2e0-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="8b2e0-125">Element</span></span>|<span data-ttu-id="8b2e0-126">Описание</span><span class="sxs-lookup"><span data-stu-id="8b2e0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b2e0-127">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="8b2e0-127">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="8b2e0-128">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-128">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="8b2e0-129">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="8b2e0-129">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="8b2e0-130">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-130">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="8b2e0-131">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="8b2e0-131">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="8b2e0-132">Коллекция переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-132">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b2e0-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8b2e0-133">Parent elements</span></span>  
  
|<span data-ttu-id="8b2e0-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="8b2e0-134">Element</span></span>|<span data-ttu-id="8b2e0-135">Описание</span><span class="sxs-lookup"><span data-stu-id="8b2e0-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b2e0-136">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="8b2e0-136">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="8b2e0-137">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-137">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8b2e0-138">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-138">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b2e0-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b2e0-139">Remarks</span></span>

<span data-ttu-id="8b2e0-140">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-140">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="8b2e0-141">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-141">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="8b2e0-142">Можно использовать [ \<аргументы >](../windows-workflow-foundation/arguments.md), [ \<состояния >](../windows-workflow-foundation/states.md) и [ \<состояния >](../windows-workflow-foundation/states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-142">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="8b2e0-143">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="8b2e0-143">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="8b2e0-144">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](../windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="8b2e0-144">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8b2e0-145">См. также</span><span class="sxs-lookup"><span data-stu-id="8b2e0-145">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="8b2e0-146">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8b2e0-146">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8b2e0-147">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="8b2e0-147">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
