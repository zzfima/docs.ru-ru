---
title: '&lt;variables&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49255241e7adc187c2df68407cae05573fc3d4d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltvariablesgt"></a><span data-ttu-id="70a8a-102">&lt;variables&gt;</span><span class="sxs-lookup"><span data-stu-id="70a8a-102">&lt;variables&gt;</span></span>
<span data-ttu-id="70a8a-103">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="70a8a-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="70a8a-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="70a8a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="70a8a-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="70a8a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="70a8a-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="70a8a-106">\<tracking></span></span>  
<span data-ttu-id="70a8a-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="70a8a-107">\<trackingProfile></span></span>  
<span data-ttu-id="70a8a-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="70a8a-108">\<workflow></span></span>  
<span data-ttu-id="70a8a-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="70a8a-109">\<activityStateQueries></span></span>  
<span data-ttu-id="70a8a-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="70a8a-110">\<activityStateQuery></span></span>  
<span data-ttu-id="70a8a-111">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="70a8a-111">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70a8a-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70a8a-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70a8a-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="70a8a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="70a8a-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="70a8a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70a8a-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70a8a-115">Attributes</span></span>  
 <span data-ttu-id="70a8a-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="70a8a-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="70a8a-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70a8a-117">Child Elements</span></span>  
  
|<span data-ttu-id="70a8a-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="70a8a-118">Element</span></span>|<span data-ttu-id="70a8a-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="70a8a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70a8a-120">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="70a8a-120">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="70a8a-121">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="70a8a-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70a8a-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="70a8a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="70a8a-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="70a8a-123">Element</span></span>|<span data-ttu-id="70a8a-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="70a8a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70a8a-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="70a8a-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="70a8a-126">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="70a8a-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="70a8a-127">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="70a8a-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70a8a-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="70a8a-128">Remarks</span></span>  
 <span data-ttu-id="70a8a-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="70a8a-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="70a8a-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="70a8a-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="70a8a-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любая переменная или аргумент из любого действия в рабочем процессе. В примере показан запрос состояния действия, который извлекает переменные и аргументы при действия `Closed` записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="70a8a-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="70a8a-132">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord, поэтому подписка на внутри отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="70a8a-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="70a8a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="70a8a-133">See Also</span></span>  
 <span data-ttu-id="70a8a-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="70a8a-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="70a8a-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="70a8a-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="70a8a-136">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="70a8a-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="70a8a-137">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="70a8a-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
