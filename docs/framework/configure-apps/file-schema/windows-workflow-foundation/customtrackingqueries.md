---
title: '&lt;customTrackingQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84c9635b37c592b4d82635deb58880d81d2fb5cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="a36ff-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="a36ff-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="a36ff-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="a36ff-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="a36ff-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="a36ff-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="a36ff-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a36ff-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a36ff-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a36ff-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a36ff-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="a36ff-107">\<tracking></span></span>  
<span data-ttu-id="a36ff-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a36ff-108">\<trackingProfile></span></span>  
<span data-ttu-id="a36ff-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="a36ff-109">\<workflow></span></span>  
<span data-ttu-id="a36ff-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="a36ff-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a36ff-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a36ff-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a36ff-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a36ff-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a36ff-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a36ff-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a36ff-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a36ff-114">Attributes</span></span>  
 <span data-ttu-id="a36ff-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a36ff-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a36ff-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a36ff-116">Child Elements</span></span>  
  
|<span data-ttu-id="a36ff-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="a36ff-117">Element</span></span>|<span data-ttu-id="a36ff-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="a36ff-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a36ff-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="a36ff-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="a36ff-120">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="a36ff-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a36ff-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a36ff-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a36ff-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="a36ff-122">Element</span></span>|<span data-ttu-id="a36ff-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="a36ff-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a36ff-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="a36ff-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="a36ff-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="a36ff-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a36ff-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a36ff-126">See Also</span></span>  
 <span data-ttu-id="a36ff-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a36ff-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="a36ff-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="a36ff-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="a36ff-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a36ff-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a36ff-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a36ff-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
