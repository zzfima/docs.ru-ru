---
title: '&lt;customTrackingQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 11ad4281d2925a48508c6a3e8258b0b1cd49a326
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749690"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="966f0-102">&lt;customTrackingQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="966f0-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="966f0-103">Представляет коллекцию запросов, используемых для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="966f0-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="966f0-104">Запрос необходим, чтобы участник отслеживания подписался на пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="966f0-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="966f0-105">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="966f0-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="966f0-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="966f0-106">\<system.serviceModel></span></span>  
<span data-ttu-id="966f0-107">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="966f0-107">\<tracking></span></span>  
<span data-ttu-id="966f0-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="966f0-108">\<trackingProfile></span></span>  
<span data-ttu-id="966f0-109">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="966f0-109">\<workflow></span></span>  
<span data-ttu-id="966f0-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="966f0-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="966f0-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="966f0-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="966f0-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="966f0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="966f0-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="966f0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="966f0-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="966f0-114">Attributes</span></span>  
 <span data-ttu-id="966f0-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="966f0-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="966f0-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="966f0-116">Child Elements</span></span>  
  
|<span data-ttu-id="966f0-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="966f0-117">Element</span></span>|<span data-ttu-id="966f0-118">Описание</span><span class="sxs-lookup"><span data-stu-id="966f0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="966f0-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="966f0-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="966f0-120">Запрос, который используется для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="966f0-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="966f0-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="966f0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="966f0-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="966f0-122">Element</span></span>|<span data-ttu-id="966f0-123">Описание</span><span class="sxs-lookup"><span data-stu-id="966f0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="966f0-124">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="966f0-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="966f0-125">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="966f0-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="966f0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="966f0-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="966f0-127">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="966f0-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="966f0-128">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="966f0-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
