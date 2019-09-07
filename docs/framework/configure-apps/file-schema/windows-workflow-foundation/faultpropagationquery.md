---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398716"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="60555-101">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="60555-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="60555-102">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="60555-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="60555-103">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="60555-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="60555-104">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="60555-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="60555-105">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="60555-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="60555-106">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="60555-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="60555-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="60555-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="60555-108">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="60555-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="60555-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="60555-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="60555-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="60555-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="60555-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="60555-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="60555-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Фаултпропагатионкуериес >** ](faultpropagationqueries.md)</span><span class="sxs-lookup"><span data-stu-id="60555-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)</span></span>\
<span data-ttu-id="60555-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Фаултпропагатионкуери >**</span><span class="sxs-lookup"><span data-stu-id="60555-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>

## <a name="syntax"></a><span data-ttu-id="60555-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60555-114">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="60555-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="60555-115">Attributes and Elements</span></span>

<span data-ttu-id="60555-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="60555-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="60555-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="60555-117">Attributes</span></span>

|<span data-ttu-id="60555-118">Атрибут</span><span class="sxs-lookup"><span data-stu-id="60555-118">Attribute</span></span>|<span data-ttu-id="60555-119">Описание</span><span class="sxs-lookup"><span data-stu-id="60555-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="60555-120">activityName</span><span class="sxs-lookup"><span data-stu-id="60555-120">activityName</span></span>|<span data-ttu-id="60555-121">Строка, указывающая имя действия обработчика сбоев, которое распространило ошибку.</span><span class="sxs-lookup"><span data-stu-id="60555-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="60555-122">Значение по умолчанию - «\*», которое указывает на то, что записи распространения ошибок возвращаются для всех действий.</span><span class="sxs-lookup"><span data-stu-id="60555-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="60555-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="60555-123">faultHandlerActivityName</span></span>|<span data-ttu-id="60555-124">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="60555-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="60555-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="60555-125">Child Elements</span></span>

<span data-ttu-id="60555-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="60555-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="60555-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="60555-127">Parent Elements</span></span>

|<span data-ttu-id="60555-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="60555-128">Element</span></span>|<span data-ttu-id="60555-129">Описание</span><span class="sxs-lookup"><span data-stu-id="60555-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60555-130">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="60555-130">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="60555-131">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="60555-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="60555-132">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="60555-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="60555-133">См. также</span><span class="sxs-lookup"><span data-stu-id="60555-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="60555-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="60555-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="60555-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="60555-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
