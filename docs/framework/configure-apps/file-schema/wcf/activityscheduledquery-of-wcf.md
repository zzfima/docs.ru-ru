---
title: <activityScheduledQuery> для WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 5087d56092296f8c68b719ec0945993adeb3de0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704723"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="9ec4d-102">\<activityScheduledQuery > из WCF</span><span class="sxs-lookup"><span data-stu-id="9ec4d-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="9ec4d-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="9ec4d-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="9ec4d-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="9ec4d-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="9ec4d-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9ec4d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9ec4d-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9ec4d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9ec4d-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="9ec4d-107">\<tracking></span></span>  
<span data-ttu-id="9ec4d-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="9ec4d-108">\<profiles></span></span>  
<span data-ttu-id="9ec4d-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9ec4d-109">\<trackingProfile></span></span>  
<span data-ttu-id="9ec4d-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="9ec4d-110">\<workflow></span></span>  
<span data-ttu-id="9ec4d-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="9ec4d-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="9ec4d-112">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="9ec4d-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ec4d-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ec4d-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ec4d-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ec4d-114">Attributes and elements</span></span>  

<span data-ttu-id="9ec4d-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9ec4d-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ec4d-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ec4d-116">Attributes</span></span>  
  
|<span data-ttu-id="9ec4d-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9ec4d-117">Attribute</span></span>|<span data-ttu-id="9ec4d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="9ec4d-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="9ec4d-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="9ec4d-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="9ec4d-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="9ec4d-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ec4d-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ec4d-121">Child elements</span></span>

<span data-ttu-id="9ec4d-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9ec4d-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="9ec4d-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ec4d-123">Parent elements</span></span>  
  
|<span data-ttu-id="9ec4d-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ec4d-124">Element</span></span>|<span data-ttu-id="9ec4d-125">Описание</span><span class="sxs-lookup"><span data-stu-id="9ec4d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ec4d-126">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="9ec4d-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="9ec4d-127">Набор запросов, которые используются для отслеживания запланировать выполнение действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="9ec4d-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ec4d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9ec4d-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="9ec4d-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9ec4d-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9ec4d-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="9ec4d-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
