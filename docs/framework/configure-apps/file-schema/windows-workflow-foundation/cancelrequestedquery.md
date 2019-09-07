---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5de459717fdc0dbf946f12dceda18dce79ca4b06
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398806"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="41a12-101">\<Канцелрекуестедкуери ></span><span class="sxs-lookup"><span data-stu-id="41a12-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="41a12-102">Представляет запрос, используемый для отслеживания запросов по отмене дочернего действия родительским.</span><span class="sxs-lookup"><span data-stu-id="41a12-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="41a12-103">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="41a12-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="41a12-104">Дополнительные сведения о запросах профиля отслеживания см. в разделе [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="41a12-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="41a12-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="41a12-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="41a12-106">&nbsp;&nbsp;[ **\<системой. > ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="41a12-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="41a12-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Отслеживание >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="41a12-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="41a12-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="41a12-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="41a12-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> рабочего процесса**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="41a12-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="41a12-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Канцелрекуестедкуериес >** ](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="41a12-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="41a12-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Канцелрекуестедкуери >**</span><span class="sxs-lookup"><span data-stu-id="41a12-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a12-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41a12-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41a12-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="41a12-113">Attributes and Elements</span></span>  
 <span data-ttu-id="41a12-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="41a12-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41a12-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="41a12-115">Attributes</span></span>  
  
|<span data-ttu-id="41a12-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="41a12-116">Attribute</span></span>|<span data-ttu-id="41a12-117">Описание</span><span class="sxs-lookup"><span data-stu-id="41a12-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41a12-118">activityName</span><span class="sxs-lookup"><span data-stu-id="41a12-118">activityName</span></span>|<span data-ttu-id="41a12-119">Строка, задающая имя действия, которое запрашивает отмену.</span><span class="sxs-lookup"><span data-stu-id="41a12-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="41a12-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="41a12-120">childActivityName</span></span>|<span data-ttu-id="41a12-121">Строка, указывающая имя дочернего действия, для которого была запрошена отмена.</span><span class="sxs-lookup"><span data-stu-id="41a12-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41a12-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="41a12-122">Child Elements</span></span>  
 <span data-ttu-id="41a12-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="41a12-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41a12-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="41a12-124">Parent Elements</span></span>  
  
|<span data-ttu-id="41a12-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="41a12-125">Element</span></span>|<span data-ttu-id="41a12-126">Описание</span><span class="sxs-lookup"><span data-stu-id="41a12-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41a12-127">\<Фаултпропагатионкуери ></span><span class="sxs-lookup"><span data-stu-id="41a12-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="41a12-128">Представляет список элементов конфигурации, которые используются для отслеживания запросов на отмену дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="41a12-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="41a12-129">Этот запрос необходим, чтобы участник отслеживания подписался на объекты записей запросов на отмену.</span><span class="sxs-lookup"><span data-stu-id="41a12-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41a12-130">См. также</span><span class="sxs-lookup"><span data-stu-id="41a12-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="41a12-131">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="41a12-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="41a12-132">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="41a12-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
