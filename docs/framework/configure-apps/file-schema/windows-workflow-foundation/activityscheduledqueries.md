---
title: '&lt;activityScheduledQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 6192fea9a520a3f453593e5efac964a5d32a492f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756297"
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="8fae5-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="8fae5-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="8fae5-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="8fae5-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="8fae5-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="8fae5-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="8fae5-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8fae5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8fae5-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8fae5-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8fae5-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="8fae5-107">\<tracking></span></span>  
<span data-ttu-id="8fae5-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8fae5-108">\<trackingProfile></span></span>  
<span data-ttu-id="8fae5-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8fae5-109">\<workflow></span></span>  
<span data-ttu-id="8fae5-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="8fae5-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fae5-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fae5-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fae5-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8fae5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8fae5-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8fae5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fae5-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8fae5-114">Attributes</span></span>  
 <span data-ttu-id="8fae5-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8fae5-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8fae5-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8fae5-116">Child Elements</span></span>  
  
|<span data-ttu-id="8fae5-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="8fae5-117">Element</span></span>|<span data-ttu-id="8fae5-118">Описание</span><span class="sxs-lookup"><span data-stu-id="8fae5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fae5-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="8fae5-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="8fae5-120">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="8fae5-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8fae5-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8fae5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8fae5-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="8fae5-122">Element</span></span>|<span data-ttu-id="8fae5-123">Описание</span><span class="sxs-lookup"><span data-stu-id="8fae5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fae5-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8fae5-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8fae5-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="8fae5-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8fae5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8fae5-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="8fae5-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8fae5-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8fae5-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="8fae5-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
