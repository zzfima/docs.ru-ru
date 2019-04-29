---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 402b938913575adfa9125b981dc2913680f07b73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790160"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="b241d-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="b241d-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="b241d-102">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="b241d-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b241d-103">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b241d-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="b241d-104">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="b241d-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="b241d-105">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="b241d-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="b241d-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b241d-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b241d-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b241d-107">\<system.serviceModel></span></span>  
<span data-ttu-id="b241d-108">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="b241d-108">\<tracking></span></span>  
<span data-ttu-id="b241d-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b241d-109">\<trackingProfile></span></span>  
<span data-ttu-id="b241d-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="b241d-110">\<workflow></span></span>  
<span data-ttu-id="b241d-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="b241d-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b241d-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b241d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b241d-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b241d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b241d-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b241d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b241d-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b241d-115">Attributes</span></span>  
 <span data-ttu-id="b241d-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b241d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b241d-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b241d-117">Child Elements</span></span>  
  
|<span data-ttu-id="b241d-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="b241d-118">Element</span></span>|<span data-ttu-id="b241d-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b241d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b241d-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="b241d-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="b241d-121">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="b241d-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b241d-122">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b241d-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b241d-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b241d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b241d-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="b241d-124">Element</span></span>|<span data-ttu-id="b241d-125">Описание</span><span class="sxs-lookup"><span data-stu-id="b241d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b241d-126">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="b241d-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b241d-127">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="b241d-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b241d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b241d-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b241d-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b241d-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b241d-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="b241d-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
