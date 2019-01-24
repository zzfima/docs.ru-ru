---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: ae6a81123379ecd0e7fdc72f4e115a462f81eb90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555041"
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="dff1e-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="dff1e-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="dff1e-103">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dff1e-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="dff1e-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="dff1e-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="dff1e-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="dff1e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="dff1e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dff1e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="dff1e-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="dff1e-107">\<tracking></span></span>  
<span data-ttu-id="dff1e-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dff1e-108">\<trackingProfile></span></span>  
<span data-ttu-id="dff1e-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="dff1e-109">\<workflow></span></span>  
<span data-ttu-id="dff1e-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="dff1e-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="dff1e-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="dff1e-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff1e-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dff1e-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dff1e-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dff1e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="dff1e-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dff1e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dff1e-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dff1e-115">Attributes</span></span>  
 <span data-ttu-id="dff1e-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dff1e-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dff1e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dff1e-117">Child Elements</span></span>  
  
|<span data-ttu-id="dff1e-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="dff1e-118">Element</span></span>|<span data-ttu-id="dff1e-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="dff1e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dff1e-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="dff1e-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="dff1e-121">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dff1e-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="dff1e-122">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="dff1e-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dff1e-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dff1e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dff1e-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="dff1e-124">Element</span></span>|<span data-ttu-id="dff1e-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="dff1e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dff1e-126">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="dff1e-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="dff1e-127">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="dff1e-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dff1e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="dff1e-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dff1e-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="dff1e-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dff1e-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="dff1e-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
