---
title: '&lt;customTrackingQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fc06c34cb4db99f5e7b6850ed8e7cf7ed073ef72
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="f4bb2-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="f4bb2-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="f4bb2-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f4bb2-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f4bb2-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f4bb2-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="f4bb2-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f4bb2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f4bb2-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f4bb2-106">\<system.serviceModel></span></span>  
<span data-ttu-id="f4bb2-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="f4bb2-107">\<tracking></span></span>  
<span data-ttu-id="f4bb2-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f4bb2-108">\<trackingProfile></span></span>  
<span data-ttu-id="f4bb2-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="f4bb2-109">\<workflow></span></span>  
<span data-ttu-id="f4bb2-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="f4bb2-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="f4bb2-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="f4bb2-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4bb2-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4bb2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4bb2-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f4bb2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f4bb2-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f4bb2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4bb2-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f4bb2-115">Attributes</span></span>  
  
|<span data-ttu-id="f4bb2-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f4bb2-116">Attribute</span></span>|<span data-ttu-id="f4bb2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f4bb2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f4bb2-118">activityName</span><span class="sxs-lookup"><span data-stu-id="f4bb2-118">activityName</span></span>|<span data-ttu-id="f4bb2-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f4bb2-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="f4bb2-120">имя</span><span class="sxs-lookup"><span data-stu-id="f4bb2-120">name</span></span>|<span data-ttu-id="f4bb2-121">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f4bb2-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4bb2-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f4bb2-122">Child Elements</span></span>  
 <span data-ttu-id="f4bb2-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f4bb2-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4bb2-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f4bb2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f4bb2-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4bb2-125">Element</span></span>|<span data-ttu-id="f4bb2-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f4bb2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4bb2-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="f4bb2-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="f4bb2-128">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f4bb2-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4bb2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f4bb2-129">See Also</span></span>  
 <span data-ttu-id="f4bb2-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f4bb2-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f4bb2-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f4bb2-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>         
 [<span data-ttu-id="f4bb2-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f4bb2-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f4bb2-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f4bb2-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
