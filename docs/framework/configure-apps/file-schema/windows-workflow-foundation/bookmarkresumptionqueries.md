---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: b0ce29213f1f281e8581b90dda17aba1bdc29072
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="dfc63-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="dfc63-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="dfc63-103">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dfc63-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="dfc63-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="dfc63-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="dfc63-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="dfc63-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="dfc63-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="dfc63-106">\<system.serviceModel></span></span>  
<span data-ttu-id="dfc63-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="dfc63-107">\<tracking></span></span>  
<span data-ttu-id="dfc63-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dfc63-108">\<trackingProfile></span></span>  
<span data-ttu-id="dfc63-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="dfc63-109">\<workflow></span></span>  
<span data-ttu-id="dfc63-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="dfc63-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="dfc63-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="dfc63-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfc63-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfc63-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfc63-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dfc63-113">Attributes and Elements</span></span>  
 <span data-ttu-id="dfc63-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dfc63-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfc63-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dfc63-115">Attributes</span></span>  
 <span data-ttu-id="dfc63-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dfc63-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dfc63-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dfc63-117">Child Elements</span></span>  
  
|<span data-ttu-id="dfc63-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="dfc63-118">Element</span></span>|<span data-ttu-id="dfc63-119">Описание</span><span class="sxs-lookup"><span data-stu-id="dfc63-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfc63-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="dfc63-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="dfc63-121">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="dfc63-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="dfc63-122">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="dfc63-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfc63-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dfc63-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dfc63-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="dfc63-124">Element</span></span>|<span data-ttu-id="dfc63-125">Описание</span><span class="sxs-lookup"><span data-stu-id="dfc63-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfc63-126">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="dfc63-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="dfc63-127">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="dfc63-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfc63-128">См. также</span><span class="sxs-lookup"><span data-stu-id="dfc63-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="dfc63-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="dfc63-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dfc63-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="dfc63-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
