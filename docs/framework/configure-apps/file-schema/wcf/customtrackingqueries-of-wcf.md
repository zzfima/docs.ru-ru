---
title: '&lt;customTrackingQueries&gt; (WCF)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8a7a69b481da7315c8d26b00c171d030f77d9b63
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="ba65d-102">&lt;customTrackingQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="ba65d-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="ba65d-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="ba65d-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ba65d-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="ba65d-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="ba65d-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ba65d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="ba65d-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ba65d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ba65d-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="ba65d-107">\<tracking></span></span>  
<span data-ttu-id="ba65d-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ba65d-108">\<trackingProfile></span></span>  
<span data-ttu-id="ba65d-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ba65d-109">\<workflow></span></span>  
<span data-ttu-id="ba65d-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="ba65d-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba65d-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba65d-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba65d-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba65d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ba65d-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba65d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba65d-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba65d-114">Attributes</span></span>  
 <span data-ttu-id="ba65d-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ba65d-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba65d-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba65d-116">Child Elements</span></span>  
  
|<span data-ttu-id="ba65d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba65d-117">Element</span></span>|<span data-ttu-id="ba65d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ba65d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba65d-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="ba65d-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="ba65d-120">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="ba65d-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba65d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba65d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ba65d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba65d-122">Element</span></span>|<span data-ttu-id="ba65d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ba65d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba65d-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ba65d-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ba65d-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="ba65d-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba65d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ba65d-126">See Also</span></span>  
 <span data-ttu-id="ba65d-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ba65d-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="ba65d-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ba65d-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="ba65d-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ba65d-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ba65d-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ba65d-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
