---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 402b938913575adfa9125b981dc2913680f07b73
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204046"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="c3607-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="c3607-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="c3607-102">Представляет коллекцию запросов, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="c3607-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c3607-103">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="c3607-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="c3607-104">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="c3607-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="c3607-105">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="c3607-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="c3607-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c3607-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="c3607-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c3607-107">\<system.serviceModel></span></span>  
<span data-ttu-id="c3607-108">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="c3607-108">\<tracking></span></span>  
<span data-ttu-id="c3607-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c3607-109">\<trackingProfile></span></span>  
<span data-ttu-id="c3607-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="c3607-110">\<workflow></span></span>  
<span data-ttu-id="c3607-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="c3607-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3607-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3607-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3607-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c3607-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c3607-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c3607-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3607-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c3607-115">Attributes</span></span>  
 <span data-ttu-id="c3607-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c3607-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c3607-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c3607-117">Child Elements</span></span>  
  
|<span data-ttu-id="c3607-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="c3607-118">Element</span></span>|<span data-ttu-id="c3607-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c3607-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3607-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c3607-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="c3607-121">Запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="c3607-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c3607-122">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="c3607-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3607-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c3607-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c3607-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="c3607-124">Element</span></span>|<span data-ttu-id="c3607-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c3607-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3607-126">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="c3607-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="c3607-127">Элемент конфигурации, содержащий все запросы для конкретного рабочего процесса, обозначенного **activityDefinitionId** свойство.</span><span class="sxs-lookup"><span data-stu-id="c3607-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3607-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c3607-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c3607-129">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="c3607-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c3607-130">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="c3607-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
