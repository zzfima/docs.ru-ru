---
title: '&lt;bookmarkResumptionQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 6463404e17edff8eb1efe3f96e44b5b9997ffca3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147815"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="25507-102">&lt;bookmarkResumptionQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="25507-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>

<span data-ttu-id="25507-103">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="25507-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="25507-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="25507-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="25507-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="25507-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="25507-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="25507-106">\<system.serviceModel></span></span>  
<span data-ttu-id="25507-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="25507-107">\<tracking></span></span>  
<span data-ttu-id="25507-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="25507-108">\<profiles></span></span>  
<span data-ttu-id="25507-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="25507-109">\<trackingProfile></span></span>  
<span data-ttu-id="25507-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="25507-110">\<workflow></span></span>  
<span data-ttu-id="25507-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="25507-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="25507-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="25507-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25507-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25507-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25507-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="25507-114">Attributes and elements</span></span>

<span data-ttu-id="25507-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="25507-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25507-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="25507-116">Attributes</span></span>  
  
|<span data-ttu-id="25507-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="25507-117">Attribute</span></span>|<span data-ttu-id="25507-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="25507-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="25507-119">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="25507-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25507-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="25507-120">Child elements</span></span>

<span data-ttu-id="25507-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="25507-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="25507-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="25507-122">Parent elements</span></span>  
  
|<span data-ttu-id="25507-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="25507-123">Element</span></span>|<span data-ttu-id="25507-124">Описание</span><span class="sxs-lookup"><span data-stu-id="25507-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25507-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="25507-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="25507-126">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="25507-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25507-127">См. также</span><span class="sxs-lookup"><span data-stu-id="25507-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="25507-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="25507-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="25507-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="25507-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
