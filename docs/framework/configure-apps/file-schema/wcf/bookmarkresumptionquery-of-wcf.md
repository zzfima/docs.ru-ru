---
title: '&lt;bookmarkResumptionQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 07215347da19a05d5915296668d990853fdae646
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087795"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="0bbeb-102">&lt;bookmarkResumptionQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="0bbeb-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="0bbeb-103">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0bbeb-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="0bbeb-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0bbeb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="0bbeb-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0bbeb-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0bbeb-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="0bbeb-107">\<tracking></span></span>  
<span data-ttu-id="0bbeb-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0bbeb-108">\<trackingProfile></span></span>  
<span data-ttu-id="0bbeb-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="0bbeb-109">\<workflow></span></span>  
<span data-ttu-id="0bbeb-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="0bbeb-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="0bbeb-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="0bbeb-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bbeb-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bbeb-112">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="0bbeb-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0bbeb-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0bbeb-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bbeb-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0bbeb-115">Attributes</span></span>  
  
|<span data-ttu-id="0bbeb-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0bbeb-116">Attribute</span></span>|<span data-ttu-id="0bbeb-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0bbeb-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0bbeb-118">имя</span><span class="sxs-lookup"><span data-stu-id="0bbeb-118">name</span></span>|<span data-ttu-id="0bbeb-119">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bbeb-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0bbeb-120">Child Elements</span></span>  
 <span data-ttu-id="0bbeb-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bbeb-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0bbeb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0bbeb-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="0bbeb-123">Element</span></span>|<span data-ttu-id="0bbeb-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="0bbeb-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bbeb-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="0bbeb-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="0bbeb-126">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bbeb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0bbeb-127">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="0bbeb-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0bbeb-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0bbeb-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="0bbeb-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
