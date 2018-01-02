---
title: '&lt;faultPropagationQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da7cf3a439e365c3ee087ffa1739c96041777e98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltfaultpropagationqueriesgt"></a><span data-ttu-id="f9b60-102">&lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="f9b60-102">&lt;faultPropagationQueries&gt;</span></span>
<span data-ttu-id="f9b60-103">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="f9b60-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f9b60-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="f9b60-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f9b60-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="f9b60-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f9b60-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="f9b60-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="f9b60-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f9b60-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f9b60-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f9b60-108">\<system.serviceModel></span></span>  
<span data-ttu-id="f9b60-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f9b60-109">\<tracking></span></span>  
<span data-ttu-id="f9b60-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f9b60-110">\<trackingProfile></span></span>  
<span data-ttu-id="f9b60-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="f9b60-111">\<workflow></span></span>  
<span data-ttu-id="f9b60-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="f9b60-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9b60-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9b60-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9b60-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f9b60-114">Attributes and Elements</span></span>  
 <span data-ttu-id="f9b60-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f9b60-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9b60-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f9b60-116">Attributes</span></span>  
 <span data-ttu-id="f9b60-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f9b60-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9b60-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f9b60-118">Child Elements</span></span>  
  
|<span data-ttu-id="f9b60-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9b60-119">Element</span></span>|<span data-ttu-id="f9b60-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="f9b60-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9b60-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="f9b60-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="f9b60-122">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="f9b60-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f9b60-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="f9b60-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9b60-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f9b60-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f9b60-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9b60-125">Element</span></span>|<span data-ttu-id="f9b60-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="f9b60-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9b60-127">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="f9b60-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f9b60-128">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="f9b60-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9b60-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f9b60-129">See Also</span></span>  
 <span data-ttu-id="f9b60-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f9b60-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f9b60-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f9b60-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="f9b60-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f9b60-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f9b60-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f9b60-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
