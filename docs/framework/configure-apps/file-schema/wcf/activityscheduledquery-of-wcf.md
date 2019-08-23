---
title: <activityScheduledQuery>WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 7787ada68210ff832ff3fd1ec93c9d346e4d2eaa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926927"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="11a16-102">\<Активитисчедуледкуери > WCF</span><span class="sxs-lookup"><span data-stu-id="11a16-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="11a16-103">Представляет коллекцию запросов, которые используются для отслеживания действия, выполнение которого запланировано родительским действием.</span><span class="sxs-lookup"><span data-stu-id="11a16-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="11a16-104">Этот запрос необходим, чтобы участник отслеживания подписался на записи запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="11a16-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="11a16-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="11a16-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="11a16-106">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="11a16-106">\<system.serviceModel></span></span>  
<span data-ttu-id="11a16-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="11a16-107">\<tracking></span></span>  
<span data-ttu-id="11a16-108">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="11a16-108">\<profiles></span></span>  
<span data-ttu-id="11a16-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="11a16-109">\<trackingProfile></span></span>  
<span data-ttu-id="11a16-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="11a16-110">\<workflow></span></span>  
<span data-ttu-id="11a16-111">\<Активитисчедуледкуериес ></span><span class="sxs-lookup"><span data-stu-id="11a16-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="11a16-112">\<Активитисчедуледкуери ></span><span class="sxs-lookup"><span data-stu-id="11a16-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a16-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11a16-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11a16-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="11a16-114">Attributes and elements</span></span>  

<span data-ttu-id="11a16-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="11a16-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11a16-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="11a16-116">Attributes</span></span>  
  
|<span data-ttu-id="11a16-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="11a16-117">Attribute</span></span>|<span data-ttu-id="11a16-118">Описание</span><span class="sxs-lookup"><span data-stu-id="11a16-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="11a16-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="11a16-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="11a16-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="11a16-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11a16-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="11a16-121">Child elements</span></span>

<span data-ttu-id="11a16-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="11a16-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="11a16-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="11a16-123">Parent elements</span></span>  
  
|<span data-ttu-id="11a16-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="11a16-124">Element</span></span>|<span data-ttu-id="11a16-125">Описание</span><span class="sxs-lookup"><span data-stu-id="11a16-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11a16-126">\<Активитисчедуледкуериес ></span><span class="sxs-lookup"><span data-stu-id="11a16-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="11a16-127">Коллекция запросов, которая используется для трассировки действия, запланированного на выполнение родительским действием.</span><span class="sxs-lookup"><span data-stu-id="11a16-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11a16-128">См. также</span><span class="sxs-lookup"><span data-stu-id="11a16-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="11a16-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="11a16-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="11a16-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="11a16-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
