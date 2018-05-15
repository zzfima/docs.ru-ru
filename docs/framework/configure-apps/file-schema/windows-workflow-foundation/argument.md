---
title: '&lt;Аргумент&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: bfcb98085e0b2292d46acfd0a57096219afff606
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltargumentgt"></a><span data-ttu-id="a3392-102">&lt;Аргумент&gt;</span><span class="sxs-lookup"><span data-stu-id="a3392-102">&lt;argument&gt;</span></span>
<span data-ttu-id="a3392-103">Элемент конфигурации, который представляет аргумент, связанный с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="a3392-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="a3392-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a3392-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a3392-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a3392-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a3392-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="a3392-106">\<tracking></span></span>  
<span data-ttu-id="a3392-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a3392-107">\<trackingProfile></span></span>  
<span data-ttu-id="a3392-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="a3392-108">\<workflow></span></span>  
<span data-ttu-id="a3392-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="a3392-109">\<activityStateQueries></span></span>  
<span data-ttu-id="a3392-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a3392-110">\<activityStateQuery></span></span>  
<span data-ttu-id="a3392-111">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="a3392-111">\<arguments></span></span>  
<span data-ttu-id="a3392-112">\<Аргумент ></span><span class="sxs-lookup"><span data-stu-id="a3392-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3392-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3392-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3392-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a3392-114">Attributes and Elements</span></span>  
 <span data-ttu-id="a3392-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a3392-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3392-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a3392-116">Attributes</span></span>  
  
|<span data-ttu-id="a3392-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a3392-117">Attribute</span></span>|<span data-ttu-id="a3392-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a3392-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3392-119">имя</span><span class="sxs-lookup"><span data-stu-id="a3392-119">name</span></span>|<span data-ttu-id="a3392-120">Строка, задающая имя аргумента.</span><span class="sxs-lookup"><span data-stu-id="a3392-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3392-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a3392-121">Child Elements</span></span>  
 <span data-ttu-id="a3392-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a3392-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3392-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a3392-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a3392-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="a3392-124">Element</span></span>|<span data-ttu-id="a3392-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a3392-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3392-126">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="a3392-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="a3392-127">Коллекция аргументов, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="a3392-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3392-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="a3392-128">Remarks</span></span>  
 <span data-ttu-id="a3392-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a3392-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a3392-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3392-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a3392-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="a3392-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a3392-132">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="a3392-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a3392-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a3392-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="a3392-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a3392-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a3392-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a3392-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
