---
title: <state> из <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: ff75895949c50cd369e4297ea77dc21106994067
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794413"
---
# <a name="state-of-states"></a><span data-ttu-id="d2b5a-102">\<Состояние > из \<состояний ></span><span class="sxs-lookup"><span data-stu-id="d2b5a-102">\<state> of \<states></span></span>
<span data-ttu-id="d2b5a-103">Элемент конфигурации, содержащий состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d2b5a-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="d2b5a-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d2b5a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="d2b5a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d2b5a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d2b5a-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="d2b5a-106">\<tracking></span></span>  
<span data-ttu-id="d2b5a-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d2b5a-107">\<trackingProfile></span></span>  
<span data-ttu-id="d2b5a-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="d2b5a-108">\<workflow></span></span>  
<span data-ttu-id="d2b5a-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="d2b5a-109">\<activityStateQueries></span></span>  
<span data-ttu-id="d2b5a-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="d2b5a-110">\<activityStateQuery></span></span>  
<span data-ttu-id="d2b5a-111">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="d2b5a-111">\<states></span></span>  
<span data-ttu-id="d2b5a-112">\<Состояние ></span><span class="sxs-lookup"><span data-stu-id="d2b5a-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b5a-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2b5a-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2b5a-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d2b5a-114">Attributes and Elements</span></span>  
 <span data-ttu-id="d2b5a-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d2b5a-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2b5a-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d2b5a-116">Attributes</span></span>  
  
|<span data-ttu-id="d2b5a-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d2b5a-117">Attribute</span></span>|<span data-ttu-id="d2b5a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d2b5a-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2b5a-119">имя</span><span class="sxs-lookup"><span data-stu-id="d2b5a-119">name</span></span>|<span data-ttu-id="d2b5a-120">Строка, содержащая состояние подписанного действия, для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d2b5a-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2b5a-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d2b5a-121">Child Elements</span></span>  
 <span data-ttu-id="d2b5a-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d2b5a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2b5a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d2b5a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d2b5a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="d2b5a-124">Element</span></span>|<span data-ttu-id="d2b5a-125">Описание</span><span class="sxs-lookup"><span data-stu-id="d2b5a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2b5a-126">\<состояния ></span><span class="sxs-lookup"><span data-stu-id="d2b5a-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="d2b5a-127">Коллекция элементов конфигурации, содержащих состояния действия, на которое установлена подписка и для которого необходимо создать запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d2b5a-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2b5a-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="d2b5a-128">Remarks</span></span>  
 <span data-ttu-id="d2b5a-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="d2b5a-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="d2b5a-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="d2b5a-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="d2b5a-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="d2b5a-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="d2b5a-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="d2b5a-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="d2b5a-133">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="d2b5a-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2b5a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d2b5a-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d2b5a-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d2b5a-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d2b5a-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="d2b5a-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
