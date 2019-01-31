---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 0424c01397a95803b9e8502d90a55d1bd4c3b5e6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269397"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="ae78a-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="ae78a-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="ae78a-102">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="ae78a-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ae78a-103">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ae78a-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="ae78a-104">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="ae78a-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="ae78a-105">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="ae78a-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="ae78a-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ae78a-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ae78a-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ae78a-107">\<system.serviceModel></span></span>  
<span data-ttu-id="ae78a-108">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="ae78a-108">\<tracking></span></span>  
<span data-ttu-id="ae78a-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ae78a-109">\<trackingProfile></span></span>  
<span data-ttu-id="ae78a-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ae78a-110">\<workflow></span></span>  
<span data-ttu-id="ae78a-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="ae78a-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae78a-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae78a-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae78a-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ae78a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ae78a-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ae78a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae78a-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ae78a-115">Attributes</span></span>  
 <span data-ttu-id="ae78a-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ae78a-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ae78a-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ae78a-117">Child Elements</span></span>  
  
|<span data-ttu-id="ae78a-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae78a-118">Element</span></span>|<span data-ttu-id="ae78a-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="ae78a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae78a-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="ae78a-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="ae78a-121">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="ae78a-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ae78a-122">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ae78a-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae78a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ae78a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ae78a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae78a-124">Element</span></span>|<span data-ttu-id="ae78a-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ae78a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae78a-126">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="ae78a-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ae78a-127">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="ae78a-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae78a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ae78a-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ae78a-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="ae78a-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ae78a-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="ae78a-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
