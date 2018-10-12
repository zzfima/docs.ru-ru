---
title: '&lt;activityScheduledQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: a3c4c8b338921c9d949edd83deb4d6073eb26b55
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123375"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="140ef-102">&lt;activityScheduledQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="140ef-102">&lt;activityScheduledQuery&gt; of WCF</span></span>

<span data-ttu-id="140ef-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="140ef-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="140ef-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="140ef-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="140ef-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="140ef-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="140ef-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="140ef-106">\<system.serviceModel></span></span>  
<span data-ttu-id="140ef-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="140ef-107">\<tracking></span></span>  
<span data-ttu-id="140ef-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="140ef-108">\<profiles></span></span>  
<span data-ttu-id="140ef-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="140ef-109">\<trackingProfile></span></span>  
<span data-ttu-id="140ef-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="140ef-110">\<workflow></span></span>  
<span data-ttu-id="140ef-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="140ef-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="140ef-112">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="140ef-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="140ef-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="140ef-113">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"   
                                  childActivityName="String"/>
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking> 
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="140ef-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="140ef-114">Attributes and elements</span></span>  

<span data-ttu-id="140ef-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="140ef-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="140ef-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="140ef-116">Attributes</span></span>  
  
|<span data-ttu-id="140ef-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="140ef-117">Attribute</span></span>|<span data-ttu-id="140ef-118">Описание</span><span class="sxs-lookup"><span data-stu-id="140ef-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="140ef-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="140ef-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="140ef-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="140ef-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="140ef-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="140ef-121">Child elements</span></span>

<span data-ttu-id="140ef-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="140ef-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="140ef-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="140ef-123">Parent elements</span></span>  
  
|<span data-ttu-id="140ef-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="140ef-124">Element</span></span>|<span data-ttu-id="140ef-125">Описание</span><span class="sxs-lookup"><span data-stu-id="140ef-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="140ef-126">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="140ef-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="140ef-127">Набор запросов, которые используются для отслеживания запланировать выполнение действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="140ef-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="140ef-128">См. также</span><span class="sxs-lookup"><span data-stu-id="140ef-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="140ef-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="140ef-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="140ef-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="140ef-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
