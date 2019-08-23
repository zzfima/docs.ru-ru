---
title: <cancelRequestedQueries>WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 0f04fc928358c96ca3112422f1a6ccd039269e47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926251"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="8c1d7-102">\<Канцелрекуестедкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="8c1d7-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="8c1d7-103">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="8c1d7-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8c1d7-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="8c1d7-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="8c1d7-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="8c1d7-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8c1d7-106">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="8c1d7-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8c1d7-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="8c1d7-107">\<tracking></span></span>  
<span data-ttu-id="8c1d7-108">\<Профили > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8c1d7-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="8c1d7-109">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8c1d7-109">\<workflow></span></span>  
<span data-ttu-id="8c1d7-110">\<Канцелрекуестедкуериес ></span><span class="sxs-lookup"><span data-stu-id="8c1d7-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c1d7-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c1d7-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c1d7-112">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c1d7-112">Attributes and elements</span></span>  

<span data-ttu-id="8c1d7-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8c1d7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c1d7-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c1d7-114">Attributes</span></span>

<span data-ttu-id="8c1d7-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="8c1d7-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="8c1d7-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8c1d7-116">Child elements</span></span>
  
|<span data-ttu-id="8c1d7-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c1d7-117">Element</span></span>|<span data-ttu-id="8c1d7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="8c1d7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c1d7-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="8c1d7-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="8c1d7-120">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="8c1d7-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c1d7-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8c1d7-121">Parent elements</span></span>  
  
|<span data-ttu-id="8c1d7-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c1d7-122">Element</span></span>|<span data-ttu-id="8c1d7-123">Описание</span><span class="sxs-lookup"><span data-stu-id="8c1d7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c1d7-124">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="8c1d7-124">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="8c1d7-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="8c1d7-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c1d7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8c1d7-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="8c1d7-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8c1d7-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8c1d7-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="8c1d7-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
