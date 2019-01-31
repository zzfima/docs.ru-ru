---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 4277df5b4c36fa2f3571ba8441a7eb8aaf6d106a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261557"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="5e8b0-101">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="5e8b0-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="5e8b0-102">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5e8b0-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="5e8b0-103">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="5e8b0-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="5e8b0-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5e8b0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5e8b0-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5e8b0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="5e8b0-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="5e8b0-106">\<tracking></span></span>  
<span data-ttu-id="5e8b0-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="5e8b0-107">\<trackingProfile></span></span>  
<span data-ttu-id="5e8b0-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="5e8b0-108">\<workflow></span></span>  
<span data-ttu-id="5e8b0-109">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="5e8b0-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="5e8b0-110">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="5e8b0-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e8b0-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e8b0-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e8b0-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5e8b0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5e8b0-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5e8b0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e8b0-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5e8b0-114">Attributes</span></span>  
 <span data-ttu-id="5e8b0-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5e8b0-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5e8b0-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5e8b0-116">Child Elements</span></span>  
  
|<span data-ttu-id="5e8b0-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="5e8b0-117">Element</span></span>|<span data-ttu-id="5e8b0-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="5e8b0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e8b0-119">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="5e8b0-119">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="5e8b0-120">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5e8b0-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="5e8b0-121">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="5e8b0-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e8b0-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5e8b0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5e8b0-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="5e8b0-123">Element</span></span>|<span data-ttu-id="5e8b0-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="5e8b0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e8b0-125">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="5e8b0-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5e8b0-126">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="5e8b0-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e8b0-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5e8b0-127">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5e8b0-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="5e8b0-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5e8b0-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="5e8b0-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
