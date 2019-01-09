---
title: '&lt;cancelRequestedQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 6b41721dcc0c489377c59bfccdd0b1a617f551b0
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149076"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="54d0a-102">&lt;cancelRequestedQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="54d0a-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>

<span data-ttu-id="54d0a-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="54d0a-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="54d0a-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="54d0a-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="54d0a-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="54d0a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="54d0a-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="54d0a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="54d0a-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="54d0a-107">\<tracking></span></span>  
<span data-ttu-id="54d0a-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="54d0a-108">\<profiles></span></span>  
<span data-ttu-id="54d0a-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="54d0a-109">\<trackingProfile></span></span>  
<span data-ttu-id="54d0a-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="54d0a-110">\<workflow></span></span>  
<span data-ttu-id="54d0a-111">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="54d0a-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="54d0a-112">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="54d0a-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d0a-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54d0a-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54d0a-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="54d0a-114">Attributes and elements</span></span>

<span data-ttu-id="54d0a-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="54d0a-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="54d0a-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="54d0a-116">Attributes</span></span>  
  
|<span data-ttu-id="54d0a-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="54d0a-117">Attribute</span></span>|<span data-ttu-id="54d0a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="54d0a-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="54d0a-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="54d0a-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="54d0a-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="54d0a-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54d0a-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="54d0a-121">Child elements</span></span>

<span data-ttu-id="54d0a-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="54d0a-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="54d0a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="54d0a-123">Parent elements</span></span>
  
|<span data-ttu-id="54d0a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="54d0a-124">Element</span></span>|<span data-ttu-id="54d0a-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="54d0a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54d0a-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="54d0a-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="54d0a-127">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="54d0a-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54d0a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="54d0a-128">See also</span></span>  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="54d0a-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="54d0a-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="54d0a-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="54d0a-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
