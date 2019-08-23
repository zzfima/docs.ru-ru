---
title: <activityScheduledQueries>WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 83e71e2038377ae4c1c3b17334eece3f30c919f6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920318"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="417d9-102">\<Активитисчедуледкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="417d9-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="417d9-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="417d9-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="417d9-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="417d9-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="417d9-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="417d9-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="417d9-106">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="417d9-106">\<system.serviceModel></span></span>  
<span data-ttu-id="417d9-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="417d9-107">\<tracking></span></span>  
<span data-ttu-id="417d9-108">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="417d9-108">\<profiles></span></span>  
<span data-ttu-id="417d9-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="417d9-109">\<trackingProfile></span></span>  
<span data-ttu-id="417d9-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="417d9-110">\<workflow></span></span>  
<span data-ttu-id="417d9-111">\<Активитисчедуледкуериес ></span><span class="sxs-lookup"><span data-stu-id="417d9-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="417d9-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="417d9-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="417d9-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="417d9-113">Attributes and elements</span></span>  

<span data-ttu-id="417d9-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="417d9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="417d9-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="417d9-115">Attributes</span></span>  

<span data-ttu-id="417d9-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="417d9-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="417d9-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="417d9-117">Child elements</span></span>  
  
|<span data-ttu-id="417d9-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="417d9-118">Element</span></span>|<span data-ttu-id="417d9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="417d9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="417d9-120">\<Активитисчедуледкуери ></span><span class="sxs-lookup"><span data-stu-id="417d9-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="417d9-121">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="417d9-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="417d9-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="417d9-122">Parent elements</span></span>  
  
|<span data-ttu-id="417d9-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="417d9-123">Element</span></span>|<span data-ttu-id="417d9-124">Описание</span><span class="sxs-lookup"><span data-stu-id="417d9-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="417d9-125">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="417d9-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="417d9-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="417d9-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="417d9-127">См. также</span><span class="sxs-lookup"><span data-stu-id="417d9-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="417d9-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="417d9-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="417d9-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="417d9-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
