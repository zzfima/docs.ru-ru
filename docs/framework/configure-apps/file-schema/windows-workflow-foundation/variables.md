---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 3ff568c267331538fb9be0e6cb40eebbca44d882
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276553"
---
# <a name="variables"></a><span data-ttu-id="b38d9-101">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="b38d9-101">\<variables></span></span>
<span data-ttu-id="b38d9-102">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="b38d9-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="b38d9-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b38d9-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b38d9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b38d9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b38d9-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="b38d9-105">\<tracking></span></span>  
<span data-ttu-id="b38d9-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b38d9-106">\<trackingProfile></span></span>  
<span data-ttu-id="b38d9-107">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="b38d9-107">\<workflow></span></span>  
<span data-ttu-id="b38d9-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="b38d9-108">\<activityStateQueries></span></span>  
<span data-ttu-id="b38d9-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b38d9-109">\<activityStateQuery></span></span>  
<span data-ttu-id="b38d9-110">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="b38d9-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b38d9-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b38d9-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b38d9-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b38d9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b38d9-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b38d9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b38d9-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b38d9-114">Attributes</span></span>  
 <span data-ttu-id="b38d9-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b38d9-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b38d9-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b38d9-116">Child Elements</span></span>  
  
|<span data-ttu-id="b38d9-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="b38d9-117">Element</span></span>|<span data-ttu-id="b38d9-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b38d9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b38d9-119">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="b38d9-119">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="b38d9-120">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="b38d9-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b38d9-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b38d9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b38d9-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="b38d9-122">Element</span></span>|<span data-ttu-id="b38d9-123">Описание</span><span class="sxs-lookup"><span data-stu-id="b38d9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b38d9-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b38d9-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="b38d9-125">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="b38d9-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b38d9-126">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="b38d9-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b38d9-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="b38d9-127">Remarks</span></span>  
 <span data-ttu-id="b38d9-128">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b38d9-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="b38d9-129">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="b38d9-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="b38d9-130">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="b38d9-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="b38d9-131">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="b38d9-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="b38d9-132">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="b38d9-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b38d9-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b38d9-133">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b38d9-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b38d9-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b38d9-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="b38d9-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
