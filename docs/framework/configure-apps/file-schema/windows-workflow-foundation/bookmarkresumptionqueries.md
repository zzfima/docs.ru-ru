---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 186990577ec4eedc7cae3710c455816c3162fc94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790290"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="51f1b-101">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="51f1b-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="51f1b-102">Представляет коллекцию запросов, используемых для отслеживания возобновления чтения с закладок в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="51f1b-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="51f1b-103">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="51f1b-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="51f1b-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="51f1b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="51f1b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="51f1b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="51f1b-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="51f1b-106">\<tracking></span></span>  
<span data-ttu-id="51f1b-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="51f1b-107">\<trackingProfile></span></span>  
<span data-ttu-id="51f1b-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="51f1b-108">\<workflow></span></span>  
<span data-ttu-id="51f1b-109">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="51f1b-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="51f1b-110">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="51f1b-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f1b-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51f1b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51f1b-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="51f1b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="51f1b-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="51f1b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51f1b-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="51f1b-114">Attributes</span></span>  
 <span data-ttu-id="51f1b-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="51f1b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="51f1b-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="51f1b-116">Child Elements</span></span>  
  
|<span data-ttu-id="51f1b-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="51f1b-117">Element</span></span>|<span data-ttu-id="51f1b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="51f1b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51f1b-119">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="51f1b-119">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="51f1b-120">Запрос, используемый для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="51f1b-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="51f1b-121">Этот запрос необходим, чтобы участник отслеживания мог подписываться на записи о возобновлении чтения с закладок.</span><span class="sxs-lookup"><span data-stu-id="51f1b-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51f1b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="51f1b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="51f1b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="51f1b-123">Element</span></span>|<span data-ttu-id="51f1b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="51f1b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51f1b-125">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="51f1b-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="51f1b-126">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="51f1b-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51f1b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="51f1b-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="51f1b-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="51f1b-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="51f1b-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="51f1b-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
