---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 563ce96f61bbb39f1590ca0f43c163ea2d3d7961
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947247"
---
# <a name="variables"></a><span data-ttu-id="97b66-101">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="97b66-101">\<variables></span></span>
<span data-ttu-id="97b66-102">Представляет коллекцию переменных, связанных с этим запросом действия.</span><span class="sxs-lookup"><span data-stu-id="97b66-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="97b66-103">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="97b66-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="97b66-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="97b66-104">\<system.serviceModel></span></span>  
<span data-ttu-id="97b66-105">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="97b66-105">\<tracking></span></span>  
<span data-ttu-id="97b66-106">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="97b66-106">\<trackingProfile></span></span>  
<span data-ttu-id="97b66-107">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="97b66-107">\<workflow></span></span>  
<span data-ttu-id="97b66-108">\<Активитистатекуериес ></span><span class="sxs-lookup"><span data-stu-id="97b66-108">\<activityStateQueries></span></span>  
<span data-ttu-id="97b66-109">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="97b66-109">\<activityStateQuery></span></span>  
<span data-ttu-id="97b66-110">\<переменные ></span><span class="sxs-lookup"><span data-stu-id="97b66-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b66-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97b66-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97b66-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="97b66-112">Attributes and Elements</span></span>  
 <span data-ttu-id="97b66-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="97b66-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97b66-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="97b66-114">Attributes</span></span>  
 <span data-ttu-id="97b66-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="97b66-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97b66-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="97b66-116">Child Elements</span></span>  
  
|<span data-ttu-id="97b66-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="97b66-117">Element</span></span>|<span data-ttu-id="97b66-118">Описание</span><span class="sxs-lookup"><span data-stu-id="97b66-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97b66-119">\<> переменной</span><span class="sxs-lookup"><span data-stu-id="97b66-119">\<variable></span></span>](variable.md)|<span data-ttu-id="97b66-120">Переменная, связанная с запросом состояния действия.</span><span class="sxs-lookup"><span data-stu-id="97b66-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97b66-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="97b66-121">Parent Elements</span></span>  
  
|<span data-ttu-id="97b66-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="97b66-122">Element</span></span>|<span data-ttu-id="97b66-123">Описание</span><span class="sxs-lookup"><span data-stu-id="97b66-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97b66-124">\<Активитистатекуери ></span><span class="sxs-lookup"><span data-stu-id="97b66-124">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="97b66-125">Представляет элемент конфигурации, используемый для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="97b66-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="97b66-126">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="97b66-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97b66-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="97b66-127">Remarks</span></span>  
 <span data-ttu-id="97b66-128">Уникальной возможностью ActivityStateQuery является возможность извлекать данные во время отслеживания выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="97b66-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="97b66-129">Это обеспечивает дополнительный контекст при доступе к записям отслеживания после выполнения.</span><span class="sxs-lookup"><span data-stu-id="97b66-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="97b66-130">Можно использовать [ \<аргументы >](arguments.md), [ \<состояния >](states.md) и [ \<состояния >](states.md) элементы, чтобы извлечь любую переменную или аргумент из любого действия в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="97b66-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="97b66-131">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="97b66-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="97b66-132">Переменные и аргументы могут извлекаться только с помощью активитистатерекорд, поэтому они подписываются в профиль отслеживания с помощью [ \<активитистатекуери >](activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="97b66-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97b66-133">См. также</span><span class="sxs-lookup"><span data-stu-id="97b66-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="97b66-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="97b66-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="97b66-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="97b66-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
