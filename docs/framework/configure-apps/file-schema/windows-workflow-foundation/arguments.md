---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: 3e9fc4f286e7aba6406ce61910da9e614e13ffca
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276575"
---
# <a name="arguments"></a><span data-ttu-id="290c9-101">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="290c9-101">\<arguments></span></span>
<span data-ttu-id="290c9-102">Представляет коллекцию аргументов, связанных с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="290c9-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="290c9-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="290c9-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="290c9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="290c9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="290c9-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="290c9-105">\<tracking></span></span>  
<span data-ttu-id="290c9-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="290c9-106">\<trackingProfile></span></span>  
<span data-ttu-id="290c9-107">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="290c9-107">\<workflow></span></span>  
<span data-ttu-id="290c9-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="290c9-108">\<activityStateQueries></span></span>  
<span data-ttu-id="290c9-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="290c9-109">\<activityStateQuery></span></span>  
<span data-ttu-id="290c9-110">\<аргументы ></span><span class="sxs-lookup"><span data-stu-id="290c9-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="290c9-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="290c9-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="290c9-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="290c9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="290c9-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="290c9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="290c9-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="290c9-114">Attributes</span></span>  
 <span data-ttu-id="290c9-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="290c9-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="290c9-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="290c9-116">Child Elements</span></span>  
  
|<span data-ttu-id="290c9-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="290c9-117">Element</span></span>|<span data-ttu-id="290c9-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="290c9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="290c9-119">\<Аргумент ></span><span class="sxs-lookup"><span data-stu-id="290c9-119">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="290c9-120">Аргумент, связанный с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="290c9-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="290c9-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="290c9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="290c9-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="290c9-122">Element</span></span>|<span data-ttu-id="290c9-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="290c9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="290c9-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="290c9-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="290c9-125">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="290c9-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="290c9-126">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="290c9-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="290c9-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="290c9-127">Remarks</span></span>  
 <span data-ttu-id="290c9-128">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="290c9-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="290c9-129">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="290c9-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="290c9-130">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="290c9-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="290c9-131">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="290c9-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="290c9-132">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="290c9-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="290c9-133">См. также</span><span class="sxs-lookup"><span data-stu-id="290c9-133">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="290c9-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="290c9-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="290c9-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="290c9-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
