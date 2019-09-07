---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 3e48256ab1127d45e95c557aa9c2434419d9ea59
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397594"
---
# <a name="variables"></a><span data-ttu-id="1ad82-101">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="1ad82-101">\<variables></span></span>
<span data-ttu-id="1ad82-102">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="1ad82-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="1ad82-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1ad82-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1ad82-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1ad82-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1ad82-105">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1ad82-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1ad82-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1ad82-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1ad82-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1ad82-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1ad82-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1ad82-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1ad82-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Активитистатекуериес >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="1ad82-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="1ad82-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Активитистатекуери >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="1ad82-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="1ad82-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<переменные >**</span><span class="sxs-lookup"><span data-stu-id="1ad82-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variables>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ad82-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ad82-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ad82-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1ad82-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1ad82-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1ad82-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ad82-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1ad82-115">Attributes</span></span>  
 <span data-ttu-id="1ad82-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="1ad82-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1ad82-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1ad82-117">Child Elements</span></span>  
  
|<span data-ttu-id="1ad82-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ad82-118">Element</span></span>|<span data-ttu-id="1ad82-119">Описание</span><span class="sxs-lookup"><span data-stu-id="1ad82-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ad82-120">\<> переменной</span><span class="sxs-lookup"><span data-stu-id="1ad82-120">\<variable></span></span>](variable.md)|<span data-ttu-id="1ad82-121">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="1ad82-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ad82-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1ad82-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1ad82-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ad82-123">Element</span></span>|<span data-ttu-id="1ad82-124">Описание</span><span class="sxs-lookup"><span data-stu-id="1ad82-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ad82-125">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="1ad82-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="1ad82-126">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="1ad82-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1ad82-127">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="1ad82-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ad82-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="1ad82-128">Remarks</span></span>  
 <span data-ttu-id="1ad82-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1ad82-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="1ad82-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="1ad82-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="1ad82-131">Можно использовать [ \<аргументы >](arguments.md), [ \<состояния >](states.md) и [ \<состояния >](states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="1ad82-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="1ad82-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="1ad82-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="1ad82-133">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="1ad82-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ad82-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1ad82-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1ad82-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1ad82-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1ad82-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="1ad82-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
