---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: d9c3f91edb41bd034bcd978b075d62f74b6e308d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945887"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="f3906-101">\<Канцелрекуестедкуери ></span><span class="sxs-lookup"><span data-stu-id="f3906-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="f3906-102">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="f3906-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f3906-103">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="f3906-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="f3906-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f3906-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f3906-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="f3906-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f3906-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f3906-106">\<tracking></span></span>  
<span data-ttu-id="f3906-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f3906-107">\<trackingProfile></span></span>  
<span data-ttu-id="f3906-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="f3906-108">\<workflow></span></span>  
<span data-ttu-id="f3906-109">\<Канцелрекуестедкуериес ></span><span class="sxs-lookup"><span data-stu-id="f3906-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="f3906-110">\<Канцелрекуестедкуери ></span><span class="sxs-lookup"><span data-stu-id="f3906-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3906-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3906-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3906-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3906-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f3906-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3906-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3906-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3906-114">Attributes</span></span>  
  
|<span data-ttu-id="f3906-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3906-115">Attribute</span></span>|<span data-ttu-id="f3906-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f3906-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3906-117">activityName</span><span class="sxs-lookup"><span data-stu-id="f3906-117">activityName</span></span>|<span data-ttu-id="f3906-118">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="f3906-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="f3906-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="f3906-119">childActivityName</span></span>|<span data-ttu-id="f3906-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="f3906-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3906-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3906-121">Child Elements</span></span>  
 <span data-ttu-id="f3906-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="f3906-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3906-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3906-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f3906-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3906-124">Element</span></span>|<span data-ttu-id="f3906-125">Описание</span><span class="sxs-lookup"><span data-stu-id="f3906-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3906-126">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="f3906-126">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="f3906-127">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="f3906-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f3906-128">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="f3906-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3906-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f3906-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f3906-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f3906-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f3906-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f3906-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
