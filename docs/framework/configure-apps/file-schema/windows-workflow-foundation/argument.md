---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: a920d60d703fe262bee96d75c420c526d54f88ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210650"
---
# <a name="argument"></a><span data-ttu-id="36997-101">\<Аргумент ></span><span class="sxs-lookup"><span data-stu-id="36997-101">\<argument></span></span>
<span data-ttu-id="36997-102">Элемент конфигурации, который представляет аргумент, связанный с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="36997-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="36997-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="36997-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="36997-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="36997-104">\<system.serviceModel></span></span>  
<span data-ttu-id="36997-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="36997-105">\<tracking></span></span>  
<span data-ttu-id="36997-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="36997-106">\<trackingProfile></span></span>  
<span data-ttu-id="36997-107">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="36997-107">\<workflow></span></span>  
<span data-ttu-id="36997-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="36997-108">\<activityStateQueries></span></span>  
<span data-ttu-id="36997-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="36997-109">\<activityStateQuery></span></span>  
<span data-ttu-id="36997-110">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="36997-110">\<arguments></span></span>  
<span data-ttu-id="36997-111">\<Аргумент ></span><span class="sxs-lookup"><span data-stu-id="36997-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36997-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36997-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36997-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="36997-113">Attributes and Elements</span></span>  
 <span data-ttu-id="36997-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="36997-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36997-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="36997-115">Attributes</span></span>  
  
|<span data-ttu-id="36997-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="36997-116">Attribute</span></span>|<span data-ttu-id="36997-117">Описание</span><span class="sxs-lookup"><span data-stu-id="36997-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36997-118">имя</span><span class="sxs-lookup"><span data-stu-id="36997-118">name</span></span>|<span data-ttu-id="36997-119">Строка, задающая имя аргумента.</span><span class="sxs-lookup"><span data-stu-id="36997-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36997-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="36997-120">Child Elements</span></span>  
 <span data-ttu-id="36997-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36997-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36997-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="36997-122">Parent Elements</span></span>  
  
|<span data-ttu-id="36997-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="36997-123">Element</span></span>|<span data-ttu-id="36997-124">Описание</span><span class="sxs-lookup"><span data-stu-id="36997-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36997-125">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="36997-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="36997-126">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="36997-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36997-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="36997-127">Remarks</span></span>  
 <span data-ttu-id="36997-128">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="36997-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="36997-129">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="36997-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="36997-130">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="36997-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="36997-131">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="36997-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="36997-132">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="36997-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="36997-133">См. также</span><span class="sxs-lookup"><span data-stu-id="36997-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="36997-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="36997-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="36997-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="36997-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
