---
title: '&lt;bookmarkResumptionQueries&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7afa80a0abfa29c02cdf2ec6c96d2049f98db436
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="0c10b-102">&lt;bookmarkResumptionQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="0c10b-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="0c10b-103">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0c10b-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0c10b-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="0c10b-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="0c10b-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0c10b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="0c10b-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0c10b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0c10b-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="0c10b-107">\<tracking></span></span>  
<span data-ttu-id="0c10b-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0c10b-108">\<trackingProfile></span></span>  
<span data-ttu-id="0c10b-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="0c10b-109">\<workflow></span></span>  
<span data-ttu-id="0c10b-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="0c10b-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="0c10b-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="0c10b-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c10b-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c10b-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0c10b-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0c10b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0c10b-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0c10b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c10b-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0c10b-115">Attributes</span></span>  
 <span data-ttu-id="0c10b-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0c10b-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c10b-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0c10b-117">Child Elements</span></span>  
  
|<span data-ttu-id="0c10b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="0c10b-118">Element</span></span>|<span data-ttu-id="0c10b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0c10b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c10b-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="0c10b-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="0c10b-121">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0c10b-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0c10b-122">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="0c10b-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c10b-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0c10b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0c10b-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="0c10b-124">Element</span></span>|<span data-ttu-id="0c10b-125">Описание</span><span class="sxs-lookup"><span data-stu-id="0c10b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c10b-126">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="0c10b-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="0c10b-127">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="0c10b-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c10b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="0c10b-128">See Also</span></span>  
 <span data-ttu-id="0c10b-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0c10b-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="0c10b-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0c10b-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="0c10b-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0c10b-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0c10b-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="0c10b-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
