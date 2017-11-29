---
title: '&lt;activityScheduledQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 779ac3995d4d5fb1b63de6ae6b9db7103691d6f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="bda4d-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="bda4d-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="bda4d-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="bda4d-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="bda4d-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="bda4d-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="bda4d-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bda4d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="bda4d-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="bda4d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="bda4d-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="bda4d-107">\<tracking></span></span>  
<span data-ttu-id="bda4d-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="bda4d-108">\<trackingProfile></span></span>  
<span data-ttu-id="bda4d-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="bda4d-109">\<workflow></span></span>  
<span data-ttu-id="bda4d-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="bda4d-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="bda4d-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="bda4d-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda4d-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bda4d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bda4d-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bda4d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="bda4d-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bda4d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bda4d-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bda4d-115">Attributes</span></span>  
  
|<span data-ttu-id="bda4d-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bda4d-116">Attribute</span></span>|<span data-ttu-id="bda4d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="bda4d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bda4d-118">activityName</span><span class="sxs-lookup"><span data-stu-id="bda4d-118">activityName</span></span>|<span data-ttu-id="bda4d-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="bda4d-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="bda4d-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="bda4d-120">childActivityName</span></span>|<span data-ttu-id="bda4d-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="bda4d-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bda4d-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bda4d-122">Child Elements</span></span>  
 <span data-ttu-id="bda4d-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bda4d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bda4d-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bda4d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bda4d-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="bda4d-125">Element</span></span>|<span data-ttu-id="bda4d-126">Описание</span><span class="sxs-lookup"><span data-stu-id="bda4d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bda4d-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="bda4d-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="bda4d-128">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="bda4d-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bda4d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="bda4d-129">See Also</span></span>  
 <span data-ttu-id="bda4d-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bda4d-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="bda4d-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bda4d-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="bda4d-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="bda4d-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="bda4d-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="bda4d-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
