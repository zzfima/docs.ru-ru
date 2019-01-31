---
title: <cancelRequestedQueries> для WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: a9364fc53c7eb62a240206f6c81bd434b25c3f40
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289475"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="7d024-102">\<cancelRequestedQueries > из WCF</span><span class="sxs-lookup"><span data-stu-id="7d024-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="7d024-103">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="7d024-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7d024-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="7d024-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="7d024-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7d024-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="7d024-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7d024-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7d024-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="7d024-107">\<tracking></span></span>  
<span data-ttu-id="7d024-108">\<профили > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="7d024-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="7d024-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="7d024-109">\<workflow></span></span>  
<span data-ttu-id="7d024-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="7d024-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d024-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d024-111">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d024-112">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="7d024-112">Attributes and elements</span></span>  

<span data-ttu-id="7d024-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7d024-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d024-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7d024-114">Attributes</span></span>

<span data-ttu-id="7d024-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d024-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="7d024-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7d024-116">Child elements</span></span>
  
|<span data-ttu-id="7d024-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="7d024-117">Element</span></span>|<span data-ttu-id="7d024-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="7d024-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d024-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="7d024-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="7d024-120">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="7d024-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d024-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7d024-121">Parent elements</span></span>  
  
|<span data-ttu-id="7d024-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="7d024-122">Element</span></span>|<span data-ttu-id="7d024-123">Описание</span><span class="sxs-lookup"><span data-stu-id="7d024-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d024-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="7d024-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="7d024-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="7d024-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d024-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7d024-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="7d024-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7d024-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7d024-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="7d024-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
