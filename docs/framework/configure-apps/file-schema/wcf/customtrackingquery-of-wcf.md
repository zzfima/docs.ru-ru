---
title: '&lt;customTrackingQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: ed29ff039cd7fd4eb0acccea1b0adf8995c3e1f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="492f3-102">&lt;customTrackingQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="492f3-102">&lt;customTrackingQuery&gt; of WCF</span></span>
<span data-ttu-id="492f3-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="492f3-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="492f3-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="492f3-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="492f3-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="492f3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="492f3-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="492f3-106">\<system.serviceModel></span></span>  
<span data-ttu-id="492f3-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="492f3-107">\<tracking></span></span>  
<span data-ttu-id="492f3-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="492f3-108">\<trackingProfile></span></span>  
<span data-ttu-id="492f3-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="492f3-109">\<workflow></span></span>  
<span data-ttu-id="492f3-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="492f3-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="492f3-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="492f3-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="492f3-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="492f3-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="492f3-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="492f3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="492f3-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="492f3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="492f3-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="492f3-115">Attributes</span></span>  
  
|<span data-ttu-id="492f3-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="492f3-116">Attribute</span></span>|<span data-ttu-id="492f3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="492f3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="492f3-118">activityName</span><span class="sxs-lookup"><span data-stu-id="492f3-118">activityName</span></span>|<span data-ttu-id="492f3-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="492f3-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="492f3-120">имя</span><span class="sxs-lookup"><span data-stu-id="492f3-120">name</span></span>|<span data-ttu-id="492f3-121">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="492f3-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="492f3-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="492f3-122">Child Elements</span></span>  
 <span data-ttu-id="492f3-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="492f3-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="492f3-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="492f3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="492f3-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="492f3-125">Element</span></span>|<span data-ttu-id="492f3-126">Описание</span><span class="sxs-lookup"><span data-stu-id="492f3-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="492f3-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="492f3-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="492f3-128">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="492f3-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="492f3-129">См. также</span><span class="sxs-lookup"><span data-stu-id="492f3-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>      
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="492f3-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="492f3-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="492f3-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="492f3-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
