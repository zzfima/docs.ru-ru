---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: b8052138a729fcba7cb158d81a63126f59e0c4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69988729"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="78d87-101">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="78d87-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="78d87-102">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="78d87-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="78d87-103">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="78d87-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="78d87-104">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="78d87-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="78d87-105">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="78d87-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="78d87-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="78d87-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="78d87-107">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="78d87-107">\<system.serviceModel></span></span>  
<span data-ttu-id="78d87-108">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="78d87-108">\<tracking></span></span>  
<span data-ttu-id="78d87-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="78d87-109">\<trackingProfile></span></span>  
<span data-ttu-id="78d87-110">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="78d87-110">\<workflow></span></span>  
<span data-ttu-id="78d87-111">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="78d87-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78d87-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78d87-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78d87-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78d87-113">Attributes and Elements</span></span>  
 <span data-ttu-id="78d87-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="78d87-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78d87-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78d87-115">Attributes</span></span>  
 <span data-ttu-id="78d87-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="78d87-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="78d87-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78d87-117">Child Elements</span></span>  
  
|<span data-ttu-id="78d87-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="78d87-118">Element</span></span>|<span data-ttu-id="78d87-119">Описание</span><span class="sxs-lookup"><span data-stu-id="78d87-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78d87-120">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="78d87-120">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="78d87-121">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="78d87-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="78d87-122">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="78d87-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78d87-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78d87-123">Parent Elements</span></span>  
  
|<span data-ttu-id="78d87-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="78d87-124">Element</span></span>|<span data-ttu-id="78d87-125">Описание</span><span class="sxs-lookup"><span data-stu-id="78d87-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78d87-126">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="78d87-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="78d87-127">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, определяемого свойством **ActivityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="78d87-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78d87-128">См. также</span><span class="sxs-lookup"><span data-stu-id="78d87-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="78d87-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="78d87-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="78d87-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="78d87-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
