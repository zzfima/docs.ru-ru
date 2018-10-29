---
title: '&lt;faultPropagationQueries&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 1db99a8d80fad5c0eca93777d87047b43371d048
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50202124"
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="8cc77-102">&lt;faultPropagationQueries&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="8cc77-102">&lt;faultPropagationQueries&gt; of WCF</span></span>

<span data-ttu-id="8cc77-103">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="8cc77-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8cc77-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="8cc77-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="8cc77-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="8cc77-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="8cc77-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="8cc77-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="8cc77-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8cc77-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8cc77-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8cc77-108">\<system.serviceModel></span></span>  
<span data-ttu-id="8cc77-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="8cc77-109">\<tracking></span></span>  
<span data-ttu-id="8cc77-110">\<профили ></span><span class="sxs-lookup"><span data-stu-id="8cc77-110">\<profiles></span></span>  
<span data-ttu-id="8cc77-111">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8cc77-111">\<trackingProfile></span></span>  
<span data-ttu-id="8cc77-112">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8cc77-112">\<workflow></span></span>  
<span data-ttu-id="8cc77-113">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="8cc77-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cc77-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cc77-114">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8cc77-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="8cc77-115">Attributes and elements</span></span>

<span data-ttu-id="8cc77-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8cc77-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="8cc77-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8cc77-117">Attributes</span></span>

<span data-ttu-id="8cc77-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8cc77-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="8cc77-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8cc77-119">Child elements</span></span>

|<span data-ttu-id="8cc77-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="8cc77-120">Element</span></span>|<span data-ttu-id="8cc77-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8cc77-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8cc77-122">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="8cc77-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="8cc77-123">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="8cc77-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8cc77-124">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="8cc77-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8cc77-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8cc77-125">Parent elements</span></span>  
  
|<span data-ttu-id="8cc77-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="8cc77-126">Element</span></span>|<span data-ttu-id="8cc77-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8cc77-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8cc77-128">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="8cc77-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8cc77-129">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="8cc77-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cc77-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8cc77-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8cc77-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="8cc77-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8cc77-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="8cc77-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
