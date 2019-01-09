---
title: '&lt;bookmarkResumptionQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: ba8c98557a859f4bd37b9aaca80a44c393429da4
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146086"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="8668a-102">&lt;bookmarkResumptionQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="8668a-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
  
<span data-ttu-id="8668a-103">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8668a-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8668a-104">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="8668a-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="8668a-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8668a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="8668a-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8668a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8668a-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="8668a-107">\<tracking></span></span>  
<span data-ttu-id="8668a-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="8668a-108">\<profiles></span></span>  
<span data-ttu-id="8668a-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8668a-109">\<trackingProfile></span></span>  
<span data-ttu-id="8668a-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8668a-110">\<workflow></span></span>  
<span data-ttu-id="8668a-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="8668a-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="8668a-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="8668a-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8668a-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8668a-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8668a-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="8668a-114">Attributes and elements</span></span>  
  
<span data-ttu-id="8668a-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8668a-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8668a-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8668a-116">Attributes</span></span>  
  
<span data-ttu-id="8668a-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8668a-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8668a-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8668a-118">Child elements</span></span>  
  
|<span data-ttu-id="8668a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="8668a-119">Element</span></span>|<span data-ttu-id="8668a-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="8668a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8668a-121">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="8668a-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="8668a-122">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8668a-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8668a-123">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="8668a-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8668a-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8668a-124">Parent elements</span></span>  
  
|<span data-ttu-id="8668a-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="8668a-125">Element</span></span>|<span data-ttu-id="8668a-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="8668a-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8668a-127">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8668a-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8668a-128">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="8668a-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8668a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8668a-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType> 
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="8668a-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8668a-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="8668a-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="8668a-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
