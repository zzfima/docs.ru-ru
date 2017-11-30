---
title: '&lt;faultPropagationQueries&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e122e8c6194545a02f6db429d550eabed5d49b27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="da849-102">&lt;faultPropagationQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="da849-102">&lt;faultPropagationQueries&gt; of WCF</span></span>
<span data-ttu-id="da849-103">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="da849-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="da849-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="da849-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="da849-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="da849-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="da849-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="da849-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="da849-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="da849-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="da849-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="da849-108">\<system.serviceModel></span></span>  
<span data-ttu-id="da849-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="da849-109">\<tracking></span></span>  
<span data-ttu-id="da849-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="da849-110">\<trackingProfile></span></span>  
<span data-ttu-id="da849-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="da849-111">\<workflow></span></span>  
<span data-ttu-id="da849-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="da849-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da849-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da849-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="da849-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="da849-114">Attributes and Elements</span></span>  
 <span data-ttu-id="da849-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="da849-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da849-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da849-116">Attributes</span></span>  
 <span data-ttu-id="da849-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="da849-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da849-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da849-118">Child Elements</span></span>  
  
|<span data-ttu-id="da849-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="da849-119">Element</span></span>|<span data-ttu-id="da849-120">Описание</span><span class="sxs-lookup"><span data-stu-id="da849-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da849-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="da849-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="da849-122">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="da849-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="da849-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="da849-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da849-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="da849-124">Parent Elements</span></span>  
  
|<span data-ttu-id="da849-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="da849-125">Element</span></span>|<span data-ttu-id="da849-126">Описание</span><span class="sxs-lookup"><span data-stu-id="da849-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da849-127">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="da849-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="da849-128">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="da849-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da849-129">См. также</span><span class="sxs-lookup"><span data-stu-id="da849-129">See Also</span></span>  
 <span data-ttu-id="da849-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="da849-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="da849-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="da849-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="da849-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="da849-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="da849-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="da849-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
