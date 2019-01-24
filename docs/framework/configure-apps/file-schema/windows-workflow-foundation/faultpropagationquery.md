---
title: '&lt;faultPropagationQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: a91a6f61b39a780ed48ad8d5f5e0dfb9ef60da39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538340"
---
# <a name="ltfaultpropagationquerygt"></a><span data-ttu-id="4e3e6-102">&lt;faultPropagationQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="4e3e6-102">&lt;faultPropagationQuery&gt;</span></span>
<span data-ttu-id="4e3e6-103">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4e3e6-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="4e3e6-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="4e3e6-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="4e3e6-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4e3e6-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="4e3e6-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4e3e6-108">\<system.serviceModel></span></span>  
<span data-ttu-id="4e3e6-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="4e3e6-109">\<tracking></span></span>  
<span data-ttu-id="4e3e6-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="4e3e6-110">\<trackingProfile></span></span>  
<span data-ttu-id="4e3e6-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="4e3e6-111">\<workflow></span></span>  
<span data-ttu-id="4e3e6-112">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="4e3e6-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="4e3e6-113">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="4e3e6-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3e6-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e3e6-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e3e6-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4e3e6-115">Attributes and Elements</span></span>  
 <span data-ttu-id="4e3e6-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e3e6-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4e3e6-117">Attributes</span></span>  
  
|<span data-ttu-id="4e3e6-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4e3e6-118">Attribute</span></span>|<span data-ttu-id="4e3e6-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4e3e6-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e3e6-120">activityName</span><span class="sxs-lookup"><span data-stu-id="4e3e6-120">activityName</span></span>|<span data-ttu-id="4e3e6-121">Строка, указывающая имя действия обработчика ошибок, которое распространяет ошибку.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="4e3e6-122">Значение по умолчанию - «\*», которое указывает на то, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="4e3e6-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="4e3e6-123">faultHandlerActivityName</span></span>|<span data-ttu-id="4e3e6-124">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e3e6-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4e3e6-125">Child Elements</span></span>  
 <span data-ttu-id="4e3e6-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e3e6-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4e3e6-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4e3e6-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e3e6-128">Element</span></span>|<span data-ttu-id="4e3e6-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="4e3e6-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e3e6-130">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="4e3e6-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="4e3e6-131">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4e3e6-132">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="4e3e6-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e3e6-133">См. также</span><span class="sxs-lookup"><span data-stu-id="4e3e6-133">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4e3e6-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="4e3e6-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4e3e6-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="4e3e6-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
