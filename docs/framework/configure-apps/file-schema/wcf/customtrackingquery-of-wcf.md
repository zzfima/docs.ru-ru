---
title: <customTrackingQuery> для WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 0a5e7c034ce1ef12a8d7d5b1753e2e441e48e293
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279491"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="0947b-102">\<customTrackingQuery > из WCF</span><span class="sxs-lookup"><span data-stu-id="0947b-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="0947b-103">Представляет запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="0947b-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="0947b-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="0947b-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="0947b-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0947b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0947b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0947b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0947b-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="0947b-107">\<tracking></span></span>  
<span data-ttu-id="0947b-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="0947b-108">\<profiles></span></span>  
<span data-ttu-id="0947b-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0947b-109">\<trackingProfile></span></span>  
<span data-ttu-id="0947b-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="0947b-110">\<workflow></span></span>  
<span data-ttu-id="0947b-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="0947b-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="0947b-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="0947b-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0947b-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0947b-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0947b-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="0947b-114">Attributes and elements</span></span>  

<span data-ttu-id="0947b-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0947b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0947b-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0947b-116">Attributes</span></span>  
  
|<span data-ttu-id="0947b-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0947b-117">Attribute</span></span>|<span data-ttu-id="0947b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="0947b-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="0947b-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="0947b-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="0947b-120">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="0947b-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0947b-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0947b-121">Child elements</span></span>

<span data-ttu-id="0947b-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0947b-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0947b-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0947b-123">Parent elements</span></span>

|<span data-ttu-id="0947b-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="0947b-124">Element</span></span>|<span data-ttu-id="0947b-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="0947b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0947b-126">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="0947b-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="0947b-127">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="0947b-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="0947b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="0947b-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0947b-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0947b-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0947b-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="0947b-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
