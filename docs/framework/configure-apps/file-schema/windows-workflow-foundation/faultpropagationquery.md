---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: f77a613f4eb0456a0085096aa478d37c78122217
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946306"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="69b43-101">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="69b43-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="69b43-102">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="69b43-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="69b43-103">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="69b43-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="69b43-104">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="69b43-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="69b43-105">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="69b43-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="69b43-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="69b43-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="69b43-107">\<System. serviceModel > </span><span class="sxs-lookup"><span data-stu-id="69b43-107">\<system.serviceModel></span></span>\
<span data-ttu-id="69b43-108">\<Отслеживание > </span><span class="sxs-lookup"><span data-stu-id="69b43-108">\<tracking></span></span>\
<span data-ttu-id="69b43-109">\<trackingProfile > </span><span class="sxs-lookup"><span data-stu-id="69b43-109">\<trackingProfile></span></span>\
<span data-ttu-id="69b43-110">\<> рабочего процесса </span><span class="sxs-lookup"><span data-stu-id="69b43-110">\<workflow></span></span>\
<span data-ttu-id="69b43-111">\<Фаултпропагатионкуериес > </span><span class="sxs-lookup"><span data-stu-id="69b43-111">\<faultPropagationQueries></span></span>\
<span data-ttu-id="69b43-112">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="69b43-112">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="69b43-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69b43-113">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="69b43-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="69b43-114">Attributes and Elements</span></span>

<span data-ttu-id="69b43-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="69b43-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="69b43-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69b43-116">Attributes</span></span>

|<span data-ttu-id="69b43-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="69b43-117">Attribute</span></span>|<span data-ttu-id="69b43-118">Описание</span><span class="sxs-lookup"><span data-stu-id="69b43-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="69b43-119">activityName</span><span class="sxs-lookup"><span data-stu-id="69b43-119">activityName</span></span>|<span data-ttu-id="69b43-120">Строка, указывающая имя действия обработчика сбоев, которое распространило ошибку.</span><span class="sxs-lookup"><span data-stu-id="69b43-120">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="69b43-121">Значение по умолчанию - «\*», которое указывает на то, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="69b43-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="69b43-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="69b43-122">faultHandlerActivityName</span></span>|<span data-ttu-id="69b43-123">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="69b43-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="69b43-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="69b43-124">Child Elements</span></span>

<span data-ttu-id="69b43-125">Нет.</span><span class="sxs-lookup"><span data-stu-id="69b43-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="69b43-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="69b43-126">Parent Elements</span></span>

|<span data-ttu-id="69b43-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="69b43-127">Element</span></span>|<span data-ttu-id="69b43-128">Описание</span><span class="sxs-lookup"><span data-stu-id="69b43-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="69b43-129">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="69b43-129">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="69b43-130">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="69b43-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="69b43-131">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="69b43-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="69b43-132">См. также</span><span class="sxs-lookup"><span data-stu-id="69b43-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="69b43-133">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="69b43-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="69b43-134">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="69b43-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
