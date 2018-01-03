---
title: '&lt;cancelRequestedQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c9ad0f766256d6507775c2cca1b9d54b474abc7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="a219e-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="a219e-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="a219e-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="a219e-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a219e-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="a219e-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="a219e-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a219e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a219e-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a219e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a219e-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="a219e-107">\<tracking></span></span>  
<span data-ttu-id="a219e-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a219e-108">\<trackingProfile></span></span>  
<span data-ttu-id="a219e-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="a219e-109">\<workflow></span></span>  
<span data-ttu-id="a219e-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="a219e-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="a219e-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="a219e-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a219e-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a219e-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a219e-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a219e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a219e-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a219e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a219e-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a219e-115">Attributes</span></span>  
  
|<span data-ttu-id="a219e-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a219e-116">Attribute</span></span>|<span data-ttu-id="a219e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a219e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a219e-118">activityName</span><span class="sxs-lookup"><span data-stu-id="a219e-118">activityName</span></span>|<span data-ttu-id="a219e-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="a219e-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="a219e-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="a219e-120">childActivityName</span></span>|<span data-ttu-id="a219e-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="a219e-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a219e-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a219e-122">Child Elements</span></span>  
 <span data-ttu-id="a219e-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a219e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a219e-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a219e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a219e-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="a219e-125">Element</span></span>|<span data-ttu-id="a219e-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="a219e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a219e-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="a219e-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="a219e-128">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="a219e-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a219e-129">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="a219e-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a219e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a219e-130">See Also</span></span>  
 <span data-ttu-id="a219e-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a219e-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="a219e-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a219e-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="a219e-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a219e-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a219e-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a219e-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
