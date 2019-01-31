---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 989d6e99457108336c38fb1eece4c9ac2444c974
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271503"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="94713-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="94713-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="94713-102">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="94713-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="94713-103">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="94713-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="94713-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="94713-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="94713-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="94713-105">\<system.serviceModel></span></span>  
<span data-ttu-id="94713-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="94713-106">\<tracking></span></span>  
<span data-ttu-id="94713-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="94713-107">\<trackingProfile></span></span>  
<span data-ttu-id="94713-108">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="94713-108">\<workflow></span></span>  
<span data-ttu-id="94713-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="94713-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94713-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94713-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94713-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="94713-111">Attributes and Elements</span></span>  
 <span data-ttu-id="94713-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="94713-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94713-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="94713-113">Attributes</span></span>  
 <span data-ttu-id="94713-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="94713-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="94713-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="94713-115">Child Elements</span></span>  
  
|<span data-ttu-id="94713-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="94713-116">Element</span></span>|<span data-ttu-id="94713-117">Описание</span><span class="sxs-lookup"><span data-stu-id="94713-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94713-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="94713-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="94713-119">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="94713-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94713-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="94713-120">Parent Elements</span></span>  
  
|<span data-ttu-id="94713-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="94713-121">Element</span></span>|<span data-ttu-id="94713-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="94713-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94713-123">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="94713-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="94713-124">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="94713-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94713-125">См. также</span><span class="sxs-lookup"><span data-stu-id="94713-125">See also</span></span>
- [<span data-ttu-id="94713-126">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="94713-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="94713-127">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="94713-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
