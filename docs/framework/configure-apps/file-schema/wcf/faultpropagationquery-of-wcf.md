---
title: <faultPropagationQuery> для WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: e5793852d49a052d05f6cb2f4efbe166d67afc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701051"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="70880-102">\<faultPropagationQuery > из WCF</span><span class="sxs-lookup"><span data-stu-id="70880-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="70880-103">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="70880-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="70880-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="70880-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="70880-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="70880-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="70880-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="70880-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="70880-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [профили отслеживания](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="70880-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="70880-108">\<system.serviceModel > \\</span><span class="sxs-lookup"><span data-stu-id="70880-108">\<system.serviceModel>\\</span></span>
<span data-ttu-id="70880-109">\<Отслеживание > \\</span><span class="sxs-lookup"><span data-stu-id="70880-109">\<tracking>\\</span></span>
<span data-ttu-id="70880-110">\<профили > \\</span><span class="sxs-lookup"><span data-stu-id="70880-110">\<profiles>\\</span></span>
<span data-ttu-id="70880-111">\<trackingProfile > \\</span><span class="sxs-lookup"><span data-stu-id="70880-111">\<trackingProfile>\\</span></span>
<span data-ttu-id="70880-112">\<рабочий процесс > \\</span><span class="sxs-lookup"><span data-stu-id="70880-112">\<workflow>\\</span></span>
<span data-ttu-id="70880-113">\<faultPropagationQueries > \\</span><span class="sxs-lookup"><span data-stu-id="70880-113">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="70880-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="70880-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="70880-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70880-115">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="70880-116">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="70880-116">Attributes and elements</span></span>

<span data-ttu-id="70880-117">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="70880-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="70880-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70880-118">Attributes</span></span>

|<span data-ttu-id="70880-119">Атрибут</span><span class="sxs-lookup"><span data-stu-id="70880-119">Attribute</span></span>|<span data-ttu-id="70880-120">Описание</span><span class="sxs-lookup"><span data-stu-id="70880-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="70880-121">Строка, указывающая имя действия обработчика ошибок, которое распространяет ошибку.</span><span class="sxs-lookup"><span data-stu-id="70880-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="70880-122">По умолчанию используется \*, которое указывает, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="70880-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="70880-123">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="70880-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="70880-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70880-124">Child elements</span></span>

<span data-ttu-id="70880-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="70880-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="70880-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="70880-126">Parent elements</span></span>

|<span data-ttu-id="70880-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="70880-127">Element</span></span>|<span data-ttu-id="70880-128">Описание</span><span class="sxs-lookup"><span data-stu-id="70880-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70880-129">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="70880-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="70880-130">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="70880-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="70880-131">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="70880-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="70880-132">См. также</span><span class="sxs-lookup"><span data-stu-id="70880-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="70880-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="70880-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="70880-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="70880-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
