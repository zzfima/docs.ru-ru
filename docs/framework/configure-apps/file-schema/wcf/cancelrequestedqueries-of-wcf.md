---
title: '&lt;cancelRequestedQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 4d746290f01e702979d1dd0165ad3fc5299e1b75
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087756"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="0799e-102">&lt;cancelRequestedQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="0799e-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="0799e-103">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="0799e-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0799e-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="0799e-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="0799e-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0799e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="0799e-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0799e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0799e-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="0799e-107">\<tracking></span></span>  
<span data-ttu-id="0799e-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0799e-108">\<trackingProfile></span></span>  
<span data-ttu-id="0799e-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="0799e-109">\<workflow></span></span>  
<span data-ttu-id="0799e-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="0799e-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0799e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0799e-111">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="0799e-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0799e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0799e-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0799e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0799e-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0799e-114">Attributes</span></span>  
 <span data-ttu-id="0799e-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0799e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0799e-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0799e-116">Child Elements</span></span>  
  
|<span data-ttu-id="0799e-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="0799e-117">Element</span></span>|<span data-ttu-id="0799e-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="0799e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0799e-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="0799e-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="0799e-120">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="0799e-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0799e-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0799e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0799e-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="0799e-122">Element</span></span>|<span data-ttu-id="0799e-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="0799e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0799e-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="0799e-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="0799e-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="0799e-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0799e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0799e-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="0799e-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0799e-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0799e-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="0799e-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
