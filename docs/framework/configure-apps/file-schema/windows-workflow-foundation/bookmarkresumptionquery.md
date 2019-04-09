---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: e43ba66e2c3ccfbb723b1eea8ef6774ad3f9f2aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140040"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="4780e-101">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="4780e-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="4780e-102">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="4780e-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="4780e-103">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="4780e-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="4780e-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4780e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4780e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4780e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4780e-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="4780e-106">\<tracking></span></span>  
<span data-ttu-id="4780e-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="4780e-107">\<trackingProfile></span></span>  
<span data-ttu-id="4780e-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="4780e-108">\<workflow></span></span>  
<span data-ttu-id="4780e-109">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="4780e-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="4780e-110">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="4780e-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4780e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4780e-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4780e-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4780e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4780e-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4780e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4780e-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4780e-114">Attributes</span></span>  
  
|<span data-ttu-id="4780e-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4780e-115">Attribute</span></span>|<span data-ttu-id="4780e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4780e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4780e-117">имя</span><span class="sxs-lookup"><span data-stu-id="4780e-117">name</span></span>|<span data-ttu-id="4780e-118">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="4780e-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4780e-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4780e-119">Child Elements</span></span>  
 <span data-ttu-id="4780e-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4780e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4780e-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4780e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4780e-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="4780e-122">Element</span></span>|<span data-ttu-id="4780e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="4780e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4780e-124">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="4780e-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="4780e-125">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4780e-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4780e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4780e-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4780e-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="4780e-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4780e-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="4780e-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
