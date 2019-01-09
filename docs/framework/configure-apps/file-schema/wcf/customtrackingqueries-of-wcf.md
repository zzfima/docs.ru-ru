---
title: '&lt;customTrackingQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: f75c6bf50d30da5a136137c858a5cd96ce0783ff
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150088"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="9b93e-102">&lt;customTrackingQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="9b93e-102">&lt;customTrackingQueries&gt; of WCF</span></span>

<span data-ttu-id="9b93e-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="9b93e-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="9b93e-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="9b93e-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="9b93e-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9b93e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="9b93e-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9b93e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9b93e-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="9b93e-107">\<tracking></span></span>  
<span data-ttu-id="9b93e-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="9b93e-108">\<profiles></span></span>  
<span data-ttu-id="9b93e-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9b93e-109">\<trackingProfile></span></span>  
<span data-ttu-id="9b93e-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="9b93e-110">\<workflow></span></span>  
<span data-ttu-id="9b93e-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="9b93e-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b93e-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b93e-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b93e-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b93e-113">Attributes and elements</span></span>

<span data-ttu-id="9b93e-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9b93e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b93e-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b93e-115">Attributes</span></span>

<span data-ttu-id="9b93e-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9b93e-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="9b93e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9b93e-117">Child elements</span></span>
  
|<span data-ttu-id="9b93e-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b93e-118">Element</span></span>|<span data-ttu-id="9b93e-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="9b93e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b93e-120">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="9b93e-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="9b93e-121">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="9b93e-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b93e-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9b93e-122">Parent elements</span></span>  
  
|<span data-ttu-id="9b93e-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b93e-123">Element</span></span>|<span data-ttu-id="9b93e-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="9b93e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b93e-125">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="9b93e-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9b93e-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="9b93e-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b93e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9b93e-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="9b93e-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9b93e-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="9b93e-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="9b93e-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
