---
title: "&lt;аргументы&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f233c7fc7d7edd020a750938a45351bb028524d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltargumentsgt"></a><span data-ttu-id="14346-102">&lt;аргументы&gt;</span><span class="sxs-lookup"><span data-stu-id="14346-102">&lt;arguments&gt;</span></span>
<span data-ttu-id="14346-103">Представляет коллекцию аргументов, связанных с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="14346-103">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="14346-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="14346-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="14346-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="14346-105">\<system.serviceModel></span></span>  
<span data-ttu-id="14346-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="14346-106">\<tracking></span></span>  
<span data-ttu-id="14346-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="14346-107">\<trackingProfile></span></span>  
<span data-ttu-id="14346-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="14346-108">\<workflow></span></span>  
<span data-ttu-id="14346-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="14346-109">\<activityStateQueries></span></span>  
<span data-ttu-id="14346-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="14346-110">\<activityStateQuery></span></span>  
<span data-ttu-id="14346-111">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="14346-111">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14346-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14346-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14346-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="14346-113">Attributes and Elements</span></span>  
 <span data-ttu-id="14346-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="14346-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14346-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="14346-115">Attributes</span></span>  
 <span data-ttu-id="14346-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="14346-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14346-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="14346-117">Child Elements</span></span>  
  
|<span data-ttu-id="14346-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="14346-118">Element</span></span>|<span data-ttu-id="14346-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="14346-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14346-120">\<Аргумент ></span><span class="sxs-lookup"><span data-stu-id="14346-120">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="14346-121">Аргумент, связанный с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="14346-121">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14346-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="14346-122">Parent Elements</span></span>  
  
|<span data-ttu-id="14346-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="14346-123">Element</span></span>|<span data-ttu-id="14346-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="14346-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14346-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="14346-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="14346-126">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="14346-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="14346-127">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="14346-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14346-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="14346-128">Remarks</span></span>  
 <span data-ttu-id="14346-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="14346-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="14346-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="14346-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="14346-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="14346-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="14346-132">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="14346-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14346-133">См. также</span><span class="sxs-lookup"><span data-stu-id="14346-133">See Also</span></span>  
 <span data-ttu-id="14346-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14346-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="14346-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14346-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="14346-136">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="14346-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="14346-137">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="14346-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
