---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: c85f3c57739c48566c97c8b1debfb7f2c3912bdf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196636"
---
# <a name="variable"></a><span data-ttu-id="2dd67-101">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="2dd67-101">\<variable></span></span>
<span data-ttu-id="2dd67-102">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="2dd67-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="2dd67-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2dd67-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="2dd67-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2dd67-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2dd67-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="2dd67-105">\<tracking></span></span>  
<span data-ttu-id="2dd67-106">\<профили ></span><span class="sxs-lookup"><span data-stu-id="2dd67-106">\<profiles></span></span>  
<span data-ttu-id="2dd67-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2dd67-107">\<trackingProfile></span></span>  
<span data-ttu-id="2dd67-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="2dd67-108">\<workflow></span></span>  
<span data-ttu-id="2dd67-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="2dd67-109">\<activityStateQueries></span></span>  
<span data-ttu-id="2dd67-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="2dd67-110">\<activityStateQuery></span></span>  
<span data-ttu-id="2dd67-111">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="2dd67-111">\<variables></span></span>  
<span data-ttu-id="2dd67-112">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="2dd67-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd67-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2dd67-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2dd67-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2dd67-114">Attributes and Elements</span></span>  
 <span data-ttu-id="2dd67-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2dd67-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2dd67-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2dd67-116">Attributes</span></span>  
  
|<span data-ttu-id="2dd67-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2dd67-117">Attribute</span></span>|<span data-ttu-id="2dd67-118">Описание</span><span class="sxs-lookup"><span data-stu-id="2dd67-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2dd67-119">имя</span><span class="sxs-lookup"><span data-stu-id="2dd67-119">name</span></span>|<span data-ttu-id="2dd67-120">Строка, задающая имя переменной.</span><span class="sxs-lookup"><span data-stu-id="2dd67-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2dd67-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2dd67-121">Child Elements</span></span>  
 <span data-ttu-id="2dd67-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2dd67-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2dd67-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2dd67-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2dd67-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="2dd67-124">Element</span></span>|<span data-ttu-id="2dd67-125">Описание</span><span class="sxs-lookup"><span data-stu-id="2dd67-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2dd67-126">\<переменная ></span><span class="sxs-lookup"><span data-stu-id="2dd67-126">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="2dd67-127">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="2dd67-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dd67-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="2dd67-128">Remarks</span></span>  
 <span data-ttu-id="2dd67-129">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="2dd67-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="2dd67-130">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="2dd67-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="2dd67-131">Можно использовать [ \<аргументы >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) и [ \<состояний >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) элементов для извлечения любые переменные или аргументы из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="2dd67-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="2dd67-132">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="2dd67-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="2dd67-133">Переменные и аргументы могут быть извлечены при помощи ActivityStateRecord и таким образом подписаны в отслеживания профиля с помощью [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="2dd67-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2dd67-134">См. также</span><span class="sxs-lookup"><span data-stu-id="2dd67-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2dd67-135">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2dd67-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2dd67-136">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2dd67-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
