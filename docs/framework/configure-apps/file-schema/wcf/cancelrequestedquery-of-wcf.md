---
title: <cancelRequestedQuery> для WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: bd6157e63761efa954744ab08ea6c66535def514
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673367"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="7836c-102">\<cancelRequestedQuery> of WCF</span><span class="sxs-lookup"><span data-stu-id="7836c-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="7836c-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="7836c-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7836c-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="7836c-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="7836c-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7836c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="7836c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7836c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7836c-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="7836c-107">\<tracking></span></span>  
<span data-ttu-id="7836c-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="7836c-108">\<profiles></span></span>  
<span data-ttu-id="7836c-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="7836c-109">\<trackingProfile></span></span>  
<span data-ttu-id="7836c-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="7836c-110">\<workflow></span></span>  
<span data-ttu-id="7836c-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="7836c-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="7836c-112">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="7836c-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7836c-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7836c-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7836c-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="7836c-114">Attributes and elements</span></span>

<span data-ttu-id="7836c-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7836c-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7836c-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7836c-116">Attributes</span></span>  
  
|<span data-ttu-id="7836c-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7836c-117">Attribute</span></span>|<span data-ttu-id="7836c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7836c-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="7836c-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="7836c-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="7836c-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="7836c-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7836c-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7836c-121">Child elements</span></span>

<span data-ttu-id="7836c-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7836c-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="7836c-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7836c-123">Parent elements</span></span>
  
|<span data-ttu-id="7836c-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="7836c-124">Element</span></span>|<span data-ttu-id="7836c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="7836c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7836c-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="7836c-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="7836c-127">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="7836c-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7836c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7836c-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7836c-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7836c-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7836c-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="7836c-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
