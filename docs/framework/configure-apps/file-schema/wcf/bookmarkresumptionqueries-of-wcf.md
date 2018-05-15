---
title: '&lt;bookmarkResumptionQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 8a83f521e444838b6495221c00211710dd99ab6b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="ba72c-102">&lt;bookmarkResumptionQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="ba72c-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="ba72c-103">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ba72c-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ba72c-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="ba72c-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="ba72c-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ba72c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="ba72c-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ba72c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ba72c-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="ba72c-107">\<tracking></span></span>  
<span data-ttu-id="ba72c-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ba72c-108">\<trackingProfile></span></span>  
<span data-ttu-id="ba72c-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ba72c-109">\<workflow></span></span>  
<span data-ttu-id="ba72c-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="ba72c-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="ba72c-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="ba72c-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba72c-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba72c-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ba72c-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba72c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ba72c-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba72c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba72c-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba72c-115">Attributes</span></span>  
 <span data-ttu-id="ba72c-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ba72c-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba72c-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba72c-117">Child Elements</span></span>  
  
|<span data-ttu-id="ba72c-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba72c-118">Element</span></span>|<span data-ttu-id="ba72c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ba72c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba72c-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="ba72c-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="ba72c-121">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ba72c-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ba72c-122">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="ba72c-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba72c-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba72c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ba72c-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba72c-124">Element</span></span>|<span data-ttu-id="ba72c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ba72c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba72c-126">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ba72c-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ba72c-127">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="ba72c-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba72c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ba72c-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="ba72c-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ba72c-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ba72c-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ba72c-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
