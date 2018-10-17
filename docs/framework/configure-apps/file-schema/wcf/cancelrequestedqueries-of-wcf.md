---
title: '&lt;cancelRequestedQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 40fbcafd641e93be6ba21635f4f6e6428be62c12
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373326"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="2b77d-102">&lt;cancelRequestedQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="2b77d-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="2b77d-103">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="2b77d-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="2b77d-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="2b77d-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="2b77d-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2b77d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2b77d-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="2b77d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2b77d-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="2b77d-107">\<tracking></span></span>  
<span data-ttu-id="2b77d-108">\<профили > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2b77d-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="2b77d-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="2b77d-109">\<workflow></span></span>  
<span data-ttu-id="2b77d-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="2b77d-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b77d-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b77d-111">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String"/>
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b77d-112">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="2b77d-112">Attributes and elements</span></span>  

<span data-ttu-id="2b77d-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2b77d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b77d-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2b77d-114">Attributes</span></span>

<span data-ttu-id="2b77d-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2b77d-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="2b77d-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2b77d-116">Child elements</span></span>
  
|<span data-ttu-id="2b77d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b77d-117">Element</span></span>|<span data-ttu-id="2b77d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="2b77d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b77d-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="2b77d-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="2b77d-120">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="2b77d-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b77d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2b77d-121">Parent elements</span></span>  
  
|<span data-ttu-id="2b77d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="2b77d-122">Element</span></span>|<span data-ttu-id="2b77d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="2b77d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b77d-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="2b77d-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="2b77d-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="2b77d-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b77d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2b77d-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="2b77d-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2b77d-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2b77d-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2b77d-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
