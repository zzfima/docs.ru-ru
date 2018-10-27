---
title: '&lt;activityScheduledQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 35bcb0dc0c33d30eee566869579edb32f131f495
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452700"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="376a5-102">&lt;activityScheduledQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="376a5-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="376a5-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="376a5-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="376a5-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="376a5-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="376a5-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="376a5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="376a5-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="376a5-106">\<system.serviceModel></span></span>  
<span data-ttu-id="376a5-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="376a5-107">\<tracking></span></span>  
<span data-ttu-id="376a5-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="376a5-108">\<profiles></span></span>  
<span data-ttu-id="376a5-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="376a5-109">\<trackingProfile></span></span>  
<span data-ttu-id="376a5-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="376a5-110">\<workflow></span></span>  
<span data-ttu-id="376a5-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="376a5-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="376a5-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="376a5-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="376a5-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="376a5-113">Attributes and elements</span></span>  

<span data-ttu-id="376a5-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="376a5-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="376a5-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="376a5-115">Attributes</span></span>  

<span data-ttu-id="376a5-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="376a5-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="376a5-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="376a5-117">Child elements</span></span>  
  
|<span data-ttu-id="376a5-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="376a5-118">Element</span></span>|<span data-ttu-id="376a5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="376a5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="376a5-120">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="376a5-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="376a5-121">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="376a5-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="376a5-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="376a5-122">Parent elements</span></span>  
  
|<span data-ttu-id="376a5-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="376a5-123">Element</span></span>|<span data-ttu-id="376a5-124">Описание</span><span class="sxs-lookup"><span data-stu-id="376a5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="376a5-125">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="376a5-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="376a5-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="376a5-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="376a5-127">См. также</span><span class="sxs-lookup"><span data-stu-id="376a5-127">See also</span></span>  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="376a5-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="376a5-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="376a5-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="376a5-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
