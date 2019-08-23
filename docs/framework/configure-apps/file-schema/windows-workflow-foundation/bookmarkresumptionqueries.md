---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: f048612673a9b6b69c3cdded6526c76359c444e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945991"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="1e666-101">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="1e666-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="1e666-102">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1e666-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1e666-103">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="1e666-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="1e666-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="1e666-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1e666-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="1e666-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1e666-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="1e666-106">\<tracking></span></span>  
<span data-ttu-id="1e666-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1e666-107">\<trackingProfile></span></span>  
<span data-ttu-id="1e666-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1e666-108">\<workflow></span></span>  
<span data-ttu-id="1e666-109">\<Букмаркресумптионкуериес ></span><span class="sxs-lookup"><span data-stu-id="1e666-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="1e666-110">\<Букмаркресумптионкуери ></span><span class="sxs-lookup"><span data-stu-id="1e666-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e666-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e666-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e666-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e666-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1e666-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e666-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e666-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e666-114">Attributes</span></span>  
 <span data-ttu-id="1e666-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="1e666-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1e666-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e666-116">Child Elements</span></span>  
  
|<span data-ttu-id="1e666-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e666-117">Element</span></span>|<span data-ttu-id="1e666-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1e666-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e666-119">\<Букмаркресумптионкуери ></span><span class="sxs-lookup"><span data-stu-id="1e666-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="1e666-120">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1e666-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1e666-121">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="1e666-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e666-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e666-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1e666-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e666-123">Element</span></span>|<span data-ttu-id="1e666-124">Описание</span><span class="sxs-lookup"><span data-stu-id="1e666-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e666-125">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1e666-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="1e666-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="1e666-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e666-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1e666-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1e666-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="1e666-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1e666-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="1e666-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
