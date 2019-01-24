---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: a5eb00d1e094484e3ec01e0db18719ec50e4b953
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515077"
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="99876-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="99876-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="99876-103">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="99876-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="99876-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="99876-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="99876-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="99876-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="99876-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99876-106">\<system.serviceModel></span></span>  
<span data-ttu-id="99876-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="99876-107">\<tracking></span></span>  
<span data-ttu-id="99876-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="99876-108">\<trackingProfile></span></span>  
<span data-ttu-id="99876-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="99876-109">\<workflow></span></span>  
<span data-ttu-id="99876-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="99876-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="99876-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="99876-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99876-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99876-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99876-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="99876-113">Attributes and Elements</span></span>  
 <span data-ttu-id="99876-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="99876-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99876-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="99876-115">Attributes</span></span>  
  
|<span data-ttu-id="99876-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="99876-116">Attribute</span></span>|<span data-ttu-id="99876-117">Описание</span><span class="sxs-lookup"><span data-stu-id="99876-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99876-118">имя</span><span class="sxs-lookup"><span data-stu-id="99876-118">name</span></span>|<span data-ttu-id="99876-119">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="99876-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99876-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="99876-120">Child Elements</span></span>  
 <span data-ttu-id="99876-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="99876-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99876-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="99876-122">Parent Elements</span></span>  
  
|<span data-ttu-id="99876-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="99876-123">Element</span></span>|<span data-ttu-id="99876-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="99876-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99876-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="99876-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="99876-126">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="99876-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99876-127">См. также</span><span class="sxs-lookup"><span data-stu-id="99876-127">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="99876-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="99876-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="99876-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="99876-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
