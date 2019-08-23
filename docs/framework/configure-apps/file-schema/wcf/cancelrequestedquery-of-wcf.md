---
title: <cancelRequestedQuery>WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 7952520edbf799e5fab6864e50962c6ec2860928
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919651"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="9e1d8-102">\<Канцелрекуестедкуери > WCF</span><span class="sxs-lookup"><span data-stu-id="9e1d8-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="9e1d8-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="9e1d8-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9e1d8-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="9e1d8-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="9e1d8-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9e1d8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="9e1d8-106">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="9e1d8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9e1d8-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="9e1d8-107">\<tracking></span></span>  
<span data-ttu-id="9e1d8-108">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="9e1d8-108">\<profiles></span></span>  
<span data-ttu-id="9e1d8-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9e1d8-109">\<trackingProfile></span></span>  
<span data-ttu-id="9e1d8-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9e1d8-110">\<workflow></span></span>  
<span data-ttu-id="9e1d8-111">\<Канцелрекуестедкуериес ></span><span class="sxs-lookup"><span data-stu-id="9e1d8-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="9e1d8-112">\<Канцелрекуестедкуери ></span><span class="sxs-lookup"><span data-stu-id="9e1d8-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e1d8-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e1d8-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e1d8-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="9e1d8-114">Attributes and elements</span></span>

<span data-ttu-id="9e1d8-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9e1d8-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e1d8-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9e1d8-116">Attributes</span></span>  
  
|<span data-ttu-id="9e1d8-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9e1d8-117">Attribute</span></span>|<span data-ttu-id="9e1d8-118">Описание</span><span class="sxs-lookup"><span data-stu-id="9e1d8-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="9e1d8-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="9e1d8-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="9e1d8-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="9e1d8-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e1d8-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9e1d8-121">Child elements</span></span>

<span data-ttu-id="9e1d8-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="9e1d8-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="9e1d8-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9e1d8-123">Parent elements</span></span>
  
|<span data-ttu-id="9e1d8-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="9e1d8-124">Element</span></span>|<span data-ttu-id="9e1d8-125">Описание</span><span class="sxs-lookup"><span data-stu-id="9e1d8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e1d8-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="9e1d8-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="9e1d8-127">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="9e1d8-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e1d8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9e1d8-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9e1d8-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9e1d8-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9e1d8-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="9e1d8-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
