---
title: '&lt;faultPropagationQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 5db043b5d4d150628df386dafb6e7bd351a0a28a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="03ea9-102">&lt;faultPropagationQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="03ea9-102">&lt;faultPropagationQueries&gt; of WCF</span></span>
<span data-ttu-id="03ea9-103">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="03ea9-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="03ea9-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="03ea9-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="03ea9-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="03ea9-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="03ea9-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="03ea9-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="03ea9-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="03ea9-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="03ea9-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="03ea9-108">\<system.serviceModel></span></span>  
<span data-ttu-id="03ea9-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="03ea9-109">\<tracking></span></span>  
<span data-ttu-id="03ea9-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="03ea9-110">\<trackingProfile></span></span>  
<span data-ttu-id="03ea9-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="03ea9-111">\<workflow></span></span>  
<span data-ttu-id="03ea9-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="03ea9-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03ea9-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03ea9-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="03ea9-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="03ea9-114">Attributes and Elements</span></span>  
 <span data-ttu-id="03ea9-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="03ea9-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03ea9-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="03ea9-116">Attributes</span></span>  
 <span data-ttu-id="03ea9-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="03ea9-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03ea9-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="03ea9-118">Child Elements</span></span>  
  
|<span data-ttu-id="03ea9-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="03ea9-119">Element</span></span>|<span data-ttu-id="03ea9-120">Описание</span><span class="sxs-lookup"><span data-stu-id="03ea9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03ea9-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="03ea9-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="03ea9-122">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="03ea9-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="03ea9-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="03ea9-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03ea9-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="03ea9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="03ea9-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="03ea9-125">Element</span></span>|<span data-ttu-id="03ea9-126">Описание</span><span class="sxs-lookup"><span data-stu-id="03ea9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03ea9-127">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="03ea9-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="03ea9-128">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="03ea9-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03ea9-129">См. также</span><span class="sxs-lookup"><span data-stu-id="03ea9-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="03ea9-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="03ea9-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="03ea9-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="03ea9-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
