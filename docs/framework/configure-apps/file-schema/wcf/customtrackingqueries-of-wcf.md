---
title: <customTrackingQueries> для WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 8b317cc289853902592e145e34b6e7bf5f84763b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704172"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="e90c2-102">\<customTrackingQueries > из WCF</span><span class="sxs-lookup"><span data-stu-id="e90c2-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="e90c2-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="e90c2-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e90c2-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="e90c2-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="e90c2-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e90c2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="e90c2-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e90c2-106">\<system.serviceModel></span></span>  
<span data-ttu-id="e90c2-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="e90c2-107">\<tracking></span></span>  
<span data-ttu-id="e90c2-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="e90c2-108">\<profiles></span></span>  
<span data-ttu-id="e90c2-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e90c2-109">\<trackingProfile></span></span>  
<span data-ttu-id="e90c2-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="e90c2-110">\<workflow></span></span>  
<span data-ttu-id="e90c2-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="e90c2-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e90c2-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e90c2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e90c2-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="e90c2-113">Attributes and elements</span></span>

<span data-ttu-id="e90c2-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e90c2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e90c2-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e90c2-115">Attributes</span></span>

<span data-ttu-id="e90c2-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e90c2-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="e90c2-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e90c2-117">Child elements</span></span>
  
|<span data-ttu-id="e90c2-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e90c2-118">Element</span></span>|<span data-ttu-id="e90c2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e90c2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e90c2-120">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="e90c2-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="e90c2-121">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="e90c2-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e90c2-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e90c2-122">Parent elements</span></span>  
  
|<span data-ttu-id="e90c2-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e90c2-123">Element</span></span>|<span data-ttu-id="e90c2-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e90c2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e90c2-125">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="e90c2-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="e90c2-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="e90c2-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e90c2-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e90c2-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e90c2-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e90c2-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e90c2-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="e90c2-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
