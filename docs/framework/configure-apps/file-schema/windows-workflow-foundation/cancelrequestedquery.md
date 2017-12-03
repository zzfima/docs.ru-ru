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
ms.openlocfilehash: c6b1137e89799af34d0808d83e56c7c333a49635
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="51a9c-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="51a9c-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="51a9c-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="51a9c-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="51a9c-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="51a9c-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="51a9c-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="51a9c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="51a9c-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="51a9c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="51a9c-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="51a9c-107">\<tracking></span></span>  
<span data-ttu-id="51a9c-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="51a9c-108">\<trackingProfile></span></span>  
<span data-ttu-id="51a9c-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="51a9c-109">\<workflow></span></span>  
<span data-ttu-id="51a9c-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="51a9c-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="51a9c-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="51a9c-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51a9c-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51a9c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51a9c-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="51a9c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="51a9c-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="51a9c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51a9c-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="51a9c-115">Attributes</span></span>  
  
|<span data-ttu-id="51a9c-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="51a9c-116">Attribute</span></span>|<span data-ttu-id="51a9c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="51a9c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51a9c-118">activityName</span><span class="sxs-lookup"><span data-stu-id="51a9c-118">activityName</span></span>|<span data-ttu-id="51a9c-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="51a9c-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="51a9c-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="51a9c-120">childActivityName</span></span>|<span data-ttu-id="51a9c-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="51a9c-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51a9c-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="51a9c-122">Child Elements</span></span>  
 <span data-ttu-id="51a9c-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="51a9c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51a9c-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="51a9c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="51a9c-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="51a9c-125">Element</span></span>|<span data-ttu-id="51a9c-126">Описание</span><span class="sxs-lookup"><span data-stu-id="51a9c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51a9c-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="51a9c-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="51a9c-128">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="51a9c-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="51a9c-129">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="51a9c-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51a9c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="51a9c-130">See Also</span></span>  
 <span data-ttu-id="51a9c-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="51a9c-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="51a9c-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="51a9c-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="51a9c-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="51a9c-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="51a9c-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="51a9c-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
