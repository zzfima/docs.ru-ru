---
title: '&lt;customTrackingQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 234703e677f838dcdccdf857ba38b8729d25a488
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146385"
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="18553-102">&lt;customTrackingQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="18553-102">&lt;customTrackingQuery&gt; of WCF</span></span>

<span data-ttu-id="18553-103">Представляет запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="18553-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="18553-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="18553-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="18553-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="18553-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="18553-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="18553-106">\<system.serviceModel></span></span>  
<span data-ttu-id="18553-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="18553-107">\<tracking></span></span>  
<span data-ttu-id="18553-108">\<профили ></span><span class="sxs-lookup"><span data-stu-id="18553-108">\<profiles></span></span>  
<span data-ttu-id="18553-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="18553-109">\<trackingProfile></span></span>  
<span data-ttu-id="18553-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="18553-110">\<workflow></span></span>  
<span data-ttu-id="18553-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="18553-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="18553-112">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="18553-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18553-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18553-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18553-114">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="18553-114">Attributes and elements</span></span>  

<span data-ttu-id="18553-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18553-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18553-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18553-116">Attributes</span></span>  
  
|<span data-ttu-id="18553-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="18553-117">Attribute</span></span>|<span data-ttu-id="18553-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="18553-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="18553-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="18553-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="18553-120">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="18553-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18553-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18553-121">Child elements</span></span>

<span data-ttu-id="18553-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="18553-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="18553-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18553-123">Parent elements</span></span>

|<span data-ttu-id="18553-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="18553-124">Element</span></span>|<span data-ttu-id="18553-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="18553-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18553-126">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="18553-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="18553-127">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="18553-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="18553-128">См. также</span><span class="sxs-lookup"><span data-stu-id="18553-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="18553-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="18553-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="18553-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="18553-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
