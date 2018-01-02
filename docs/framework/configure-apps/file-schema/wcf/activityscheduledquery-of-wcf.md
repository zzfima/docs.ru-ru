---
title: '&lt;activityScheduledQuery&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: afb421993c39e66e437a0ecbb35091532df61716
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="13d95-102">&lt;activityScheduledQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="13d95-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="13d95-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="13d95-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="13d95-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="13d95-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="13d95-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="13d95-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="13d95-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="13d95-106">\<system.serviceModel></span></span>  
<span data-ttu-id="13d95-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="13d95-107">\<tracking></span></span>  
<span data-ttu-id="13d95-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="13d95-108">\<trackingProfile></span></span>  
<span data-ttu-id="13d95-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="13d95-109">\<workflow></span></span>  
<span data-ttu-id="13d95-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="13d95-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="13d95-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="13d95-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d95-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13d95-112">Syntax</span></span>  
  
```xml
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13d95-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="13d95-113">Attributes and Elements</span></span>  
 <span data-ttu-id="13d95-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="13d95-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13d95-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="13d95-115">Attributes</span></span>  
  
|<span data-ttu-id="13d95-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="13d95-116">Attribute</span></span>|<span data-ttu-id="13d95-117">Описание</span><span class="sxs-lookup"><span data-stu-id="13d95-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13d95-118">activityName</span><span class="sxs-lookup"><span data-stu-id="13d95-118">activityName</span></span>|<span data-ttu-id="13d95-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="13d95-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="13d95-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="13d95-120">childActivityName</span></span>|<span data-ttu-id="13d95-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="13d95-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13d95-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="13d95-122">Child Elements</span></span>  
 <span data-ttu-id="13d95-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="13d95-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13d95-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="13d95-124">Parent Elements</span></span>  
  
|<span data-ttu-id="13d95-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="13d95-125">Element</span></span>|<span data-ttu-id="13d95-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="13d95-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13d95-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="13d95-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="13d95-128">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="13d95-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13d95-129">См. также</span><span class="sxs-lookup"><span data-stu-id="13d95-129">See Also</span></span>  
 <span data-ttu-id="13d95-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span><span class="sxs-lookup"><span data-stu-id="13d95-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span></span>     
 <span data-ttu-id="13d95-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="13d95-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="13d95-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="13d95-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="13d95-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="13d95-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
