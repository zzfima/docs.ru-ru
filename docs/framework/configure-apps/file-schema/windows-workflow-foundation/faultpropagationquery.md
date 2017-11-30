---
title: '&lt;faultPropagationQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3c9dc0e0580c884377e790fa8c1e9a23de9ecd1c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltfaultpropagationquerygt"></a><span data-ttu-id="32311-102">&lt;faultPropagationQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="32311-102">&lt;faultPropagationQuery&gt;</span></span>
<span data-ttu-id="32311-103">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="32311-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="32311-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="32311-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="32311-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="32311-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="32311-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="32311-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="32311-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="32311-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="32311-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="32311-108">\<system.serviceModel></span></span>  
<span data-ttu-id="32311-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="32311-109">\<tracking></span></span>  
<span data-ttu-id="32311-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="32311-110">\<trackingProfile></span></span>  
<span data-ttu-id="32311-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="32311-111">\<workflow></span></span>  
<span data-ttu-id="32311-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="32311-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="32311-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="32311-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32311-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32311-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32311-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="32311-115">Attributes and Elements</span></span>  
 <span data-ttu-id="32311-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="32311-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32311-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="32311-117">Attributes</span></span>  
  
|<span data-ttu-id="32311-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="32311-118">Attribute</span></span>|<span data-ttu-id="32311-119">Описание</span><span class="sxs-lookup"><span data-stu-id="32311-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32311-120">activityName</span><span class="sxs-lookup"><span data-stu-id="32311-120">activityName</span></span>|<span data-ttu-id="32311-121">Строка, указывающая имя действия обработчика ошибок, которое распространяет ошибку.</span><span class="sxs-lookup"><span data-stu-id="32311-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="32311-122">Значение по умолчанию - «*», которое указывает на то, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="32311-122">The default is *, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="32311-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="32311-123">faultHandlerActivityName</span></span>|<span data-ttu-id="32311-124">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="32311-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32311-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="32311-125">Child Elements</span></span>  
 <span data-ttu-id="32311-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="32311-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32311-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="32311-127">Parent Elements</span></span>  
  
|<span data-ttu-id="32311-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="32311-128">Element</span></span>|<span data-ttu-id="32311-129">Описание</span><span class="sxs-lookup"><span data-stu-id="32311-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32311-130">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="32311-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="32311-131">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="32311-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="32311-132">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="32311-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32311-133">См. также</span><span class="sxs-lookup"><span data-stu-id="32311-133">See Also</span></span>  
 <span data-ttu-id="32311-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="32311-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="32311-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="32311-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="32311-136">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="32311-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="32311-137">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="32311-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
