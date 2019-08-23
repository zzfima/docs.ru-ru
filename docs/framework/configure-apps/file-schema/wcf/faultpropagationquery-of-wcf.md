---
title: <faultPropagationQuery>WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: 6ba6478ca500c0a8ef150966a97898f8743ffdf8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925621"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="d50ae-102">\<Фаултпропагатионкуери > WCF</span><span class="sxs-lookup"><span data-stu-id="d50ae-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="d50ae-103">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="d50ae-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d50ae-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="d50ae-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="d50ae-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="d50ae-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="d50ae-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="d50ae-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="d50ae-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d50ae-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="d50ae-108">\<System. serviceModel > </span><span class="sxs-lookup"><span data-stu-id="d50ae-108">\<system.serviceModel></span></span>\
<span data-ttu-id="d50ae-109">\<Отслеживание > </span><span class="sxs-lookup"><span data-stu-id="d50ae-109">\<tracking></span></span>\
<span data-ttu-id="d50ae-110">\<Профили > </span><span class="sxs-lookup"><span data-stu-id="d50ae-110">\<profiles></span></span>\
<span data-ttu-id="d50ae-111">\<trackingProfile > </span><span class="sxs-lookup"><span data-stu-id="d50ae-111">\<trackingProfile></span></span>\
<span data-ttu-id="d50ae-112">\<> рабочего процесса </span><span class="sxs-lookup"><span data-stu-id="d50ae-112">\<workflow></span></span>\
<span data-ttu-id="d50ae-113">\<Фаултпропагатионкуериес > </span><span class="sxs-lookup"><span data-stu-id="d50ae-113">\<faultPropagationQueries></span></span>\
<span data-ttu-id="d50ae-114">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="d50ae-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="d50ae-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d50ae-115">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="d50ae-116">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="d50ae-116">Attributes and elements</span></span>

<span data-ttu-id="d50ae-117">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d50ae-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d50ae-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d50ae-118">Attributes</span></span>

|<span data-ttu-id="d50ae-119">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d50ae-119">Attribute</span></span>|<span data-ttu-id="d50ae-120">Описание</span><span class="sxs-lookup"><span data-stu-id="d50ae-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="d50ae-121">Строка, указывающая имя действия обработчика сбоев, которое распространило ошибку.</span><span class="sxs-lookup"><span data-stu-id="d50ae-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="d50ae-122">Значение по умолчанию — \*, что означает, что для всех действий возвращаются записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="d50ae-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="d50ae-123">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="d50ae-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d50ae-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d50ae-124">Child elements</span></span>

<span data-ttu-id="d50ae-125">Нет.</span><span class="sxs-lookup"><span data-stu-id="d50ae-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d50ae-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d50ae-126">Parent elements</span></span>

|<span data-ttu-id="d50ae-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="d50ae-127">Element</span></span>|<span data-ttu-id="d50ae-128">Описание</span><span class="sxs-lookup"><span data-stu-id="d50ae-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d50ae-129">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="d50ae-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="d50ae-130">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="d50ae-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d50ae-131">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="d50ae-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d50ae-132">См. также</span><span class="sxs-lookup"><span data-stu-id="d50ae-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d50ae-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="d50ae-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d50ae-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="d50ae-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
