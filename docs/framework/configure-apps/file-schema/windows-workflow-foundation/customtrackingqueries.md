---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 429940b2ed69d8be497626f634a21adca540b529
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945840"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="22a05-101">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="22a05-101">\<customTrackingQueries></span></span>
<span data-ttu-id="22a05-102">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="22a05-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="22a05-103">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="22a05-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="22a05-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="22a05-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="22a05-105">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="22a05-105">\<system.serviceModel></span></span>  
<span data-ttu-id="22a05-106">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="22a05-106">\<tracking></span></span>  
<span data-ttu-id="22a05-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="22a05-107">\<trackingProfile></span></span>  
<span data-ttu-id="22a05-108">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="22a05-108">\<workflow></span></span>  
<span data-ttu-id="22a05-109">\<Кустомтраккингкуериес ></span><span class="sxs-lookup"><span data-stu-id="22a05-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a05-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22a05-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22a05-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22a05-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22a05-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="22a05-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22a05-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22a05-113">Attributes</span></span>  
 <span data-ttu-id="22a05-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="22a05-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="22a05-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22a05-115">Child Elements</span></span>  
  
|<span data-ttu-id="22a05-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="22a05-116">Element</span></span>|<span data-ttu-id="22a05-117">Описание</span><span class="sxs-lookup"><span data-stu-id="22a05-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22a05-118">\<Кустомтраккингкуери ></span><span class="sxs-lookup"><span data-stu-id="22a05-118">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="22a05-119">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="22a05-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22a05-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22a05-120">Parent Elements</span></span>  
  
|<span data-ttu-id="22a05-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="22a05-121">Element</span></span>|<span data-ttu-id="22a05-122">Описание</span><span class="sxs-lookup"><span data-stu-id="22a05-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22a05-123">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="22a05-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="22a05-124">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="22a05-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22a05-125">См. также</span><span class="sxs-lookup"><span data-stu-id="22a05-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="22a05-126">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="22a05-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="22a05-127">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="22a05-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
