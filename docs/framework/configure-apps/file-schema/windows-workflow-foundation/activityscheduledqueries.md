---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: e6891144d613623b199e7279aa091d4d7cbe4445
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284561"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="341e9-101">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="341e9-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="341e9-102">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="341e9-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="341e9-103">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="341e9-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="341e9-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="341e9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="341e9-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="341e9-105">\<system.serviceModel></span></span>  
<span data-ttu-id="341e9-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="341e9-106">\<tracking></span></span>  
<span data-ttu-id="341e9-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="341e9-107">\<trackingProfile></span></span>  
<span data-ttu-id="341e9-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="341e9-108">\<workflow></span></span>  
<span data-ttu-id="341e9-109">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="341e9-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="341e9-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="341e9-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="341e9-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="341e9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="341e9-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="341e9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="341e9-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="341e9-113">Attributes</span></span>  
 <span data-ttu-id="341e9-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="341e9-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="341e9-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="341e9-115">Child Elements</span></span>  
  
|<span data-ttu-id="341e9-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="341e9-116">Element</span></span>|<span data-ttu-id="341e9-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="341e9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="341e9-118">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="341e9-118">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="341e9-119">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="341e9-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="341e9-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="341e9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="341e9-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="341e9-121">Element</span></span>|<span data-ttu-id="341e9-122">Описание</span><span class="sxs-lookup"><span data-stu-id="341e9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="341e9-123">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="341e9-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="341e9-124">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="341e9-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="341e9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="341e9-125">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="341e9-126">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="341e9-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="341e9-127">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="341e9-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
