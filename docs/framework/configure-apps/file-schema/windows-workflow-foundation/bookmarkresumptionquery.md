---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: e43ba66e2c3ccfbb723b1eea8ef6774ad3f9f2aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790277"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="77c6f-101">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="77c6f-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="77c6f-102">Представляет запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего потока.</span><span class="sxs-lookup"><span data-stu-id="77c6f-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="77c6f-103">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="77c6f-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="77c6f-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="77c6f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="77c6f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="77c6f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="77c6f-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="77c6f-106">\<tracking></span></span>  
<span data-ttu-id="77c6f-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="77c6f-107">\<trackingProfile></span></span>  
<span data-ttu-id="77c6f-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="77c6f-108">\<workflow></span></span>  
<span data-ttu-id="77c6f-109">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="77c6f-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="77c6f-110">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="77c6f-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77c6f-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77c6f-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77c6f-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="77c6f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="77c6f-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="77c6f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77c6f-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="77c6f-114">Attributes</span></span>  
  
|<span data-ttu-id="77c6f-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="77c6f-115">Attribute</span></span>|<span data-ttu-id="77c6f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="77c6f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77c6f-117">имя</span><span class="sxs-lookup"><span data-stu-id="77c6f-117">name</span></span>|<span data-ttu-id="77c6f-118">Строка, задающая имя записи закладки, которое используется для подписки.</span><span class="sxs-lookup"><span data-stu-id="77c6f-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77c6f-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="77c6f-119">Child Elements</span></span>  
 <span data-ttu-id="77c6f-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="77c6f-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77c6f-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="77c6f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="77c6f-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="77c6f-122">Element</span></span>|<span data-ttu-id="77c6f-123">Описание</span><span class="sxs-lookup"><span data-stu-id="77c6f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77c6f-124">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="77c6f-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="77c6f-125">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="77c6f-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77c6f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="77c6f-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="77c6f-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="77c6f-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="77c6f-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="77c6f-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
