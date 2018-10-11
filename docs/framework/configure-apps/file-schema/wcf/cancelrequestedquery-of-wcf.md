---
title: '&lt;cancelRequestedQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 38d946a213131e8dcb6f4100d0ad67f7c167f342
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086405"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="13c13-102">&lt;cancelRequestedQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="13c13-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="13c13-103">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="13c13-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="13c13-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="13c13-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="13c13-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="13c13-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="13c13-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="13c13-106">\<system.serviceModel></span></span>  
<span data-ttu-id="13c13-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="13c13-107">\<tracking></span></span>  
<span data-ttu-id="13c13-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="13c13-108">\<trackingProfile></span></span>  
<span data-ttu-id="13c13-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="13c13-109">\<workflow></span></span>  
<span data-ttu-id="13c13-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="13c13-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="13c13-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="13c13-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c13-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13c13-112">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="13c13-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="13c13-113">Attributes and Elements</span></span>  
 <span data-ttu-id="13c13-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="13c13-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13c13-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="13c13-115">Attributes</span></span>  
  
|<span data-ttu-id="13c13-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="13c13-116">Attribute</span></span>|<span data-ttu-id="13c13-117">Описание</span><span class="sxs-lookup"><span data-stu-id="13c13-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13c13-118">activityName</span><span class="sxs-lookup"><span data-stu-id="13c13-118">activityName</span></span>|<span data-ttu-id="13c13-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="13c13-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="13c13-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="13c13-120">childActivityName</span></span>|<span data-ttu-id="13c13-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="13c13-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13c13-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="13c13-122">Child Elements</span></span>  
 <span data-ttu-id="13c13-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="13c13-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13c13-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="13c13-124">Parent Elements</span></span>  
  
|<span data-ttu-id="13c13-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="13c13-125">Element</span></span>|<span data-ttu-id="13c13-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="13c13-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13c13-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="13c13-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="13c13-128">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="13c13-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="13c13-129">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="13c13-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13c13-130">См. также</span><span class="sxs-lookup"><span data-stu-id="13c13-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>     
 [<span data-ttu-id="13c13-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="13c13-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="13c13-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="13c13-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
