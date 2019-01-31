---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 2199e66342c6fa3afca9d8ccd3b620560b123ede
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260844"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="06ae0-101">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="06ae0-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="06ae0-102">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="06ae0-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="06ae0-103">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="06ae0-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="06ae0-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="06ae0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="06ae0-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="06ae0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="06ae0-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="06ae0-106">\<tracking></span></span>  
<span data-ttu-id="06ae0-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="06ae0-107">\<trackingProfile></span></span>  
<span data-ttu-id="06ae0-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="06ae0-108">\<workflow></span></span>  
<span data-ttu-id="06ae0-109">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="06ae0-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="06ae0-110">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="06ae0-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ae0-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06ae0-111">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06ae0-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="06ae0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="06ae0-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="06ae0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06ae0-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="06ae0-114">Attributes</span></span>  
  
|<span data-ttu-id="06ae0-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="06ae0-115">Attribute</span></span>|<span data-ttu-id="06ae0-116">Описание</span><span class="sxs-lookup"><span data-stu-id="06ae0-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06ae0-117">activityName</span><span class="sxs-lookup"><span data-stu-id="06ae0-117">activityName</span></span>|<span data-ttu-id="06ae0-118">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="06ae0-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="06ae0-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="06ae0-119">childActivityName</span></span>|<span data-ttu-id="06ae0-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="06ae0-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06ae0-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="06ae0-121">Child Elements</span></span>  
 <span data-ttu-id="06ae0-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="06ae0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06ae0-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="06ae0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="06ae0-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="06ae0-124">Element</span></span>|<span data-ttu-id="06ae0-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="06ae0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06ae0-126">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="06ae0-126">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="06ae0-127">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="06ae0-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06ae0-128">См. также</span><span class="sxs-lookup"><span data-stu-id="06ae0-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="06ae0-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="06ae0-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="06ae0-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="06ae0-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
