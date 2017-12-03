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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 908c340167d50d4d16e0eeff7cc2e01290b55e7a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="ec16f-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ec16f-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="ec16f-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="ec16f-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ec16f-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ec16f-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="ec16f-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ec16f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ec16f-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ec16f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ec16f-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="ec16f-107">\<tracking></span></span>  
<span data-ttu-id="ec16f-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ec16f-108">\<trackingProfile></span></span>  
<span data-ttu-id="ec16f-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ec16f-109">\<workflow></span></span>  
<span data-ttu-id="ec16f-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="ec16f-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="ec16f-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="ec16f-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec16f-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec16f-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec16f-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ec16f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ec16f-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ec16f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec16f-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec16f-115">Attributes</span></span>  
  
|<span data-ttu-id="ec16f-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ec16f-116">Attribute</span></span>|<span data-ttu-id="ec16f-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ec16f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec16f-118">activityName</span><span class="sxs-lookup"><span data-stu-id="ec16f-118">activityName</span></span>|<span data-ttu-id="ec16f-119">Строка, задающая имя действия, сформировавшего запись отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ec16f-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="ec16f-120">имя</span><span class="sxs-lookup"><span data-stu-id="ec16f-120">name</span></span>|<span data-ttu-id="ec16f-121">Строка, задающая имя выдаваемой пользовательской записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ec16f-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec16f-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ec16f-122">Child Elements</span></span>  
 <span data-ttu-id="ec16f-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ec16f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec16f-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ec16f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ec16f-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec16f-125">Element</span></span>|<span data-ttu-id="ec16f-126">Описание</span><span class="sxs-lookup"><span data-stu-id="ec16f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec16f-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="ec16f-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="ec16f-128">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="ec16f-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec16f-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ec16f-129">See Also</span></span>  
 <span data-ttu-id="ec16f-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ec16f-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="ec16f-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ec16f-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>         
 [<span data-ttu-id="ec16f-132">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ec16f-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ec16f-133">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ec16f-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
