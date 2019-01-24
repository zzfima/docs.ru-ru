---
title: '&lt;faultPropagationQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 546b37279c8ba58f9dd9f07dabacb7af602ff232
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610062"
---
# <a name="ltfaultpropagationqueriesgt"></a><span data-ttu-id="2a6d0-102">&lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="2a6d0-102">&lt;faultPropagationQueries&gt;</span></span>
<span data-ttu-id="2a6d0-103">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2a6d0-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="2a6d0-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="2a6d0-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="2a6d0-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2a6d0-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="2a6d0-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2a6d0-108">\<system.serviceModel></span></span>  
<span data-ttu-id="2a6d0-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="2a6d0-109">\<tracking></span></span>  
<span data-ttu-id="2a6d0-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2a6d0-110">\<trackingProfile></span></span>  
<span data-ttu-id="2a6d0-111">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="2a6d0-111">\<workflow></span></span>  
<span data-ttu-id="2a6d0-112">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="2a6d0-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a6d0-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a6d0-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a6d0-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2a6d0-114">Attributes and Elements</span></span>  
 <span data-ttu-id="2a6d0-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a6d0-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2a6d0-116">Attributes</span></span>  
 <span data-ttu-id="2a6d0-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2a6d0-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2a6d0-118">Child Elements</span></span>  
  
|<span data-ttu-id="2a6d0-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a6d0-119">Element</span></span>|<span data-ttu-id="2a6d0-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2a6d0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a6d0-121">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="2a6d0-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="2a6d0-122">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2a6d0-123">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a6d0-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2a6d0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2a6d0-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a6d0-125">Element</span></span>|<span data-ttu-id="2a6d0-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="2a6d0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a6d0-127">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="2a6d0-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="2a6d0-128">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="2a6d0-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a6d0-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2a6d0-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2a6d0-130">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="2a6d0-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2a6d0-131">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="2a6d0-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
