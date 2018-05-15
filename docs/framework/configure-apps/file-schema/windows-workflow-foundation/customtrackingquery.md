---
title: '&lt;customTrackingQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 7ddf19ed75d50f3cd5f20de8b0e2dfcdd5ea82b0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="f0610-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="f0610-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="f0610-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f0610-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f0610-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f0610-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="f0610-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f0610-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f0610-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f0610-106">\<system.serviceModel></span></span>  
<span data-ttu-id="f0610-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f0610-107">\<tracking></span></span>  
<span data-ttu-id="f0610-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f0610-108">\<trackingProfile></span></span>  
<span data-ttu-id="f0610-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="f0610-109">\<workflow></span></span>  
<span data-ttu-id="f0610-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="f0610-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="f0610-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="f0610-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0610-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0610-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0610-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f0610-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f0610-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f0610-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0610-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f0610-115">Attributes</span></span>  
  
|<span data-ttu-id="f0610-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f0610-116">Attribute</span></span>|<span data-ttu-id="f0610-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f0610-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0610-118">activityName</span><span class="sxs-lookup"><span data-stu-id="f0610-118">activityName</span></span>|<span data-ttu-id="f0610-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f0610-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="f0610-120">имя</span><span class="sxs-lookup"><span data-stu-id="f0610-120">name</span></span>|<span data-ttu-id="f0610-121">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f0610-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0610-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f0610-122">Child Elements</span></span>  
 <span data-ttu-id="f0610-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f0610-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0610-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f0610-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f0610-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f0610-125">Element</span></span>|<span data-ttu-id="f0610-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f0610-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0610-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="f0610-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="f0610-128">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f0610-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0610-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f0610-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>         
 [<span data-ttu-id="f0610-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f0610-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f0610-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f0610-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
