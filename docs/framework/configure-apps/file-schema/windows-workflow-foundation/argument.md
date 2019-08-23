---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: f2aeb61e2e72f5bd6a696c031279f2c57907166b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946149"
---
# <a name="argument"></a><span data-ttu-id="7c613-101">\<> аргумента</span><span class="sxs-lookup"><span data-stu-id="7c613-101">\<argument></span></span>
<span data-ttu-id="7c613-102">Элемент конфигурации, который представляет аргумент, связанный с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="7c613-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="7c613-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7c613-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7c613-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="7c613-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7c613-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="7c613-105">\<tracking></span></span>  
<span data-ttu-id="7c613-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="7c613-106">\<trackingProfile></span></span>  
<span data-ttu-id="7c613-107">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7c613-107">\<workflow></span></span>  
<span data-ttu-id="7c613-108">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="7c613-108">\<activityStateQueries></span></span>  
<span data-ttu-id="7c613-109">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="7c613-109">\<activityStateQuery></span></span>  
<span data-ttu-id="7c613-110">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="7c613-110">\<arguments></span></span>  
<span data-ttu-id="7c613-111">\<> аргумента</span><span class="sxs-lookup"><span data-stu-id="7c613-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c613-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c613-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c613-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7c613-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7c613-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7c613-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c613-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7c613-115">Attributes</span></span>  
  
|<span data-ttu-id="7c613-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7c613-116">Attribute</span></span>|<span data-ttu-id="7c613-117">Описание</span><span class="sxs-lookup"><span data-stu-id="7c613-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c613-118">имя</span><span class="sxs-lookup"><span data-stu-id="7c613-118">name</span></span>|<span data-ttu-id="7c613-119">Строка, задающая имя аргумента.</span><span class="sxs-lookup"><span data-stu-id="7c613-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c613-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7c613-120">Child Elements</span></span>  
 <span data-ttu-id="7c613-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="7c613-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c613-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7c613-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7c613-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="7c613-123">Element</span></span>|<span data-ttu-id="7c613-124">Описание</span><span class="sxs-lookup"><span data-stu-id="7c613-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c613-125">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="7c613-125">\<arguments></span></span>](arguments.md)|<span data-ttu-id="7c613-126">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="7c613-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c613-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c613-127">Remarks</span></span>  
 <span data-ttu-id="7c613-128">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7c613-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="7c613-129">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="7c613-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="7c613-130">Можно использовать [ \<аргументы >](arguments.md), [ \<состояния >](states.md) и [ \<состояния >](states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="7c613-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="7c613-131">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="7c613-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="7c613-132">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="7c613-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7c613-133">См. также</span><span class="sxs-lookup"><span data-stu-id="7c613-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7c613-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7c613-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7c613-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="7c613-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
