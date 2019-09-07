---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: f06a2188ea3561437c1453d3a1cb23d42d767f53
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398915"
---
# <a name="arguments"></a><span data-ttu-id="4e3ba-101">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="4e3ba-101">\<arguments></span></span>
<span data-ttu-id="4e3ba-102">Представляет коллекцию аргументов, связанных с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="4e3ba-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4e3ba-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="4e3ba-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e3ba-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4e3ba-105">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4e3ba-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="4e3ba-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="4e3ba-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="4e3ba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="4e3ba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="4e3ba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4e3ba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="4e3ba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Активитистатекуериес >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="4e3ba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="4e3ba-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Активитистатекуери >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="4e3ba-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="4e3ba-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<аргументы >**</span><span class="sxs-lookup"><span data-stu-id="4e3ba-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<arguments>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3ba-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e3ba-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e3ba-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4e3ba-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4e3ba-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e3ba-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4e3ba-115">Attributes</span></span>  
 <span data-ttu-id="4e3ba-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e3ba-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4e3ba-117">Child Elements</span></span>  
  
|<span data-ttu-id="4e3ba-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e3ba-118">Element</span></span>|<span data-ttu-id="4e3ba-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4e3ba-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e3ba-120">\<> аргумента</span><span class="sxs-lookup"><span data-stu-id="4e3ba-120">\<argument></span></span>](argument.md)|<span data-ttu-id="4e3ba-121">Аргумент, связанный с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-121">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e3ba-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4e3ba-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4e3ba-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e3ba-123">Element</span></span>|<span data-ttu-id="4e3ba-124">Описание</span><span class="sxs-lookup"><span data-stu-id="4e3ba-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e3ba-125">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="4e3ba-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="4e3ba-126">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="4e3ba-127">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e3ba-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e3ba-128">Remarks</span></span>  
 <span data-ttu-id="4e3ba-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="4e3ba-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="4e3ba-131">Можно использовать [ \<аргументы >](arguments.md), [ \<состояния >](states.md) и [ \<состояния >](states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="4e3ba-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="4e3ba-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="4e3ba-133">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="4e3ba-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4e3ba-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4e3ba-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4e3ba-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="4e3ba-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4e3ba-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="4e3ba-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
