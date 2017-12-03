---
title: '&lt;activityScheduledQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d860474c4a638a347f85c07862c330f58cc30c09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="13842-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="13842-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="13842-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="13842-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="13842-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="13842-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="13842-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="13842-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="13842-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="13842-106">\<system.serviceModel></span></span>  
<span data-ttu-id="13842-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="13842-107">\<tracking></span></span>  
<span data-ttu-id="13842-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="13842-108">\<trackingProfile></span></span>  
<span data-ttu-id="13842-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="13842-109">\<workflow></span></span>  
<span data-ttu-id="13842-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="13842-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13842-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13842-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13842-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="13842-112">Attributes and Elements</span></span>  
 <span data-ttu-id="13842-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="13842-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13842-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="13842-114">Attributes</span></span>  
 <span data-ttu-id="13842-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="13842-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13842-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="13842-116">Child Elements</span></span>  
  
|<span data-ttu-id="13842-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="13842-117">Element</span></span>|<span data-ttu-id="13842-118">Описание</span><span class="sxs-lookup"><span data-stu-id="13842-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13842-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="13842-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="13842-120">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="13842-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13842-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="13842-121">Parent Elements</span></span>  
  
|<span data-ttu-id="13842-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="13842-122">Element</span></span>|<span data-ttu-id="13842-123">Описание</span><span class="sxs-lookup"><span data-stu-id="13842-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13842-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="13842-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="13842-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="13842-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13842-126">См. также</span><span class="sxs-lookup"><span data-stu-id="13842-126">See Also</span></span>  
 <span data-ttu-id="13842-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="13842-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="13842-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="13842-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="13842-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="13842-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="13842-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="13842-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
