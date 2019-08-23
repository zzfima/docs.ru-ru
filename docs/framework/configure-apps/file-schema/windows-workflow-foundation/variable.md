---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: a8f66f950db1edf8cd6ec21400785fb7e01b878e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947273"
---
# <a name="variable"></a><span data-ttu-id="88444-101">\<> переменной</span><span class="sxs-lookup"><span data-stu-id="88444-101">\<variable></span></span>
<span data-ttu-id="88444-102">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="88444-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="88444-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="88444-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="88444-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="88444-104">\<system.serviceModel></span></span>  
<span data-ttu-id="88444-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="88444-105">\<tracking></span></span>  
<span data-ttu-id="88444-106">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="88444-106">\<profiles></span></span>  
<span data-ttu-id="88444-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="88444-107">\<trackingProfile></span></span>  
<span data-ttu-id="88444-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="88444-108">\<workflow></span></span>  
<span data-ttu-id="88444-109">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="88444-109">\<activityStateQueries></span></span>  
<span data-ttu-id="88444-110">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="88444-110">\<activityStateQuery></span></span>  
<span data-ttu-id="88444-111">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="88444-111">\<variables></span></span>  
<span data-ttu-id="88444-112">\<> переменной</span><span class="sxs-lookup"><span data-stu-id="88444-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88444-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88444-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88444-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="88444-114">Attributes and Elements</span></span>  
 <span data-ttu-id="88444-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="88444-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88444-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="88444-116">Attributes</span></span>  
  
|<span data-ttu-id="88444-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="88444-117">Attribute</span></span>|<span data-ttu-id="88444-118">Описание</span><span class="sxs-lookup"><span data-stu-id="88444-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88444-119">имя</span><span class="sxs-lookup"><span data-stu-id="88444-119">name</span></span>|<span data-ttu-id="88444-120">Строка, задающая имя переменной.</span><span class="sxs-lookup"><span data-stu-id="88444-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88444-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="88444-121">Child Elements</span></span>  
 <span data-ttu-id="88444-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="88444-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88444-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="88444-123">Parent Elements</span></span>  
  
|<span data-ttu-id="88444-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="88444-124">Element</span></span>|<span data-ttu-id="88444-125">Описание</span><span class="sxs-lookup"><span data-stu-id="88444-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88444-126">\<> переменной</span><span class="sxs-lookup"><span data-stu-id="88444-126">\<variable></span></span>](variable.md)|<span data-ttu-id="88444-127">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="88444-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88444-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="88444-128">Remarks</span></span>  
 <span data-ttu-id="88444-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="88444-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="88444-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="88444-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="88444-131">Можно использовать [ \<аргументы >](arguments.md), [ \<состояния >](states.md) и [ \<состояния >](states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="88444-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="88444-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="88444-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="88444-133">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="88444-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88444-134">См. также</span><span class="sxs-lookup"><span data-stu-id="88444-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="88444-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="88444-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="88444-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="88444-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
