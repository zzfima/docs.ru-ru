---
title: '&lt;faultPropagationQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: df7119363e94a070bb898c984c12cf82755c3407
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087704"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="46a2e-102">&lt;faultPropagationQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="46a2e-102">&lt;faultPropagationQuery&gt; of WCF</span></span>
<span data-ttu-id="46a2e-103">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="46a2e-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="46a2e-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="46a2e-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="46a2e-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="46a2e-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="46a2e-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="46a2e-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="46a2e-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="46a2e-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="46a2e-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="46a2e-108">\<system.serviceModel></span></span>  
<span data-ttu-id="46a2e-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="46a2e-109">\<tracking></span></span>  
<span data-ttu-id="46a2e-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="46a2e-110">\<trackingProfile></span></span>  
<span data-ttu-id="46a2e-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="46a2e-111">\<workflow></span></span>  
<span data-ttu-id="46a2e-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="46a2e-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="46a2e-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="46a2e-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a2e-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46a2e-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String"/>
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46a2e-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46a2e-115">Attributes and Elements</span></span>  
 <span data-ttu-id="46a2e-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="46a2e-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46a2e-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46a2e-117">Attributes</span></span>  
  
|<span data-ttu-id="46a2e-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="46a2e-118">Attribute</span></span>|<span data-ttu-id="46a2e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="46a2e-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46a2e-120">activityName</span><span class="sxs-lookup"><span data-stu-id="46a2e-120">activityName</span></span>|<span data-ttu-id="46a2e-121">Строка, указывающая имя действия обработчика ошибок, которое распространяет ошибку.</span><span class="sxs-lookup"><span data-stu-id="46a2e-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="46a2e-122">Значение по умолчанию - «\*», которое указывает на то, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="46a2e-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="46a2e-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="46a2e-123">faultHandlerActivityName</span></span>|<span data-ttu-id="46a2e-124">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="46a2e-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46a2e-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46a2e-125">Child Elements</span></span>  
 <span data-ttu-id="46a2e-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="46a2e-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46a2e-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46a2e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="46a2e-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="46a2e-128">Element</span></span>|<span data-ttu-id="46a2e-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="46a2e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46a2e-130">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="46a2e-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="46a2e-131">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="46a2e-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="46a2e-132">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="46a2e-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46a2e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="46a2e-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="46a2e-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="46a2e-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="46a2e-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="46a2e-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
