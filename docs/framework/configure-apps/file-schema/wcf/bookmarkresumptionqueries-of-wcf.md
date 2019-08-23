---
title: <bookmarkResumptionQueries>WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 5ec9827e9862866096265da576c91b10573012d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919741"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="a0396-102">\<Букмаркресумптионкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="a0396-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="a0396-103">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a0396-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="a0396-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="a0396-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="a0396-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a0396-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="a0396-106">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="a0396-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a0396-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="a0396-107">\<tracking></span></span>  
<span data-ttu-id="a0396-108">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="a0396-108">\<profiles></span></span>  
<span data-ttu-id="a0396-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a0396-109">\<trackingProfile></span></span>  
<span data-ttu-id="a0396-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a0396-110">\<workflow></span></span>  
<span data-ttu-id="a0396-111">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="a0396-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="a0396-112">\<Букмаркресумптионкуери ></span><span class="sxs-lookup"><span data-stu-id="a0396-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0396-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0396-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0396-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a0396-114">Attributes and elements</span></span>  
  
<span data-ttu-id="a0396-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a0396-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0396-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a0396-116">Attributes</span></span>  
  
<span data-ttu-id="a0396-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="a0396-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0396-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a0396-118">Child elements</span></span>  
  
|<span data-ttu-id="a0396-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0396-119">Element</span></span>|<span data-ttu-id="a0396-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a0396-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0396-121">\<Букмаркресумптионкуери ></span><span class="sxs-lookup"><span data-stu-id="a0396-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="a0396-122">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a0396-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="a0396-123">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="a0396-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0396-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a0396-124">Parent elements</span></span>  
  
|<span data-ttu-id="a0396-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0396-125">Element</span></span>|<span data-ttu-id="a0396-126">Описание</span><span class="sxs-lookup"><span data-stu-id="a0396-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0396-127">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a0396-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="a0396-128">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="a0396-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0396-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a0396-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a0396-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a0396-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a0396-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a0396-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
