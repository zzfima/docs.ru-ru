---
title: '&lt;Аргументы&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: 6810e004d74cec1dec3056017eb324ff667d9f1d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152582"
---
# <a name="ltargumentsgt"></a><span data-ttu-id="601fe-102">&lt;Аргументы&gt;</span><span class="sxs-lookup"><span data-stu-id="601fe-102">&lt;arguments&gt;</span></span>
<span data-ttu-id="601fe-103">Представляет коллекцию аргументов, связанных с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="601fe-103">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="601fe-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="601fe-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="601fe-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="601fe-105">\<system.serviceModel></span></span>  
<span data-ttu-id="601fe-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="601fe-106">\<tracking></span></span>  
<span data-ttu-id="601fe-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="601fe-107">\<trackingProfile></span></span>  
<span data-ttu-id="601fe-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="601fe-108">\<workflow></span></span>  
<span data-ttu-id="601fe-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="601fe-109">\<activityStateQueries></span></span>  
<span data-ttu-id="601fe-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="601fe-110">\<activityStateQuery></span></span>  
<span data-ttu-id="601fe-111">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="601fe-111">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="601fe-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="601fe-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="601fe-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="601fe-113">Attributes and Elements</span></span>  
 <span data-ttu-id="601fe-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="601fe-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="601fe-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="601fe-115">Attributes</span></span>  
 <span data-ttu-id="601fe-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="601fe-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="601fe-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="601fe-117">Child Elements</span></span>  
  
|<span data-ttu-id="601fe-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="601fe-118">Element</span></span>|<span data-ttu-id="601fe-119">Описание</span><span class="sxs-lookup"><span data-stu-id="601fe-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="601fe-120">\<Аргумент ></span><span class="sxs-lookup"><span data-stu-id="601fe-120">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="601fe-121">Аргумент, связанный с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="601fe-121">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="601fe-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="601fe-122">Parent Elements</span></span>  
  
|<span data-ttu-id="601fe-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="601fe-123">Element</span></span>|<span data-ttu-id="601fe-124">Описание</span><span class="sxs-lookup"><span data-stu-id="601fe-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="601fe-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="601fe-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="601fe-126">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="601fe-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="601fe-127">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="601fe-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="601fe-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="601fe-128">Remarks</span></span>  
 <span data-ttu-id="601fe-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="601fe-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="601fe-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="601fe-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="601fe-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="601fe-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="601fe-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="601fe-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="601fe-133">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="601fe-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="601fe-134">См. также</span><span class="sxs-lookup"><span data-stu-id="601fe-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="601fe-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="601fe-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="601fe-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="601fe-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
