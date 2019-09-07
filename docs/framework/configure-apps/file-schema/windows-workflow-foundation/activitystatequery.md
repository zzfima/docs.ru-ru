---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 5d3c35589330ab5bed5f89c0dafac006b9e3af55
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398940"
---
# <a name="activitystatequery"></a><span data-ttu-id="b2fca-101">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="b2fca-101">\<activityStateQuery></span></span>
<span data-ttu-id="b2fca-102">Представляет запрос, используемый для трассировки изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b2fca-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="b2fca-103">Например, вы можете захотеть отследить каждый раз, когда действие "отправить электронное письмо" завершается в рамках экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b2fca-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="b2fca-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на объекты записей состояния действия.</span><span class="sxs-lookup"><span data-stu-id="b2fca-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="b2fca-105">Состояния, доступные для подписки, указаны в ActivtyStates.</span><span class="sxs-lookup"><span data-stu-id="b2fca-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="b2fca-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b2fca-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b2fca-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b2fca-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b2fca-108">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b2fca-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="b2fca-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="b2fca-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="b2fca-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="b2fca-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="b2fca-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b2fca-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="b2fca-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Активитистатекуериес >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="b2fca-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="b2fca-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Активитистатекуери >**</span><span class="sxs-lookup"><span data-stu-id="b2fca-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2fca-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2fca-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2fca-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b2fca-115">Attributes and Elements</span></span>  
 <span data-ttu-id="b2fca-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b2fca-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2fca-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2fca-117">Attributes</span></span>  
  
|<span data-ttu-id="b2fca-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b2fca-118">Attribute</span></span>|<span data-ttu-id="b2fca-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b2fca-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2fca-120">activityName</span><span class="sxs-lookup"><span data-stu-id="b2fca-120">activityName</span></span>|<span data-ttu-id="b2fca-121">Строка, указывающая имя действия, по которому будут фильтроваться экземпляры <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="b2fca-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2fca-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2fca-122">Child Elements</span></span>  
  
|<span data-ttu-id="b2fca-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2fca-123">Element</span></span>|<span data-ttu-id="b2fca-124">Описание</span><span class="sxs-lookup"><span data-stu-id="b2fca-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2fca-125">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="b2fca-125">\<arguments></span></span>](arguments.md)|<span data-ttu-id="b2fca-126">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="b2fca-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="b2fca-127">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="b2fca-127">\<states></span></span>](states.md)|<span data-ttu-id="b2fca-128">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="b2fca-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="b2fca-129">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="b2fca-129">\<states></span></span>](states.md)|<span data-ttu-id="b2fca-130">Коллекция переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="b2fca-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2fca-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2fca-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b2fca-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2fca-132">Element</span></span>|<span data-ttu-id="b2fca-133">Описание</span><span class="sxs-lookup"><span data-stu-id="b2fca-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2fca-134">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="b2fca-134">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="b2fca-135">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="b2fca-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b2fca-136">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="b2fca-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2fca-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2fca-137">Remarks</span></span>  
 <span data-ttu-id="b2fca-138">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b2fca-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="b2fca-139">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="b2fca-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="b2fca-140">Можно использовать [ \<аргументы >](arguments.md), [ \<состояния >](states.md) и [ \<состояния >](states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="b2fca-140">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="b2fca-141">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="b2fca-141">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="b2fca-142">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="b2fca-142">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2fca-143">См. также</span><span class="sxs-lookup"><span data-stu-id="b2fca-143">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b2fca-144">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b2fca-144">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b2fca-145">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="b2fca-145">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
