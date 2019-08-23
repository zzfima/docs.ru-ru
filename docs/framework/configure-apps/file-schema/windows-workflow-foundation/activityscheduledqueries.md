---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 89de9ef10449fbae78a8c5b558101a2cf6477b07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945526"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="d5c41-101">\<Активитисчедуледкуериес ></span><span class="sxs-lookup"><span data-stu-id="d5c41-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="d5c41-102">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="d5c41-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d5c41-103">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="d5c41-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="d5c41-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="d5c41-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d5c41-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="d5c41-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d5c41-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="d5c41-106">\<tracking></span></span>  
<span data-ttu-id="d5c41-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d5c41-107">\<trackingProfile></span></span>  
<span data-ttu-id="d5c41-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d5c41-108">\<workflow></span></span>  
<span data-ttu-id="d5c41-109">\<Активитисчедуледкуериес ></span><span class="sxs-lookup"><span data-stu-id="d5c41-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5c41-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5c41-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5c41-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5c41-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d5c41-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5c41-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5c41-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5c41-113">Attributes</span></span>  
 <span data-ttu-id="d5c41-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="d5c41-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d5c41-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5c41-115">Child Elements</span></span>  
  
|<span data-ttu-id="d5c41-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5c41-116">Element</span></span>|<span data-ttu-id="d5c41-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d5c41-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5c41-118">\<Активитисчедуледкуери ></span><span class="sxs-lookup"><span data-stu-id="d5c41-118">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="d5c41-119">Запрос, который используется для отслеживания действия, запланированного к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="d5c41-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5c41-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5c41-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d5c41-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5c41-121">Element</span></span>|<span data-ttu-id="d5c41-122">Описание</span><span class="sxs-lookup"><span data-stu-id="d5c41-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5c41-123">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d5c41-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="d5c41-124">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="d5c41-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5c41-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d5c41-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d5c41-126">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d5c41-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d5c41-127">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="d5c41-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
