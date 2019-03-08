---
title: <faultPropagationQuery> для WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: e5793852d49a052d05f6cb2f4efbe166d67afc62
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675411"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="a4eb3-102">\<faultPropagationQuery > из WCF</span><span class="sxs-lookup"><span data-stu-id="a4eb3-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="a4eb3-103">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a4eb3-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="a4eb3-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="a4eb3-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="a4eb3-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a4eb3-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="a4eb3-108">\<system.serviceModel > \\</span><span class="sxs-lookup"><span data-stu-id="a4eb3-108">\<system.serviceModel>\\</span></span>
<span data-ttu-id="a4eb3-109">\<Отслеживание > \\</span><span class="sxs-lookup"><span data-stu-id="a4eb3-109">\<tracking>\\</span></span>
<span data-ttu-id="a4eb3-110">\<профили > \\</span><span class="sxs-lookup"><span data-stu-id="a4eb3-110">\<profiles>\\</span></span>
<span data-ttu-id="a4eb3-111">\<trackingProfile > \\</span><span class="sxs-lookup"><span data-stu-id="a4eb3-111">\<trackingProfile>\\</span></span>
<span data-ttu-id="a4eb3-112">\<рабочий процесс > \\</span><span class="sxs-lookup"><span data-stu-id="a4eb3-112">\<workflow>\\</span></span>
<span data-ttu-id="a4eb3-113">\<faultPropagationQueries > \\</span><span class="sxs-lookup"><span data-stu-id="a4eb3-113">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="a4eb3-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="a4eb3-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="a4eb3-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4eb3-115">Syntax</span></span>

```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4eb3-116">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4eb3-116">Attributes and elements</span></span>

<span data-ttu-id="a4eb3-117">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4eb3-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4eb3-118">Attributes</span></span>

|<span data-ttu-id="a4eb3-119">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a4eb3-119">Attribute</span></span>|<span data-ttu-id="a4eb3-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a4eb3-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="a4eb3-121">Строка, указывающая имя действия обработчика ошибок, которое распространяет ошибку.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="a4eb3-122">По умолчанию используется \*, которое указывает, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="a4eb3-123">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a4eb3-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4eb3-124">Child elements</span></span>

<span data-ttu-id="a4eb3-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a4eb3-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4eb3-126">Parent elements</span></span>

|<span data-ttu-id="a4eb3-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4eb3-127">Element</span></span>|<span data-ttu-id="a4eb3-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="a4eb3-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4eb3-129">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="a4eb3-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="a4eb3-130">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a4eb3-131">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="a4eb3-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a4eb3-132">См. также</span><span class="sxs-lookup"><span data-stu-id="a4eb3-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a4eb3-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a4eb3-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a4eb3-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a4eb3-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
