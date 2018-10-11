---
title: '&lt;activityScheduledQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 9a53d72316dad0178f24e05656a4fb4531b88aec
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087769"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="c3946-102">&lt;activityScheduledQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="c3946-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="c3946-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="c3946-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="c3946-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="c3946-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="c3946-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c3946-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="c3946-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c3946-106">\<system.serviceModel></span></span>  
<span data-ttu-id="c3946-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="c3946-107">\<tracking></span></span>  
<span data-ttu-id="c3946-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c3946-108">\<trackingProfile></span></span>  
<span data-ttu-id="c3946-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="c3946-109">\<workflow></span></span>  
<span data-ttu-id="c3946-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="c3946-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="c3946-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="c3946-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3946-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3946-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3946-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c3946-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c3946-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c3946-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3946-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c3946-115">Attributes</span></span>  
  
|<span data-ttu-id="c3946-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c3946-116">Attribute</span></span>|<span data-ttu-id="c3946-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c3946-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3946-118">activityName</span><span class="sxs-lookup"><span data-stu-id="c3946-118">activityName</span></span>|<span data-ttu-id="c3946-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="c3946-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="c3946-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="c3946-120">childActivityName</span></span>|<span data-ttu-id="c3946-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="c3946-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3946-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c3946-122">Child Elements</span></span>  
 <span data-ttu-id="c3946-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c3946-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3946-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c3946-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c3946-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="c3946-125">Element</span></span>|<span data-ttu-id="c3946-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="c3946-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3946-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="c3946-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="c3946-128">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="c3946-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3946-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c3946-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="c3946-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c3946-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="c3946-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="c3946-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
