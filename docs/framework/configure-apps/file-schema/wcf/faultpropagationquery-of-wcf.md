---
title: <faultPropagationQuery>WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855328"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="a261e-102">\<Фаултпропагатионкуери > WCF</span><span class="sxs-lookup"><span data-stu-id="a261e-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="a261e-103">Представляет запрос, который используется для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="a261e-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a261e-104">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="a261e-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="a261e-105">Такой запрос следует использовать для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="a261e-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="a261e-106">Этот запрос необходим, чтобы участник отслеживания подписался на записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="a261e-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="a261e-107">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a261e-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="a261e-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a261e-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a261e-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a261e-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a261e-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a261e-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="a261e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Профили >** </span><span class="sxs-lookup"><span data-stu-id="a261e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="a261e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a261e-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="a261e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a261e-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="a261e-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Фаултпропагатионкуериес >** ](faultpropagationqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a261e-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)</span></span>\
<span data-ttu-id="a261e-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Фаултпропагатионкуери >**</span><span class="sxs-lookup"><span data-stu-id="a261e-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="a261e-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a261e-116">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="a261e-117">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a261e-117">Attributes and elements</span></span>

<span data-ttu-id="a261e-118">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a261e-118">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a261e-119">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a261e-119">Attributes</span></span>

|<span data-ttu-id="a261e-120">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a261e-120">Attribute</span></span>|<span data-ttu-id="a261e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a261e-121">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="a261e-122">Строка, указывающая имя действия обработчика сбоев, которое распространило ошибку.</span><span class="sxs-lookup"><span data-stu-id="a261e-122">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="a261e-123">Значение по умолчанию — \*, что означает, что для всех действий возвращаются записи распространения ошибок.</span><span class="sxs-lookup"><span data-stu-id="a261e-123">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="a261e-124">Строка, указывающая имя действия, ставшего источником ошибки.</span><span class="sxs-lookup"><span data-stu-id="a261e-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a261e-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a261e-125">Child elements</span></span>

<span data-ttu-id="a261e-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="a261e-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a261e-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a261e-127">Parent elements</span></span>

|<span data-ttu-id="a261e-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="a261e-128">Element</span></span>|<span data-ttu-id="a261e-129">Описание</span><span class="sxs-lookup"><span data-stu-id="a261e-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a261e-130">\<Фаултпропагатионкуериес ></span><span class="sxs-lookup"><span data-stu-id="a261e-130">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="a261e-131">Представляет список элементов конфигурации, которые используются для отслеживания обработки ошибок, возникающих в рамках действия.</span><span class="sxs-lookup"><span data-stu-id="a261e-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a261e-132">Это событие возникает каждый раз, когда FaultHandler обрабатывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="a261e-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a261e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a261e-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a261e-134">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a261e-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a261e-135">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="a261e-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
