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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab16fe138701d180f528b5ec07e106acd53023b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="dbc32-102">&lt;cancelRequestedQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="dbc32-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="dbc32-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="dbc32-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="dbc32-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="dbc32-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="dbc32-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dbc32-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="dbc32-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="dbc32-106">\<system.serviceModel></span></span>  
<span data-ttu-id="dbc32-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="dbc32-107">\<tracking></span></span>  
<span data-ttu-id="dbc32-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dbc32-108">\<trackingProfile></span></span>  
<span data-ttu-id="dbc32-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="dbc32-109">\<workflow></span></span>  
<span data-ttu-id="dbc32-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="dbc32-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="dbc32-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="dbc32-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc32-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbc32-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dbc32-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dbc32-113">Attributes and Elements</span></span>  
 <span data-ttu-id="dbc32-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dbc32-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbc32-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dbc32-115">Attributes</span></span>  
  
|<span data-ttu-id="dbc32-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dbc32-116">Attribute</span></span>|<span data-ttu-id="dbc32-117">Описание</span><span class="sxs-lookup"><span data-stu-id="dbc32-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbc32-118">activityName</span><span class="sxs-lookup"><span data-stu-id="dbc32-118">activityName</span></span>|<span data-ttu-id="dbc32-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="dbc32-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="dbc32-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="dbc32-120">childActivityName</span></span>|<span data-ttu-id="dbc32-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="dbc32-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbc32-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dbc32-122">Child Elements</span></span>  
 <span data-ttu-id="dbc32-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dbc32-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbc32-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dbc32-124">Parent Elements</span></span>  
  
|<span data-ttu-id="dbc32-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="dbc32-125">Element</span></span>|<span data-ttu-id="dbc32-126">Описание</span><span class="sxs-lookup"><span data-stu-id="dbc32-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbc32-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="dbc32-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="dbc32-128">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="dbc32-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="dbc32-129">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="dbc32-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbc32-130">См. также</span><span class="sxs-lookup"><span data-stu-id="dbc32-130">See Also</span></span>  
 <span data-ttu-id="dbc32-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dbc32-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="dbc32-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dbc32-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>     
 [<span data-ttu-id="dbc32-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="dbc32-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dbc32-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="dbc32-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
