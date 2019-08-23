---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 628dbf801cae5f61dc7d518c27df3380dd2d3d23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945946"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="58ed9-101">\<Канцелрекуестедкуериес ></span><span class="sxs-lookup"><span data-stu-id="58ed9-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="58ed9-102">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="58ed9-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="58ed9-103">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="58ed9-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="58ed9-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="58ed9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="58ed9-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="58ed9-105">\<system.serviceModel></span></span>  
<span data-ttu-id="58ed9-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="58ed9-106">\<tracking></span></span>  
<span data-ttu-id="58ed9-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="58ed9-107">\<trackingProfile></span></span>  
<span data-ttu-id="58ed9-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="58ed9-108">\<workflow></span></span>  
<span data-ttu-id="58ed9-109">\<Канцелрекуестедкуериес ></span><span class="sxs-lookup"><span data-stu-id="58ed9-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58ed9-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58ed9-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58ed9-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="58ed9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="58ed9-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="58ed9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58ed9-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="58ed9-113">Attributes</span></span>  
 <span data-ttu-id="58ed9-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="58ed9-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="58ed9-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="58ed9-115">Child Elements</span></span>  
  
|<span data-ttu-id="58ed9-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="58ed9-116">Element</span></span>|<span data-ttu-id="58ed9-117">Описание</span><span class="sxs-lookup"><span data-stu-id="58ed9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58ed9-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="58ed9-118">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="58ed9-119">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="58ed9-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58ed9-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="58ed9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="58ed9-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="58ed9-121">Element</span></span>|<span data-ttu-id="58ed9-122">Описание</span><span class="sxs-lookup"><span data-stu-id="58ed9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58ed9-123">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="58ed9-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="58ed9-124">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="58ed9-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58ed9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="58ed9-125">See also</span></span>

- [<span data-ttu-id="58ed9-126">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="58ed9-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="58ed9-127">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="58ed9-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
