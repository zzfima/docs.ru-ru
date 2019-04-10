---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5f2e46d5e4cdd64c37219476790b9ff92c606b6b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215317"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="d1572-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="d1572-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="d1572-102">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="d1572-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d1572-103">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="d1572-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="d1572-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d1572-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="d1572-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d1572-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d1572-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="d1572-106">\<tracking></span></span>  
<span data-ttu-id="d1572-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d1572-107">\<trackingProfile></span></span>  
<span data-ttu-id="d1572-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="d1572-108">\<workflow></span></span>  
<span data-ttu-id="d1572-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d1572-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="d1572-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="d1572-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1572-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1572-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1572-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d1572-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d1572-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d1572-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1572-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d1572-114">Attributes</span></span>  
  
|<span data-ttu-id="d1572-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d1572-115">Attribute</span></span>|<span data-ttu-id="d1572-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d1572-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1572-117">activityName</span><span class="sxs-lookup"><span data-stu-id="d1572-117">activityName</span></span>|<span data-ttu-id="d1572-118">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="d1572-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="d1572-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="d1572-119">childActivityName</span></span>|<span data-ttu-id="d1572-120">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="d1572-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1572-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d1572-121">Child Elements</span></span>  
 <span data-ttu-id="d1572-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d1572-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1572-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d1572-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d1572-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1572-124">Element</span></span>|<span data-ttu-id="d1572-125">Описание</span><span class="sxs-lookup"><span data-stu-id="d1572-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1572-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="d1572-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="d1572-127">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="d1572-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d1572-128">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="d1572-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1572-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d1572-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d1572-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d1572-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d1572-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="d1572-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
