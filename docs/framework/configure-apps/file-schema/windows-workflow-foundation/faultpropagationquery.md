---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 1a6899eaa04ad16192e07f4bc2ad1abe6e4aedd5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257373"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="7dfe6-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="7dfe6-101">\<faultPropagationQuery></span></span>
<span data-ttu-id="7dfe6-102">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7dfe6-103">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="7dfe6-104">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="7dfe6-105">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="7dfe6-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7dfe6-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7dfe6-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7dfe6-107">\<system.serviceModel></span></span>  
<span data-ttu-id="7dfe6-108">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="7dfe6-108">\<tracking></span></span>  
<span data-ttu-id="7dfe6-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="7dfe6-109">\<trackingProfile></span></span>  
<span data-ttu-id="7dfe6-110">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="7dfe6-110">\<workflow></span></span>  
<span data-ttu-id="7dfe6-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="7dfe6-111">\<faultPropagationQueries></span></span>  
<span data-ttu-id="7dfe6-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="7dfe6-112">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dfe6-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7dfe6-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dfe6-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7dfe6-114">Attributes and Elements</span></span>  
 <span data-ttu-id="7dfe6-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dfe6-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7dfe6-116">Attributes</span></span>  
  
|<span data-ttu-id="7dfe6-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7dfe6-117">Attribute</span></span>|<span data-ttu-id="7dfe6-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7dfe6-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7dfe6-119">activityName</span><span class="sxs-lookup"><span data-stu-id="7dfe6-119">activityName</span></span>|<span data-ttu-id="7dfe6-120">Строка, указывающая имя действия обработчика ошибок, которое распространяет ошибку.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-120">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="7dfe6-121">Значение по умолчанию - «\*», которое указывает на то, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="7dfe6-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="7dfe6-122">faultHandlerActivityName</span></span>|<span data-ttu-id="7dfe6-123">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dfe6-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7dfe6-124">Child Elements</span></span>  
 <span data-ttu-id="7dfe6-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7dfe6-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7dfe6-126">Parent Elements</span></span>  
  
|<span data-ttu-id="7dfe6-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="7dfe6-127">Element</span></span>|<span data-ttu-id="7dfe6-128">Описание</span><span class="sxs-lookup"><span data-stu-id="7dfe6-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dfe6-129">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="7dfe6-129">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="7dfe6-130">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7dfe6-131">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="7dfe6-131">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7dfe6-132">См. также</span><span class="sxs-lookup"><span data-stu-id="7dfe6-132">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7dfe6-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7dfe6-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7dfe6-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="7dfe6-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
