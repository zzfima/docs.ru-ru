---
title: <activityScheduledQueries> для WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 1c9c292080016d7a2d0014ed07be371c0e247621
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285783"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="4b873-102">\<activityScheduledQueries > из WCF</span><span class="sxs-lookup"><span data-stu-id="4b873-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="4b873-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="4b873-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="4b873-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="4b873-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="4b873-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4b873-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4b873-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4b873-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4b873-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="4b873-107">\<tracking></span></span>  
<span data-ttu-id="4b873-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="4b873-108">\<profiles></span></span>  
<span data-ttu-id="4b873-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="4b873-109">\<trackingProfile></span></span>  
<span data-ttu-id="4b873-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="4b873-110">\<workflow></span></span>  
<span data-ttu-id="4b873-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="4b873-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b873-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b873-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b873-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="4b873-113">Attributes and elements</span></span>  

<span data-ttu-id="4b873-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4b873-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b873-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4b873-115">Attributes</span></span>  

<span data-ttu-id="4b873-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4b873-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b873-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4b873-117">Child elements</span></span>  
  
|<span data-ttu-id="4b873-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b873-118">Element</span></span>|<span data-ttu-id="4b873-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="4b873-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b873-120">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="4b873-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="4b873-121">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="4b873-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b873-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4b873-122">Parent elements</span></span>  
  
|<span data-ttu-id="4b873-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b873-123">Element</span></span>|<span data-ttu-id="4b873-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="4b873-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b873-125">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="4b873-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="4b873-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="4b873-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b873-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4b873-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="4b873-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="4b873-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4b873-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="4b873-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
