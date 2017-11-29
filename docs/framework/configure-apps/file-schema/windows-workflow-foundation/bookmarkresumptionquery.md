---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e52b4ef5104397d3c4b8abc89a1d637b17fcde9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="c5419-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="c5419-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="c5419-103">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="c5419-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="c5419-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="c5419-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="c5419-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c5419-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c5419-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c5419-106">\<system.serviceModel></span></span>  
<span data-ttu-id="c5419-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="c5419-107">\<tracking></span></span>  
<span data-ttu-id="c5419-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c5419-108">\<trackingProfile></span></span>  
<span data-ttu-id="c5419-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="c5419-109">\<workflow></span></span>  
<span data-ttu-id="c5419-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="c5419-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="c5419-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="c5419-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5419-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5419-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5419-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c5419-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c5419-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c5419-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5419-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c5419-115">Attributes</span></span>  
  
|<span data-ttu-id="c5419-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c5419-116">Attribute</span></span>|<span data-ttu-id="c5419-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c5419-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5419-118">имя</span><span class="sxs-lookup"><span data-stu-id="c5419-118">name</span></span>|<span data-ttu-id="c5419-119">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="c5419-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5419-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c5419-120">Child Elements</span></span>  
 <span data-ttu-id="c5419-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c5419-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5419-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c5419-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c5419-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="c5419-123">Element</span></span>|<span data-ttu-id="c5419-124">Описание</span><span class="sxs-lookup"><span data-stu-id="c5419-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5419-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="c5419-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="c5419-126">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c5419-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5419-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c5419-127">See Also</span></span>  
 <span data-ttu-id="c5419-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c5419-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="c5419-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c5419-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="c5419-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c5419-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="c5419-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="c5419-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
