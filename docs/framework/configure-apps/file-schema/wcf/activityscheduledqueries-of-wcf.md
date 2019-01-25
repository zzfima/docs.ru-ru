---
title: '&lt;activityScheduledQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 5430058049e8a09c1e2a289e1f997338c23b9d94
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492160"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="12856-102">&lt;activityScheduledQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="12856-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="12856-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="12856-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="12856-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="12856-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="12856-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="12856-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="12856-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="12856-106">\<system.serviceModel></span></span>  
<span data-ttu-id="12856-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="12856-107">\<tracking></span></span>  
<span data-ttu-id="12856-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="12856-108">\<profiles></span></span>  
<span data-ttu-id="12856-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="12856-109">\<trackingProfile></span></span>  
<span data-ttu-id="12856-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="12856-110">\<workflow></span></span>  
<span data-ttu-id="12856-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="12856-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12856-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12856-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12856-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="12856-113">Attributes and elements</span></span>  

<span data-ttu-id="12856-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="12856-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12856-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="12856-115">Attributes</span></span>  

<span data-ttu-id="12856-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="12856-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12856-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="12856-117">Child elements</span></span>  
  
|<span data-ttu-id="12856-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="12856-118">Element</span></span>|<span data-ttu-id="12856-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="12856-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12856-120">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="12856-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="12856-121">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="12856-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12856-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="12856-122">Parent elements</span></span>  
  
|<span data-ttu-id="12856-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="12856-123">Element</span></span>|<span data-ttu-id="12856-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="12856-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12856-125">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="12856-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="12856-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="12856-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12856-127">См. также</span><span class="sxs-lookup"><span data-stu-id="12856-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="12856-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="12856-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="12856-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="12856-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
