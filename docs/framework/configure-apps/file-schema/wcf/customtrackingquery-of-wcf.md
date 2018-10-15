---
title: '&lt;customTrackingQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: e13064afbd9f5dbc8d7216eb384001e1e005785c
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316237"
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="57456-102">&lt;customTrackingQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="57456-102">&lt;customTrackingQuery&gt; of WCF</span></span>

<span data-ttu-id="57456-103">Представляет запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="57456-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="57456-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="57456-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="57456-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="57456-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="57456-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="57456-106">\<system.serviceModel></span></span>  
<span data-ttu-id="57456-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="57456-107">\<tracking></span></span>  
<span data-ttu-id="57456-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="57456-108">\<profiles></span></span>  
<span data-ttu-id="57456-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="57456-109">\<trackingProfile></span></span>  
<span data-ttu-id="57456-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="57456-110">\<workflow></span></span>  
<span data-ttu-id="57456-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="57456-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="57456-112">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="57456-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57456-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57456-113">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="57456-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="57456-114">Attributes and elements</span></span>  

<span data-ttu-id="57456-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="57456-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57456-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="57456-116">Attributes</span></span>  
  
|<span data-ttu-id="57456-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="57456-117">Attribute</span></span>|<span data-ttu-id="57456-118">Описание</span><span class="sxs-lookup"><span data-stu-id="57456-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="57456-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="57456-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="57456-120">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="57456-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57456-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="57456-121">Child elements</span></span>

<span data-ttu-id="57456-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="57456-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="57456-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="57456-123">Parent elements</span></span>

|<span data-ttu-id="57456-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="57456-124">Element</span></span>|<span data-ttu-id="57456-125">Описание</span><span class="sxs-lookup"><span data-stu-id="57456-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57456-126">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="57456-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="57456-127">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="57456-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="57456-128">См. также</span><span class="sxs-lookup"><span data-stu-id="57456-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="57456-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="57456-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="57456-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="57456-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
