---
title: '&lt;faultPropagationQuery&gt; (WCF)'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: c3853c470a9243835e071d35008dfff5b885591d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123323"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="50aaf-102">&lt;faultPropagationQuery&gt; (WCF)</span><span class="sxs-lookup"><span data-stu-id="50aaf-102">&lt;faultPropagationQuery&gt; of WCF</span></span>

<span data-ttu-id="50aaf-103">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="50aaf-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="50aaf-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="50aaf-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="50aaf-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="50aaf-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="50aaf-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="50aaf-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="50aaf-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="50aaf-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="50aaf-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="50aaf-108">\<system.serviceModel></span></span>  
<span data-ttu-id="50aaf-109">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="50aaf-109">\<tracking></span></span>  
<span data-ttu-id="50aaf-110">\<профили ></span><span class="sxs-lookup"><span data-stu-id="50aaf-110">\<profiles></span></span>  
<span data-ttu-id="50aaf-111">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="50aaf-111">\<trackingProfile></span></span>  
<span data-ttu-id="50aaf-112">\<рабочий процесс ></span><span class="sxs-lookup"><span data-stu-id="50aaf-112">\<workflow></span></span>  
<span data-ttu-id="50aaf-113">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="50aaf-113">\<faultPropagationQueries></span></span>  
<span data-ttu-id="50aaf-114">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="50aaf-114">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50aaf-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50aaf-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50aaf-116">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="50aaf-116">Attributes and elements</span></span>

<span data-ttu-id="50aaf-117">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="50aaf-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="50aaf-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="50aaf-118">Attributes</span></span>  
  
|<span data-ttu-id="50aaf-119">Атрибут</span><span class="sxs-lookup"><span data-stu-id="50aaf-119">Attribute</span></span>|<span data-ttu-id="50aaf-120">Описание</span><span class="sxs-lookup"><span data-stu-id="50aaf-120">Description</span></span>|  
|---------------|-----------------|  
|`faultSourceActivityName`|<span data-ttu-id="50aaf-121">Строка, указывающая имя действия обработчика ошибок, которое распространяет ошибку.</span><span class="sxs-lookup"><span data-stu-id="50aaf-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="50aaf-122">По умолчанию используется \*, которое указывает, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="50aaf-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|`faultHandlerActivityName`|<span data-ttu-id="50aaf-123">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="50aaf-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50aaf-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="50aaf-124">Child elements</span></span>

<span data-ttu-id="50aaf-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="50aaf-125">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="50aaf-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="50aaf-126">Parent elements</span></span>  
  
|<span data-ttu-id="50aaf-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="50aaf-127">Element</span></span>|<span data-ttu-id="50aaf-128">Описание</span><span class="sxs-lookup"><span data-stu-id="50aaf-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50aaf-129">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="50aaf-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="50aaf-130">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="50aaf-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="50aaf-131">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="50aaf-131">This event occurs each time a FaultHandler processes a fault.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="50aaf-132">См. также</span><span class="sxs-lookup"><span data-stu-id="50aaf-132">See also</span></span>  
 
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="50aaf-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="50aaf-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="50aaf-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="50aaf-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
