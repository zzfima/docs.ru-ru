---
title: '&lt;activityScheduledQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: fd7830bc178de0693f0632cea3b390d792408ec1
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147883"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="27f74-102">&lt;activityScheduledQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="27f74-102">&lt;activityScheduledQuery&gt; of WCF</span></span>

<span data-ttu-id="27f74-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="27f74-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="27f74-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="27f74-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="27f74-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="27f74-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="27f74-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="27f74-106">\<system.serviceModel></span></span>  
<span data-ttu-id="27f74-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="27f74-107">\<tracking></span></span>  
<span data-ttu-id="27f74-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="27f74-108">\<profiles></span></span>  
<span data-ttu-id="27f74-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="27f74-109">\<trackingProfile></span></span>  
<span data-ttu-id="27f74-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="27f74-110">\<workflow></span></span>  
<span data-ttu-id="27f74-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="27f74-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="27f74-112">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="27f74-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27f74-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27f74-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27f74-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="27f74-114">Attributes and elements</span></span>  

<span data-ttu-id="27f74-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="27f74-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27f74-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27f74-116">Attributes</span></span>  
  
|<span data-ttu-id="27f74-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27f74-117">Attribute</span></span>|<span data-ttu-id="27f74-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="27f74-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="27f74-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="27f74-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="27f74-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="27f74-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27f74-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27f74-121">Child elements</span></span>

<span data-ttu-id="27f74-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="27f74-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="27f74-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="27f74-123">Parent elements</span></span>  
  
|<span data-ttu-id="27f74-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="27f74-124">Element</span></span>|<span data-ttu-id="27f74-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="27f74-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27f74-126">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="27f74-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="27f74-127">Набор запросов, которые используются для отслеживания запланировать выполнение действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="27f74-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27f74-128">См. также</span><span class="sxs-lookup"><span data-stu-id="27f74-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="27f74-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="27f74-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="27f74-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="27f74-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
