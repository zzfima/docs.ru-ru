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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3ab5fc54b80d91f89121f9acfd1f041672e11d4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="6c069-102">&lt;activityScheduledQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="6c069-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="6c069-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="6c069-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="6c069-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="6c069-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="6c069-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6c069-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="6c069-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6c069-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6c069-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="6c069-107">\<tracking></span></span>  
<span data-ttu-id="6c069-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6c069-108">\<trackingProfile></span></span>  
<span data-ttu-id="6c069-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="6c069-109">\<workflow></span></span>  
<span data-ttu-id="6c069-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="6c069-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="6c069-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="6c069-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c069-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c069-112">Syntax</span></span>  
  
```xml
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c069-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c069-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6c069-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6c069-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c069-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c069-115">Attributes</span></span>  
  
|<span data-ttu-id="6c069-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6c069-116">Attribute</span></span>|<span data-ttu-id="6c069-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6c069-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c069-118">activityName</span><span class="sxs-lookup"><span data-stu-id="6c069-118">activityName</span></span>|<span data-ttu-id="6c069-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="6c069-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="6c069-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="6c069-120">childActivityName</span></span>|<span data-ttu-id="6c069-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="6c069-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c069-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c069-122">Child Elements</span></span>  
 <span data-ttu-id="6c069-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6c069-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c069-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c069-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6c069-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c069-125">Element</span></span>|<span data-ttu-id="6c069-126">Описание</span><span class="sxs-lookup"><span data-stu-id="6c069-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c069-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="6c069-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="6c069-128">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="6c069-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c069-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6c069-129">See Also</span></span>  
 <span data-ttu-id="6c069-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span><span class="sxs-lookup"><span data-stu-id="6c069-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span></span>     
 <span data-ttu-id="6c069-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="6c069-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="6c069-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="6c069-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="6c069-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="6c069-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
