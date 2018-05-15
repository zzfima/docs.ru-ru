---
title: '&lt;cancelRequestedQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 24970d0fa810db13423fa4c0fc37a4531feeb550
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="8d3f4-102">&lt;cancelRequestedQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="8d3f4-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="8d3f4-103">Представляет коллекцию запросов, используемых для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="8d3f4-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8d3f4-104">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="8d3f4-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="8d3f4-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8d3f4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="8d3f4-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8d3f4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8d3f4-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="8d3f4-107">\<tracking></span></span>  
<span data-ttu-id="8d3f4-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8d3f4-108">\<trackingProfile></span></span>  
<span data-ttu-id="8d3f4-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8d3f4-109">\<workflow></span></span>  
<span data-ttu-id="8d3f4-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="8d3f4-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3f4-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d3f4-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d3f4-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8d3f4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8d3f4-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8d3f4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d3f4-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d3f4-114">Attributes</span></span>  
 <span data-ttu-id="8d3f4-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8d3f4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8d3f4-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d3f4-116">Child Elements</span></span>  
  
|<span data-ttu-id="8d3f4-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d3f4-117">Element</span></span>|<span data-ttu-id="8d3f4-118">Описание</span><span class="sxs-lookup"><span data-stu-id="8d3f4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d3f4-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="8d3f4-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="8d3f4-120">Запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="8d3f4-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d3f4-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d3f4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8d3f4-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d3f4-122">Element</span></span>|<span data-ttu-id="8d3f4-123">Описание</span><span class="sxs-lookup"><span data-stu-id="8d3f4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d3f4-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8d3f4-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8d3f4-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `a HYPERLINK "http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="8d3f4-125">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d3f4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8d3f4-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="8d3f4-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8d3f4-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8d3f4-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="8d3f4-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
