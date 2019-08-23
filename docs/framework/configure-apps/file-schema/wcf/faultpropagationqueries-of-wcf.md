---
title: <faultPropagationQueries>WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: aeb964fc8c96c8cb9aeb316bb95f9565fc4a7f18
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918947"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="a7f79-102">\<Фаултпропагатионкуериес > WCF</span><span class="sxs-lookup"><span data-stu-id="a7f79-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="a7f79-103">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="a7f79-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a7f79-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="a7f79-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="a7f79-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="a7f79-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="a7f79-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="a7f79-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="a7f79-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a7f79-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a7f79-108">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="a7f79-108">\<system.serviceModel></span></span>  
<span data-ttu-id="a7f79-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="a7f79-109">\<tracking></span></span>  
<span data-ttu-id="a7f79-110">\<Профили ></span><span class="sxs-lookup"><span data-stu-id="a7f79-110">\<profiles></span></span>  
<span data-ttu-id="a7f79-111">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a7f79-111">\<trackingProfile></span></span>  
<span data-ttu-id="a7f79-112">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a7f79-112">\<workflow></span></span>  
<span data-ttu-id="a7f79-113">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="a7f79-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f79-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7f79-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7f79-115">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a7f79-115">Attributes and elements</span></span>

<span data-ttu-id="a7f79-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a7f79-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="a7f79-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a7f79-117">Attributes</span></span>

<span data-ttu-id="a7f79-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="a7f79-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="a7f79-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a7f79-119">Child elements</span></span>

|<span data-ttu-id="a7f79-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="a7f79-120">Element</span></span>|<span data-ttu-id="a7f79-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a7f79-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7f79-122">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="a7f79-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="a7f79-123">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="a7f79-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a7f79-124">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="a7f79-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7f79-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a7f79-125">Parent elements</span></span>  
  
|<span data-ttu-id="a7f79-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="a7f79-126">Element</span></span>|<span data-ttu-id="a7f79-127">Описание</span><span class="sxs-lookup"><span data-stu-id="a7f79-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7f79-128">\<> рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="a7f79-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="a7f79-129">Элемент конфигурации, содержащий все запросы для определенного рабочего процесса, обозначенного свойством `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="a7f79-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7f79-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a7f79-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a7f79-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a7f79-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a7f79-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a7f79-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
