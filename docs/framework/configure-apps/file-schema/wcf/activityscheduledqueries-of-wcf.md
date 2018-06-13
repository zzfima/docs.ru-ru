---
title: '&lt;activityScheduledQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 946406e5513a0fee6793071c397f61bf1fe71c65
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744893"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="08604-102">&lt;activityScheduledQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="08604-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="08604-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="08604-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="08604-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="08604-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="08604-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="08604-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="08604-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="08604-106">\<system.serviceModel></span></span>  
<span data-ttu-id="08604-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="08604-107">\<tracking></span></span>  
<span data-ttu-id="08604-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="08604-108">\<trackingProfile></span></span>  
<span data-ttu-id="08604-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="08604-109">\<workflow></span></span>  
<span data-ttu-id="08604-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="08604-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08604-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08604-111">Syntax</span></span>  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08604-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="08604-112">Attributes and Elements</span></span>  
 <span data-ttu-id="08604-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08604-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08604-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08604-114">Attributes</span></span>  
 <span data-ttu-id="08604-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="08604-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="08604-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08604-116">Child Elements</span></span>  
  
|<span data-ttu-id="08604-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="08604-117">Element</span></span>|<span data-ttu-id="08604-118">Описание</span><span class="sxs-lookup"><span data-stu-id="08604-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08604-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="08604-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="08604-120">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="08604-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08604-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08604-121">Parent Elements</span></span>  
  
|<span data-ttu-id="08604-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="08604-122">Element</span></span>|<span data-ttu-id="08604-123">Описание</span><span class="sxs-lookup"><span data-stu-id="08604-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08604-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="08604-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="08604-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="08604-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08604-126">См. также</span><span class="sxs-lookup"><span data-stu-id="08604-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="08604-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="08604-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="08604-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="08604-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
