---
title: '&lt;customTrackingQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 060e2b5c8efd51f6245a39bd9562a69f0111fd41
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50038790"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="61433-102">&lt;customTrackingQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="61433-102">&lt;customTrackingQueries&gt; of WCF</span></span>

<span data-ttu-id="61433-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="61433-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="61433-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="61433-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="61433-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="61433-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="61433-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="61433-106">\<system.serviceModel></span></span>  
<span data-ttu-id="61433-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="61433-107">\<tracking></span></span>  
<span data-ttu-id="61433-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="61433-108">\<profiles></span></span>  
<span data-ttu-id="61433-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="61433-109">\<trackingProfile></span></span>  
<span data-ttu-id="61433-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="61433-110">\<workflow></span></span>  
<span data-ttu-id="61433-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="61433-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61433-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61433-112">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61433-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="61433-113">Attributes and elements</span></span>

<span data-ttu-id="61433-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="61433-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61433-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="61433-115">Attributes</span></span>

<span data-ttu-id="61433-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="61433-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="61433-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="61433-117">Child elements</span></span>
  
|<span data-ttu-id="61433-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="61433-118">Element</span></span>|<span data-ttu-id="61433-119">Описание</span><span class="sxs-lookup"><span data-stu-id="61433-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61433-120">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="61433-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="61433-121">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="61433-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61433-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="61433-122">Parent elements</span></span>  
  
|<span data-ttu-id="61433-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="61433-123">Element</span></span>|<span data-ttu-id="61433-124">Описание</span><span class="sxs-lookup"><span data-stu-id="61433-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61433-125">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="61433-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="61433-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="61433-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61433-127">См. также</span><span class="sxs-lookup"><span data-stu-id="61433-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="61433-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="61433-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="61433-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="61433-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
