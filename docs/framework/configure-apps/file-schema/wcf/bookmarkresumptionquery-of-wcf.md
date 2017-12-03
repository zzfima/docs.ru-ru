---
title: '&lt;bookmarkResumptionQuery&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 124b05d8e1ce9831a1efb3c6e62cc5e9fd3058fc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="f068b-102">&lt;bookmarkResumptionQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="f068b-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="f068b-103">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="f068b-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="f068b-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="f068b-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="f068b-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f068b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="f068b-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f068b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="f068b-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f068b-107">\<tracking></span></span>  
<span data-ttu-id="f068b-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f068b-108">\<trackingProfile></span></span>  
<span data-ttu-id="f068b-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="f068b-109">\<workflow></span></span>  
<span data-ttu-id="f068b-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="f068b-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="f068b-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="f068b-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f068b-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f068b-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f068b-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f068b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f068b-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f068b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f068b-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f068b-115">Attributes</span></span>  
  
|<span data-ttu-id="f068b-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f068b-116">Attribute</span></span>|<span data-ttu-id="f068b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f068b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f068b-118">имя</span><span class="sxs-lookup"><span data-stu-id="f068b-118">name</span></span>|<span data-ttu-id="f068b-119">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="f068b-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f068b-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f068b-120">Child Elements</span></span>  
 <span data-ttu-id="f068b-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f068b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f068b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f068b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f068b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="f068b-123">Element</span></span>|<span data-ttu-id="f068b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="f068b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f068b-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="f068b-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="f068b-126">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f068b-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f068b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f068b-127">See Also</span></span>  
 <span data-ttu-id="f068b-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f068b-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f068b-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f068b-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="f068b-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f068b-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f068b-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f068b-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
