---
title: '&lt;Переменная&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 185e7e7196f6679ec3d1fae8a2a256b934022ca9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647885"
---
# <a name="ltvariablegt"></a><span data-ttu-id="94326-102">&lt;Переменная&gt;</span><span class="sxs-lookup"><span data-stu-id="94326-102">&lt;variable&gt;</span></span>
<span data-ttu-id="94326-103">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="94326-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="94326-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="94326-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="94326-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="94326-105">\<system.serviceModel></span></span>  
<span data-ttu-id="94326-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="94326-106">\<tracking></span></span>  
<span data-ttu-id="94326-107">\<профили ></span><span class="sxs-lookup"><span data-stu-id="94326-107">\<profiles></span></span>  
<span data-ttu-id="94326-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="94326-108">\<trackingProfile></span></span>  
<span data-ttu-id="94326-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="94326-109">\<workflow></span></span>  
<span data-ttu-id="94326-110">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="94326-110">\<activityStateQueries></span></span>  
<span data-ttu-id="94326-111">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="94326-111">\<activityStateQuery></span></span>  
<span data-ttu-id="94326-112">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="94326-112">\<variables></span></span>  
<span data-ttu-id="94326-113">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="94326-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94326-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94326-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94326-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="94326-115">Attributes and Elements</span></span>  
 <span data-ttu-id="94326-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="94326-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94326-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="94326-117">Attributes</span></span>  
  
|<span data-ttu-id="94326-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="94326-118">Attribute</span></span>|<span data-ttu-id="94326-119">Описание</span><span class="sxs-lookup"><span data-stu-id="94326-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94326-120">имя</span><span class="sxs-lookup"><span data-stu-id="94326-120">name</span></span>|<span data-ttu-id="94326-121">Строка, задающая имя переменной.</span><span class="sxs-lookup"><span data-stu-id="94326-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94326-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="94326-122">Child Elements</span></span>  
 <span data-ttu-id="94326-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="94326-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94326-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="94326-124">Parent Elements</span></span>  
  
|<span data-ttu-id="94326-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="94326-125">Element</span></span>|<span data-ttu-id="94326-126">Описание</span><span class="sxs-lookup"><span data-stu-id="94326-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94326-127">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="94326-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="94326-128">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="94326-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94326-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="94326-129">Remarks</span></span>  
 <span data-ttu-id="94326-130">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="94326-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="94326-131">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="94326-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="94326-132">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="94326-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="94326-133">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="94326-133">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="94326-134">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="94326-134">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="94326-135">См. также</span><span class="sxs-lookup"><span data-stu-id="94326-135">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="94326-136">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="94326-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="94326-137">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="94326-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
