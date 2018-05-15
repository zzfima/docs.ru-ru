---
title: '&lt;Переменная&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 7d41d80bfe83cfafca01509d50709e21730bcb97
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltvariablegt"></a><span data-ttu-id="72529-102">&lt;Переменная&gt;</span><span class="sxs-lookup"><span data-stu-id="72529-102">&lt;variable&gt;</span></span>
<span data-ttu-id="72529-103">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="72529-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="72529-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="72529-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="72529-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="72529-105">\<system.serviceModel></span></span>  
<span data-ttu-id="72529-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="72529-106">\<tracking></span></span>  
<span data-ttu-id="72529-107">\<профили ></span><span class="sxs-lookup"><span data-stu-id="72529-107">\<profiles></span></span>  
<span data-ttu-id="72529-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="72529-108">\<trackingProfile></span></span>  
<span data-ttu-id="72529-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="72529-109">\<workflow></span></span>  
<span data-ttu-id="72529-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="72529-110">\<activityStateQueries></span></span>  
<span data-ttu-id="72529-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="72529-111">\<activityStateQuery></span></span>  
<span data-ttu-id="72529-112">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="72529-112">\<variables></span></span>  
<span data-ttu-id="72529-113">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="72529-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72529-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72529-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72529-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="72529-115">Attributes and Elements</span></span>  
 <span data-ttu-id="72529-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="72529-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72529-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="72529-117">Attributes</span></span>  
  
|<span data-ttu-id="72529-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="72529-118">Attribute</span></span>|<span data-ttu-id="72529-119">Описание</span><span class="sxs-lookup"><span data-stu-id="72529-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72529-120">имя</span><span class="sxs-lookup"><span data-stu-id="72529-120">name</span></span>|<span data-ttu-id="72529-121">Строка, задающая имя переменной.</span><span class="sxs-lookup"><span data-stu-id="72529-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72529-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="72529-122">Child Elements</span></span>  
 <span data-ttu-id="72529-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="72529-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72529-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="72529-124">Parent Elements</span></span>  
  
|<span data-ttu-id="72529-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="72529-125">Element</span></span>|<span data-ttu-id="72529-126">Описание</span><span class="sxs-lookup"><span data-stu-id="72529-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72529-127">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="72529-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="72529-128">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="72529-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72529-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="72529-129">Remarks</span></span>  
 <span data-ttu-id="72529-130">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="72529-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="72529-131">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="72529-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="72529-132">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="72529-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="72529-133">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="72529-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="72529-134">См. также</span><span class="sxs-lookup"><span data-stu-id="72529-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="72529-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="72529-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="72529-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="72529-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
