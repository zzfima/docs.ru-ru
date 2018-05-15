---
title: '&lt;cancelRequestedQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e532ea482108c9a5cabe13a99afddca10f8341d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="ea1fc-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ea1fc-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="ea1fc-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="ea1fc-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ea1fc-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="ea1fc-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="ea1fc-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ea1fc-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ea1fc-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ea1fc-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ea1fc-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="ea1fc-107">\<tracking></span></span>  
<span data-ttu-id="ea1fc-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ea1fc-108">\<trackingProfile></span></span>  
<span data-ttu-id="ea1fc-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ea1fc-109">\<workflow></span></span>  
<span data-ttu-id="ea1fc-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="ea1fc-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="ea1fc-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="ea1fc-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1fc-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea1fc-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea1fc-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea1fc-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ea1fc-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea1fc-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea1fc-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea1fc-115">Attributes</span></span>  
  
|<span data-ttu-id="ea1fc-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea1fc-116">Attribute</span></span>|<span data-ttu-id="ea1fc-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ea1fc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea1fc-118">activityName</span><span class="sxs-lookup"><span data-stu-id="ea1fc-118">activityName</span></span>|<span data-ttu-id="ea1fc-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="ea1fc-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="ea1fc-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="ea1fc-120">childActivityName</span></span>|<span data-ttu-id="ea1fc-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="ea1fc-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea1fc-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea1fc-122">Child Elements</span></span>  
 <span data-ttu-id="ea1fc-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea1fc-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea1fc-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea1fc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ea1fc-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea1fc-125">Element</span></span>|<span data-ttu-id="ea1fc-126">Описание</span><span class="sxs-lookup"><span data-stu-id="ea1fc-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea1fc-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="ea1fc-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="ea1fc-128">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="ea1fc-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ea1fc-129">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="ea1fc-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea1fc-130">См. также</span><span class="sxs-lookup"><span data-stu-id="ea1fc-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="ea1fc-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ea1fc-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ea1fc-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ea1fc-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
