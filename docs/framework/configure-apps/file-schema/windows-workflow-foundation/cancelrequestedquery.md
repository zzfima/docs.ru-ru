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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e1697b245f9ab61cab3e4b26b1756259f0eba9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="5e4a8-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="5e4a8-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="5e4a8-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="5e4a8-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="5e4a8-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="5e4a8-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="5e4a8-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5e4a8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="5e4a8-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="5e4a8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="5e4a8-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="5e4a8-107">\<tracking></span></span>  
<span data-ttu-id="5e4a8-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="5e4a8-108">\<trackingProfile></span></span>  
<span data-ttu-id="5e4a8-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="5e4a8-109">\<workflow></span></span>  
<span data-ttu-id="5e4a8-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="5e4a8-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="5e4a8-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="5e4a8-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e4a8-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e4a8-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e4a8-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5e4a8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5e4a8-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5e4a8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e4a8-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5e4a8-115">Attributes</span></span>  
  
|<span data-ttu-id="5e4a8-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5e4a8-116">Attribute</span></span>|<span data-ttu-id="5e4a8-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5e4a8-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e4a8-118">activityName</span><span class="sxs-lookup"><span data-stu-id="5e4a8-118">activityName</span></span>|<span data-ttu-id="5e4a8-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="5e4a8-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="5e4a8-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="5e4a8-120">childActivityName</span></span>|<span data-ttu-id="5e4a8-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="5e4a8-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e4a8-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5e4a8-122">Child Elements</span></span>  
 <span data-ttu-id="5e4a8-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5e4a8-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e4a8-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5e4a8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5e4a8-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="5e4a8-125">Element</span></span>|<span data-ttu-id="5e4a8-126">Описание</span><span class="sxs-lookup"><span data-stu-id="5e4a8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e4a8-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="5e4a8-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="5e4a8-128">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="5e4a8-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="5e4a8-129">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="5e4a8-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e4a8-130">См. также</span><span class="sxs-lookup"><span data-stu-id="5e4a8-130">See Also</span></span>  
 <span data-ttu-id="5e4a8-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e4a8-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="5e4a8-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e4a8-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="5e4a8-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="5e4a8-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="5e4a8-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="5e4a8-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
