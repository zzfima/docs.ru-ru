---
title: '&lt;cancelRequestedQuery&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2af49aab76e82a97aeee92b4799b91011f70c509
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="3333b-102">&lt;cancelRequestedQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="3333b-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="3333b-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="3333b-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3333b-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="3333b-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="3333b-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3333b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="3333b-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3333b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3333b-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="3333b-107">\<tracking></span></span>  
<span data-ttu-id="3333b-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3333b-108">\<trackingProfile></span></span>  
<span data-ttu-id="3333b-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="3333b-109">\<workflow></span></span>  
<span data-ttu-id="3333b-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="3333b-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="3333b-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="3333b-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3333b-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3333b-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3333b-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3333b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3333b-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3333b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3333b-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3333b-115">Attributes</span></span>  
  
|<span data-ttu-id="3333b-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3333b-116">Attribute</span></span>|<span data-ttu-id="3333b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="3333b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3333b-118">activityName</span><span class="sxs-lookup"><span data-stu-id="3333b-118">activityName</span></span>|<span data-ttu-id="3333b-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="3333b-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="3333b-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="3333b-120">childActivityName</span></span>|<span data-ttu-id="3333b-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="3333b-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3333b-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3333b-122">Child Elements</span></span>  
 <span data-ttu-id="3333b-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3333b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3333b-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3333b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3333b-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="3333b-125">Element</span></span>|<span data-ttu-id="3333b-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="3333b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3333b-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="3333b-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="3333b-128">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="3333b-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3333b-129">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="3333b-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3333b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3333b-130">See Also</span></span>  
 <span data-ttu-id="3333b-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3333b-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3333b-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3333b-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>     
 [<span data-ttu-id="3333b-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="3333b-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3333b-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="3333b-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
