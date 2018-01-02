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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 821ded03ced33ee44c6588daefaf9049741abf8c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="9d98b-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="9d98b-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="9d98b-103">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="9d98b-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9d98b-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="9d98b-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="9d98b-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9d98b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9d98b-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9d98b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9d98b-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="9d98b-107">\<tracking></span></span>  
<span data-ttu-id="9d98b-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9d98b-108">\<trackingProfile></span></span>  
<span data-ttu-id="9d98b-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="9d98b-109">\<workflow></span></span>  
<span data-ttu-id="9d98b-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="9d98b-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="9d98b-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="9d98b-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d98b-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d98b-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d98b-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9d98b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9d98b-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9d98b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d98b-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9d98b-115">Attributes</span></span>  
  
|<span data-ttu-id="9d98b-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9d98b-116">Attribute</span></span>|<span data-ttu-id="9d98b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9d98b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d98b-118">имя</span><span class="sxs-lookup"><span data-stu-id="9d98b-118">name</span></span>|<span data-ttu-id="9d98b-119">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="9d98b-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d98b-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9d98b-120">Child Elements</span></span>  
 <span data-ttu-id="9d98b-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9d98b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d98b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9d98b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9d98b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="9d98b-123">Element</span></span>|<span data-ttu-id="9d98b-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="9d98b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d98b-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="9d98b-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="9d98b-126">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9d98b-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d98b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9d98b-127">See Also</span></span>  
 <span data-ttu-id="9d98b-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9d98b-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="9d98b-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9d98b-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="9d98b-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9d98b-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9d98b-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="9d98b-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
