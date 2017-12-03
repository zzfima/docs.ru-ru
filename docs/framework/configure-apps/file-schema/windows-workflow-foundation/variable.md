---
title: "&lt;переменная&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad2a4d3768c26755a9437826c70585a43f967d09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltvariablegt"></a><span data-ttu-id="ea479-102">&lt;переменная&gt;</span><span class="sxs-lookup"><span data-stu-id="ea479-102">&lt;variable&gt;</span></span>
<span data-ttu-id="ea479-103">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="ea479-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="ea479-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ea479-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ea479-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ea479-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ea479-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="ea479-106">\<tracking></span></span>  
<span data-ttu-id="ea479-107">\<профили ></span><span class="sxs-lookup"><span data-stu-id="ea479-107">\<profiles></span></span>  
<span data-ttu-id="ea479-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ea479-108">\<trackingProfile></span></span>  
<span data-ttu-id="ea479-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ea479-109">\<workflow></span></span>  
<span data-ttu-id="ea479-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="ea479-110">\<activityStateQueries></span></span>  
<span data-ttu-id="ea479-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="ea479-111">\<activityStateQuery></span></span>  
<span data-ttu-id="ea479-112">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="ea479-112">\<variables></span></span>  
<span data-ttu-id="ea479-113">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="ea479-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea479-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea479-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea479-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea479-115">Attributes and Elements</span></span>  
 <span data-ttu-id="ea479-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea479-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea479-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea479-117">Attributes</span></span>  
  
|<span data-ttu-id="ea479-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea479-118">Attribute</span></span>|<span data-ttu-id="ea479-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ea479-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea479-120">имя</span><span class="sxs-lookup"><span data-stu-id="ea479-120">name</span></span>|<span data-ttu-id="ea479-121">Строка, задающая имя переменной.</span><span class="sxs-lookup"><span data-stu-id="ea479-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea479-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea479-122">Child Elements</span></span>  
 <span data-ttu-id="ea479-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea479-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea479-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea479-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ea479-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea479-125">Element</span></span>|<span data-ttu-id="ea479-126">Описание</span><span class="sxs-lookup"><span data-stu-id="ea479-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea479-127">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="ea479-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="ea479-128">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="ea479-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea479-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea479-129">Remarks</span></span>  
 <span data-ttu-id="ea479-130">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ea479-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ea479-131">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="ea479-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ea479-132">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ea479-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ea479-133">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="ea479-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ea479-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ea479-134">See Also</span></span>  
 <span data-ttu-id="ea479-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ea479-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="ea479-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ea479-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="ea479-137">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ea479-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ea479-138">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ea479-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
