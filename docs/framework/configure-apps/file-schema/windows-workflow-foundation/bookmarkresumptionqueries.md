---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fb3cf8457dc19081e9eb51091453764513da8ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="8d893-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="8d893-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="8d893-103">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8d893-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8d893-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="8d893-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="8d893-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8d893-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8d893-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8d893-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8d893-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="8d893-107">\<tracking></span></span>  
<span data-ttu-id="8d893-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8d893-108">\<trackingProfile></span></span>  
<span data-ttu-id="8d893-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8d893-109">\<workflow></span></span>  
<span data-ttu-id="8d893-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="8d893-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="8d893-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="8d893-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d893-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d893-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d893-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8d893-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8d893-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8d893-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d893-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d893-115">Attributes</span></span>  
 <span data-ttu-id="8d893-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8d893-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8d893-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d893-117">Child Elements</span></span>  
  
|<span data-ttu-id="8d893-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d893-118">Element</span></span>|<span data-ttu-id="8d893-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="8d893-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d893-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="8d893-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="8d893-121">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8d893-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8d893-122">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="8d893-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d893-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d893-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8d893-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d893-124">Element</span></span>|<span data-ttu-id="8d893-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="8d893-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d893-126">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8d893-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8d893-127">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="8d893-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d893-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8d893-128">See Also</span></span>  
 <span data-ttu-id="8d893-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8d893-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="8d893-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8d893-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="8d893-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8d893-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8d893-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="8d893-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
