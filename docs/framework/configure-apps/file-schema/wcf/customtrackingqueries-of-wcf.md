---
title: <customTrackingQueries>WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: abc0c7dfb426338ec6bca61b0a4b87754bb63588
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925943"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="a2304-102">\<Кустомтраккингкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="a2304-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="a2304-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="a2304-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="a2304-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="a2304-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="a2304-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a2304-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="a2304-106">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="a2304-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a2304-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="a2304-107">\<tracking></span></span>  
<span data-ttu-id="a2304-108">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="a2304-108">\<profiles></span></span>  
<span data-ttu-id="a2304-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a2304-109">\<trackingProfile></span></span>  
<span data-ttu-id="a2304-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a2304-110">\<workflow></span></span>  
<span data-ttu-id="a2304-111">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="a2304-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2304-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2304-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2304-113">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a2304-113">Attributes and elements</span></span>

<span data-ttu-id="a2304-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a2304-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2304-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a2304-115">Attributes</span></span>

<span data-ttu-id="a2304-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="a2304-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="a2304-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a2304-117">Child elements</span></span>
  
|<span data-ttu-id="a2304-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="a2304-118">Element</span></span>|<span data-ttu-id="a2304-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a2304-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2304-120">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="a2304-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="a2304-121">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="a2304-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2304-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a2304-122">Parent elements</span></span>  
  
|<span data-ttu-id="a2304-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="a2304-123">Element</span></span>|<span data-ttu-id="a2304-124">Описание</span><span class="sxs-lookup"><span data-stu-id="a2304-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2304-125">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a2304-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="a2304-126">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="a2304-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2304-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a2304-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a2304-128">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a2304-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a2304-129">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a2304-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
